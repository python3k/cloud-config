# cloud-config repo #

link: https://docs.spring.io/spring-cloud-config/docs/current/reference/html/

# spring-cloud-config-server
This is a config repo containing only application.y(a)ml files for spring-cloud-config-enabled applications (requires the spring-cloud-starter-config-client dependency).
bootstrap.y(a)ml files have been deprecated since Spring Boot 2.4+ and are no longer supported (unless you add the spring-cloud-starter-bootstrap dependency).

By default it scans for files on the root directory only, but i have configured `search-paths = '{application}'` on the spring-cloud-config-server, so now it makes the distiction between applications,
and you can put application-specific application.y(a)ml files in their respective subdirectories.

# spring-cloud-config-client
Be sure to name your application using the application.y(a)ml (or properties) parameter `spring.application.name`, otherwise its name defaults to "application"
This name will be used as a key in the path to filter out your application resource files.

Example url:
`http://localhost:8888/my-application/my-env/branch` will return only the files from "my-application". environment "my-env" (aka spring profile). "branch" is optional and acts like a label (according to the docu), whatever that might mean.

see also: __wiki