# rank-cats-by-witnessing

A vector function that ranks cat images by the quality of **witnessing** — the feeling that a moment was discovered and caught rather than deliberately produced.

## What It Does

The internet produces an enormous volume of cat imagery every day. Most of it follows a familiar pattern: a photogenic cat posed against a clean background, carefully lit and composed. These images are pleasant, but they lack the quality that makes the best cat photos genuinely moving — the sense that something real happened, someone was lucky enough to be there, and they shared it.

`rank-cats-by-witnessing` takes a collection of cat images and returns a score distribution that ranks them along this axis. Images that feel found, accidental, and honestly shared rise to the top. Images that feel manufactured, staged, or professionally produced sink to the bottom.

## Input

The function accepts an **array of cat images** with a minimum of 2 items.

```json
{
  "type": "array",
  "items": { "type": "image" },
  "minItems": 2
}
```

Each element is an image content part (e.g., a base64-encoded image or image URL). The images are the items being ranked — no additional metadata or text is required.

## Output

The function returns an **array of scores** with the same length as the input array. Each score corresponds to the image at the same index. The scores sum to approximately 1 and represent a probability distribution — higher scores indicate stronger witnessing quality relative to the other images in the set.

## What It Evaluates

The function evaluates each image across three core dimensions, each capturing a different facet of what it means to witness rather than produce.

### 1. Spontaneity

The degree to which an image feels **discovered rather than arranged**. High-spontaneity images carry the fingerprints of real, unoptimized life:

- **Imperfect framing** — the photographer grabbed their phone in a hurry, not pausing to compose
- **Natural, uncontrolled lighting** — overhead kitchen fixtures, afternoon sun through blinds, the glow of a screen in a dark room
- **Genuine clutter** — the actual mess of a lived-in space rather than a curated backdrop
- **An unaware subject** — the cat is mid-action, mid-sleep, or mid-stare, clearly not posing or looking into the lens

An image ranks high on spontaneity when nothing about it has been prepared, cleaned, or optimized for the camera. It is evidence that the world was going about its business and someone simply noticed.

### 2. Impermanence

The degree to which the captured moment feels **fleeting and unrepeatable**. High-impermanence images convey split-second timing:

- **Motion and transition** — a cat mid-leap, mid-yawn, or mid-fall with its body in an impossible shape
- **Unique instants** — a kitten's first encounter with a mirror, the narrow window between knocking something off a table and the aftermath
- **Expressions that vanish** — a face caught in a fraction-of-a-second contortion that will never happen again in quite the same way

An image ranks high on impermanence when it carries the electricity of "I cannot believe I caught that" — the sense that the photographer either captured it or lost it forever, and they captured it.

### 3. Generosity

The degree to which the image feels like **a gift shared out of genuine delight** rather than an act of performance or self-promotion. High-generosity images convey:

- **Absence of curation** — no evidence of selecting from many takes, no polished presentation, no branding
- **Warmth and humor** — the unmistakable tone of "can you believe he sleeps like this?" or "she has been sitting in this bag for an hour"
- **Directness** — the rougher and more immediate the path from moment to sharing, the more generous the image feels

An image ranks high on generosity when it reads as a dispatch from someone's ordinary life, offered not to impress but because the moment delighted them and they wanted others to feel that delight too.

## Use Cases

- **Social media feeds** — surface the posts that feel most alive and genuine, prioritizing authentic moments over polished content
- **Community curation** — help moderators or automated systems distinguish photos that spark real joy from ones that merely perform photographic competence
- **Content discovery** — build recommendation systems that favor the texture of real life over production value
- **Browsing and comfort** — help users find the photos that feel like small gifts from strangers, not advertisements for a lifestyle
- **Dataset filtering** — given a large corpus of cat images, extract the subset with the highest witnessing quality for downstream use

## Philosophy

`rank-cats-by-witnessing` privileges attention over intention, luck over skill, and connection over performance. A photograph that ranks high across all three dimensions may be blurry, poorly lit, and badly framed by any technical standard — but it will feel alive in a way that a technically perfect image often does not. The function measures not the quality of the photograph, but the quality of the seeing.