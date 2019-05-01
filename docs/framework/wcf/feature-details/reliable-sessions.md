---
title: Sesiones de confianza
ms.date: 03/30/2017
f1_keywords:
- Windows Communication Foundation, sessions and instances
- WCF, sessions and instances
- sessions and instances [WCF]
helpviewer_keywords:
- instances [WCF]
- sessions [WCF]
ms.assetid: 143951b3-3aa0-4540-b4b7-d33e77e874a1
ms.openlocfilehash: 9a2cd06c4c5a73d9fb5c4c7f09632e10c3eb0d87
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61991164"
---
# <a name="reliable-sessions"></a>Sesiones de confianza

En esta sección se describe qué un Windows Communication Foundation (WCF) sesión confiable es lo se usa, cómo y cuándo usar uno, qué configuraciones de enlace admiten e indicaciones sobre procedimientos recomendados. La siguiente tabla resume los detalles sobre los puntos esenciales y temas relacionados de esta sección.

La sesión confiable WCF proporciona características que garantiza que los mensajes enviados entre puntos de conexión se transfieren a través de intermediarios de transporte o SOAP y se entregan una sola vez y, opcionalmente, en el mismo orden en que se enviaron.

Para utilizar una sesión confiable con una aplicación de WCF, use uno de los enlaces proporcionados por el sistema en WCF que admiten una sesión confiable de manera predeterminada o como una opción o crear su propio enlace personalizado que admita la sesión.

## <a name="in-this-section"></a>En esta sección

[Información general de las sesiones confiables](../../../../docs/framework/wcf/feature-details/reliable-sessions-overview.md) describe las sesiones confiables, cuándo utilizarlas, los distintos enlaces que admiten sesiones confiables, y cómo funcionan.

[Cómo: Exchange mensajes dentro de una sesión confiable](../../../../docs/framework/wcf/feature-details/how-to-exchange-messages-within-a-reliable-session.md) se describe cómo crear una sesión confiable a través de HTTP mediante un enlace personalizado especificado en la configuración.

[Cómo: Proteger los mensajes dentro de sesiones confiables](../../../../docs/framework/wcf/feature-details/how-to-secure-messages-within-reliable-sessions.md) se describe cómo proteger una sesión confiable.

[Cómo: Creación de un enlace de la sesión confiable de personalizado con HTTPS](../../../../docs/framework/wcf/feature-details/how-to-create-a-custom-reliable-session-binding-with-https.md) se describe cómo crear una sesión confiable a través de HTTPS.

[Procedimientos recomendados para las sesiones confiables](../../../../docs/framework/wcf/feature-details/best-practices-for-reliable-sessions.md) se describen algunos de los procedimientos recomendados relacionados con el uso de una sesión confiable.

## <a name="reference"></a>Referencia

<xref:System.ServiceModel.ReliableSession>

## <a name="see-also"></a>Vea también

- [Colas y sesiones de confianza](../../../../docs/framework/wcf/feature-details/queues-and-reliable-sessions.md)
- [Sesiones, creación de instancias y simultaneidad](../../../../docs/framework/wcf/feature-details/sessions-instancing-and-concurrency.md)
