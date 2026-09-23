# TwinPane self-hosted Supabase updates

This branch starts from Supabase `self-hosted/v0.8.1` at commit
`8c7a4d9dbbaf8b552893822e89d7bf06f33f9220`. Coolify deploys it with
`/docker` as the base directory and `/docker-compose.yml` as the Compose file.

## Local change

`volumes/api/envoy/cds.yaml` routes the Realtime cluster to the Compose service
name `realtime`. Coolify's managed Compose network resolves that name. The
upstream hostname `realtime-dev.supabase-realtime` does not resolve there and
causes HTTP 503 on `/realtime/v1/websocket`.

Keep this routing change when moving to a newer Supabase self-hosted release.
Do not replace the file blindly: review upstream changes to the Envoy cluster,
health check, and WebSocket route first.

## Release procedure

1. Choose an explicit `self-hosted/v*` release. Read its changelog and breaking
   changes. Do not point Coolify at a moving branch.
2. Back up Postgres, Storage, and the self-hosted configuration. Verify a test
   restore. Supabase's `update.sh` backs up configuration, not database or
   Storage data.
3. Merge or rebase the chosen upstream release into a new TwinPane branch.
   Resolve conflicts and verify that Envoy still routes Realtime to `realtime`.
   Check all Compose image tags and any new environment variables together.
4. Test the candidate on a separate stack, including license activation,
   Realtime WebSocket upgrade, and a client/server file transfer.
5. Pin Coolify to the tested commit. Deploy in a maintenance window and repeat
   the checks against `https://api.twinpane.com`.

For the current deployment, a successful WebSocket handshake returns
`101 Switching Protocols` from `/realtime/v1/websocket`. A 503 indicates that
the gateway's Realtime upstream is unavailable.

Supabase's update guide: https://supabase.com/docs/guides/self-hosting/updating
