---
ms.openlocfilehash: b1910bf0338bccd77ad9e983990d4d193698ec1f
ms.sourcegitcommit: 721c3e4bdbb1ea0bb420818ec944c538fe5c513a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/01/2020
ms.locfileid: "96477184"
---
### <a name="workflow-xoml-file-checksums-changed-from-md5-to-sha256"></a><span data-ttu-id="b0a03-101">Las sumas de comprobación del archivo XOML han cambiado de MD5 a SHA256</span><span class="sxs-lookup"><span data-stu-id="b0a03-101">Workflow XOML file checksums changed from MD5 to SHA256</span></span>

#### <a name="details"></a><span data-ttu-id="b0a03-102">Detalles</span><span class="sxs-lookup"><span data-stu-id="b0a03-102">Details</span></span>

<span data-ttu-id="b0a03-103">Cuando se compilan los proyectos de flujo de trabajo que contienen archivos XOML, se incluye una suma de comprobación del contenido del archivo XOML en el código generado como un valor <xref:System.Workflow.ComponentModel.Compiler.WorkflowMarkupSourceAttribute.MD5Digest?displayProperty=nameWithType> con el fin de admitir la depuración de flujos de trabajo basados en XOML con Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="b0a03-103">To support debugging XOML-based workflows with Visual Studio, when workflow projects containing XOML files build, a checksum of the contents of the XOML file is included in the code generated as a <xref:System.Workflow.ComponentModel.Compiler.WorkflowMarkupSourceAttribute.MD5Digest?displayProperty=nameWithType> value.</span></span> <span data-ttu-id="b0a03-104">En .NET Framework 4.7.2 y versiones anteriores, este hash de suma de comprobación usaba el algoritmo MD5, que causaba problemas en sistemas compatibles con FIPS.</span><span class="sxs-lookup"><span data-stu-id="b0a03-104">In the .NET Framework 4.7.2 and earlier versions, this checksum hashing used the MD5 algorithm, which caused issues on FIPS-enabled systems.</span></span> <span data-ttu-id="b0a03-105">A partir de .NET Framework 4.8, el algoritmo que se usa es SHA256.</span><span class="sxs-lookup"><span data-stu-id="b0a03-105">Starting with the .NET Framework 4.8, the algorithm used is SHA256.</span></span> <span data-ttu-id="b0a03-106">Para ser compatible con WorkflowMarkupSourceAttribute.MD5Digest, se usan solo los primeros 16 bytes de la suma de comprobación generada. Esto puede causar problemas durante la depuración.</span><span class="sxs-lookup"><span data-stu-id="b0a03-106">To be compatible with the WorkflowMarkupSourceAttribute.MD5Digest, only the first 16 bytes of the generated checksum are used.This may cause problems during debugging.</span></span> <span data-ttu-id="b0a03-107">Es posible que deba volver a compilar el proyecto.</span><span class="sxs-lookup"><span data-stu-id="b0a03-107">You may need to re-build your project.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="b0a03-108">Sugerencia</span><span class="sxs-lookup"><span data-stu-id="b0a03-108">Suggestion</span></span>

<span data-ttu-id="b0a03-109">Si volver a compilar el proyecto no soluciona el problema, intente establecer el modificador de `AppContext`&quot;Switch.System.Workflow.ComponentModel.UseLegacyHashForXomlFileChecksum&quot; como true. En el código:</span><span class="sxs-lookup"><span data-stu-id="b0a03-109">If re-building your project does not solve the problem, try setting the `AppContext` switch &quot;Switch.System.Workflow.ComponentModel.UseLegacyHashForXomlFileChecksum&quot; to true.In code:</span></span>

<pre><code class="lang-csharp">System.AppContext.SetSwitch(&quot;Switch.System.Workflow.ComponentModel.UseLegacyHashForXomlFileChecksum&quot;, true);&#13;&#10;</code></pre>

<span data-ttu-id="b0a03-110">O en un archivo de configuración (esto debe estar en el archivo MSBuild.exe.config de MSBuild.exe que está usando):</span><span class="sxs-lookup"><span data-stu-id="b0a03-110">Or in a configuration file (this needs to be in MSBuild.exe.config for the MSBuild.exe that you are using):</span></span>

<pre><code class="lang-xml">&lt;configuration&gt;&#13;&#10;&lt;runtime&gt;&#13;&#10;&lt;AppContextSwitchOverrides value=&quot;Switch.System.Workflow.ComponentModel.UseLegacyHashForXomlFileChecksum=true&quot; /&gt;&#13;&#10;&lt;/runtime&gt;&#13;&#10;&lt;/configuration&gt;&#13;&#10;</code></pre>

| <span data-ttu-id="b0a03-111">NOMBRE</span><span class="sxs-lookup"><span data-stu-id="b0a03-111">Name</span></span>    | <span data-ttu-id="b0a03-112">Valor</span><span class="sxs-lookup"><span data-stu-id="b0a03-112">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="b0a03-113">Ámbito</span><span class="sxs-lookup"><span data-stu-id="b0a03-113">Scope</span></span>   | <span data-ttu-id="b0a03-114">Secundaria</span><span class="sxs-lookup"><span data-stu-id="b0a03-114">Minor</span></span>       |
| <span data-ttu-id="b0a03-115">Versión</span><span class="sxs-lookup"><span data-stu-id="b0a03-115">Version</span></span> | <span data-ttu-id="b0a03-116">4.8</span><span class="sxs-lookup"><span data-stu-id="b0a03-116">4.8</span></span>         |
| <span data-ttu-id="b0a03-117">Tipo</span><span class="sxs-lookup"><span data-stu-id="b0a03-117">Type</span></span>    | <span data-ttu-id="b0a03-118">Redestinación</span><span class="sxs-lookup"><span data-stu-id="b0a03-118">Retargeting</span></span> |
