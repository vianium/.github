# Vianium

> The modern internet, back on Windows Phone 8.1.

Windows Phone 8.1 still boots — but its networking has been frozen
since 2014: no modern TLS, no HTTP/2, no ALPN. The hardware works; the
modern internet just won't answer it.

**Vianium** rebuilds that entire stack from raw TCP sockets up —
clean-room, from the specifications — and ships the real apps that run
on it: a Telegram client, a web browser, a music player, an AI chat
client, and a Cloud Firestore SDK. Built with WinRT for Windows Phone
8.1, and compatible with Windows 10 Mobile.

An ecosystem of 23 public repositories, designed, authored, and
maintained by one person — **Angel Careaga**
([@AngelCareaga](https://github.com/AngelCareaga)).

## Highlights

- Native gRPC streaming to Cloud Firestore — no proxy, no gRPC-Web.
- TLS 1.3 with ALPN on an OS whose newest built-in TLS predates the standard.
- A clean-room browser engine — its own DOM, CSS, layout, and JavaScript runtime.
- Telegram MTProto 2.0 — secret chats, VoIP calls, MTProxy obfuscation.
- Runs in as little as 512 MB of RAM.
- Built with WinRT (C++/CX + C#) — runs on Windows Phone 8.1 and Windows 10 Mobile.
- 23 repositories, clean-room from specifications, one author.

## Repositories

### Foundation libraries — Apache 2.0

| Repo | Language | Purpose |
|---|---|---|
| [vianium-kernel](https://github.com/vianium/vianium-kernel) | C++ | `Result<T>`, arena allocators, event bus, base types |
| [vianium-managed-kernel](https://github.com/vianium/vianium-managed-kernel) | C# | `Result<T>`, primitives for managed contexts |
| [vianium-crypto](https://github.com/vianium/vianium-crypto) | C++ | SHA, HMAC, AES, BigNum, ECDH P-256 |
| [vianium-tls](https://github.com/vianium/vianium-tls) | C++ + WinRT | TLS 1.3 + TLS 1.2 with ALPN, pinning, OCSP, CT |
| [vianium-net](https://github.com/vianium/vianium-net) | C++ | Sockets, DNS, DoH |
| [vianium-http](https://github.com/vianium/vianium-http) | C++ | HTTP/1.1 + H2, connection pool, HSTS |
| [vianium-grpc](https://github.com/vianium/vianium-grpc) | C# | gRPC framing + HPACK over HTTP/2 |
| [vianium-audio](https://github.com/vianium/vianium-audio) | C++/CX | Real-time microphone capture and speaker playback (WASAPI), PCM resampling |

### Domain protocols and libraries — Apache 2.0

| Repo | Language | Purpose |
|---|---|---|
| [vianium-mtproto](https://github.com/vianium/vianium-mtproto) | C++ | Telegram MTProto 2.0, TL schema layer 214 |
| [vianium-mtproxy](https://github.com/vianium/vianium-mtproxy) | C++ + WinRT | MTProxy v2 obfuscated transport (legacy / secure / fake-TLS) |
| [vianium-voip](https://github.com/vianium/vianium-voip) | C++ | RTP, SRTP, OPUS, libtgvoip wrapper |
| [vianium-media](https://github.com/vianium/vianium-media) | C++/CX | Audio DSP, tag parser, FFmpeg interop |
| [vianium-image-palette](https://github.com/vianium/vianium-image-palette) | C++/CX | Image color palette extraction |
| [vianium-innertube](https://github.com/vianium/vianium-innertube) | C++/CX | YouTube Innertube API client |
| [vianium-store](https://github.com/vianium/vianium-store) | C# | Cloud Firestore client (98.9% Android SDK parity) |
| [vianium-genai](https://github.com/vianium/vianium-genai) | C# | Provider-neutral AI chat client (Gemini, OpenAI) — text, streaming, and Live voice |

### Products — PolyForm Noncommercial 1.0.0

Authored and maintained by **Angel Careaga**.

| Repo | Purpose |
|---|---|
| [vianium-browser](https://github.com/vianium/vianium-browser) | Native web browser |
| [vianigram](https://github.com/vianium/vianigram) | Telegram client |
| [vianium-music](https://github.com/vianium/vianium-music) | Music player with YouTube Music streaming |
| [vianium-localsend](https://github.com/vianium/vianium-localsend) | LocalSend P2P file-sharing client for LAN |
| [vianium-chat](https://github.com/vianium/vianium-chat) | Native multi-provider AI chat client (Gemini, ChatGPT) |

### Meta

| Repo | Purpose |
|---|---|
| [vianium-docs](https://github.com/vianium/vianium-docs) | Architecture, ADRs, governance |
| [.github](https://github.com/vianium/.github) | Org templates and policies |

## Licensing

Vianium uses a dual licensing strategy:

- **Libraries** (foundation + domain) are released under the
  **Apache License 2.0**, with NOTICE-based attribution. Use them for
  any purpose, including commercial, as long as attribution is
  preserved.
- **Products** (browser, Telegram client, music player) are released
  under the **PolyForm Noncommercial 1.0.0** license. Free for
  personal, educational, research, and noncommercial organizational
  use. Commercial use requires separate permission.

PolyForm Noncommercial is source-available, not OSI-defined open
source. Tier 3 products are correctly described as
"source-available."

For the full rationale, see
[vianium-docs/licensing-policy.md](https://github.com/vianium/vianium-docs/blob/main/licensing-policy.md).

## About the author

**Angel Careaga** is the founder, author, and primary maintainer of the
Vianium project. He designs and writes from-scratch native systems
software, focused on resource-constrained mobile platforms and the
protocols that make modern networking work.

His work in this organization includes clean-room implementations of
TLS 1.3, HTTP/2, gRPC, MTProto, RTP/OPUS, Cloud Firestore, and the
LocalSend P2P protocol — all built from specifications, targeting
hardware many consider obsolete.

Every repository in this organization carries his name in its `NOTICE`
file and in the SPDX header of every source file. The Apache License 2.0
on the library tier guarantees this attribution travels with the code
wherever it goes.

### Contact

- Email: [hello@angelcareaga.com](mailto:hello@angelcareaga.com)
- Website: [angelcareaga.com](https://angelcareaga.com)
- GitHub: [@AngelCareaga](https://github.com/AngelCareaga)
- Developer / technical: [dev.angelcareaga@gmail.com](mailto:dev.angelcareaga@gmail.com)

For commercial licensing inquiries on Tier 3 products
([vianium-browser](https://github.com/vianium/vianium-browser),
[vianigram](https://github.com/vianium/vianigram),
[vianium-music](https://github.com/vianium/vianium-music),
[vianium-localsend](https://github.com/vianium/vianium-localsend),
[vianium-chat](https://github.com/vianium/vianium-chat)),
write to [hello@angelcareaga.com](mailto:hello@angelcareaga.com).
