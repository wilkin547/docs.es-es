---
ms.openlocfilehash: 26facb645de175d7ef0432394fc2b84f59e8437d
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/05/2020
ms.locfileid: "89497326"
---
### <a name="error-codes-for-maxrequestlength-or-maxreceivedmessagesize-are-different"></a>Los códigos de error para maxRequestLength o maxReceivedMessageSize son diferentes

#### <a name="details"></a>Detalles

Los mensajes de servicios web de WCF hospedados en Internet Information Services (IIS) o Servidor de desarrollo de ASP.NET que superan maxRequestLength (en ASP.NET) o maxReceivedMessageSize (en WCF) tienen otro código de error. El código de estado HTTP ha cambiado de 400 (Solicitud incorrecta) a 413 (Entidad de solicitud demasiado grande), y los mensajes que superan el valor maxRequestLength o maxReceivedMessageSize inician una excepción <xref:System.ServiceModel.ProtocolException?displayProperty=fullName>. Esto incluye los casos en los que el modo de transferencia es Streamed.

#### <a name="suggestion"></a>Sugerencia

Este cambio facilita la depuración en casos donde la longitud del mensaje supera los límites permitidos por ASP.NET o WCF. Debe modificar cualquier código que realice el procesamiento en función de un código de estado HTTP 400.

| NOMBRE    | Valor       |
|:--------|:------------|
| Ámbito   |Borde|
|Versión|4.5|
|Tipo|Tiempo de ejecución|

#### <a name="affected-apis"></a>API afectadas

No detectable a través del análisis de la API.

<!--

#### Affected APIs

Not detectable via API analysis.

-->
