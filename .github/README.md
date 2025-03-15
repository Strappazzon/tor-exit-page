<!-- markdownlint-disable MD033 MD041 -->
<div align="center">
  <img width="96" src="../_components/logo.svg" alt="Logo">
</div>

<div align="center">
  <strong>Tor Exit Router Page</strong>
</div>

<p align="center">
  <em>Alternative design to the default Tor Project's page</em>
</p>
<!-- markdownlint-enable MD033 MD041 -->

## About

This is an alternative design to the [default "This is a Tor Exit Router" page](https://gitlab.torproject.org/tpo/core/tor/raw/HEAD/contrib/operator-tools/tor-exit-notice.html) provided by The Tor Project.

This notice is intended to be placed on a virtual host for a domain that your Tor exit router IP reverse resolves to, so that people who may be about to file an abuse complaint would check it first before bothering you or your ISP.

## Getting Started

### Configuration

You must configure the notice page before you start using it.  
To do so, open **_config.yml** with a source code editor and start adjusting the variables to your needs.

| Key                | Type     | Description                                                                                                                                                 |
|--------------------|----------|-------------------------------------------------------------------------------------------------------------------------------------------------------------|
| `title`            | String   | The title of the page.<br>This will appear in the browser tab, heading under the logo and page metadata.                                                    |
| `ips`              | String[] | A list with one or more IPs of your Tor exit router.<br>Can be disabled.                                                                                    |
| `name`             | String   | Your name or username by which you are known online.                                                                                                        |
| `email`            | String   | The email that will receive the complaints.                                                                                                                 |
| `pgp`              | String   | **Default: `null`**<br>The URL to the public PGP key associated with the email that will receive the complaints.                                            |
| `p2p`              | Boolean  | **Default: `true`**<br>Disable if common P2P ports are not blocked by your Tor exit router.                                                                 |
| `sections.dmca`    | Boolean  | **Default: `true`**<br> Disable to hide the DMCA law section.                                                                                               |
| `sections.ecpa`    | Boolean  | **Default: `false`**<br>US-only. Enable if you are a US operator.<br>More info [here](https://en.wikipedia.org/wiki/Electronic_Communications_Privacy_Act). |
| `sections.credits` | Boolean  | **Default: `true`**<br>Disable to hide the footer that links back to my website and this repository.                                                        |

### Build

See: [CONTRIBUTING.md](./CONTRIBUTING.md#Getting-Started).

## Licensing

The code is open source under the terms of the [GNU General Public License v3](https://github.com/Strappazzon//tor-exit-page//blob/-/LICENSE.txt).

[Tor overview illustration](../_components/tor-overview.svg) by The Tor Project.

Tor Browser logo by Fabián Alexis from [Wikimedia Commons](https://commons.wikimedia.org/wiki/File:Antu_tor-browser.svg) ([CC BY-SA 3.0 License](https://creativecommons.org/licenses/by-sa/3.0/)).

By contributing to this repository, you agree that the content you contribute may be provided under the terms of the [GNU General Public License v3](https://github.com/Strappazzon//tor-exit-page//blob/-/LICENSE-CODE.txt).
