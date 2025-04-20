---
layout: default
title: UHT Registry
---

# Universal Hex Taxonomy (UHT) Registry

This site provides self-describing UHT codes. Browse the available entries:

- [0xF3A0C4E1 - Bi‑directional Actuator](codes/0xF3A0C4E1.md)
- [0xF3A0C4E2 - Linear Actuator](codes/0xF3A0C4E2.md)


<h2>Create a New UHT Entry</h2>
<p>Enter your new UHT code:</p>
<input type="text" id="hexInput" placeholder="e.g. 0xF3A0C4E3" />
<button onclick="generateMarkdown()">Generate .md Template</button>

<pre id="output" style="white-space: pre-wrap; margin-top: 1em; background: #f5f5f5; padding: 1em; border-radius: 6px;"></pre>

<script>
function generateMarkdown() {
  const hex = document.getElementById("hexInput").value.trim();
  if (!/^0x[0-9A-Fa-f]{8}$/.test(hex)) {
    alert("Please enter a valid 32-bit hex code, like 0xF3A0C4E3.");
    return;
  }

  const md = `---
layout: default
title: <Component Title>

# UHT Code ${hex}

**Label:** <Component Name>  
**Category:** Functional Component  

**Tags:** tag1, tag2  

**Defined By:** [uht-core/registry](https://github.com/uht-core/registry)  

**Version:** 1.0  

**Related Codes:** 0x________
`;

  document.getElementById("output").textContent = md;
}
</script>
