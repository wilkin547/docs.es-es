---
ms.openlocfilehash: 424872b25436c7fcbe603639028e813eed6f9b99
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/05/2020
ms.locfileid: "89496228"
---
### <a name="assemblies-compiled-with-regexcompiletoassembly-breaks-between-40-and-45"></a><span data-ttu-id="45b24-101">Los ensamblados compilados con Regex.CompileToAssembly se interrumpen entre las versiones 4.0 y 4.5</span><span class="sxs-lookup"><span data-stu-id="45b24-101">Assemblies compiled with Regex.CompileToAssembly breaks between 4.0 and 4.5</span></span>

#### <a name="details"></a><span data-ttu-id="45b24-102">Detalles</span><span class="sxs-lookup"><span data-stu-id="45b24-102">Details</span></span>

<span data-ttu-id="45b24-103">Si un ensamblado de expresiones regulares compiladas se crea con .NET Framework 4.5 pero tiene como destino .NET Framework 4, se inicia una excepción al intentar usar una de las expresiones regulares de ese ensamblado en un sistema con .NET Framework 4 instalado.</span><span class="sxs-lookup"><span data-stu-id="45b24-103">If an assembly of compiled regular expressions is built with the .NET Framework 4.5 but targets the .NET Framework 4, attempting to use one of the regular expressions in that assembly on a system with .NET Framework 4 installed throws an exception.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="45b24-104">Sugerencia</span><span class="sxs-lookup"><span data-stu-id="45b24-104">Suggestion</span></span>

<span data-ttu-id="45b24-105">Para evitar este problema, realice una de las acciones siguientes:</span><span class="sxs-lookup"><span data-stu-id="45b24-105">To work around this problem, you can do either of the following:</span></span><ul><li><span data-ttu-id="45b24-106">Compile el ensamblado que contiene las expresiones regulares con .NET Framework 4.</span><span class="sxs-lookup"><span data-stu-id="45b24-106">Build the assembly that contains the regular expressions with the .NET Framework 4.</span></span></li><li><span data-ttu-id="45b24-107">Use una expresión regular interpretada.</span><span class="sxs-lookup"><span data-stu-id="45b24-107">Use an interpreted regular expression.</span></span></li></ul>

| <span data-ttu-id="45b24-108">NOMBRE</span><span class="sxs-lookup"><span data-stu-id="45b24-108">Name</span></span>    | <span data-ttu-id="45b24-109">Valor</span><span class="sxs-lookup"><span data-stu-id="45b24-109">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="45b24-110">Ámbito</span><span class="sxs-lookup"><span data-stu-id="45b24-110">Scope</span></span>   |<span data-ttu-id="45b24-111">Secundaria</span><span class="sxs-lookup"><span data-stu-id="45b24-111">Minor</span></span>|
|<span data-ttu-id="45b24-112">Versión</span><span class="sxs-lookup"><span data-stu-id="45b24-112">Version</span></span>|<span data-ttu-id="45b24-113">4.5</span><span class="sxs-lookup"><span data-stu-id="45b24-113">4.5</span></span>|
|<span data-ttu-id="45b24-114">Tipo</span><span class="sxs-lookup"><span data-stu-id="45b24-114">Type</span></span>|<span data-ttu-id="45b24-115">Tiempo de ejecución</span><span class="sxs-lookup"><span data-stu-id="45b24-115">Runtime</span></span>|

#### <a name="affected-apis"></a><span data-ttu-id="45b24-116">API afectadas</span><span class="sxs-lookup"><span data-stu-id="45b24-116">Affected APIs</span></span>

- <xref:System.Text.RegularExpressions.Regex.CompileToAssembly(System.Text.RegularExpressions.RegexCompilationInfo[],System.Reflection.AssemblyName)?displayProperty=nameWithType>
- <xref:System.Text.RegularExpressions.Regex.CompileToAssembly(System.Text.RegularExpressions.RegexCompilationInfo[],System.Reflection.AssemblyName,System.Reflection.Emit.CustomAttributeBuilder[])?displayProperty=nameWithType>
- <xref:System.Text.RegularExpressions.Regex.CompileToAssembly(System.Text.RegularExpressions.RegexCompilationInfo[],System.Reflection.AssemblyName,System.Reflection.Emit.CustomAttributeBuilder[],System.String)?displayProperty=nameWithType>

<!--

#### Affected APIs

- `M:System.Text.RegularExpressions.Regex.CompileToAssembly(System.Text.RegularExpressions.RegexCompilationInfo[],System.Reflection.AssemblyName)`
- `M:System.Text.RegularExpressions.Regex.CompileToAssembly(System.Text.RegularExpressions.RegexCompilationInfo[],System.Reflection.AssemblyName,System.Reflection.Emit.CustomAttributeBuilder[])`
- `M:System.Text.RegularExpressions.Regex.CompileToAssembly(System.Text.RegularExpressions.RegexCompilationInfo[],System.Reflection.AssemblyName,System.Reflection.Emit.CustomAttributeBuilder[],System.String)`

-->
