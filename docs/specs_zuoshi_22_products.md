# 琢石橡塑官網 22項產品完整實作規格書 (specs_zuoshi_22_products)

本規格書由 **AntiGravity (AG)** 撰寫，為首期 6 款產品（頁面 8-13）以及新增 16 款高分子添加劑/顏料產品（頁面 14-29）的完整數據定位與前端實作指南。本規格書為 `opencode` 實作之唯一數據準則。

---

## 🏗️ 1. 技術數據表渲染標準化 (Technical Data Rendering)

為了支援 22 個產品不同結構的技術數據表，前端 React 組件必須實作 **「通用多態技術數據表渲染器」**，支援以下 6 種資料表樣式：

1. **熱膨脹微膠囊表 (`microspheres`)**
2. **樹脂載體母粒表/化學發泡劑表/發泡助劑母粒表/色母粒表 (`generic_columns`)**
3. **螢光增白劑表/抗氧化劑表/紫外線吸收劑表 (`brightener`/`antioxidant`/`uv`)**
4. **抗靜電助劑/耐黃變助劑簡單參數表 (`simple_param`)**
5. **TPU 抗靜電助劑三維參數表 (`tpu_static_param`)**
6. **顏料光學物性與材料推薦大表 (`pigment_table` - 適用紅、黃、酞菁、無機、群青、螢光顏料)**

---

## 🔍 2. 新增 16 項產品資料對照

### 7. 螢光增白劑 (FLUORESCENT WHITENING AGENTS)

- **ID**: `brightener`
- **特性**: 增白劑，是無色到淺色有機化合物。吸收紫外光轉化為紫至藍色螢光，產生更明亮外觀，獲得更亮色彩或遮蓋泛黃。

#### 產品概述
- 產品為有機增白劑，可吸收電磁波譜中紫外線和可見光譜中紫色（波長340-370奈米）的光，重新發射可見光譜中藍色（波長420-470奈米）的光。這是一種螢光現象。
- 增白劑由於能發射更多的藍光，使原本呈現黃色或橘色的物體消弱呈色上的黃相，廣泛應用於塑料、噴漆、油墨方案和纖維中。

#### 應用領域
- 適用於 PVC、PS、PP、PE、ABS、EVA 等多種高分子材料。
- 廣泛應用於塑膠加工、纖維著色、油墨及塗料配方，獲得極佳白度與光澤度。

#### 儲藏與注意事項
- 注意事項：在聚乙烯 (PE) 中，增白劑 127 的耐候性有限。建議用量通常在 0.05-0.5% 之間，具體用量取決於應用和所需的白度。如果使用金紅石型二氧化鈦，可能需要增加光學增白劑 127 的用量。
- 螢光增白劑 OB 和 OB-1 的具體應用選擇，需要根據不同的產品和生產工藝進行測試，以確定最佳的增白效果。
- 儲藏與搬運：內襯塑料袋、外覆紙塑複合箱包裝，避光防水保存。增白劑的儲放需要注意陰涼乾燥、通風良好、避免高溫和陽光直射，以及使用密閉的耐腐蝕性容器。同時，應採取必要的安全措施，避免接觸和誤食，並定期檢查儲存狀況。

#### 數據規格結構
```json
[
  {
    "model": "127",
    "name": "4,4'-雙(2-二甲氧基苯乙烯基)聯苯",
    "enName": "4,4'-bis(2-methoxystyryl)biphenyl",
    "scope": "PVC/PS/PP"
  },
  {
    "model": "OB-1",
    "name": "二苯乙烯基雙苯並噁唑",
    "enName": "2,2'-(1,2-Ethenediyldi-4,1-phenylene)bisbenzoxazole",
    "scope": "PVC/PS/PP/PE/ABS/EVA"
  },
  {
    "model": "OB",
    "name": "2,5-雙(5-叔丁基-1,3-苯並噁唑-2-基)噻吩",
    "enName": "2,5-BIS(5-TERT-BUTYL-BENZOXAZOL-2-YL)THIOPHENE",
    "scope": "PVC/PS/PP/PE/ABS"
  }
]
```

---

### 8. 抗氧化劑 (ANTIOXIDANTS)

- **ID**: `antioxidant`
- **特性**: 主要用於防止聚合物材料和油脂、塗料在光照和熱作用下氧化降解。有效抑制或延緩氧化反應，延長產品使用壽命。

#### 產品概述
- 抗氧化劑通過捕獲塑料降解過程中產生的自由基而長期持續性發揮抗氧作用。有良好的防止光和熱引起的變色作用，同時還具有一定的光穩定作用。
- 提高產品的加工穩定性和耐用性。可與其它抗氧化劑協同使用。

#### 應用領域
- 適用於 PVC、PS、PE、PP、ABS、PU、SBS 等多種材料的防老化保護。

#### 儲藏與注意事項
- 儲藏與搬運：內襯塑料袋、外覆紙塑複合箱包裝，避光防水保存。抗氧化劑的儲放需要注意陰涼乾燥、通風良好、避免高溫和陽光直射，以及使用密閉的耐腐蝕性容器。同時，應採取必要的安全措施，避免接觸和誤食，並定期檢查儲存狀況。

#### 數據規格結構
```json
[
  {
    "model": "1076",
    "name": "β-(3,5-二叔丁基-4-羥基苯基)丙酸正十八碳醇酯",
    "enName": "Octadecyl-3-(3',5'-di-t-butyl-4'-hydroxyphenyl) propionate",
    "scope": "PVC/PS/PE/PP/ABS/PU",
    "note": "抗氧化劑 1076 適用於多種材料，特別是聚合物，能有效防止材料因氧化而降解，延長產品的使用壽命。一般用量為 0.1%-1%。"
  },
  {
    "model": "1010",
    "name": "β-(3,5-二叔丁基-4-羥基苯基)丙酸]季戊四醇酯",
    "enName": "Pentaerythritol tetrakis(3-(3,5-di-tert-butyl-4-hydroxyphenyl)propionate)",
    "scope": "PVC/PS/PE/PP/ABS/SBS",
    "note": "抗氧化劑 1010 的化學結構使其具有良好的抗氧化性能和熱穩定性，在多種材料中得到廣泛應用。在製品中的用量為 0.05% 到 1%。"
  },
  {
    "model": "168",
    "name": "三[2.4-二叔丁基苯基]亞磷酸酯",
    "enName": "Tris(2,4-ditert-butylphenyl)phosphite",
    "scope": "PE/PC/PP/ABS",
    "note": "抗氧化劑 168 屬於亞磷酸酯類抗氧化劑，需與酚類主抗氧劑（如 1010、1076）協同使用以提升綜合性能。在聚丙烯加工中添加 0.1% 抗氧化劑 168 與 0.05% 抗氧化劑 1010 的復配體系，可使材料熱氧老化壽命延長至單一體系的 2.3 倍。"
  }
]
```

