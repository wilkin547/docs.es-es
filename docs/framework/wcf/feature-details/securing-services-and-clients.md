---
description: 'Más información sobre: protección de servicios y clientes'
title: Protección de servicios y clientes
ms.date: 03/30/2017
helpviewer_keywords:
- message security [WCF]
ms.assetid: e681f3bd-0c09-4a58-b0e4-0ecbdf1aa6c7
ms.openlocfilehash: ff947e8bf975fd3fb3c6513ee0bf49bb21a951dd
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99632638"
---
# <a name="securing-services-and-clients"></a>Protección de servicios y clientes

La información de esta sección se centra en la programación de la seguridad en Windows Communication Foundation (WCF). Generalmente, esto incluye la selección de un enlace proporcionado por el sistema adecuado, el establecimiento de las propiedades del elemento de seguridad y, a continuación, el establecimiento de las propiedades de los comportamientos del servicio que rigen la recuperación de las credenciales utilizadas por el servicio o el cliente. Estas técnicas cubren los requisitos de seguridad de la mayoría de los usuarios para la mayoría de los escenarios, tal como se muestra en [escenarios de seguridad comunes](common-security-scenarios.md). Si su escenario requiere más capacidades, consulte en primer lugar las [capacidades de seguridad con enlaces personalizados](security-capabilities-with-custom-bindings.md). Si una solución no es aparente, vea [ampliar la seguridad](../extending/extending-security.md). Si va a crear (o interoperar con) un sistema que utiliza notificaciones enriquecidas, consulte los temas de [autorización](authorization-in-wcf.md).  
  
## <a name="in-this-section"></a>En esta sección  

 [Programación de la seguridad de WCF](programming-wcf-security.md)  
 Información general del modelo de programación utilizado para proteger los mensajes.  
  
 [Información general de la seguridad del transporte](transport-security-overview.md)  
 Información general de cómo proteger los mensajes en el nivel de transporte.  
  
 [Seguridad de los mensajes](message-security-in-wcf.md)  
 Resume las razones para utilizar la seguridad de nivel de mensaje en Windows Communication Foundation (WCF).  
  
 [Sesiones seguras](secure-sessions.md)  
 Explicación de las consideraciones necesarias para proteger una sesión de WCF.  
  
 [Trabajar con certificados](working-with-certificates.md)  
 Explicación de algunas de las tareas comunes necesarias para la utilización de los certificados X.509.  
  
## <a name="reference"></a>Referencia  

 <xref:System.ServiceModel>  
  
 <xref:System.ServiceModel.Channels>  
  
 <xref:System.ServiceModel.Security>  
  
## <a name="related-sections"></a>Secciones relacionadas  

 [Conceptos de seguridad](security-concepts.md)  
  
 [Extensión de la seguridad](../extending/extending-security.md)  
  
 [Escenarios de seguridad comunes](common-security-scenarios.md)  
  
 [Enlaces y seguridad](bindings-and-security.md)  
  
 [Capacidades de seguridad con enlaces personalizados](security-capabilities-with-custom-bindings.md)  
  
 [Extensión de la seguridad](../extending/extending-security.md)  
  
 [Autorización](authorization-in-wcf.md)  
  
## <a name="see-also"></a>Vea también

- [Programación básica de WCF](../basic-wcf-programming.md)
- [Modelo de seguridad para Windows Server App Fabric](/previous-versions/appfabric/ee677202(v=azure.10))
