---
ms.openlocfilehash: 9b184f54650d2efb31ec66f443198b19ceaeb5f3
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/01/2020
ms.locfileid: "85614704"
---
### <a name="applicationfiltermessage-no-longer-throws-for-re-entrant-implementations-of-imessagefilterprefiltermessage"></a>Ya no se inicia Application.FilterMessage para las implementaciones reentrantes de IMessageFilter.PreFilterMessage

#### <a name="details"></a>Detalles

Antes de .NET Framework 4.6.1, la llamada a <xref:System.Windows.Forms.Application.FilterMessage(System.Windows.Forms.Message@)> con un <xref:System.Windows.Forms.IMessageFilter.PreFilterMessage(System.Windows.Forms.Message@)> que llamaba a <xref:System.Windows.Forms.Application.AddMessageFilter(System.Windows.Forms.IMessageFilter)?displayProperty=fullName> o <xref:System.Windows.Forms.Application.RemoveMessageFilter(System.Windows.Forms.IMessageFilter)?displayProperty=fullName> (mientras también se llamaba a <xref:System.Windows.Forms.Application.DoEvents>) iniciaría una excepción <xref:System.IndexOutOfRangeException?displayProperty=fullName>.<p/>A partir de las aplicaciones que tengan como destino .NET Framework 4.6.1, esta excepción ya no se inicia y es posible usar los filtros reentrantes como se indica anteriormente.

#### <a name="suggestion"></a>Sugerencia

Tenga en cuenta que <xref:System.Windows.Forms.Application.FilterMessage(System.Windows.Forms.Message@)> ya no se iniciará para el comportamiento de <xref:System.Windows.Forms.IMessageFilter.PreFilterMessage(System.Windows.Forms.Message@)> reentrantes descrito anteriormente. Esto solo afecta a las aplicaciones destinadas a .NET Framework 4.6.1. Es posible desactivar este cambio en las aplicaciones destinadas a .NET Framework 4.6.1 (o activarlo en las que tengan como destino versiones anteriores de .NET Framework) mediante el modificador de compatibilidad [DontSupportReentrantFilterMessage](~/docs/framework/migration-guide/mitigation-custom-imessagefilter-prefiltermessage-implementations.md#mitigation).

| NOMBRE          | Valor       |
|:--------------|:------------|
| Ámbito         | Borde        |
| Versión       | 4.6.1       |
| Tipo          | Redestinación |

#### <a name="affected-apis"></a>API afectadas

- <xref:System.Windows.Forms.Application.FilterMessage(System.Windows.Forms.Message@)?displayProperty=nameWithType>
