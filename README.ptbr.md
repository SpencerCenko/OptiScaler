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
**3.** [**quais APIs e Upscalers são Suportados?**](#apiups)  
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


<a id="about"></a>
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
- Desde v0.9.0, Inputs e Outputs do FG foram separados, adicionado suporte ao XeFG e ao FSR4-FG , também integramos Fakenvapi e o mod Nukem's FSR3-FG 
- Para uma lista detalhada de todas as funcionalidades, consulte [Funcionalidades](Features.md)


> [!IMPORTANT]
> _**Sempre consulte a [lista de compatibilidade na wiki](https://github.com/optiscaler/OptiScaler/wiki) para problemas conhecidos e soluções alternativas.**_  
> Também consulte  [***problemas conhecidos do OptiScaler***](#known-issues) no final a respeito de compatibilidade ao **RTSS** .  
> Uma [***lista de compatibilidade FSR4***](https://github.com/optiscaler/OptiScaler/wiki/FSR4-Compatibility-List) separa está dísponível para jogos testados pela comunidade.  
> ***[3]** Para itens **não integrados**, consulte [Instalação](#installation).*  

> [!NOTE]
> ### Notas de upscaler
> <details>
>  <summary><b>Clique para [1], [2] </b></summary>  
>  
> **[1]** para jogos **Unreal Engine**, apenas UE XeSS -> Opti XeSS/FSR4 funciona  
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

<a id="how-it-work"></a>
## Como funciona? 
* O OptiScaler age como um intermediário, ele intercepta os chamados do upscaler pelo jogo (_**Inputs**_) e os redireciona para o upscaler escolhido no back-end (_**Output**_), permitindo o usuário à substituir uma tecnologia por outra. **Inputs -> OptiScaler -> Outputs**  
* _Ou de forma mais simples, **Input** é o upscaler usado nas configurações do jogo, e **Output** o que é selecionado no Overlay do optiscaler._
* _O mesmo vale para as opções de FG que são separadas em **FG Source** e **FG Output**._

> [!NOTE]
> * Pressionar **`Insert`** deve abrir o **Overlay** do Optiscaler no jogo, com todas as opções (_`ShortcutKey=` pode ser alterado nos arquivos INI, ou em **Keybinds** no overlay_). 
> * Pressionar **`Page Up`** mostra o status de performance no topo superior esquerdo da tela, e é possível alternar entre diferentes modos com **`Page Down`** (_Teclas de atalho(Keybinds) podem ser customizáveis no overlay_).  
> * Se o overlay do Optiscaler desaparece instantaneamente após tentar apertar Insert algumas vezes, tente **`Alt + Insert`** ([solução alternativa](https://github.com/optiscaler/OptiScaler/issues/484) para layouts de teclado alternativos).

![inputs_e_outputs](https://github.com/user-attachments/assets/7ff37fd7-515f-488d-99ff-faa586e206fc)

<a id="apiups"></a>
## quais APIs e Upscalers são Suportados? 
Atualmente o **OptiScaler** pode ser usado com DirectX 11, DirectX 12 e Vulkan, mas cada API tem diferentes tipos de upscalers suportados.  
[**OptiFG**](#optifg--hudfix-experimental-hud-ghosting-fix) atualmente **só em suportado em DX12** e isso é explicado em um tópico separado.

#### Para DirectX 12
- XeSS (Padrão)
- FSR 2.1.2, 2.2.1
- FSR 3.X (e FSR 2.3.X)
- FSR 4.X (via atualização do FSR3.X, _oficialmente exclusivo para RDNA4_)
- DLSS

#### Para DirectX 11
- FSR 2.2.1 (Padrão, DX11 nativo)
- FSR 3.1.2 (port não oficial para DX11 nativo)
- DLSS (DX11 nativo)
- XeSS 2.X (DX11 nativo, _Apenas para Intel ARC_)
- XeSS, FSR 2.1.2, 2.2.1, FSR 3.X com Dx12 (_via D3D11on12_)$`^1`$
- FSR 4.X (via FSR 3.X com atualização em Dx12, _oficialmente exclusivo para RDNA4_)

> [!NOTE]
> <details>
>  <summary><b>Clique para expandir [1]</b></summary>
>
> _**[1]** Essas implementações usam DirectX12 como background para permitir o funcionamento de upscalers exclusivos do DX12. Esse método gera uma penalidade de performance de até 10%, mas permite muito mais opções de upscalers. Além disso, a implementação nativa do FSR 2.2.1 é uma adaptação do renderizador da Unity, que tem seus próprios problemas, alguns desses problemas foram corrigidos pelo OptiScaler._
> </details>

#### Para Vulkan
- FSR 4.X (via FSR 3.X com atualização em Dx12, _oficialmente exclusivo para RDNA4_)
- FSR2 2.1.2 (Padrão), 2.2.1
- FSR3 3.1 (e FSR2 2.3.2)
- DLSS
- XeSS 2.x

#### OptiFG + HUDfix (correção experimental de ghosting na HUD) 
**OptiFG** foi adicionado em **v0.7** e é **suportado apenas em DX12**. 
É um jeito **experimental** de adicionar FG para jogos sem Frame Generation nativo, ou também pode ser usado como último recurso caso o FG nativo não esteja funcionando corretamente.  
* Atualmente suporta FSR3-FG (precisa do HUDfix para evitar o ghosting na HUD), XeFG e FSR4-FG (o modelo ML lida com a HUD, então pode ou não precisar do HUDfix HUDfix).

Para mais informações sobre o OptiFG e como usá-lo, consulte a página na Wiki - [OptiFG](https://github.com/optiscaler/OptiScaler/wiki/OptiFG).

<a id="installation"></a>
## Instalação
> [!CAUTION]
> _**Aviso**: **não use esse mod em jogos online.** ele pode acionar o anti-cheat do jogo, resultando em banimentos!_

> [!IMPORTANT]
> **Para as etapas de instalação, consulte a [**Wiki**](https://github.com/optiscaler/OptiScaler/wiki)**  

## Configuração
Por favor, consulte [esse](Config.md) documento para os parâmetros de configuração e explicações. Se sua placa de vídeo não é da Nvidia, consulte [GPU spoofing options](Spoofing.md) *(Irá ser atualizado)*
<a id="known-issues"></a>
## Problemas conhecidos 

> [!NOTE]
> **Para uma lista de problemas conhecidos, consulte a [**Wiki**](https://github.com/optiscaler/OptiScaler/wiki)**.
> 
> Também vale a pena checar a [Lista de compatibilidade](https://github.com/optiscaler/OptiScaler/wiki/Compatibility-List) for possible game issues and their fixes.

<a id="compilation"></a>
## Compilação 

### Requisistos
* Visual Studio 2022

### Instruções
* Clone esse repositório com **todos os seus submódulos**.
* Abra o OptiScaler.sln com o Visual Studio 2022.
* compile o projeto

## Agradecimentos
* @PotatoOfDoom pelo CyberFSR2
* @Artur pelo DLSS Enabler e por ter me ajudado à implementar a api NVNGX corretamente
* @LukeFZ & @Nukem pelos seus ótimos mods e por compartilharem seu conhecimentos 
* @FakeMichau pelo seu suporte contínuo, pelos testes e pela expansão contínua de funcionalidades(feature creep)
* @QM pelos seus esforços constantes nos testes e por me ajudar a ter aos jogos
* @TheRazerMD pelos constantes testes e suporte
* @Cryio, @krispy, @krisshietala, @Lordubuntu, @scz, @Veeqo pelo seu trabalho duro na (agora datado) [matrix de compatibilidade](https://docs.google.com/spreadsheets/d/1qsvM0uRW-RgAYsOVprDWK2sjCqHnd_1teYAx00_TwUY)
* e toda a comunidade de DLSS2FSR por todo o seu suporte

## Créditos
Esse projeto usa [FreeType](https://gitlab.freedesktop.org/freetype/freetype) licensiado sob o [FTL](https://gitlab.freedesktop.org/freetype/freetype/-/blob/master/docs/FTL.TXT)

## Patrocinadores
<table>
 <tbody>
  <tr>
   <td align="center"><img alt="[SignPath]" src="https://avatars.githubusercontent.com/u/34448643" height="30"/></td>
   <td>Assinatura de código gratuita no Windows fornecida por <a href="https://signpath.io/">SignPath.io</a>, certificado por <a href="https://signpath.org/">SignPath Foundation</a></td>
  </tr>
 </tbody>
</table>
