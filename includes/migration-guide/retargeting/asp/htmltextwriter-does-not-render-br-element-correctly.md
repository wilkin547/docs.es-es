---
ms.openlocfilehash: 8f03e5166e7f1f598e9bba7fb8c550809f287b82
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/01/2020
ms.locfileid: "85615743"
---
### <a name="htmltextwriter-does-not-render-br-element-correctly"></a>HtmlTextWriter no representa el elemento `<br/>` de forma correcta

#### <a name="details"></a>Detalles

A partir de .NET Framework 4.6, al llamar a <xref:System.Web.UI.HtmlTextWriter.RenderBeginTag(System.String)> y <xref:System.Web.UI.HtmlTextWriter.RenderEndTag> con un elemento `<BR />` solo insertará correctamente un `<BR />` (en lugar de dos).

#### <a name="suggestion"></a>Sugerencia

Si alguna aplicación dependía de la etiqueta `<BR />` adicional, debería llamarse a <xref:System.Web.UI.HtmlTextWriter.RenderBeginTag(System.String)> una segunda vez. Tenga en cuenta que este cambio de comportamiento solo afecta a las aplicaciones que tengan como destino .NET Framework 4.6 o una versión posterior, por lo que otra opción es seleccionar como destino una versión anterior de .NET Framework para conseguir el comportamiento anterior.

| NOMBRE    | Valor       |
|:--------|:------------|
| Ámbito   | Borde        |
| Versión | 4.6         |
| Tipo    | Redestinación |

#### <a name="affected-apis"></a>API afectadas

- <xref:System.Web.UI.HtmlTextWriter.RenderBeginTag(System.String)?displayProperty=nameWithType>
- <xref:System.Web.UI.HtmlTextWriter.RenderBeginTag(System.Web.UI.HtmlTextWriterTag)?displayProperty=nameWithType>
