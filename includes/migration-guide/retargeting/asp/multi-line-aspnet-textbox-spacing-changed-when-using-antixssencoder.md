---
ms.openlocfilehash: 150b98255b3075a8fe8cad60ce234206b788a5f5
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/01/2020
ms.locfileid: "85617269"
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
