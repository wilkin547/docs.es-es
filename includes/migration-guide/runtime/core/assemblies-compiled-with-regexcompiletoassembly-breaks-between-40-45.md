---
ms.openlocfilehash: 0bd90b3d479a7e0897aaf78b7718ae156a4a239f
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/01/2020
ms.locfileid: "85620550"
---
### <a name="assemblies-compiled-with-regexcompiletoassembly-breaks-between-40-and-45"></a>Los ensamblados compilados con Regex.CompileToAssembly se interrumpen entre las versiones 4.0 y 4.5

#### <a name="details"></a>Detalles

Si un ensamblado de expresiones regulares compiladas se crea con .NET Framework 4.5 pero tiene como destino .NET Framework 4, se inicia una excepción al intentar usar una de las expresiones regulares de ese ensamblado en un sistema con .NET Framework 4 instalado.

#### <a name="suggestion"></a>Sugerencia

Para evitar este problema, realice una de las acciones siguientes:<ul><li>Compile el ensamblado que contiene las expresiones regulares con .NET Framework 4.</li><li>Use una expresión regular interpretada.</li></ul>

| NOMBRE    | Valor       |
|:--------|:------------|
| Ámbito   |Secundaria|
|Versión|4.5|
|Tipo|Tiempo de ejecución

#### <a name="affected-apis"></a>API afectadas

-<xref:System.Text.RegularExpressions.Regex.CompileToAssembly(System.Text.RegularExpressions.RegexCompilationInfo[],System.Reflection.AssemblyName)?displayProperty=nameWithType></li><li><xref:System.Text.RegularExpressions.Regex.CompileToAssembly(System.Text.RegularExpressions.RegexCompilationInfo[],System.Reflection.AssemblyName,System.Reflection.Emit.CustomAttributeBuilder[])?displayProperty=nameWithType></li><li><xref:System.Text.RegularExpressions.Regex.CompileToAssembly(System.Text.RegularExpressions.RegexCompilationInfo[],System.Reflection.AssemblyName,System.Reflection.Emit.CustomAttributeBuilder[],System.String)?displayProperty=nameWithType></li></ul>|
