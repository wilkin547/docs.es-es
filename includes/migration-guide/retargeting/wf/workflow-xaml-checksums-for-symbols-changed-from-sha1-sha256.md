---
ms.openlocfilehash: 946e71f2f466664c8f9fcf4811288ce693a872eb
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/01/2020
ms.locfileid: "85616293"
---
### <a name="workflow-xaml-checksums-for-symbols-changed-from-sha1-to-sha256"></a><span data-ttu-id="c367e-101">Sumas de comprobación de flujo de trabajo XAML para los símbolos que se han cambiado de SHA1 a SHA256</span><span class="sxs-lookup"><span data-stu-id="c367e-101">Workflow XAML checksums for symbols changed from SHA1 to SHA256</span></span>

#### <a name="details"></a><span data-ttu-id="c367e-102">Detalles</span><span class="sxs-lookup"><span data-stu-id="c367e-102">Details</span></span>

<span data-ttu-id="c367e-103">Para admitir la depuración con Visual Studio, el tiempo de ejecución de flujo de trabajo genera una suma de comprobación para un archivo XAML de flujo de trabajo mediante un algoritmo de hash.</span><span class="sxs-lookup"><span data-stu-id="c367e-103">To support debugging with Visual Studio, the Workflow runtime generates a checksum for a workflow XAML file using a hashing algorithm.</span></span> <span data-ttu-id="c367e-104">En .NET Framework 4.6.2 y versiones anteriores, el hash de suma de comprobación de flujo de trabajo usaba el algoritmo MD5, que causaba problemas en sistemas compatibles con FIPS.</span><span class="sxs-lookup"><span data-stu-id="c367e-104">In the .NET Framework 4.6.2 and earlier versions, workflow checksum hashing used the MD5 algorithm, which caused issues on FIPS-enabled systems.</span></span> <span data-ttu-id="c367e-105">A partir de .NET Framework 4.7, el algoritmo predeterminado se ha cambiado a SHA1.</span><span class="sxs-lookup"><span data-stu-id="c367e-105">Starting with the .NET Framework 4.7, the default algorithm was changed to SHA1.</span></span> <span data-ttu-id="c367e-106">A partir de .NET Framework 4.8, el algoritmo predeterminado se ha cambiado a SHA256.</span><span class="sxs-lookup"><span data-stu-id="c367e-106">Starting with the .NET Framework 4.8, the default algorithm was changed to SHA256.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="c367e-107">Sugerencia</span><span class="sxs-lookup"><span data-stu-id="c367e-107">Suggestion</span></span>

<span data-ttu-id="c367e-108">Si el código no puede cargar las instancias de flujo de trabajo o no puede buscar símbolos adecuados debido a un error de suma de comprobación, pruebe a establecer el valor `AppContext` "Switch.System.Activities.UseSHA1HashForDebuggerSymbols" en `true`.</span><span class="sxs-lookup"><span data-stu-id="c367e-108">If your code is unable to load workflow instances or to find appropriate symbols due to a checksum failure, try setting the `AppContext` switch "Switch.System.Activities.UseSHA1HashForDebuggerSymbols" to `true`.</span></span> <span data-ttu-id="c367e-109">Mediante código:</span><span class="sxs-lookup"><span data-stu-id="c367e-109">In code:</span></span>

```csharp
System.AppContext.SetSwitch("Switch.System.Activities.UseSHA1HashForDebuggerSymbols", true);
```

<span data-ttu-id="c367e-110">O bien, en la configuración:</span><span class="sxs-lookup"><span data-stu-id="c367e-110">Or in configuration:</span></span>

```xml
<configuration>
  <runtime>
    <AppContextSwitchOverrides value="Switch.System.Activities.UseSHA1HashForDebuggerSymbols=true" />
  </runtime>
</configuration>
```

| <span data-ttu-id="c367e-111">NOMBRE</span><span class="sxs-lookup"><span data-stu-id="c367e-111">Name</span></span>    | <span data-ttu-id="c367e-112">Valor</span><span class="sxs-lookup"><span data-stu-id="c367e-112">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="c367e-113">Ámbito</span><span class="sxs-lookup"><span data-stu-id="c367e-113">Scope</span></span>   | <span data-ttu-id="c367e-114">Secundaria</span><span class="sxs-lookup"><span data-stu-id="c367e-114">Minor</span></span>       |
| <span data-ttu-id="c367e-115">Versión</span><span class="sxs-lookup"><span data-stu-id="c367e-115">Version</span></span> | <span data-ttu-id="c367e-116">4.8</span><span class="sxs-lookup"><span data-stu-id="c367e-116">4.8</span></span>         |
| <span data-ttu-id="c367e-117">Tipo</span><span class="sxs-lookup"><span data-stu-id="c367e-117">Type</span></span>    | <span data-ttu-id="c367e-118">Redestinación</span><span class="sxs-lookup"><span data-stu-id="c367e-118">Retargeting</span></span> |
