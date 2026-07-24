# Cloud City Coffee — `/coffee` for Claude Code

Chat with **Lando**, Cloud City Roasters' barista, right in your terminal: tell him how you
like your coffee, get a real recommendation (origins, roast, tasting notes), and check out
on a secure Stripe page in your browser. **First order? 10% comes off automatically** —
verified on our order page, no codes to remember.

## Install

```
/plugin marketplace add bobbyuzda1/cloudcityroasters-plugin
/plugin install cloud-city-coffee@cloudcityroasters-plugin
```

Then just type `/coffee`.

## Privacy

- No card data ever touches the terminal — payment happens on Stripe's hosted checkout.
- The terminal never asks for your email; you enter it once on our secure order page
  (where the first-order discount is applied), and the newsletter there is a separate
  unchecked opt-in.
- With your consent, your last order is remembered in `~/.cloud-city-coffee.json` on your
  machine — no email stored. `/coffee forget` deletes it.

## License

Proprietary — see [LICENSE](../../LICENSE). Install and use freely; no derivatives.
