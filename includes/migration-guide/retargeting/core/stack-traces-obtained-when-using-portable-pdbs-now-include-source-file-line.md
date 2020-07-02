---
ms.openlocfilehash: c7500550cd9714a9788a7dea68af04823f000f7f
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/01/2020
ms.locfileid: "85614799"
---
### <a name="stack-traces-obtained-when-using-portable-pdbs-now-include-source-file-and-line-information-if-requested"></a>Los seguimientos de la pila obtenidos al usar archivos PDB portátiles ahora incluyen información del archivo y la línea de origen si se solicita

#### <a name="details"></a>Detalles

A partir de .NET Framework 4.7.2, los seguimientos de la pila obtenidos al usar archivos PDB portátiles incluyen información del archivo y la línea de origen cuando se solicita. En las versiones anteriores a .NET Framework 4.7.2, la información del archivo y la línea de origen no estaba disponible al usar archivos PDB portátiles incluso si se solicitaba de forma explícita.

#### <a name="suggestion"></a>Sugerencia

Para las aplicaciones que tienen como destino .NET Framework 4.7.2, se puede rechazar la información del archivo y la línea de origen cuando se usan archivos PDB portátiles si no es adecuada mediante la adición de lo siguiente a la sección `<runtime>` del archivo `app.config`:

```xml
<runtime>
  <AppContextSwitchOverrides value="Switch.System.Diagnostics.IgnorePortablePDBsInStackTraces=true" />
</runtime>
```

Para las aplicaciones que tienen como destino versiones anteriores de .NET Framework, pero que se ejecutan en .NET Framework 4.7.2 o versiones posteriores, se puede incluir la información del archivo y la línea de origen cuando se usan archivos PDB portátiles si se agrega lo siguiente a la sección `<runtime>` del archivo `app.config`:

```xml
<runtime>
  <AppContextSwitchOverrides value="Switch.System.Diagnostics.IgnorePortablePDBsInStackTraces=false" />
</runtime>
```

| NOMBRE    | Valor       |
|:--------|:------------|
| Ámbito   | Borde        |
| Versión | 4.7.2       |
| Tipo    | Redestinación |

#### <a name="affected-apis"></a>API afectadas

- <xref:System.Diagnostics.StackTrace.%23ctor(System.Boolean)>
- <xref:System.Diagnostics.StackTrace.%23ctor(System.Exception,System.Boolean)>
- <xref:System.Diagnostics.StackTrace.%23ctor(System.Exception,System.Int32,System.Boolean)>
