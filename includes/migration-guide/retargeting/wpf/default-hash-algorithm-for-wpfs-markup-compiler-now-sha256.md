---
ms.openlocfilehash: 4303b177ffe01328965c909a5a3809414fcead91
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/01/2020
ms.locfileid: "85614928"
---
### <a name="the-default-hash-algorithm-for-wpfs-markup-compiler-is-now-sha256"></a><span data-ttu-id="ccbc0-101">Ahora el algoritmo hash predeterminado para el compilador de marcado de WPF es SHA256</span><span class="sxs-lookup"><span data-stu-id="ccbc0-101">The default hash algorithm for WPF's Markup Compiler is now SHA256</span></span>

#### <a name="details"></a><span data-ttu-id="ccbc0-102">Detalles</span><span class="sxs-lookup"><span data-stu-id="ccbc0-102">Details</span></span>

<span data-ttu-id="ccbc0-103">MarkupCompiler de WPF proporciona servicios de compilación para los archivos de marcado XAML.</span><span class="sxs-lookup"><span data-stu-id="ccbc0-103">The WPF MarkupCompiler provides compilation services for XAML markup files.</span></span>  <span data-ttu-id="ccbc0-104">En .NET Framework 4.7.1 y versiones anteriores, el algoritmo hash predeterminado que se usaba para las sumas de comprobación era SHA1.</span><span class="sxs-lookup"><span data-stu-id="ccbc0-104">In the .NET Framework 4.7.1 and earlier versions, the default hash algorithm used for checksums was SHA1.</span></span> <span data-ttu-id="ccbc0-105">Por motivos de seguridad recientes con SHA1, este valor predeterminado se ha cambiado a SHA256 a partir de .NET Framework 4.7.2.</span><span class="sxs-lookup"><span data-stu-id="ccbc0-105">Due to recent security concerns with SHA1, this default has been changed to SHA256 starting with the .NET Framework 4.7.2.</span></span>  <span data-ttu-id="ccbc0-106">Este cambio afecta a la generación de todas las sumas de comprobación para los archivos de marcado durante la compilación.</span><span class="sxs-lookup"><span data-stu-id="ccbc0-106">This change affects all checksum generation for markup files during compilation.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="ccbc0-107">Sugerencia</span><span class="sxs-lookup"><span data-stu-id="ccbc0-107">Suggestion</span></span>

<span data-ttu-id="ccbc0-108">Un desarrollador que tenga como destino .NET Framework 4.7.2 o una versión posterior y quiera revertir al comportamiento de los algoritmos hash SHA1 debe establecer la marca de AppContext siguiente.</span><span class="sxs-lookup"><span data-stu-id="ccbc0-108">A developer who targets .NET Framework 4.7.2 or greater and wants to revert to SHA1 hashing behavior must set the following AppContext flag.</span></span>

<pre><code class="lang-xml">&lt;configuration&gt;&#13;&#10;&lt;runtime&gt;&#13;&#10;&lt;AppContextSwitchOverrides value=&quot;Switch.System.Windows.Markup.DoNotUseSha256ForMarkupCompilerChecksumAlgorithm=true&quot;/&gt;&#13;&#10;&lt;/runtime&gt;&#13;&#10;&lt;/configuration&gt;&#13;&#10;</code></pre>

<span data-ttu-id="ccbc0-109">Un desarrollador que quiera usar algoritmos hash SHA256, al tiempo que selecciona como destino una versión de .NET Framework inferior a la 4.7.2, debe establecer la marca de AppContext siguiente.</span><span class="sxs-lookup"><span data-stu-id="ccbc0-109">A developer who wants to utilize SHA256 hashing while targeting a framework version below .NET 4.7.2 must set the below AppContext flag.</span></span>  <span data-ttu-id="ccbc0-110">Tenga en cuenta que la versión instalada de .NET Framework debe ser 4.7.2 o posterior.</span><span class="sxs-lookup"><span data-stu-id="ccbc0-110">Note that the installed version of the .NET Framework must be 4.7.2 or greater.</span></span>

<pre><code class="lang-xml">&lt;configuration&gt;&#13;&#10;&lt;runtime&gt;&#13;&#10;&lt;AppContextSwitchOverrides value=&quot;Switch.System.Windows.Markup.DoNotUseSha256ForMarkupCompilerChecksumAlgorithm=false&#13;&#10;&lt;/runtime&gt;&#13;&#10;&lt;/configuration&gt;&#13;&#10;</code></pre>

| <span data-ttu-id="ccbc0-111">NOMBRE</span><span class="sxs-lookup"><span data-stu-id="ccbc0-111">Name</span></span>    | <span data-ttu-id="ccbc0-112">Valor</span><span class="sxs-lookup"><span data-stu-id="ccbc0-112">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="ccbc0-113">Ámbito</span><span class="sxs-lookup"><span data-stu-id="ccbc0-113">Scope</span></span>   | <span data-ttu-id="ccbc0-114">Transparente</span><span class="sxs-lookup"><span data-stu-id="ccbc0-114">Transparent</span></span> |
| <span data-ttu-id="ccbc0-115">Versión</span><span class="sxs-lookup"><span data-stu-id="ccbc0-115">Version</span></span> | <span data-ttu-id="ccbc0-116">4.7.2</span><span class="sxs-lookup"><span data-stu-id="ccbc0-116">4.7.2</span></span>       |
| <span data-ttu-id="ccbc0-117">Tipo</span><span class="sxs-lookup"><span data-stu-id="ccbc0-117">Type</span></span>    | <span data-ttu-id="ccbc0-118">Redestinación</span><span class="sxs-lookup"><span data-stu-id="ccbc0-118">Retargeting</span></span> |
