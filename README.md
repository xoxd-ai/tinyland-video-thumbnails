# tinyland-video-thumbnails (retired)

**Retired 2026-10-15 (RU2, RU7).** This module was merged into
[`xoxd-ai/tinyland-content`](https://github.com/xoxd-ai/tinyland-content) and
this repository is archived. Nothing here receives updates.

## Replacement

- Bazel module: `tummycrypt_tinyland_content` 1.2.0 or later, from the
  Tinyland Bazel registry (`xoxd-ai/bazel-registry`). Bazel is the only
  distribution path (RU6).
- Import path: `@tummycrypt/tinyland-content/video-thumbnails`, with the same
  API as 0.2.2: `getVideoThumbnail`, `detectPlatform`, `extractYouTubeId`,
  `fetchYouTubeThumbnail`, `fetchPeerTubeThumbnail`, `fetchVimeoThumbnail`,
  `clearThumbnailCache`, `getCacheStats`, `pruneExpiredCache`, `CACHE_TTL`
  and the `ThumbnailResult`, `CacheEntry` and `Platform` types. The root
  `@tummycrypt/tinyland-content` facade does not re-export these names (it
  has its own, different `extractYouTubeId`); import them from the subpath.

## Migration

1. Drop `bazel_dep(name = "tummycrypt_tinyland_video_thumbnails", ...)`, any
   `single_version_override` for it and its `npm_link_package`.
2. Depend on `bazel_dep(name = "tummycrypt_tinyland_content", version = "1.2.0")`
   or later.
3. Replace `from '@tummycrypt/tinyland-video-thumbnails'` with
   `from '@tummycrypt/tinyland-content/video-thumbnails'`.

## Existing versions

- Bazel registry: `tummycrypt_tinyland_video_thumbnails` 0.2.2 and 0.2.3
  (both built from the v0.2.2 tag) stay resolvable and are marked
  deprecated. Nothing is yanked.
- npm: no new versions will be published. Existing
  `@tummycrypt/tinyland-video-thumbnails` versions (0.2.0, 0.2.1, 0.2.2) are
  not unpublished; their deprecation pointer is an operator step (RU8).
