# Immich Stacker

Automatically stacks related photos in Immich by matching file extensions (e.g., JPG + DNG pairs).

## Services

| Service | Image |
|---------|-------|
| stacker | `mattdavis90/immich-stacker:latest` |

## Ports

No ports exposed. Runs as a one-shot job.

## Volumes

No volumes mounted.

## Environment Variables

| Variable | Required | Description |
|----------|----------|-------------|
| `IMMICH_API_KEY` | Yes | Immich API key |
| `IMMICH_ENDPOINT` | Yes | Immich server endpoint URL |
| `IMMICH_MATCH` | No | Regex to match files for stacking (default: `\.(JPG\|DNG)$`) |
| `IMMICH_PARENT` | No | Regex to determine the parent/primary file in a stack (default: `\.JPG$`) |

## Notes

- Container restart policy is set to `no` — designed to run once and exit.
- Useful for automatically grouping RAW + JPEG pairs in Immich.
