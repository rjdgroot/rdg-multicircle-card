# RdG multicircle card

Configurable 3x2 grid card with 3 to 6 circle graphs for any value sensor. Specially designed for energy dashboards.
Only works with the original RdG circle card.

---

## 🛠 Installation (via HACS)

1. Go to HACS → Settings → Custom Repositories
2. Add: `https://github.com/rjdgroot/rdg-multicircle-card`
3. Select **Lovelace** as category
4. After adding, find **RdG multicircle card** in the Frontend section
5. Install and then add to your dashboard resources:

```yaml
- url: /hacsfiles/rdg-multicircle-card/rdg-multicircle-card.js
  type: module
```

---

## 🧩 rdg-multicircle-card

Displays up to **six** circular values in a responsive 3x2 grid.  
Each circle uses the `rdg-circle-card` internally and supports its options.

### 🔧 Example configuration

```yaml
type: custom:rdg-multicircle-card
circles:
  - entity: sensor.temp_1
    name: Bedroom
    min: 0
    max: 30
    color: '#00AEEF'
  - entity: sensor.temp_2
    name: Living Room
    min: 0
    max: 30
    color: '#FF5555'
  ...
show_names: true
strokeWidth: 12
gap: 8
```

### ⚙️ Global Options

| Option         | Description                            | Default |
|----------------|----------------------------------------|---------|
| `show_names`   | Show labels below each circle          | true    |
| `strokeWidth`  | Stroke width for all circles           | 10      |
| `gap`          | Space between circles (px)             | 8       |

Each object under `circles:` supports the same options as `rdg-circle-card`.

---

## 🧪 Roadmap / Ideas

- [ ] Color gradients based on value
- [ ] Many more to come

---

## 📄 License

Created by [@rjdgroot](https://github.com/rjdgroot)
