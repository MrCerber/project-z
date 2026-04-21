# Project Z

Open-source communication platform with an open protocol.
Privacy-first, censorship-resistant alternative to Discord.
Israeli company, universal product.

> This project is in early design phase. No code exists yet.
> Update this file as the codebase grows.

## Tech Stack

- Server: Go
- Client: Tauri + React + TypeScript (strict mode, no `any`)
- Voice/Video: WebTransport P2P + SRTP
- Encryption: RSA-2048 + AES-256 + TLS 1.3
- Database: PostgreSQL + Redis
- IDs: UUID v7 with type prefix (`usr_`, `msg_`, `chn_`, `srv_`, `bot_`, `rol_`, `att_`, `tkn_`)

## Architecture

Two server types — chosen at creation, permanent, cannot change:
- **Cloud** — data stored at Project Z
- **Self Hosted** — data stored at owner, registered in global Registry

Voice/Video routing:
- 2 users → Direct E2E P2P
- 3–8 users → E2E Mesh P2P
- 9+ users → SFU (SRTP, server cannot read content)

## Code Style

- Go: idiomatic, no global state, handle all errors explicitly, no panics in production code
- TypeScript: strict mode, functional components only, no `any`, no implicit returns
- CSS: Tailwind utility classes only in client
- Tests: write tests before implementation (TDD, red-green-refactor)
- Commits: conventional commits (`feat:`, `fix:`, `chore:`, `docs:`, `test:`)

## Security Rules — Never Violate

- Never expose secrets, keys, or tokens in code, logs, or comments
- Never store private keys server-side — they belong to the user only
- Never skip error handling on crypto operations
- Never modify audit log entries after creation — append only
- All user data access must be logged to the audit log

## What NOT to Touch Without Explicit Instruction

- `crypto/` — encryption implementation
- `registry/` — Registry protocol
- `audit/` — audit log structure
- `auth/secrets.go` — secret generation logic

## Lessons Learned

> After every mistake or correction — add a rule here to prevent it repeating.

- (empty — add rules as the project evolves)