---

### 9. 紫外線吸收劑 (ULTRAVIOLET ABSORBENTS)

- **ID**: `uv-absorber`
- **特性**: 可在 290-400 nm 範圍內吸收主要不可見的紫外線光。熱穩定性佳，揮發性低、化學穩定性好，不與製品中材料組份發生不利反應。

#### 產品概述
- 紫外線吸收劑是一種光穩定劑，能吸收陽光及螢光光源中的紫外線部分，而本身又不發生變化。
- 塑料和其它高分子材料在日光和螢光下，因紫外線的作用，產生自動氧化反應，導致聚合物的降解而劣化，使外觀及機械性能變作。加入紫外線吸收劑後可選擇性地吸收這種高能量的紫外線，使之變成無害的能量而釋放或消耗。

#### 應用領域
- 廣泛應用於 PVC、PE、PP、SBS、PS、PU、ABS、Acrylic 等材料之光穩定防護。

#### 儲藏與注意事項
- 儲藏與搬運：內襯塑料袋、外覆紙塑複合箱/紙桶包裝，避光防水保存。紫外線吸收劑的儲放需要注意陰涼乾燥、通風良好、避免高溫和陽光直射，以及使用密閉的耐腐蝕性容器。同時，應採取必要的安全措施，避免接觸和誤食，並定期檢查儲存狀況。

#### 數據規格結構
```json
[
  {
    "model": "UV-201",
    "name": "2-羥基-4-正辛氧基二苯甲酮",
    "enName": "2-Hydroxy-4-(octyloxy)benzophenone",
    "scope": "PVC/PE/PP/SBS",
    "note": "本品為能夠強烈地吸收波長為 270-330nm 的紫外線，可用於各種塑料，兼容性好，揮發性小。一般用量為 0.1%-1%。"
  },
  {
    "model": "UV-P",
    "name": "2-(2'-羥基-5'-甲基苯基)苯並三唑",
    "enName": "2-(2'-Hydroxy-5'-methyl-phenyl)benzotriazole",
    "scope": "PVC/PS/PU/ABS/Acrylic",
    "note": "能溶於汽油、苯、丙酮等多種有機溶劑。能吸收 270～380nm 波長的紫外線。熔點 130～131℃。在透明製品中的穩定性較在著色製品是更好。在製品中的用量為 0.1%-0.5%。"
  },
  {
    "model": "UV-770",
    "name": "雙(2,2,6,6-四甲基-4-哌啶基)癸二酸酯",
    "enName": "Bis(2,2,6,6-tetramethyl-4-piperidyl)sebacate",
    "scope": "PE/PS/PP/ABS/SBS",
    "note": "受阻胺類光穩定劑，光穩定效果優於一般紫外線吸收劑，與抗氧劑並用能提高耐熱性，進一步提高耐老化性能，與聚合物有較好的相容性，熱穩定性優，可用於高溫加工與其它紫外線吸收劑並用具有協同效應。作為光穩定劑，建議加量 0.1-0.5%。"
  }
]
```

---

### 10. EVA抗靜電助劑-粉末 (EVA ANTISTATIC ADDITIVE POWDER)

- **ID**: `antistatic-eva`
- **特性**: EVP-715 為專用型醋酸乙烯抗靜電助劑。表面電阻率穩定，抗靜電分子賦予材料一定潤滑性，降低摩擦係數，抑制靜電產生。

#### 產品概述
- 產品為高分子永久型抗靜電助劑，屬親水性聚合物。當其和高分子基體共混後，一方面由於其分子鏈的運動能力較強，分子間便於質子移動，通過離子導電來傳導和釋放產生的靜電荷；抗靜電能力是通過其特殊的分散形態體現的。構成導電性表層。
- 不與製品中材料組成上發生不利反應。製品置放不吐霜。其建議添加量為：15.0-25.0。

#### 應用領域
- EVA 薄膜、擠出板材、鞋材、注塑發泡製品等。

#### 儲藏與注意事項
- 注意事項：置於陰涼避光且通風良好處、必須存放於乾燥，避光密閉容器中，常規有效期為 12 個月，開封後請在 3 個月內使用完畢。
- ※詳細安全資料請參見物質安全資料表 (MSDS)

#### 數據規格結構
```json
[
  {
    "param": "外觀 (目測)",
    "val": "白色粉末"
  },
  {
    "param": "密度",
    "val": "1.20-1.25g/cm³"
  },
  {
    "param": "電阻率 Ω·m",
    "val": "10^7"
  },
  {
    "param": "包裝",
    "val": "25KG/紙塑複合袋"
  }
]
```

---

### 11. 螢光顏料 (FLUORESCENT PIGMENTS)

- **ID**: `fluorescent-pigment-p18`
- **特性**: 在受到紫外線或其他特定波長光照射時，吸收光能發出更長波長的可見光，呈現出鮮豔的「螢光」效果。

#### 產品概述
- 具高亮度與高反射率，螢光顏料比普通顏料更亮，反射光線更強，色彩更鮮豔。
- 由超細均勻和不透明的熱固性氨基樹脂微球顆粒組成。濃度高，著色力強，易分散，抗粘輥和耐溶劑。它們適用於塑料，增塑溶膠和油墨。塗料和其他著色區域。適用於 PP，PE，EVA，硬質 PVC 等。

#### 應用領域
- 適用於塑料、增塑溶膠、油墨、塗料及其他著色領域，如 PP、PE、EVA、硬質 PVC 等。

#### 儲藏與注意事項
- 儲藏與搬運：內襯塑料袋、外覆紙箱包裝，避光防水保存，防潮防高溫。應採取必要的安全措施，避免接觸和誤食，並定期檢查儲存狀況。

