# Express4j

```java
package app;

import static express4j.Express4j.createApp;
import express4j.http.message.Response;

/**
 * @author Julian Jupiter
 */
public class Express4jApp {
    private static final System.Logger LOGGER = System.getLogger(Express4jApp.class.getName());

    public static void main(String[] args) {
        var app = createApp();
        app.get("/hello-world", request -> {
            return Response.ok()
                    .header("Content-Type", "text/plain")
                    .body("Hello, world!");
        });
        app.run(() -> LOGGER.log(System.Logger.Level.INFO, () -> "App is running..."));
    }
}
```
