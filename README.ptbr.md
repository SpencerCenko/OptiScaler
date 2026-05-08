<div align="center">

  ![Logo](https://github.com/user-attachments/assets/c7dad5da-0b29-4710-8a57-b58e4e407abd)

</div>
<hr />
<br />
<div align="center">
  <a href="https://github.com/sponsors/cdozdil?frequency=one-time"><img src="images/gh-sponsor-red.png" /></a>
  <a href="https://buymeacoffee.com/nitec"><img src="images/bmac.png" /></a>
</div>
<br />

## Sumário

**1.** [**Sobre**](#about)  
**2.** [**Como funciona?**](#how-it-works)  
**3.** [**APIs suportadas e Upscalers**](#which-apis-and-upscalers-are-supported)  
**4.** [**Instalação**](#installation)  
**5.** [**Problemas conhecidos**](#known-issues)  
**6.** [**Compilação e créditos**](#compilation)  
**7.** [**Wiki**](https://github.com/optiscaler/OptiScaler/wiki)

<br />
<div align="center">
  <a href="https://discord.gg/wEyd9w4hG5"><img src="https://img.shields.io/badge/OptiScaler-blue?style=for-the-badge&logo=discord&logoColor=white&logoSize=auto&color=5865F2" alt="Discord invite"></a>
  <a href="https://github.com/optiscaler/OptiScaler/releases/latest"><img src="https://img.shields.io/badge/Download-Stable-green?style=for-the-badge&logo=github&logoSize=auto" alt="Stable release"></a>
  <a href="https://github.com/optiscaler/OptiScaler/releases/tag/nightly"><img src="https://img.shields.io/badge/Download-Nightly-purple?style=for-the-badge&logo=github&logoSize=auto" alt="Nightly release"></a>
  <a href="https://github.com/optiscaler/OptiScaler/wiki"><img src="https://img.shields.io/badge/Documentation-blue?style=for-the-badge&logo=gitbook&logoColor=white&logoSize=auto" alt="Wiki"></a>
</div>
<div align="center">
  <a href="https://github.com/optiscaler/OptiScaler/releases"><img src="https://img.shields.io/github/downloads/optiscaler/optiscaler/total?style=for-the-badge&logo=gitextensions&logoSize=auto&label=Total" alt="Total DL"></a>
  <a href="https://github.com/optiscaler/OptiScaler/releases/latest"><img src="https://img.shields.io/github/downloads/optiscaler/optiscaler/latest/total?style=for-the-badge&logo=gitextensions&logoSize=auto&label=Stable&color=green&logoColor=white" alt="Stable DL"></a>
  <a href="https://github.com/optiscaler/OptiScaler/releases/tag/nightly"><img src="https://img.shields.io/github/downloads/optiscaler/OptiScaler/nightly/total?style=for-the-badge&logo=gitextensions&logoColor=white&logoSize=auto&label=Nightly&color=purple" alt="Nightly DL"></a>
  <a href="https://github.com/optiscaler/OptiScaler/stargazers"><img src="https://img.shields.io/github/stars/optiscaler/optiscaler?style=for-the-badge&logo=githubsponsors&logoColor=white&label=S.T.A.R.S." alt="Stars"></a>
</div>


## Sobre
 **OptiScaler** é uma ferramenta que te permite substituir upscalers em jogos que ***já suportam DLSS2+ / FSR2+ / XeSS*** ($`^1`$), assim como gerenciar o ***frame generation*** nos jogos já mencionados _(seja substituindo o FG já existente ou habilitando-o em jogos que suportam DX12 através do experimental ***OptiFG***)_. Também oferece várias opções de customização para todos os usuários, incluindo aqueles com placas de vídeo Nvidia usando DLSS.

> [!CAUTION]
> * Temos recebido relatos sobre alguns **websites FALSOS** se apresentando como o time OptiScaler, então nós gostaríamos fortemente de ressaltar que nós **NÃO TEMOS um website oficial!**
> * **Nós NÃO temos um aplicativo gerenciador oficial**, então por favor sejam cautelosos baixando ou usando eles!
> * Os únicos **lugares LEGÍTIMOS** são esse Github, nosso servidor no Discord e a página de Nitec no site NexusMods.  
> * OptiScaler é **GRÁTIS**, qualquer tipo de necessidade de pagamento é golpe!  

> [!TIP]
> _Por exemplo, se um jogo só tem DLSS disponível, o OptiScaler pode ser usado para substituir o DLSS por XeSS ou FSR 3.1 (também funciona em jogos que só tem FSR2, como The Outer Worlds Spacer's Choice, embora exija prover manualmente o arquivo nvngx_dlss.dll)._
  
**Aspectos chave do OptiScaler:**
- Habilita o uso de XeSS, FSR2, FSR3, **FSR4**$`^2`$ (_oficialmente, disponível apenas para RDNA4_) e DLSS em jogos com upscaler(temporal) habilitado
- Permite que os usuários ajustem sua experiência de upscaling conforme desejar, usando uma vasta gama de ajustes e aprimoramentos (RCAS e MAS, Output Scaling, Presets do DLSS, Ratio e DRS Overrides etc.)
- Desde v0.7.0+, adicionado o suporte ao ***frame generation experimental DX12*** com uma possível solução de HUDfix ([**OptiFG**](#optifg--hudfix-experimental-hud-ghosting-fix))
- Suporte ao [**Fakenvapi**](#installation) integrado - habilitando Reflex hooking e injetando _Anti-Lag 2_ (apenas RDNA1+), _LatencyFlex_ (LFX) ou _XeLL_ (apenas Intel) - _integrado desde 0.9_  
- Desde v0.7.7, adicionado suporte ao mod **Nukem's** FSR3-FG [**dlssg-to-fsr3**](#installation), apenas suportado em jogos com *** DLSS-FG nativo*** - _integrado desde 0.9_
- Desde v0.7.8, aicionado suporte ao **ASI plugin loading**(_desabilitado_ por padrão(`LoadAsiPlugins=` no INI), carrega de uma pasta customizada, por padrão `plugins`)
- Novo projeto - [**OptiPatcher**](https://github.com/optiscaler/OptiPatcher) - um Plugin ASI para o OptiScaler que permite inputs DLSS e DLSSG sem necessidade de spoofing em ***jogos suportados***.
- Desde v0.7.8, OptiScaler agora aplica automáticamente certos patches aos jogos para uma melhor experiência.
- Desde v0.9.0, Inputs e Outputs de FG separados, adicionado suporte ao XeFG e ao FSR4-FG , também integramos Fakenvapi e o mod Nukem's FSR3-FG 
- Para uma lista detalhada de todas as funcionalidades, consulte [Funcionalidades](Features.md)


> [!IMPORTANT]
> _**Sempre consulte a [lista de compatibilidade na wiki](https://github.com/optiscaler/OptiScaler/wiki) para problemas conhecidos e soluções alternativas.**_  
> Também consulte  [***problemas conhecidos do OptiScaler***](#known-issues) no final a respeito de compatibilidade ao **RTSS** .  
> Uma [***lista de compatibilidade FSR4***](https://github.com/optiscaler/OptiScaler/wiki/FSR4-Compatibility-List) separa está dísponível para jogos testados pela comunidade.  
> ***[3]** Para itens **não integrados**, consulte [Instalação](#installation).*  

> [!NOTE]
> ### Notas de upscaler
> <details>
>  <summary><b>Click for [1], [2] </b></summary>  
>  
> **[1]** para jogos **Unreal Engine**, apenasUE XeSS -> Opti XeSS/FSR4 funciona  
>  
> *a respeito dos **inputs do XeSS**, já que o plugin da **Unreal Engine** não fornece profundidade, substituir XeSS em jogos quebra outros upscalers (por exemplo: Redout 2 é um jogo com apenas XeSS), mas você ainda pode aplicar RCAS sharpening(nitidez) ao XeSS para reduzir o aspecto borrado.* 
>
> *a respeito dos **inputs do FSR**, FSR 3.1 é a primeira versão totalmente padronizada, é uma API voltada para o futuro e que deve ser totalmente suportada. já que o FSR2 e FSR3 suportam interfaces customizadas, o suporte nos jogos dependerá totalmente da implementação dos desenvolvedores. Com jogos Unreal Engine, você pode precisar de [ini tweaks](https://github.com/optiscaler/OptiScaler/wiki/Unreal-Engine-Tweaks) para inputs FSR.*  
>
> **[2]** *a respeito do **FSR4**, consulte [lista de compatibilidade FSR4](https://github.com/optiscaler/OptiScaler/wiki/FSR4-Compatibility-List) para jogos suportados e informações gerais.*
> 
> </details>


## Servidor do Discord oficial: [OptiScaler](https://discord.gg/wEyd9w4hG5)

*Esse projeto é baseado no excelente [CyberFSR2](https://github.com/PotatoOfDoom/CyberFSR2) de [PotatoOfDoom](https://github.com/PotatoOfDoom).*

## Como funciona?
* O OptiScaler age como um intermediário, ele intercepta os chamados do upscaler pelo jogo (_**Inputs**_) e os redireciona para o upscaler escolhido no back-end (_**Output**_), permitindo o usuário à substituir uma tecnologia por outra. **Inputs -> OptiScaler -> Outputs**  
* _Or put more bluntly, **Input** is the upscaler used in game settings, and **Output** the one selected in Opti Overlay._
* _Same goes for FG options which are separated into **FG Source** and **FG Output**._

> [!NOTE]
> * Pressing **`Insert`** should open the Optiscaler **Overlay** in-game with all of the options (_`ShortcutKey=` can be changed in the INI file, or under **Keybinds** in the overlay_). 
> * Pressing **`Page Up`** shows the performance stats overlay in the top left, and can be cycled between different modes with **`Page Down`** (_keybinds customisable in the overlay_).  
> * If Opti overlay is instantly disappearing after trying Insert a few times, maybe try **`Alt + Insert`** ([reported workaround](https://github.com/optiscaler/OptiScaler/issues/484) for alternate keyboard layouts).

![inputs_and_outputs](https://github.com/user-attachments/assets/7ff37fd7-515f-488d-99ff-faa586e206fc)

## Which APIs and Upscalers are Supported?
Currently **OptiScaler** can be used with DirectX 11, DirectX 12 and Vulkan, but each API has different sets of supported upscalers.  
[**OptiFG**](#optifg--hudfix-experimental-hud-ghosting-fix) currently **only supports DX12** and is explained in a separate paragraph.

#### For DirectX 12
- XeSS (Default)
- FSR 2.1.2, 2.2.1
- FSR 3.X (and FSR 2.3.X)
- FSR 4.X (via FSR3.X update, _officially RDNA4 only_)
- DLSS

#### For DirectX 11
- FSR 2.2.1 (Default, native DX11)
- FSR 3.1.2 (unofficial port to native DX11)
- DLSS (native DX11)
- XeSS 2.X (native DX11, _Intel ARC only_)
- XeSS, FSR 2.1.2, 2.2.1, FSR 3.X w/Dx12 (_via D3D11on12_)$`^1`$
- FSR 4.X (via FSR 3.X w/Dx12 update, _officially RDNA4 only_)

> [!NOTE]
> <details>
>  <summary><b>Expand for [1]</b></summary>
>
> _**[1]** These implementations use a background DirectX12 device to be able to use DX12-only upscalers. There's a performance penalty up to 10-ish % for this method, but allows many more upscaler options. Also native DX11 implementation of FSR 2.2.1 is a backport from Unity renderer and has its own problems of which some were fixed by OptiScaler._
> </details>

#### For Vulkan
- FSR 4.X (via FSR 3.X w/Dx12 update, _officially RDNA4 only_)
- FSR2 2.1.2 (Default), 2.2.1
- FSR3 3.1 (and FSR2 2.3.2)
- DLSS
- XeSS 2.x

#### OptiFG + HUDfix (experimental HUD ghosting fix) 
**OptiFG** was added with **v0.7** and is **only supported in DX12**. 
It's an **experimental** way of adding FG to games without native Frame Generation, or can also be used as a last case scenario if the native FG is not working properly.  
* Currently supports FSR3-FG (requires HUDfix to avoid HUD ghosting), XeFG and FSR4-FG (ML model deals with the HUD, so may or may not require HUDfix).

For more information on OptiFG and how to use it, please check the Wiki page - [OptiFG](https://github.com/optiscaler/OptiScaler/wiki/OptiFG).


## Installation
> [!CAUTION]
> _**Warning**: **Do not use this mod with online games.** It may trigger anti-cheat software and cause bans!_

> [!IMPORTANT]
> **For installation steps, please check the [**Wiki**](https://github.com/optiscaler/OptiScaler/wiki)**  

## Configuration
Please check [this](Config.md) document for configuration parameters and explanations. If your GPU is not an Nvidia one, check [GPU spoofing options](Spoofing.md) *(Will be updated)*

## Known Issues

> [!NOTE]
> **For a list of known issues, please check the [**Wiki**](https://github.com/optiscaler/OptiScaler/wiki)**.
> 
> Also worth checking the [Compatibility List](https://github.com/optiscaler/OptiScaler/wiki/Compatibility-List) for possible game issues and their fixes.

## Compilation

### Requirements
* Visual Studio 2022

### Instructions
* Clone this repo with **all of its submodules**.
* Open the OptiScaler.sln with Visual Studio 2022.
* Build the project

## Thanks
* @PotatoOfDoom for CyberFSR2
* @Artur for DLSS Enabler and helping me implement NVNGX api correctly
* @LukeFZ & @Nukem for their great mods and sharing their knowledge 
* @FakeMichau for continous support, testing and feature creep
* @QM for continous testing efforts and helping me to reach games
* @TheRazerMD for continous testing and support
* @Cryio, @krispy, @krisshietala, @Lordubuntu, @scz, @Veeqo for their hard work on (now outdated) [compatibility matrix](https://docs.google.com/spreadsheets/d/1qsvM0uRW-RgAYsOVprDWK2sjCqHnd_1teYAx00_TwUY)
* And the whole DLSS2FSR community for all their support

## Credit
This project uses [FreeType](https://gitlab.freedesktop.org/freetype/freetype) licensed under the [FTL](https://gitlab.freedesktop.org/freetype/freetype/-/blob/master/docs/FTL.TXT)

## Sponsors
<table>
 <tbody>
  <tr>
   <td align="center"><img alt="[SignPath]" src="https://avatars.githubusercontent.com/u/34448643" height="30"/></td>
   <td>Free code signing on Windows provided by <a href="https://signpath.io/">SignPath.io</a>, certificate by <a href="https://signpath.org/">SignPath Foundation</a></td>
  </tr>
 </tbody>
</table>