#### 數據規格結構
```json
[
  {
    "model": "5120",
    "name": "檸檬黃 (LEMON YELLOW)"
  },
  {
    "model": "5121",
    "name": "綠色 (GREEN)"
  },
  {
    "model": "5122",
    "name": "橙黃 (ORANGE YELLOW)"
  },
  {
    "model": "5123",
    "name": "橙色 (ORANGE)"
  },
  {
    "model": "5124",
    "name": "橙紅 (ORANGE RED)"
  },
  {
    "model": "5125",
    "name": "粉紅 (PINK)"
  },
  {
    "model": "5126",
    "name": "大紅 (RED)"
  },
  {
    "model": "5127",
    "name": "玫紅 (ROSE)"
  },
  {
    "model": "5128",
    "name": "紫紅 (MAGENTA)"
  },
  {
    "model": "5129",
    "name": "藍色 (BLUE)"
  },
  {
    "model": "5140",
    "name": "紫色 (VIOLET)"
  }
]
```

---

### 12. TPU耐黃變助劑母粒 (TPU YELLOWING RESISTANCE MASTERBATCH)

- **ID**: `yellowing-resistance`
- **特性**: 專用型聚氨酯耐黃變母粒，兼具抗熱氧化與光穩定劑作用，能有效與樹脂融合且均勻分散，有效延長製品因紫外光照而老化的現象。

#### 產品概述
- 產品為選擇熔融指數較穩定適中的 TPU 材料為載體，低溫合成製造，粘度適當。
- 其顆粒狀本體混溶性佳，可均勻分散於材料上。不與製品中材料組成上發生不利反應。製品置放不吐霜。其建議添加量為：1.2-2.0%。作用效能對於光穩定性、抗氧化及紫外線吸收表現上，均有優異的效能。

#### 應用領域
- TPU 薄膜、異型材、鞋材、押出製品等。

#### 儲藏與注意事項
- 注意事項：置於陰涼避光且通風良好處、必須存放於乾燥，避光密閉容器中，常規有效期為 6 個月。
- ※詳細安全資料請參見物質安全資料表 (MSDS)

#### 數據規格結構
```json
[
  {
    "param": "外觀 (目測)",
    "val": "淡黃色顆粒"
  },
  {
    "param": "密度",
    "val": "0.95-1.08g/cm³"
  },
  {
    "param": "熔點",
    "val": "135-140℃"
  },
  {
    "param": "包裝",
    "val": "25KG/紙塑複合袋"
  }
]
```

---

### 13. TPU抗靜電助劑母粒 (ESU-320) (TPU ANTISTATIC ADDITIVE MASTERBATCH)

- **ID**: `antistatic-tpu`
- **特性**: ESU-320 為專用型熱塑聚氨酯彈性體母粒，屬長效性內加型抗靜電添加劑。兼具製品物性功能，無析出及製品吐霜發白情況。

#### 產品概述
- 以 TPU(n) 型嵌段線性聚合接枝製造生產，可供透明製品應用，外拌添加無需預烘本產品。
- 產品選擇熔融指數較穩定適中的 TPU 材料為載體（約 Shore A 70），其顆粒狀本體混溶性佳，可均勻分散於材料上。不與製品中材料組成上發生不利反應。其建議添加量為：5.0-10.0%。其電阻率作用可達 ≦10^9 歐姆/公分，適用於要求優異防靜電性能產品。

#### 應用領域
- TPU 薄膜、異型材、鞋材、膠輪、押出板材/片材/管材製品等。

#### 儲藏與注意事項
- 注意事項：置於陰涼避光、乾燥、未開封下保存，常規有效期為一年；若開封後請在三個月內使用完畢，避免光照。應置放於溫度低於 40℃ 的環境。
- ※詳細安全資料請參見物質安全資料表 (MSDS)

#### 數據規格結構
```json
[
  {
    "param": "外觀",
    "method": "目測",
    "unit": "-",
    "val": "淡黃色半透明顆粒"
  },
  {
    "param": "熔指",
    "method": "GB/T 3682",
    "unit": "190℃/2.16kg/min",
    "val": "7.2"
  },
  {
    "param": "密度",
    "method": "GB/T4472-2011",
    "unit": "g/cm³",
    "val": "1.1-1.2"
  },
  {
    "param": "電阻",
    "method": "GB/T 1410 Ω/cm",
    "unit": "-",
    "val": "≦10^9"
  }
]
```

---

### 14. 鐳雕助劑 (LASER MARKING POWDER)

- **ID**: `laser-marking`
- **特性**: 塑料工藝中可進行直接混拌注塑或造粒再行加工。過程中不改變材料加工工藝參數，利用激光機雷雕打標即可。

#### 產品概述
- 適用於 355nm（紫外線激光）、532nm（綠光激光）和 1064nm（光纖激光）。
- 應用鐳雕機設備建議採塑料用紫外鐳雕機（藍色光源）及光纖鐳雕機（紅色光源）。粉末無須與塑料顆粒烘料處理，建議可先將原料烘乾後，再行加入鐳雕助劑，進行充分分散。

#### 應用領域
- PVC、PS、PE、PP、ABS、PA6、PA66、PC、PC/ABS、PBT、POM、SEBS、SBS、TPU 等。

#### 儲藏與注意事項
- 注意事項：另添加阻燃助劑的塑料製件，可能會明顯降低鐳雕效果。若需實現阻燃效果，建議增加鐳雕助劑的使用量。
- 如鐳雕效果未能達到預期，建議調整激光設備參數。波長與能量相對反比，調整功率與速度，可相對改善表面效果。
- 儲放需要注意陰涼乾燥、通風良好、避免高溫和陽光直射。同時，應採取必要的安全措施。

#### 數據規格結構
```json
[
  {
    "model": "淡灰色粉末",
    "effect": "白雕黑",
    "amt": "2‰-5‰",
    "scope": "PVC, PS, PE, PP, ABS, PA6, PA66, PC, PC/ABS, PBT, POM, SEBS, SBS, TPU"
  },
  {
    "model": "黑色粉末",
    "effect": "黑雕白",
    "amt": "2‰-5‰",
    "scope": "PVC, PS, PE, PP, ABS, PA6, PA66, PC, PC/ABS, PBT, POM, SEBS, SBS, TPU"
  },
  {
    "model": "黑色粉末",
    "effect": "黑雕金",
    "amt": "2‰-5‰",
    "scope": "PVC, PS, PE, PP, ABS, PA6, PA66, PC, PC/ABS, PBT, POM, SEBS, SBS, TPU"
  },
  {
    "model": "青灰色粉末",
    "effect": "白雕黑 (透明級)",
    "amt": "2‰-5‰",
    "scope": "PC/PMMA透明料"
  }
]
```

