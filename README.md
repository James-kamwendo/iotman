# Welcome To IOTMAN+ Guide

![iotman-banner](IOTMAN+.png)

<!-- <p align="center">
  <a href="https://packagist.org/packages/James-kamwendo/framework"><img src="https://img.shields.io/packagist/l/James-kamwendo/framework" alt="License"></a>
</p> -->

## About IOTMAN+

IOTMAN+, simply put is a web application friendly admin UI for Open Balena. We believe deployment and management of Iot devices must be an enjoyable and interesting experience to be truly fulfilling. IOTMAN+ takes the pain out of deployment and management by easing common tasks you do with Open Balena, such as:

- Fleet or App Management.
- Device Management.
- Access Tokens Management
- Services Management
- User Management
- Organization Managemnt

IOTMAN+ is accessible, powerful, and provides tools required for large, robust applications, built in Next JS and Django.

## How To Use IOTMAN+ With Open Balena

Currently, the offical documentation for IOTMAN+ is under development, it will be released soon. From there you will be able to access the most extensive and thorough documentation and video tutorials where you will be guided through if you don't feel like reading or need more visuals, making it a breeze to get started with the integration. While we're still working on the project documentation, please follow the guide below.

### Installation (Docker Compose)

**Note**: Before the following steps, if you don't have a running instance of [Open Balena](https://open-balena.pages.dev/getting-started), please install it using their updated get started documentation `https://open-balena.pages.dev/getting-started/`.

1. Get the iotman-plus project to your open balena server

```sh
git clone https://github.com/James-kamwendo/iotman.git
cd iotman/
chmod -x quickstart
```

2. Configure iotman-plus-admin

This will set the environments required by the iotman plus to sync with your open balena instance.

```sh
./quickstart -u <OPENBALENA_DB_USER> -p <OPENBALENA_DB_PASSWORD> -d <DOMAIN> -P [OPENBALENA_DB_PORT] -i [PROTOCOL]
```

**Note**: For a full list of quickstart configuration options, run `iotman/quickstart -h`.

3. Set up hostnames

If running locally, edit `/etc/hosts` or `C:\Windows\System32\Drivers\etc\hosts` to include the hostnames to make sure you're openbalena is up and running:

```sh
127.0.0.1 api.mydomain.com
127.0.0.1 ca.mydomain.com
127.0.0.1 cloudlink.mydomain.com
127.0.0.1 logs.mydomain.com
127.0.0.1 ocsp.mydomain.com
127.0.0.1 registry2.mydomain.com
127.0.0.1 s3.mydomain.com
127.0.0.1 tunnel.mydomain.com
```

If hosted, set up your hostnames to point to the public IP addresses of your containers to point to your openbalena server:

```sh
api.mydomain.com
ca.mydomain.com
cloudlink.mydomain.com
logs.mydomain.com
ocsp.mydomain.com
registry2.mydomain.com
s3.mydomain.com
tunnel.mydomain.com
```

4. Start open-balena
   
make sure your open balena instance is running first before starting up the iotman-plus

```sh
make up
```

5. Start iotman-plus

Reaching this far it means you successfully configured the environments in step 2. Otherwise let's finish by running the containers.

```sh
docker compose up

# [optionally] add -d to the command to run in the background
```

## Web Access

Once both open-balena and iotman-plus are running, you can access the admin interface via `http://localhost:3000`.  Log in using the credentials your openbalena instance was initially set up to. Enjoy the experience. Ciao!

## Contributing

Thank you for considering contributing to IOTMAN+! The contribution guide will be found in the [IotMan+ documentation](https://iotman+.com/docs/contributions), once we finish working on the project documentation, keep in touch.

## Code of Conduct

In order to ensure that the IOTMAN+ community is welcoming to all, please review and abide by the [Code of Conduct](https://iotman+.com/docs/contributions#code-of-conduct), by the time we will release the official documentation.

## Security Vulnerabilities

If you discover a security vulnerability within IOTMAN+, please send an e-mail to James Kamwendo via [james@iotmanplus.com](mailto:james@iotmanplus.com). All security vulnerabilities will be promptly addressed.

## License

The IOTMAN+ is open-sourced software licensed under the [MIT license](https://opensource.org/licenses/MIT).
