---
title: Http Server Initialization
menu: docs_architecture
weight: 10
---

## Architecture overview

Below is a diagram of HttpServer initalization, which happens on the following code
```rust
#[actix_rt::main]
async fn main() -> std::io::Result<()> {
    HttpServer::new(|| {
        App::new()
            .route("/", web::to(|| HttpResponse::Ok()))
    })
    .bind("127.0.0.1:8088")?
    .run()
    .await
}
```

![](/img/diagrams/http_server.svg)