---

### 15. 紅色顏料 (RED PIGMENTS)

- **ID**: `pigment-red`
- **特性**: 提供優異之耐遷移性、耐光性及耐熱性能，廣泛適用於各類塑膠著色及高溫加工條件。

#### 產品概述
- 主要由各類有機紅色顏料組成，包含 Pigment Red 53:1, 48:1, 48:3, 254, 48:2, 57:1, 176, 185 等型號。
- 產品經由精細加工，色澤鮮明，分散性優良，能有效提升最終製品之著色良率與耐候性。
- Full Shade: PVC/Pigment=100/0.2 | Tint Shade: PVC/Pigment/TiO2=100/0.2/1
- ●：推薦使用  X：不推薦使用  ○：選擇性使用

#### 應用領域
- 廣泛適用於 PP、PE、PVC、TPU、PS、ABS 等高分子材料及注塑/擠出成型加工。

#### 儲藏與注意事項
- 儲藏與搬運：內襯塑料袋、外覆紙塑複合袋或紙箱包裝，避光防水防潮保存。小心輕放，防止包裝破損。

#### 數據規格結構
```json
[
  {
    "model": "2501",
    "ci": "Pigment Red 53:1",
    "cas": "5160-02-1",
    "migration": "4",
    "light": "4",
    "heat": "220",
    "acid": "4~5",
    "alkali": "4",
    "halogen": "●",
    "pp": "●",
    "pe": "●",
    "pvc": "●",
    "tpu": "●",
    "ps": "●",
    "abs": "●"
  },
  {
    "model": "2548",
    "ci": "Pigment Red 48:1",
    "cas": "7585-41-3",
    "migration": "4",
    "light": "4~5",
    "heat": "200",
    "acid": "4~5",
    "alkali": "4",
    "halogen": "●",
    "pp": "●",
    "pe": "●",
    "pvc": "●",
    "tpu": "●",
    "ps": "●",
    "abs": "●"
  },
  {
    "model": "2503",
    "ci": "Pigment Red 48:3",
    "cas": "15782-05-5",
    "migration": "4~5",
    "light": "5",
    "heat": "210",
    "acid": "5",
    "alkali": "5",
    "halogen": "●",
    "pp": "●",
    "pe": "●",
    "pvc": "●",
    "tpu": "●",
    "ps": "●",
    "abs": "●"
  },
  {
    "model": "2508",
    "ci": "Pigment Red 254",
    "cas": "84632-65-5",
    "migration": "5",
    "light": "7~8",
    "heat": "280",
    "acid": "5",
    "alkali": "5",
    "halogen": "●",
    "pp": "●",
    "pe": "●",
    "pvc": "●",
    "tpu": "●",
    "ps": "●",
    "abs": "●"
  },
  {
    "model": "2502",
    "ci": "Pigment Red 48:2",
    "cas": "7023-61-2",
    "migration": "4~5",
    "light": "6",
    "heat": "210",
    "acid": "4~5",
    "alkali": "4~5",
    "halogen": "●",
    "pp": "●",
    "pe": "●",
    "pvc": "●",
    "tpu": "●",
    "ps": "●",
    "abs": "●"
  },
  {
    "model": "2504",
    "ci": "Pigment Red 57:1",
    "cas": "5281-04-9",
    "migration": "4~5",
    "light": "6",
    "heat": "210",
    "acid": "4~5",
    "alkali": "4~5",
    "halogen": "●",
    "pp": "●",
    "pe": "●",
    "pvc": "●",
    "tpu": "●",
    "ps": "●",
    "abs": "●"
  },
  {
    "model": "2510",
    "ci": "Pigment Red 176",
    "cas": "12225-06-8",
    "migration": "5",
    "light": "7~8",
    "heat": "260",
    "acid": "4~5",
    "alkali": "4~5",
    "halogen": "●",
    "pp": "●",
    "pe": "●",
    "pvc": "●",
    "tpu": "●",
    "ps": "●",
    "abs": "●"
  },
  {
    "model": "2511",
    "ci": "Pigment Red 185",
    "cas": "51920-12-8",
    "migration": "5",
    "light": "7~8",
    "heat": "250",
    "acid": "4~5",
    "alkali": "4~5",
    "halogen": "●",
    "pp": "●",
    "pe": "●",
    "pvc": "●",
    "tpu": "●",
    "ps": "●",
    "abs": "●"
  }
]
```

---

### 16. 酞菁顏料/紫色顏料 (PHTHALOCYANINE & VIOLET PIGMENTS)

- **ID**: `pigment-phthalocyanine`
- **特性**: 高效能酞菁藍、酞菁綠及紫色顏料，耐光度達 7-8 級，耐溫高達 280-300℃，為高品質製品著色首選。

#### 產品概述
- 提供 C.I. Pigment Blue 15, Blue 15:3, Green 7, Violet 23 等型號。
- 具有極其優異的耐熱性、耐候性與耐酸鹼性能，無鹵素環保認證，色彩飽和度極高。
- Full Shade: PVC/Pigment=100/0.2 | Tint Shade: PVC/Pigment/TiO2=100/0.2/1
- ●：推薦使用  X：不推薦使用  ○：選擇性使用

#### 應用領域
- 適用於 PP、PE、PVC、TPU、PS、ABS 等多類塑膠工程，以及高級電線電纜料、汽車內飾件著色。

#### 儲藏與注意事項
- 儲藏與搬運：內襯塑料袋、外覆紙塑複合袋包裝，避光防水保存，避免高溫直曬。

