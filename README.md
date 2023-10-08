# Spring Boot, SAML, and Aurora

A Spring Boot example app that shows how to implement single sign-on (SSO) with Spring Security's SAML and Aurora.

**Prerequisites:** 

Java 17

## Getting Started

To install this example application, run the following commands:

```bash
git clone https://github.com/ronalzan/aurora-saml-springboot.git
cd aurora-saml-springboot
```

### Create a SAML App in Aurora

Aurora developer is responsible for this step.

### Run the App and Login

1) Update **metadata-uri** in /src/main/resources/application.yml. Please contact Aurora support to provide the URL.
2) Update **private-key-location** and **certificate-location** in /src/main/resources/application.yml with your application private and public key. You can create a private key and certificate using OpenSSL:
   
```shell
openssl req -newkey rsa:2048 -nodes -keyout local.key -x509 -days 365 -out local.crt
```

3) Place your private keys and certificate in /src/main/resources/
4) Run your Spring Boot app from your IDE or you can use command line below:

```shell
./gradlew bootRun
```

5) Open `http://localhost:8080` in your favorite browser and log in with the credentials you used to create your account.
6) You should see a successful result in your browser.

## Reference

https://docs.spring.io/spring-security/reference/servlet/saml2/login/index.html


## License

Apache 2.0, see [LICENSE](LICENSE).

[blog]: https://developer.okta.com/blog/2022/08/05/spring-boot-saml
