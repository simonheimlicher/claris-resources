# AI Agent Context Guide: claris-resources

## Quick Start

1. Read this file for module overview
2. See `~/Sites/hugo/CLAUDE.md` for workspace-level context
3. See `~/Sites/hugo/modules/hugo-claris/root/CLAUDE.md` for theme that uses this module

## Module Overview

`claris-resources` provides general-purpose Hugo partials for resource handling. It is a dependency of `hugo-claris` and is NOT used directly by sites.

## Key Functionality

### Image Processing

Located in `layouts/partials/claris/_functions/resources/images/`:

| Partial | Purpose |
|---------|---------|
| `process-image.html` | Main image processing entry point |
| `get-srcset.html` | Generate responsive srcset |
| `get-dimensions.html` | Calculate image dimensions |
| `parse-aspect-ratio.html` | Parse aspect ratio strings |
| `render-image-attrs.html` | Generate img tag attributes |

### Font Preloading

Located in `layouts/partials/claris/_functions/resources/fonts/`:

| Partial | Purpose |
|---------|---------|
| `preload.html` | Generate font preload links |

### Resource Utilities

Located in `layouts/partials/claris/_functions/resources/`:

| Partial | Purpose |
|---------|---------|
| `get-resource.html` | Generic resource fetching |

## Module Relationship

```
sites/heimlicher.com
    └── hugo-claris (theme)
            └── claris-resources (THIS MODULE)
```

This module is included via `hugo-claris`'s `go.mod`. Sites don't reference it directly.

## Development

When developing alongside `hugo-claris`:

1. Both modules should be in `go.work`
2. Changes here are immediately visible in `hugo-claris`
3. No separate commit/push needed during development

## No Worktrees

Unlike `hugo-claris`, this module uses a single branch (`main`) without worktrees, since it's only included indirectly via `hugo-claris`.