#### 數據規格結構
```json
[
  {
    "model": "6702",
    "ci": "Pigment Blue 15",
    "cas": "147-14-8",
    "migration": "5",
    "light": "7~8",
    "heat": "280",
    "acid": "4~5",
    "halogen": "●",
    "pp": "●",
    "pe": "●",
    "pvc": "●",
    "tpu": "●",
    "ps": "●",
    "abs": "●"
  },
  {
    "model": "6706",
    "ci": "Pigment Blue 15:3",
    "cas": "147-14-8",
    "migration": "4",
    "light": "7~8",
    "heat": "280",
    "acid": "4~5",
    "halogen": "●",
    "pp": "●",
    "pe": "●",
    "pvc": "●",
    "tpu": "●",
    "ps": "●",
    "abs": "●"
  },
  {
    "model": "6708",
    "ci": "Pigment Blue 15:3",
    "cas": "147-14-8",
    "migration": "5",
    "light": "7~8",
    "heat": "300",
    "acid": "4~5",
    "halogen": "●",
    "pp": "●",
    "pe": "●",
    "pvc": "●",
    "tpu": "●",
    "ps": "●",
    "abs": "●"
  },
  {
    "model": "5501",
    "ci": "Pigment Green 7",
    "cas": "1328-53-6",
    "migration": "5",
    "light": "7~8",
    "heat": "260",
    "acid": "4~5",
    "halogen": "●",
    "pp": "●",
    "pe": "●",
    "pvc": "●",
    "tpu": "●",
    "ps": "●",
    "abs": "●"
  },
  {
    "model": "5502",
    "ci": "Pigment Green 7",
    "cas": "1328-53-6",
    "migration": "5",
    "light": "7~8",
    "heat": "240",
    "acid": "4~5",
    "halogen": "●",
    "pp": "●",
    "pe": "●",
    "pvc": "●",
    "tpu": "●",
    "ps": "●",
    "abs": "●"
  },
  {
    "model": "7508",
    "ci": "Pigment Violet 23",
    "cas": "6358-30-1",
    "migration": "3",
    "light": "6~7",
    "heat": "260",
    "acid": "4~5",
    "halogen": "●",
    "pp": "●",
    "pe": "●",
    "pvc": "●",
    "tpu": "●",
    "ps": "●",
    "abs": "●"
  }
]
```

---

### 17. 螢光顏料 (高牢度) (HIGH-FASTNESS FLUORESCENT PIGMENTS)

- **ID**: `fluorescent-pigment-p24`
- **特性**: 超亮螢光顏料，專為塑料與油墨著色調配，展現鮮明發光效果，兼顧耐溫與高反射率性能。

#### 產品概述
- 提供型號 5120 至 5129 等多款高彩度著色方案。
- 相較於傳統有機顏料，螢光顏料色系明亮鮮豔，具有良好的分散性與混熔性。
- Full Shade: PVC/Pigment=100/0.2 | Tint Shade: PVC/Pigment/TiO2=100/0.2/1
- ●：推薦使用  X：不推薦使用  ○：選擇性使用

#### 應用領域
- 適用於 PP、PE、PVC、TPU、PS、ABS 等高分子材料，廣泛應用於文具玩具、安全警告標示及多色印刷領域。

#### 儲藏與注意事項
- 儲藏與搬運：內襯塑料袋、外覆紙塑袋或紙盒包裝，注意陰涼避光、防潮存放。

#### 數據規格結構
```json
[
  {
    "model": "5120",
    "ci": "Fluorescent Yellow",
    "cas": "-",
    "migration": "4~5",
    "light": "4",
    "heat": "220",
    "acid": "4~5",
    "halogen": "●",
    "pp": "●",
    "pe": "●",
    "pvc": "●",
    "tpu": "●",
    "ps": "●",
    "abs": "●"
  },
  {
    "model": "5121",
    "ci": "Fluorescent Green",
    "cas": "-",
    "migration": "4~5",
    "light": "4",
    "heat": "220",
    "acid": "4~5",
    "halogen": "●",
    "pp": "●",
    "pe": "●",
    "pvc": "●",
    "tpu": "●",
    "ps": "●",
    "abs": "●"
  },
  {
    "model": "5123",
    "ci": "Fluorescent Orange",
    "cas": "-",
    "migration": "4~5",
    "light": "4",
    "heat": "220",
    "acid": "4~5",
    "halogen": "●",
    "pp": "●",
    "pe": "●",
    "pvc": "●",
    "tpu": "●",
    "ps": "●",
    "abs": "●"
  },
  {
    "model": "5125",
    "ci": "Fluorescent Pink",
    "cas": "-",
    "migration": "4~5",
    "light": "4",
    "heat": "220",
    "acid": "4~5",
    "halogen": "●",
    "pp": "●",
    "pe": "●",
    "pvc": "●",
    "tpu": "●",
    "ps": "●",
    "abs": "●"
  },
  {
    "model": "5126",
    "ci": "Fluorescent Red",
    "cas": "-",
    "migration": "4~5",
    "light": "4",
    "heat": "220",
    "acid": "4~5",
    "halogen": "●",
    "pp": "●",
    "pe": "●",
    "pvc": "●",
    "tpu": "●",
    "ps": "●",
    "abs": "●"
  },
  {
    "model": "5127",
    "ci": "Fluorescent Rose",
    "cas": "-",
    "migration": "4~5",
    "light": "4",
    "heat": "220",
    "acid": "4~5",
    "halogen": "●",
    "pp": "●",
    "pe": "●",
    "pvc": "●",
    "tpu": "●",
    "ps": "●",
    "abs": "●"
  },
  {
    "model": "5140",
    "ci": "Fluorescent Violet",
    "cas": "-",
    "migration": "4~5",
    "light": "4",
    "heat": "220",
    "acid": "4~5",
    "halogen": "●",
    "pp": "●",
    "pe": "●",
    "pvc": "●",
    "tpu": "●",
    "ps": "●",
    "abs": "●"
  },
  {
    "model": "5129",
    "ci": "Fluorescent Blue",
    "cas": "-",
    "migration": "4~5",
    "light": "4",
    "heat": "220",
    "acid": "4~5",
    "halogen": "●",
    "pp": "●",
    "pe": "●",
    "pvc": "●",
    "tpu": "●",
    "ps": "●",
    "abs": "●"
  }
]
```

---

### 18. 氧化鐵顏料 (IRON OXIDE PIGMENTS)

- **ID**: `pigment-iron-oxide`
- **特性**: 經典氧化鐵紅、鐵黃、鐵黑顏料，極佳耐遷移性與高化學穩定性，性價比極高之無機著色產品。

