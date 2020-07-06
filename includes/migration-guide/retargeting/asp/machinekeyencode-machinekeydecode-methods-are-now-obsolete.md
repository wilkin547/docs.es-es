---
ms.openlocfilehash: e9d34465970287ed94c0f0373ee4ae94d55aa1ff
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/01/2020
ms.locfileid: "85617266"
---
### <a name="machinekeyencode-and-machinekeydecode-methods-are-now-obsolete"></a>Los métodos MachineKey.Encode y MachineKey.Decode ahora están obsoletos

#### <a name="details"></a>Detalles

Estos métodos están obsoletos. La compilación del código que llama a estos métodos genera una advertencia del compilador.

#### <a name="suggestion"></a>Sugerencia

Las alternativas recomendadas son <xref:System.Web.Security.MachineKey.Protect(System.Byte[],System.String[])> y <xref:System.Web.Security.MachineKey.Unprotect(System.Byte[],System.String[])>. Como alternativa, se pueden suprimir las advertencias de compilación o usar un compilador anterior para evitarlas. Las API siguen siendo compatibles.

| NOMBRE    | Valor       |
|:--------|:------------|
| Ámbito   | Secundaria       |
| Versión | 4.5         |
| Tipo    | Redestinación |

#### <a name="affected-apis"></a>API afectadas

- <xref:System.Web.Security.MachineKey.Encode(System.Byte[],System.Web.Security.MachineKeyProtection)?displayProperty=nameWithType>
- <xref:System.Web.Security.MachineKey.Decode(System.String,System.Web.Security.MachineKeyProtection)?displayProperty=nameWithType>
