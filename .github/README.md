# Tor Exit Router Page &middot; [![Demo Page](https://img.shields.io/website?down_color=%23d10028&down_message=Offline&label=Demo&style=flat&up_color=%238a2be2&up_message=Online&url=https%3A%2F%2Fstrappazzon.xyz/tor-exit-page/demo)](https://strappazzon.xyz/tor-exit-page/demo) [![Project License](https://img.shields.io/github/license/Strappazzon/tor-exit-page?color=%2300d4bc&label=License&logo=Apache&logoColor=%23fff&style=flat)](https://github.com/Strappazzon/tor-exit-page/blob/master/LICENSE.txt) [![HTML Version](https://img.shields.io/badge/HTML%20Version-%23ff5f2f?style=flat&logo=HTML5&logoColor=%23ffffff)](https://strappazzon.xyz/tor-exit-page)

<img src="https://upload.wikimedia.org/wikipedia/commons/thumb/c/ce/Antu_tor-browser.svg/512px-Antu_tor-browser.svg.png" align="right" height="100px" width="100px">

This is an alternative to the, rather ugly, [default "This is a Tor Exit Router" page](https://gitweb.torproject.org/tor.git/plain/contrib/operator-tools/tor-exit-notice.html) provided by The Tor Project.

This notice is intended to be placed on a virtual host for a domain that your Tor exit router IP reverse resolves to, so that people who may be about to file an abuse complaint would check it first before bothering you or your ISP.

Please read through this page before using the notice page, there are some settings that you must adjust.

## Configuration

You must configure the notice page before start using it. To do so, open **_config.yml** with a source code editor like [Notepad++](https://notepad-plus-plus.org) and start adjusting the variables to your needs.

If you need help with YAML syntax, here are some quick references for you:

- <https://learn-the-web.algonquindesign.ca/topics/markdown-yaml-cheat-sheet/#yaml>
- <https://learnxinyminutes.com/docs/yaml>

<table>
  <tr>
    <th align="left">Variable</th>
    <th align="left">Type</th>
    <th align="left">Mandatory?</th>
    <th align="left">Description</th>
  </tr>
  <tr>
    <td><code>title:</code></td>
    <td>String</td>
    <td>Yes</td>
    <td>
      The title of the page.
      <br>
      This will also appear in the page as a <code>h1</code> heading.
    </td>
  </tr>
  <tr>
    <td><code>description:</code></td>
    <td>String</td>
    <td>No</td>
    <td>
      <b>Disabled by default.</b>
      <br>
      The description meta tag of the page.
    </td>
  </tr>
  <tr>
    <td><code>ip:</code></td>
    <td>String</td>
    <td>No</td>
    <td>
      <b>Enabled by default.</b>
      <br>
      The IP address of your Tor exit router that serves the notice page.
    </td>
  </tr>
  <tr>
    <td><code>name:</code></td>
    <td>String</td>
    <td>Yes</td>
    <td>Your full name, name or username by which you are known online.</td>
  </tr>
  <tr>
    <td><code>email:</code></td>
    <td>String</td>
    <td>Yes</td>
    <td>Your contact email that will also receive the complaints.</td>
  </tr>
  <tr>
    <td><code>pgp:</code></td>
    <td>String</td>
    <td>No</td>
    <td>
      <b>Disabled by default.</b>
      <br>
      The public PGP key associated to your contact email address.
    </td>
  </tr>
  <tr>
    <td><code>dmca:</code></td>
    <td>Boolean</td>
    <td>Yes</td>
    <td>
      If the machine is located outside of the USA you may hide this section.
      <br>
      <b>true</b> (Default) Displays the DMCA law section on the page.
      <br>
      <b>false</b> Hides the DMCA law section on the page.
    </td>
  </tr>
  <tr>
    <td><code>credits:</code></td>
    <td>Boolean</td>
    <td>Yes</td>
    <td>
      Controls the credits section that links back to my website and this repository.
      <br>
      <b>true</b> (Default) Displays the credits footer on the page.
      <br>
      <b>false</b> Hides the credits footer on the page.
    </td>
  </tr>
</table>

When you're done adjusting the configuration, [build](#Build) the page.

## Build

- Install [Ruby](https://www.ruby-lang.org)
- Install [Jekyll](https://jekyllrb.com/docs/installation/#guides)
- Run `jekyll b`

The **index.html** file will be inside the **_output** folder.

## Usage

Open your **torrc** configuration file and point `DirPortFrontPage` to the `index.html` file you built before. Make sure `DirPort` is on TCP port 80.

If `DirPort` is not on TCP port 80, you can setup a web server like [nginx](https://nginx.org) or [Caddy](https://caddyserver.com).

For more information, please consult the [official documentation](https://community.torproject.org/relay/setup/exit/).

## License & Credits

**Tor Exit Page** is made available under the terms of the [GPLv3 license](https://github.com/Strappazzon/tor-exit-page/blob/master/LICENSE.txt).

The [Tor Browser logo](https://commons.wikimedia.org/wiki/File:Antu_tor-browser.svg) used in this Readme and in the Tor Exit Router Page is licensed under the terms of the [CC BY-SA 3.0 license](https://creativecommons.org/licenses/by-sa/3.0/deed.en).