#### 產品概述
- 提供 Pigment Red 101, Pigment Yellow 42, Pigment Black 11 等經典氧化鐵著色型號。
- 具有非常優異的遮蓋力、著色力與極佳耐光耐候性，化學穩定性高，無鹵素環保安全。
- Full Shade: PVC/Pigment=100/0.2 | Tint Shade: PVC/Pigment/TiO2=100/0.2/1
- ●：推薦使用  X：不推薦使用  ○：選擇性使用

#### 應用領域
- 廣泛應用於建材防護、塑膠抽粒改性、EVA 發泡、橡膠製品及高溫塗料著色。

#### 儲藏與注意事項
- 儲藏與搬運：防潮避光，置於乾燥陰涼處保存。搬運時輕拿輕放防止破損。

#### 數據規格結構
```json
[
  {
    "model": "8110",
    "ci": "Pigment Red 101",
    "cas": "1309-37-1",
    "migration": "5",
    "light": "6~7",
    "heat": "220",
    "acid": "4~5",
    "halogen": "●",
    "pp": "●",
    "pe": "●",
    "pvc": "●",
    "tpu": "●",
    "ps": "●",
    "abs": "●"
  },
  {
    "model": "8120",
    "ci": "Pigment Red 101",
    "cas": "1309-37-1",
    "migration": "5",
    "light": "6~7",
    "heat": "220",
    "acid": "4~5",
    "halogen": "●",
    "pp": "●",
    "pe": "●",
    "pvc": "●",
    "tpu": "●",
    "ps": "●",
    "abs": "●"
  },
  {
    "model": "8130",
    "ci": "Pigment Red 101",
    "cas": "1309-37-1",
    "migration": "5",
    "light": "6~7",
    "heat": "220",
    "acid": "4~5",
    "halogen": "●",
    "pp": "●",
    "pe": "●",
    "pvc": "●",
    "tpu": "●",
    "ps": "●",
    "abs": "●"
  },
  {
    "model": "8150",
    "ci": "Pigment Red 101",
    "cas": "1309-37-1",
    "migration": "5",
    "light": "6~7",
    "heat": "220",
    "acid": "4~5",
    "halogen": "●",
    "pp": "●",
    "pe": "●",
    "pvc": "●",
    "tpu": "●",
    "ps": "●",
    "abs": "●"
  },
  {
    "model": "8180",
    "ci": "Pigment Red 101",
    "cas": "1309-37-1",
    "migration": "5",
    "light": "6~7",
    "heat": "220",
    "acid": "4~5",
    "halogen": "●",
    "pp": "●",
    "pe": "●",
    "pvc": "●",
    "tpu": "●",
    "ps": "●",
    "abs": "●"
  },
  {
    "model": "8190",
    "ci": "Pigment Red 101",
    "cas": "1309-37-1",
    "migration": "5",
    "light": "6~7",
    "heat": "220",
    "acid": "4~5",
    "halogen": "●",
    "pp": "●",
    "pe": "●",
    "pvc": "●",
    "tpu": "●",
    "ps": "●",
    "abs": "●"
  },
  {
    "model": "4500",
    "ci": "Pigment Yellow 42",
    "cas": "51274-00-1",
    "migration": "5",
    "light": "6~7",
    "heat": "200",
    "acid": "4~5",
    "halogen": "●",
    "pp": "●",
    "pe": "●",
    "pvc": "●",
    "tpu": "●",
    "ps": "●",
    "abs": "●"
  },
  {
    "model": "F602",
    "ci": "Pigment Black 11",
    "cas": "1317-61-9",
    "migration": "5",
    "light": "6~7",
    "heat": "220",
    "acid": "4~5",
    "halogen": "●",
    "pp": "●",
    "pe": "●",
    "pvc": "●",
    "tpu": "●",
    "ps": "●",
    "abs": "●"
  }
]
```

---

### 19. 群青/鈦白粉/炭黑 (ULTRAMARINE & TITANIUM & CARBON)

- **ID**: `pigment-ultramarine`
- **特性**: 經典白、黑、群青藍無機顏料，擁有優異之耐光、高耐溫與極佳耐遷移性，適用極為苛刻之加工環境。

#### 產品概述
- 提供經典的 Pigment Blue 29 (群青藍)、Pigment Violet 15 (群青紫)、Pigment White 6 (鈦白粉-金紅石/銳鈦型)、Pigment Black 7 (高效炭黑) 等型號。
- 耐溫範圍由 300℃ 到高達 500℃ (如鈦白粉)，具有極高化學安定性與耐酸鹼度。
- Full Shade: PVC/Pigment=100/0.2 | Tint Shade: PVC/Pigment/TiO2=100/0.2/1
- ●：推薦使用  X：不推薦使用  ○：選擇性使用

#### 應用領域
- 電線電纜、工程塑料、高端包裝薄膜、汽車塑料零部件以及精密注塑擠出。

#### 儲藏與注意事項
- 儲藏與搬運：注意防潮密封保存，放置於乾燥通風之庫房，防止破損與化學物交叉污染。

#### 數據規格結構
```json
[
  {
    "model": "6804",
    "ci": "Pigment Blue 29",
    "cas": "57455-37-5",
    "migration": "5",
    "light": "7~8",
    "heat": "300",
    "acid": "1",
    "halogen": "●",
    "pp": "●",
    "pe": "●",
    "pvc": "●",
    "tpu": "●",
    "ps": "●",
    "abs": "●"
  },
  {
    "model": "6806",
    "ci": "Pigment Blue 29",
    "cas": "57455-37-5",
    "migration": "5",
    "light": "7~8",
    "heat": "300",
    "acid": "2~3",
    "halogen": "●",
    "pp": "●",
    "pe": "●",
    "pvc": "●",
    "tpu": "●",
    "ps": "●",
    "abs": "●"
  },
  {
    "model": "6807",
    "ci": "Pigment Violet 15",
    "cas": "12769-96-9",
    "migration": "5",
    "light": "7~8",
    "heat": "300",
    "acid": "1",
    "halogen": "●",
    "pp": "●",
    "pe": "●",
    "pvc": "●",
    "tpu": "●",
    "ps": "●",
    "abs": "●"
  },
  {
    "model": "R424",
    "ci": "Pigment White 6",
    "cas": "13463-67-7",
    "migration": "5",
    "light": "8",
    "heat": "500",
    "acid": "4~5",
    "halogen": "●",
    "pp": "●",
    "pe": "●",
    "pvc": "●",
    "tpu": "●",
    "ps": "●",
    "abs": "●"
  },
  {
    "model": "989",
    "ci": "Pigment Black 7",
    "cas": "1333-86-4",
    "migration": "5",
    "light": "8",
    "heat": "300",
    "acid": "4~5",
    "halogen": "●",
    "pp": "●",
    "pe": "●",
    "pvc": "●",
    "tpu": "●",
    "ps": "●",
    "abs": "●"
  }
]
```

