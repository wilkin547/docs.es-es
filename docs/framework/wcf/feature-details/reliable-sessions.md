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
ms.openlocfilehash: 1d87f6f4d94763dc8f6ac7e929c22b17940097ca
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54735430"
---
# <a name="reliable-sessions"></a>Sesiones de confianza

En esta sección se describe qué un Windows Communication Foundation (WCF) sesión confiable es lo se usa, cómo y cuándo usar uno, qué configuraciones de enlace admiten e indicaciones sobre procedimientos recomendados. La siguiente tabla resume los detalles sobre los puntos esenciales y temas relacionados de esta sección.

La sesión confiable WCF proporciona funciones que garantiza que los mensajes enviados entre puntos de conexión se transfieren a través de intermediarios de transporte o SOAP y se entregan una sola vez y, opcionalmente, en el mismo orden en que se enviaron.

Para utilizar una sesión confiable con una aplicación de WCF, use uno de los enlaces proporcionados por el sistema en WCF que admiten una sesión confiable de manera predeterminada o como una opción o crear su propio enlace personalizado que admita la sesión.

## <a name="in-this-section"></a>En esta sección

[Información general de las sesiones confiables](../../../../docs/framework/wcf/feature-details/reliable-sessions-overview.md)   
Describe las sesiones confiables, cuándo utilizarlas, los diferentes enlaces que admiten las sesiones confiables y cómo funcionan.

[Cómo: Mensajes de Exchange dentro de una sesión confiable](../../../../docs/framework/wcf/feature-details/how-to-exchange-messages-within-a-reliable-session.md)   
Describe cómo crear una sesión confiable sobre HTTP utilizando un enlace personalizado especificado en la configuración.

[Cómo: Proteger los mensajes dentro de sesiones confiables](../../../../docs/framework/wcf/feature-details/how-to-secure-messages-within-reliable-sessions.md)   
Describe cómo proteger una sesión confiable.

[Cómo: Creación de un enlace personalizado de sesión confiable con HTTPS](../../../../docs/framework/wcf/feature-details/how-to-create-a-custom-reliable-session-binding-with-https.md)   
Describe cómo crear una sesión confiable sobre HTTPS.

[Procedimientos recomendados para las sesiones confiables](../../../../docs/framework/wcf/feature-details/best-practices-for-reliable-sessions.md)   
Describe algunos de los procedimientos recomendados asociados al uso de una sesión confiable.

## <a name="reference"></a>Referencia

<xref:System.ServiceModel.ReliableSession>

## <a name="see-also"></a>Vea también

- [Colas y sesiones de confianza](../../../../docs/framework/wcf/feature-details/queues-and-reliable-sessions.md)
- [Sesiones, creación de instancias y simultaneidad](../../../../docs/framework/wcf/feature-details/sessions-instancing-and-concurrency.md)
