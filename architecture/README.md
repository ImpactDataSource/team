Solution architecture
==

Specific architecture decisions will be documented in their corresponding
repositories. With that said, we will generally use the following technologies:

* **Ember** for front-end and client-facing UX (Includes Ember-cli and Ember Data)
* **Express** for server-side API and models
* **SASS** for structured styling and responsive CSS
* **Grunt** for server-side task running

Whenever appropriate, new applications which can be built off the main services
API will be structured as independent lightweight front-end applications.

Following best practices, all applications store sensitive configuration in the
environment and not the codebase. Local configuration can generally be specified
in a .env file in the root of your application, which is excluded from GIT.

#### Deployment

[Heroku](https://www.heroku.com) is used for all production applications, QA
environments, and review apps. Each application will be configured in a [Pipeline](https://devcenter.heroku.com/articles/pipelines). This ensures that
all code being reviewed at any stage in the feature development lifecycle is
done so on an exact replica of the production environment.

[IBM Compose](https://www.compose.io) is used for some databases and provides
automated backups and disaster recovery in addition to general database
environment optimization and configuration.

[MLab](https://www.mlab.com/) is used as a database host in some cases,
configured as a heroku add-on. This service also provides automatic backups and
disaster recovery.

Due to ephemeral file systems on all production applications, any permanent file
storage will utilize [Amazon S3 buckets](https://aws.amazon.com/s3/). When files
are uploaded by users, a CORS upload will be used to transfer the file directly
between the user and S3 without involving the production application.

[Cloudflare](https://www.cloudflare.com) is used as both a CDN and a layer of
threat mitigation. If custom proxying is required an additional proxy server may
be used which runs [NGINX](http://nginx.org). Generally, all caching should be
deferred to either Cloudflare **_or_** NGINX to avoid cache conflicts and
prevent deployment complications.