---

### 20. 耐高溫無機顏料 (HIGH TEMPERATURE INORGANIC PIGMENTS)

- **ID**: `pigment-high-temp`
- **特性**: 頂級複合無機金屬氧化物顏料 (CICP)，耐溫高達 750-1200℃，極佳耐化學性與超常戶外耐候防護性能。

#### 產品概述
- 提供 Pigment Yellow 53, Brown 24, Brown 33, Black 28, Blue 28, Violet 16, Green 50 等最頂級之環保耐溫無機色彩方案。
- 專為超高加工溫度 (如氟塑料、工程聚酯) 或極端戶外環境 (汽車高溫烤漆、工業塗料) 開發。
- Full Shade: PVC/Pigment=100/0.2 | Tint Shade: PVC/Pigment/TiO2=100/0.2/1
- ●：推薦使用  X：不推薦使用  ○：選擇性使用

#### 應用領域
- 氟碳噴塗、工程塑料 (PA/PC/PBT)、戶外防腐鋼捲塗料、矽橡膠高溫加工、超高性能發泡材料著色。

#### 儲藏與注意事項
- 儲藏與搬運：存放於乾燥庫房，防止潮濕，按一般化學品運輸，安全性極高。

#### 數據規格結構
```json
[
  {
    "model": "195",
    "ci": "Pigment Yellow 53",
    "cas": "8007-18-9",
    "migration": "5",
    "light": "8",
    "heat": "1000",
    "acid": "4~5",
    "halogen": "●",
    "pp": "●",
    "pe": "●",
    "pvc": "●",
    "tpu": "●",
    "ps": "●",
    "abs": "●"
  },
  {
    "model": "10P225",
    "ci": "Pigment Brown 24",
    "cas": "68186-90-3",
    "migration": "5",
    "light": "8",
    "heat": "1000",
    "acid": "4~5",
    "halogen": "●",
    "pp": "●",
    "pe": "●",
    "pvc": "●",
    "tpu": "●",
    "ps": "●",
    "abs": "●"
  },
  {
    "model": "157A",
    "ci": "Pigment Brown 33",
    "cas": "68186-88-9",
    "migration": "5",
    "light": "8",
    "heat": "1000",
    "acid": "4~5",
    "halogen": "●",
    "pp": "●",
    "pe": "●",
    "pvc": "●",
    "tpu": "●",
    "ps": "●",
    "abs": "●"
  },
  {
    "model": "BK-1",
    "ci": "Pigment Black 28",
    "cas": "68186-91-4",
    "migration": "5",
    "light": "8",
    "heat": "750",
    "acid": "4~5",
    "halogen": "●",
    "pp": "●",
    "pe": "●",
    "pvc": "●",
    "tpu": "●",
    "ps": "●",
    "abs": "●"
  },
  {
    "model": "385A",
    "ci": "Pigment Blue 28",
    "cas": "1345-16-0",
    "migration": "5",
    "light": "8",
    "heat": "1200",
    "acid": "4~5",
    "halogen": "●",
    "pp": "●",
    "pe": "●",
    "pvc": "●",
    "tpu": "●",
    "ps": "●",
    "abs": "●"
  },
  {
    "model": "11T",
    "ci": "Pigment Violet 16",
    "cas": "10101-66-3",
    "migration": "5",
    "light": "8",
    "heat": "280",
    "acid": "4~5",
    "halogen": "●",
    "pp": "●",
    "pe": "●",
    "pvc": "●",
    "tpu": "●",
    "ps": "●",
    "abs": "●"
  },
  {
    "model": "223A",
    "ci": "Pigment Green 50",
    "cas": "68186-85-6",
    "migration": "5",
    "light": "8",
    "heat": "1000",
    "acid": "4~5",
    "halogen": "●",
    "pp": "●",
    "pe": "●",
    "pvc": "●",
    "tpu": "●",
    "ps": "●",
    "abs": "●"
  }
]
```

---

### 21. 紅色顏料/橙色顏料 (RED & ORANGE PIGMENTS (ENGINEERING))

- **ID**: `pigment-orange-red`
- **特性**: 中高端工程著色紅色與橙色顏料，卓越抗遷移與耐候性能，無鹵素環保認證，適用大宗工業加工。

#### 產品概述
- 提供 Pigment Red 272, Red 166, Red 149, Orange 64, Red 122, Red 208, Violet 19 等熱門著色劑型號。
- 優異的發色強度、優良的光學穩定性及耐化學溶劑性能。
- Full Shade: PVC/Pigment=100/0.2 | Tint Shade: PVC/Pigment/TiO2=100/0.2/1
- ●：推薦使用  X：不推薦使用  ○：選擇性使用

#### 應用領域
- 適用於 PP、PE、PVC、TPU、PS、ABS 以及汽車儀表板、高品質玩具、家電外殼之配色。

#### 儲藏與注意事項
- 儲藏與搬運：注意密封保存，存放在避光、防潮且通風良好的室內倉庫中。

