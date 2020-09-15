---
ms.openlocfilehash: c7500550cd9714a9788a7dea68af04823f000f7f
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/01/2020
ms.locfileid: "85614799"
---
### <a name="stack-traces-obtained-when-using-portable-pdbs-now-include-source-file-and-line-information-if-requested"></a><span data-ttu-id="5e0ab-101">Los seguimientos de la pila obtenidos al usar archivos PDB portátiles ahora incluyen información del archivo y la línea de origen si se solicita</span><span class="sxs-lookup"><span data-stu-id="5e0ab-101">Stack traces obtained when using portable PDBs now include source file and line information if requested</span></span>

#### <a name="details"></a><span data-ttu-id="5e0ab-102">Detalles</span><span class="sxs-lookup"><span data-stu-id="5e0ab-102">Details</span></span>

<span data-ttu-id="5e0ab-103">A partir de .NET Framework 4.7.2, los seguimientos de la pila obtenidos al usar archivos PDB portátiles incluyen información del archivo y la línea de origen cuando se solicita.</span><span class="sxs-lookup"><span data-stu-id="5e0ab-103">Starting with .NET Framework 4.7.2, stack traces obtained when using portable PDBs include source file and line information when requested.</span></span> <span data-ttu-id="5e0ab-104">En las versiones anteriores a .NET Framework 4.7.2, la información del archivo y la línea de origen no estaba disponible al usar archivos PDB portátiles incluso si se solicitaba de forma explícita.</span><span class="sxs-lookup"><span data-stu-id="5e0ab-104">In versions prior to .NET Framework 4.7.2, source file and line information would be unavailable when using portable PDBs even if explicitly requested.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="5e0ab-105">Sugerencia</span><span class="sxs-lookup"><span data-stu-id="5e0ab-105">Suggestion</span></span>

<span data-ttu-id="5e0ab-106">Para las aplicaciones que tienen como destino .NET Framework 4.7.2, se puede rechazar la información del archivo y la línea de origen cuando se usan archivos PDB portátiles si no es adecuada mediante la adición de lo siguiente a la sección `<runtime>` del archivo `app.config`:</span><span class="sxs-lookup"><span data-stu-id="5e0ab-106">For applications that target the .NET Framework 4.7.2, you can opt out of the source file and line information when using portable PDBs if it is not desirable by adding the following to the `<runtime>` section of your `app.config` file:</span></span>

```xml
<runtime>
  <AppContextSwitchOverrides value="Switch.System.Diagnostics.IgnorePortablePDBsInStackTraces=true" />
</runtime>
```

<span data-ttu-id="5e0ab-107">Para las aplicaciones que tienen como destino versiones anteriores de .NET Framework, pero que se ejecutan en .NET Framework 4.7.2 o versiones posteriores, se puede incluir la información del archivo y la línea de origen cuando se usan archivos PDB portátiles si se agrega lo siguiente a la sección `<runtime>` del archivo `app.config`:</span><span class="sxs-lookup"><span data-stu-id="5e0ab-107">For applications that target earlier versions of the .NET Framework but run on the .NET Framework 4.7.2 or later, you can opt in to the source file and line information when using portable PDBs by adding the following to the `<runtime>` section of your `app.config` file:</span></span>

```xml
<runtime>
  <AppContextSwitchOverrides value="Switch.System.Diagnostics.IgnorePortablePDBsInStackTraces=false" />
</runtime>
```

| <span data-ttu-id="5e0ab-108">NOMBRE</span><span class="sxs-lookup"><span data-stu-id="5e0ab-108">Name</span></span>    | <span data-ttu-id="5e0ab-109">Valor</span><span class="sxs-lookup"><span data-stu-id="5e0ab-109">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="5e0ab-110">Ámbito</span><span class="sxs-lookup"><span data-stu-id="5e0ab-110">Scope</span></span>   | <span data-ttu-id="5e0ab-111">Borde</span><span class="sxs-lookup"><span data-stu-id="5e0ab-111">Edge</span></span>        |
| <span data-ttu-id="5e0ab-112">Versión</span><span class="sxs-lookup"><span data-stu-id="5e0ab-112">Version</span></span> | <span data-ttu-id="5e0ab-113">4.7.2</span><span class="sxs-lookup"><span data-stu-id="5e0ab-113">4.7.2</span></span>       |
| <span data-ttu-id="5e0ab-114">Tipo</span><span class="sxs-lookup"><span data-stu-id="5e0ab-114">Type</span></span>    | <span data-ttu-id="5e0ab-115">Redestinación</span><span class="sxs-lookup"><span data-stu-id="5e0ab-115">Retargeting</span></span> |

#### <a name="affected-apis"></a><span data-ttu-id="5e0ab-116">API afectadas</span><span class="sxs-lookup"><span data-stu-id="5e0ab-116">Affected APIs</span></span>

- <xref:System.Diagnostics.StackTrace.%23ctor(System.Boolean)>
- <xref:System.Diagnostics.StackTrace.%23ctor(System.Exception,System.Boolean)>
- <xref:System.Diagnostics.StackTrace.%23ctor(System.Exception,System.Int32,System.Boolean)>
