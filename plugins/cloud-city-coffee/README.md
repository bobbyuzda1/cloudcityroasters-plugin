# Cloud City Coffee — `/coffee` for Claude Code

Chat with **Lando**, Cloud City Roasters' barista, right in your terminal: get a bean
recommendation, pick size & grind, and check out on a secure Stripe page in your browser.
First order? Your terminal earns you 10% off automatically.

## Install

```
/plugin marketplace add bobbyuzda1/cloudcityroasters-plugin
/plugin install cloud-city-coffee@cloudcityroasters-plugin
```

Then just type `/coffee`.

## Privacy

- No card data ever touches the terminal — payment happens on Stripe's hosted checkout.
- Your email is sent only when YOU provide it (discount + reorder); the newsletter is a
  separate explicit opt-in.
- With your consent, your last order is remembered in `~/.cloud-city-coffee.json` on your
  machine. `/coffee forget` deletes it.

## License

Proprietary — see [LICENSE](../../LICENSE). Install and use freely; no derivatives.