#### 數據規格結構
```json
[
  {
    "model": "2572",
    "ci": "Pigment Red 272",
    "cas": "350249-32-0",
    "migration": "5",
    "light": "7~8",
    "heat": "280",
    "acid": "4~5",
    "halogen": "●",
    "pp": "●",
    "pe": "●",
    "pvc": "●",
    "tpu": "●",
    "ps": "●",
    "abs": "●"
  },
  {
    "model": "2566",
    "ci": "Pigment Red 166",
    "cas": "3905-19-9",
    "migration": "4",
    "light": "7~8",
    "heat": "280",
    "acid": "4~5",
    "halogen": "●",
    "pp": "●",
    "pe": "●",
    "pvc": "●",
    "tpu": "●",
    "ps": "●",
    "abs": "●"
  },
  {
    "model": "2549",
    "ci": "Pigment Red 149",
    "cas": "4948-15-6",
    "migration": "5",
    "light": "7~8",
    "heat": "300",
    "acid": "4~5",
    "halogen": "●",
    "pp": "●",
    "pe": "●",
    "pvc": "●",
    "tpu": "●",
    "ps": "●",
    "abs": "●"
  },
  {
    "model": "4584",
    "ci": "Pigment Orange 64",
    "cas": "72102-84-2",
    "migration": "5",
    "light": "7~8",
    "heat": "280",
    "acid": "4~5",
    "halogen": "●",
    "pp": "●",
    "pe": "●",
    "pvc": "●",
    "tpu": "●",
    "ps": "●",
    "abs": "●"
  },
  {
    "model": "2507",
    "ci": "Pigment Red 122",
    "cas": "16043-40-6",
    "migration": "5",
    "light": "7~8",
    "heat": "260",
    "acid": "4~5",
    "halogen": "●",
    "pp": "●",
    "pe": "●",
    "pvc": "●",
    "tpu": "●",
    "ps": "●",
    "abs": "●"
  },
  {
    "model": "2512",
    "ci": "Pigment Red 208",
    "cas": "31778-10-6",
    "migration": "5",
    "light": "7~8",
    "heat": "240",
    "acid": "4~5",
    "halogen": "●",
    "pp": "●",
    "pe": "●",
    "pvc": "●",
    "tpu": "●",
    "ps": "●",
    "abs": "●"
  },
  {
    "model": "2505",
    "ci": "Pigment Violet 19",
    "cas": "1047-16-1",
    "migration": "5",
    "light": "7~8",
    "heat": "280",
    "acid": "4~5",
    "halogen": "●",
    "pp": "●",
    "pe": "●",
    "pvc": "●",
    "tpu": "●",
    "ps": "●",
    "abs": "●"
  }
]
```

---

### 22. 黃色顏料 (YELLOW PIGMENTS)

- **ID**: `pigment-yellow`
- **特性**: 中高端工程著色黃色顏料，發色強度優異，分散性好，極佳熱穩定性與光穩定保護。

#### 產品概述
- 提供 Pigment Yellow 81, Yellow 151, Yellow 180, Yellow 62, Yellow 191, Yellow 83, Yellow 139, Yellow 181 等全系列黃色著色劑型號。
- 具有寬廣的耐溫範圍 (最高可達 300℃)，發色鮮明飽滿，無鹵素環保認證。
- Full Shade: PVC/Pigment=100/0.2 | Tint Shade: PVC/Pigment/TiO2=100/0.2/1
- ●：推薦使用  X：不推薦使用  ○：選擇性使用

#### 應用領域
- 廣泛應用於塑料著色、吹膜拉絲、射出模壓、工程塑料抽粒、EVA 發泡配色等大宗生產。

#### 儲藏與注意事項
- 儲藏與搬運：注意避光防潮密封儲存，防護包裝防止破損洩漏。

#### 數據規格結構
```json
[
  {
    "model": "4562",
    "ci": "Pigment Yellow 81",
    "cas": "22094-93-5",
    "migration": "4~5",
    "light": "7~8",
    "heat": "220",
    "acid": "4~5",
    "halogen": "●",
    "pp": "●",
    "pe": "●",
    "pvc": "●",
    "tpu": "●",
    "ps": "●",
    "abs": "●"
  },
  {
    "model": "4551",
    "ci": "Pigment Yellow 151",
    "cas": "31837-42-0",
    "migration": "5",
    "light": "7~8",
    "heat": "260",
    "acid": "4~5",
    "halogen": "●",
    "pp": "●",
    "pe": "●",
    "pvc": "●",
    "tpu": "●",
    "ps": "●",
    "abs": "●"
  },
  {
    "model": "4568",
    "ci": "Pigment Yellow 180",
    "cas": "77804-81-0",
    "migration": "5",
    "light": "7~8",
    "heat": "280",
    "acid": "4~5",
    "halogen": "●",
    "pp": "●",
    "pe": "●",
    "pvc": "●",
    "tpu": "●",
    "ps": "●",
    "abs": "●"
  },
  {
    "model": "4662",
    "ci": "Pigment Yellow 62",
    "cas": "12286-66-7",
    "migration": "4~5",
    "light": "7~8",
    "heat": "240",
    "acid": "4~5",
    "halogen": "●",
    "pp": "●",
    "pe": "●",
    "pvc": "●",
    "tpu": "●",
    "ps": "●",
    "abs": "●"
  },
  {
    "model": "4563",
    "ci": "Pigment Yellow 191",
    "cas": "129423-54-7",
    "migration": "4~5",
    "light": "7~8",
    "heat": "280",
    "acid": "4~5",
    "halogen": "●",
    "pp": "●",
    "pe": "●",
    "pvc": "●",
    "tpu": "●",
    "ps": "●",
    "abs": "●"
  },
  {
    "model": "4566",
    "ci": "Pigment Yellow 83",
    "cas": "5567-15-7",
    "migration": "4~5",
    "light": "7~8",
    "heat": "220",
    "acid": "4~5",
    "halogen": "●",
    "pp": "●",
    "pe": "●",
    "pvc": "●",
    "tpu": "●",
    "ps": "●",
    "abs": "●"
  },
  {
    "model": "4539",
    "ci": "Pigment Yellow 139",
    "cas": "36888-99-0",
    "migration": "5",
    "light": "7~8",
    "heat": "240",
    "acid": "4~5",
    "halogen": "●",
    "pp": "●",
    "pe": "●",
    "pvc": "●",
    "tpu": "●",
    "ps": "●",
    "abs": "●"
  },
  {
    "model": "4581",
    "ci": "Pigment Yellow 181",
    "cas": "74441-05-7",
    "migration": "5",
    "light": "7~8",
    "heat": "300",
    "acid": "4~5",
    "halogen": "●",
    "pp": "●",
    "pe": "●",
    "pvc": "●",
    "tpu": "●",
    "ps": "●",
    "abs": "●"
  }
]
```

---

