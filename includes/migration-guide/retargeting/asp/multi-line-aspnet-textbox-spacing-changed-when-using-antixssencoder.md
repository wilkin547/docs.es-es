---
ms.openlocfilehash: 53860bb867522503c5cb9bd35e25fadd00a116a2
ms.sourcegitcommit: 97405ed212f69b0a32faa66a5d5fae7e76628b68
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/01/2020
ms.locfileid: "91609171"
---
### <a name="multi-line-aspnet-textbox-spacing-changed-when-using-antixssencoder"></a>Cambio de interlineado de los cuadros de texto multilínea de ASP.NET al usar AntiXSSEncoder

#### <a name="details"></a>Detalles

En .NET Framework 4.0, se introdujeron líneas adicionales entre las líneas de un cuadro de texto multilínea en postback si se usaba el elemento <xref:System.Web.Security.AntiXss.AntiXssEncoder?displayProperty=fullName>. En .NET Framework 4.5 no se incluyen estos saltos de línea adicionales, pero únicamente si la aplicación web tiene como destino .NET Framework 4.5.

#### <a name="suggestion"></a>Sugerencia

Tenga en cuenta que las aplicaciones web de la versión 4.0 redestinadas a .NET Framework 4.5 pueden tener cuadros de texto multilínea mejorados para dejar de introducir saltos de línea adicionales. Si este no es el comportamiento deseado, la aplicación puede tener el anterior cuando se ejecuta en .NET Framework 4.5 si se establece .NET Framework 4.0 como destino.

| NOMBRE    | Valor       |
|:--------|:------------|
| Ámbito   | Secundaria       |
| Versión | 4.5         |
| Tipo    | Redestinación |
