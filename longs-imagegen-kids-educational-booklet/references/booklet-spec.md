# Booklet Spec

## Booklet Object

```yaml
booklet:
  title:
  audience_age:
  learning_goal:
  booklet_thesis:
  page_count:
  output_ratio:
  style_mode:
  character_system:
  recurring_visual_tokens:
  hard_constraints:

pages:
  - page_number:
    page_role:
    page_thesis:
    title:
    core_message:
    teaching_points: []
    page_pattern:
    secondary_pattern:
    illustration_plan:
    text_blocks: []
    interaction:
    recurring_tokens: []
    constraints: []
```

## Required Rules

MUST complete `booklet` before rendering.

MUST complete all page-level `page_role + page_thesis + page_pattern` before rendering Page 1.

MUST keep `page_thesis` singular.

MUST keep `teaching_points` within the page's visual capacity.

MUST resolve conflicting copy before render.

MUST record any inferred assumption that affects age level, page count, or learning sequence.

SHOULD preserve the user's original terminology when educational accuracy depends on it.

NEVER let style selection change educational meaning.
