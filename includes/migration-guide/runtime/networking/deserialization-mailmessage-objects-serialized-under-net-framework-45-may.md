---
ms.openlocfilehash: ad953a1562db407c04d7860c60eb5964fe6fe2ca
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/01/2020
ms.locfileid: "85620638"
---
### <a name="deserialization-of-mailmessage-objects-serialized-under-the-net-framework-45-may-fail"></a>Se puede producir un error en las deserialización de los objetos MailMessage serializados en .NET Framework 4.5

#### <a name="details"></a>Detalles

A partir de .NET Framework 4.5, los objetos <xref:System.Web.Mail.MailMessage> pueden incluir caracteres que no sean ASCII. En .NET Framework 4, solo se admiten caracteres ASCII. Los objetos <xref:System.Web.Mail.MailMessage> que contienen caracteres que no son ASCII y que están serializados en .NET Framework 4.5 o una versión posterior no se pueden deserializar en .NET Framework 4.

#### <a name="suggestion"></a>Sugerencia

Asegúrese de que el código proporciona control de excepciones al deserializar un objeto <xref:System.Web.Mail.MailMessage>.

| NOMBRE    | Valor       |
|:--------|:------------|
| Ámbito   |Secundaria|
|Versión|4.5|
|Tipo|Tiempo de ejecución

#### <a name="affected-apis"></a>API afectadas

-<xref:System.Web.Mail.MailMessage?displayProperty=nameWithType></li></ul>|
