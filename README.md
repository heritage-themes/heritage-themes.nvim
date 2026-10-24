# Heritage Themes

Colour themes drawn from the colour traditions of different cultures. 65 dark and light colour schemes in 32 families; each family maps the named colours of one tradition to syntax roles.

This repository holds the Neovim plugin that [Heritage Themes](https://github.com/heritage-themes/heritage-themes) generates for each release. Report problems and make changes there.

## Install

The plugin needs Neovim 0.10 or later and a terminal with 24-bit colour, for which Neovim turns on `termguicolors` itself.

With [lazy.nvim](https://github.com/folke/lazy.nvim):

```lua
{
  "heritage-themes/heritage-themes.nvim",
  lazy = false,
  priority = 1000,
  config = function()
    vim.cmd.colorscheme("heritage-holi-night")
  end,
}
```

With `vim.pack`, built into Neovim 0.12:

```lua
vim.pack.add({ "https://github.com/heritage-themes/heritage-themes.nvim" })
vim.cmd.colorscheme("heritage-holi-night")
```

Without a plugin manager, unzip `heritage-themes-nvim-<version>.zip` from the [latest release](https://github.com/heritage-themes/heritage-themes/releases/latest) into `~/.local/share/nvim/site/pack/heritage/start/`.

Run `:colorscheme heritage-` and press `Tab` to list the schemes. Each scheme sets `background` to its own brightness.

## What is coloured

Each scheme colours the editor, Tree-sitter captures, LSP semantic tokens, diagnostics, the status line, tab line, window bar, floating windows, the completion menu, diff mode and the terminal. It also colours the signs of [gitsigns.nvim](https://github.com/lewis6991/gitsigns.nvim), and ships a [lualine](https://github.com/nvim-lualine/lualine.nvim) theme of the same name, which lualine's default `auto` theme loads.

Code is coloured by Tree-sitter once a parser for its language is installed, for example with [nvim-treesitter](https://github.com/nvim-treesitter/nvim-treesitter). The groups follow the capture names of nvim-treesitter's queries, so a construct takes one colour in every language: keys in YAML, TOML and JSON take the field colour, and decorators, annotations and attributes the annotation colour.

To change a group, set it in a `ColorScheme` autocommand, so that it survives switching schemes:

```lua
vim.api.nvim_create_autocmd("ColorScheme", {
  pattern = "heritage-*",
  callback = function()
    vim.api.nvim_set_hl(0, "Comment", { fg = "#808080", italic = true })
  end,
})
```

## Colour schemes

| Family | Colour schemes | Tradition |
| --- | --- | --- |
| [Ainu](https://github.com/heritage-themes/heritage-themes/tree/master/themes/ainu) | `heritage-ainu-kaparamip-dark`, `heritage-ainu-attus-light` | The appliqué robes of the Ainu of Hokkaido: bold appliqué keywords, red method declarations at the openings, green thread strings, yellow fields and blue-violet numbers, on indigo cotton or elm-bark cloth. |
| [Aizome](https://github.com/heritage-themes/heritage-themes/tree/master/themes/aizome) | `heritage-aizome-kachi-dark`, `heritage-aizome-kamenozoki-light` | Japanese indigo dyeing in a single hue: hierarchy by depth of dye, with sashiko-white declarations, green-leaning asagi strings and violet-leaning kon numbers. |
| [Bengal](https://github.com/heritage-themes/heritage-themes/tree/master/themes/bengal) | `heritage-bengal-baluchari-dark`, `heritage-bengal-laal-paar-light` | Bengal's looms and Durga Puja: aparajita keywords, Baluchari-magenta strings, paddy-green methods and terracotta types, on wine-dark Baluchari silk or a white laal paar sari with a red border. |
| [Danqing](https://github.com/heritage-themes/heritage-themes/tree/master/themes/danqing) | `heritage-danqing-ink-dark`, `heritage-danqing-paper-light` | Chinese painting pigments, led by the blue-green landscape: azurite keywords, malachite strings, cinnabar methods and gamboge types on inkstone or aged xuan paper, with Spock blocks marked like red seal stamps. |
| [Edo](https://github.com/heritage-themes/heritage-themes/tree/master/themes/edo) | `heritage-edo-cha-dark`, `heritage-edo-nezumi-light` | The forty-eight browns and hundred greys of Edo-period dress: muted indigo keywords, brown literals, tinted-grey names, and a hidden red lining for the caret and labels. |
| [Gujarat](https://github.com/heritage-themes/heritage-themes/tree/master/themes/gujarat) | `heritage-gujarat-navratri-dark`, `heritage-gujarat-rann-light` | Gujarat's Navratri, Rann of Kutch and patola silk: parrot-green keywords, patola-red types, turmeric methods and garba-pink strings, on a mirror-worked night or the white salt desert. |
| [Hmong](https://github.com/heritage-themes/heritage-themes/tree/master/themes/hmong) | `heritage-hmong-batik-dark`, `heritage-hmong-hemp-light` | The batik and cross-stitch of the Hmong pleated skirt: names in the tones of indigo batik, with pink keywords, lime strings and orange numbers from the cross-stitch, on indigo or undyed hemp. |
| [Holi](https://github.com/heritage-themes/heritage-themes/tree/master/themes/holi) | `heritage-holi-night`, `heritage-holi-day` | The Indian festival of colours at full strength: gulabi-pink keywords, saffron strings, green types and blue methods, thrown like gulal over the ash of the Holika bonfire or over white cotton. |
| [Kalaallisuut](https://github.com/heritage-themes/heritage-themes/tree/master/themes/kalaallisuut) | `heritage-kalaallisuut-qernertoq-dark`, `heritage-kalaallisuut-qaqortoq-light` | The West Greenlandic national dress and its colours for age and marital status: red keywords, confirmation pink strings, yellow kamik numbers, blue anorak types, green bead methods and black-and-white fields. |
| [Kalamkari](https://github.com/heritage-themes/heritage-themes/tree/master/themes/kalamkari) | `heritage-kalamkari-indigo-dark`, `heritage-kalamkari-cotton-light` | Indian hand-painted textiles and their natural dyes, kept muted: aubergine keywords, indigo types, madder methods and myrobalan strings on a vat of indigo or unbleached cotton, outlined in iron-black ink. |
| [Kashubia](https://github.com/heritage-themes/heritage-themes/tree/master/themes/kashubia) | `heritage-kashubia-zemia-dark`, `heritage-kashubia-niebo-light` | The seven colours of Kashubian embroidery: cornflower keywords, navy types and light-blue methods under yellow strings, green fields and red numbers, on black earth or white linen. |
| [Kerala](https://github.com/heritage-themes/heritage-themes/tree/master/themes/kerala) | `heritage-kerala-backwaters-dark`, `heritage-kerala-kasavu-light` | Kerala's backwaters, Kathakali stage and kasavu loom: kathi-red keywords, zari-gold strings, pacha-green methods and backwater-teal types, on palm-dark water at night or off-white handloom with a gold border. |
| [Łowicz](https://github.com/heritage-themes/heritage-themes/tree/master/themes/lowicz) | `heritage-lowicz-wycinanka-dark`, `heritage-lowicz-kodra-light` | The striped wool and layered paper cut-outs of Łowicz: orange keywords, green strings, emerald types and violet methods with yellow fields and cinnabar numbers, on a black template or a white paper strip. |
| [Maramureș](https://github.com/heritage-themes/heritage-themes/tree/master/themes/maramures) | `heritage-maramures-zadie-dark`, `heritage-maramures-canepa-light` | The striped aprons and flowered skirts of Maramureș, coloured by age: married red keywords, pumpkin-flower strings, blue numbers, dark green types, rose methods and leather-brown fields. |
| [Maya](https://github.com/heritage-themes/heritage-themes/tree/master/themes/maya) | `heritage-maya-corte-dark`, `heritage-maya-huipil-light` | The town dress of the Guatemalan Maya read through the K'iche' colour roads: green keywords, red strings, yellow types, purple methods and indigo fields, on the jaspe corte or the white huipil. |
| [Morocco](https://github.com/heritage-themes/heritage-themes/tree/master/themes/morocco) | `heritage-morocco-majorelle-dark`, `heritage-morocco-marrakech-dark`, `heritage-morocco-zellige-dark` | Three Moroccan walls on saturated backgrounds: Majorelle ultramarine with yellow pots, Marrakech red clay with turquoise doors, and zellige jade with saffron and cobalt tile. |
| [Mudhif](https://github.com/heritage-themes/heritage-themes/tree/master/themes/mudhif) | `heritage-mudhif-qir-dark`, `heritage-mudhif-qasab-light` | The reed guest house of the Marsh Arabs of Iraq: hierarchy from the tone and weight of reed gold, with green reed shoots for strings and the willow fire for numbers. |
| [Mughal](https://github.com/heritage-themes/heritage-themes/tree/master/themes/mughal) | `heritage-mughal-night`, `heritage-mughal-wasli-light` | Mughal miniature painting: lapis-lazuli keywords, vermilion types, gold-leaf methods and verdigris strings on a lamp-lit night or burnished wasli paper, with Spock labels lettered in gold. |
| [Ndebele](https://github.com/heritage-themes/heritage-themes/tree/master/themes/ndebele) | `heritage-ndebele-nzima-dark`, `heritage-ndebele-mhlophe-light` | The painted walls of the Ndebele homestead: keywords drawn as the black outline, with sky-blue types, green methods, yellow strings and pink fields as the flat fills, on black paint or white lime-wash. |
| [Peru](https://github.com/heritage-themes/heritage-themes/tree/master/themes/peru) | `heritage-peru-kulli-dark`, `heritage-peru-puka-dark` | Andean natural dyes on two dyed-through grounds: q'olle-yellow keywords, ch'illka-green strings and anqas-blue types on purple corn, and ch'illka-green keywords with turquoise methods on cochineal crimson. |
| [Podhale](https://github.com/heritage-themes/heritage-themes/tree/master/themes/podhale) | `heritage-podhale-klobuk-dark`, `heritage-podhale-sukno-light` | The Highlander costume of Podhale: crimson keywords and navy strings from the cords of the parzenica, brass methods, green fields, blue types and coral numbers, on a black felt hat or white broadcloth. |
| [Punjab](https://github.com/heritage-themes/heritage-themes/tree/master/themes/punjab) | `heritage-punjab-phulkari-dark`, `heritage-punjab-basant-light` | Punjab's phulkari embroidery and Basant mustard fields: golden-silk keywords, orange-silk methods, turquoise strings and saag-green types, on madder-rust khaddar or a field of flowering mustard. |
| [Rajasthan](https://github.com/heritage-themes/heritage-themes/tree/master/themes/rajasthan) | `heritage-rajasthan-blue-city-dark`, `heritage-rajasthan-pink-city-light` | The colours of Rajasthan's cities and cloth: kesariya-saffron keywords, rani-pink strings, golden-sandstone types and blue-pottery methods, on the blue houses of Jodhpur by night or the pink sandstone of Jaipur by day. |
| [Sardinia](https://github.com/heritage-themes/heritage-themes/tree/master/themes/sardinia) | `heritage-sardinia-orbace-dark`, `heritage-sardinia-camisa-light` | The traditional dress of Sardinia: saffron keywords and scarlet strings from the dyed silk and wool, indigo methods, walnut-brown fields and coral numbers, on black orbace or white linen. |
| [Shaker](https://github.com/heritage-themes/heritage-themes/tree/master/themes/shaker) | `heritage-shaker-prussian-dark`, `heritage-shaker-plaster-light` | The paint of the Shaker villages: bold meetinghouse keywords in plaster white or Prussian blue, Shaker red strings, pumpkin methods, yellow ochre fields, chrome green types and verdigris numbers. |
| [Shuimo](https://github.com/heritage-themes/heritage-themes/tree/master/themes/shuimo) | `heritage-shuimo-night`, `heritage-shuimo-day` | Chinese ink-wash painting: hierarchy by ink tone and weight rather than hue, with indigo and ochre washes and a red seal as the only accents. |
| [Tamil](https://github.com/heritage-themes/heritage-themes/tree/master/themes/tamil) | `heritage-tamil-kolam-dark`, `heritage-tamil-olai-light` | Tamil Nadu's kolam, palm-leaf manuscripts and Kanchipuram silk: peacock-neck keywords, mango strings, lac-red types and sapphire methods, on a dark granite threshold or a palm leaf. |
| [Wixárika](https://github.com/heritage-themes/heritage-themes/tree/master/themes/wixarika) | `heritage-wixarika-haramara-dark`, `heritage-wixarika-wirikuta-light` | The yarn paintings and beadwork of the Wixárika (Huichol): the five colours of maize, with yellow keywords, blue strings, purple fields, red types and peyote-green methods, on the black of the western sea or the light of the eastern desert. |
| [Wuxing](https://github.com/heritage-themes/heritage-themes/tree/master/themes/wuxing) | `heritage-wuxing-night`, `heritage-wuxing-day` | Chinese colour symbolism and the Five Elements: vermilion keywords (Fire), jade strings (Wood), imperial-yellow types (Earth), and a rice-paper or indigo-ink canvas in place of stark white and black (Metal and Water). |
| [Yolŋu](https://github.com/heritage-themes/heritage-themes/tree/master/themes/yolngu) | `heritage-yolngu-galawu-dark`, `heritage-yolngu-gapan-light` | The ochres of Yolŋu bark painting from north-east Arnhem Land: red keywords, yellow strings, orange types, haematite fields and pink numbers, with white or charcoal methods, on stringybark or white clay. |
| [Zalipie](https://github.com/heritage-themes/heritage-themes/tree/master/themes/zalipie) | `heritage-zalipie-sadza-dark`, `heritage-zalipie-wapno-light` | The painted cottages of Zalipie: lime, soot and clay for text, keywords and comments, and the flowers for names, with rose methods, leaf-green strings and violet types, on a soot plinth or a lime-washed wall. |
| [Złotnica](https://github.com/heritage-themes/heritage-themes/tree/master/themes/zlotnica) | `heritage-zlotnica-aksamit-dark`, `heritage-zlotnica-plotno-light` | The gold-and-silver embroidered bonnets of Kashubia: hierarchy by metal, tone and weight, with sapphire, burgundy and emerald velvet as the only colours, on green velvet or white linen. |

Each family's page describes its colour tradition. The same themes are available for JetBrains IDEs, VS Code, Sublime Text and Zed: see [Heritage Themes on GitHub](https://github.com/heritage-themes/heritage-themes).

Report a problem or suggest a tradition on the [issue tracker](https://github.com/heritage-themes/heritage-themes/issues). Include the colour scheme, Neovim version, language and a screenshot.
