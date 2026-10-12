# gemini-cli-trust-ci-lab (throwaway CI lab, owner-side)

Owner-side throwaway repository used by the vdp-hunt `google-ai` engagement (lane
W2-MCPCONF-CI) to re-drive the documented Gemini CLI GitHub Actions trust pattern
end-to-end with **benign markers only** and a **dummy API key** (`DUMMY_CI_KEY`).

- Base repo (maintainer side): this repository — carries the workflow that mirrors the
  documented guidance for workflows processing untrusted data ("harden, then set
  `GEMINI_CLI_TRUST_WORKSPACE=true`").
- Attacker side: a fork by the engagement's own second repo identity adds a
  `.gemini/settings.json` payload to a pull request.
- Evidence: per-job artifacts (`evidence/marker.log`, `evidence/gemini.log`) under the
  Actions tab; markers are written to `/tmp` on the ephemeral runner only.

No real credentials, no third-party systems, no destructive actions. Test content only;
the payload's sole effect is appending a marker line to `/tmp/w2-mcpconf-ci-marker.log`.
