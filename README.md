# Raf3

Solo full-stack + hardware developer based in Blantyre, Malawi.

I build complete systems — firmware through backend through hardware. Currently shipping the **ZAP Bracelet**, an NFC payment wearable targeting Malawi's mobile money ecosystem (Airtel Money / TNM Mpamba), and **schem**, a Rust DSL for PCB schematics that came out of building it.

---

## Active projects

### [`schem`](https://github.com/Raf3-Tech/schem) — PCB schematic DSL in Rust
A human- and LLM-readable language for describing circuit schematics, with a compiler that validates electrical constraints and emits KiCad netlists.

```
component U1 ESP32-C3-MINI-1 {
  power { vcc: VCC_3V3  gnd: GND }
  gpio  { 4: NFC_IRQ  0: I2C_SDA  1: I2C_SCL }
}
constraint trace_width >= 0.2mm
constraint max_voltage  <= 3.3V
```

```
$ schem build zap_bracelet.schem
✓ zap_bracelet.schem → zap_bracelet.net
  11 nets  •  5 components  •  6 constraints
```

**Stack:** Rust · pest PEG · KiCad netlist output · v0.2 adds `.kicad_sch` + Gerber JSON

---

### ZAP Bracelet — NFC wearable payment device
End-to-end solo build targeting unbanked mobile money users in Malawi.

| Layer | Tech |
|---|---|
| Firmware | Rust (Embassy) · ESP32-C3 · IRQ-driven NFC via PN532 |
| Backend | Rust · Actix-web · PostgreSQL · all amounts in MWK tambala (`u64`) |
| Payment adapters | TypeScript · Airtel Money API · TNM Mpamba API |
| Hardware | KiCad PCB · magnetic clasp wearable form factor · wireless-only charging |
| Dashboard | Node.js · coral/blue/purple dark theme |

100-user pilot in progress. The `schem` DSL was built directly from the friction of designing this board.

---

## Stack

**Languages:** Rust · TypeScript · C (firmware)  
**Hardware:** KiCad · ESP32-C3 · NFC (PN532) · PCB design  
**Backend:** Actix-web · PostgreSQL · Docker  
**Tools:** Claude Code · Diode Computers CLI · defmt

---

## Currently interested in

Problems at the intersection of hardware tooling, Rust compilers, and AI-assisted EDA workflows. If you're working on any of that — especially automated PCB layout, schematic DSLs, or fab integrations — I want to talk.

**Reach me:** [twitter.com/raf3](https://twitter.com) · [linkedin.com/in/raf3](https://linkedin.com)
