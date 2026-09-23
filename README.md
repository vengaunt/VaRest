![GitHub](https://img.shields.io/github/license/ufna/VaRest)
![GitHub release (latest by date including pre-releases)](https://img.shields.io/github/v/release/vengaunt/VaRest?include_prereleases)
<p align="center">
  <img src="Resources/Icon128.png" alt="VaRest" width="96">
</p>

<h1 align="center">VaRest</h1>

<p align="center">
  REST and JSON for Unreal Engine, from Blueprints.
</p>

<p align="center">
  <a href="https://www.fab.com/listings/5b751595-fe3e-4e85-b217-9b5496ab6d3f">Fab</a>
  ·
  <a href="https://github.com/vengaunt/VaRest/wiki">Docs</a>
  ·
  <a href="https://github.com/vengaunt/VaRest">GitHub</a>
  ·
  <a href="mailto:ziyabahceci@proton.me">Contact</a>
</p>

VaRest is a plugin that makes HTTP and JSON server communication straightforward in Unreal Engine. Requests, JSON objects, and JSON values are Blueprint types, so a call does not need C++.

The original plugin was created and published by Vladimir Alyamkin. That repository is archived. With his permission, [Vengaunt](https://www.ziyabahceci.dev) maintains this continuation and publishes it on [Fab](https://www.fab.com/listings/5b751595-fe3e-4e85-b217-9b5496ab6d3f).

## Features

- HTTP and HTTPS requests, with verbs `GET`, `POST`, `PUT`, `DELETE`, and custom verbs
- Content types for JSON, `x-www-form-urlencoded` (URL or body), and binary data
- Blueprint wrappers for JSON objects and JSON values, including nested objects, arrays, and strings
- Completion events and latent Blueprint nodes for asynchronous requests
- Helpers to build JSON values, decode a string, and load JSON from a file

Usage examples and installation notes are on the [docs page](https://github.com/vengaunt/VaRest/wiki).

## Engine support

`develop` targets **Unreal Engine 5.8**.

Older engine lines stay on their own branches:

| Branch | Unreal Engine |
| --- | --- |
| `develop` | 5.8 |
| `origin/5.5` | 5.5 |
| `5.4` | 5.4 |
| `5.0` | 5.0 |
| `4.27` through `4.19` | the version in the branch name |

5.6 and 5.7 were added on the way to the current 5.8 update. Copy the matching branch into your project's `Plugins` folder and enable **VaRest**.

The plugin modules are allowed on Win64, Linux, Mac, Oculus, iOS, and Android. Although so, any build would theoritically work as long as the device running the build has an internet connection.

## Requests

1. **Construct Json Request**, or **Construct Json Request (Empty)**.
2. Set the verb, content type, and request JSON when the call has a body.
3. Start it with **Process URL**, or **Apply URL** for a latent node.
4. Use **On Request Complete** and **On Request Fail**. **Get Status** reports `NotStarted`, `Processing`, `Failed`, `Failed_ConnectionError`, or `Succeeded`.

**Call URL** is the short form: URL, verb, content type, JSON object, and a callback.

On `develop`, a request that is still running is cancelled when its world tears down. That includes stopping Play In Editor, changing levels, and exiting the game. The success and fail callbacks do not run in that case.

## Contact

Ziya Bahceci — [ziyabahceci@proton.me](mailto:ziyabahceci@proton.me)

Open-Source Contributions are always welcome. If you want to support this project financially, you can just send me a mail.

## License

VaRest is released under the [MIT License](LICENSE). Copyright (c) 2014 Vladimir Alyamkin.

Unreal® is a trademark or registered trademark of Epic Games, Inc. in the United States of America and elsewhere.

Unreal® Engine, Copyright 1998–2026, Epic Games, Inc. All rights reserved.
