---
title: "Protección de servicios y clientes"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: message security [WCF]
ms.assetid: e681f3bd-0c09-4a58-b0e4-0ecbdf1aa6c7
caps.latest.revision: "13"
author: BrucePerlerMS
ms.author: bruceper
manager: mbaldwin
ms.openlocfilehash: ed37992b5488d33b9292bdd54eef47f9eb12f225
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="securing-services-and-clients"></a>Protección de servicios y clientes
La información de esta sección se centra en programar la seguridad en [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)]. Generalmente, esto incluye la selección de un enlace proporcionado por el sistema adecuado, el establecimiento de las propiedades del elemento de seguridad y, a continuación, el establecimiento de las propiedades de los comportamientos del servicio que rigen la recuperación de las credenciales utilizadas por el servicio o el cliente. Estas técnicas cubran los requisitos de seguridad de la mayoría de los usuarios para la mayoría de los escenarios, como se muestra en [escenarios comunes de seguridad](../../../../docs/framework/wcf/feature-details/common-security-scenarios.md). Si su escenario requiere más capacidades, primero vea [capacidades de seguridad con enlaces personalizados](../../../../docs/framework/wcf/feature-details/security-capabilities-with-custom-bindings.md); si no es evidente, una solución, consulte [extender seguridad](../../../../docs/framework/wcf/extending/extending-security.md). Si está creando (o interoperar con) un sistema que utiliza notificaciones completo, vea los temas de [autorización](../../../../docs/framework/wcf/feature-details/authorization-in-wcf.md).  
  
## <a name="in-this-section"></a>En esta sección  
 [Programar la seguridad WCF](../../../../docs/framework/wcf/feature-details/programming-wcf-security.md)  
 Información general del modelo de programación utilizado para proteger los mensajes.  
  
 [Información general sobre la seguridad de transporte](../../../../docs/framework/wcf/feature-details/transport-security-overview.md)  
 Información general de cómo proteger los mensajes en el nivel de transporte.  
  
 [Seguridad de mensajes](../../../../docs/framework/wcf/feature-details/message-security-in-wcf.md)  
 Resume las razones para utilizar la seguridad del nivel de mensaje en [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)].  
  
 [Sesiones seguras](../../../../docs/framework/wcf/feature-details/secure-sessions.md)  
 Una explicación de las consideraciones necesarias para proteger una sesión [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].  
  
 [Trabajar con certificados](../../../../docs/framework/wcf/feature-details/working-with-certificates.md)  
 Explicación de algunas de las tareas comunes necesarias para la utilización de los certificados X.509.  
  
## <a name="reference"></a>Referencia  
 <xref:System.ServiceModel>  
  
 <xref:System.ServiceModel.Channels>  
  
 <xref:System.ServiceModel.Security>  
  
## <a name="related-sections"></a>Secciones relacionadas  
 [Conceptos de seguridad](../../../../docs/framework/wcf/feature-details/security-concepts.md)  
  
 [Extensión de la seguridad](../../../../docs/framework/wcf/extending/extending-security.md)  
  
 [Escenarios comunes de seguridad](../../../../docs/framework/wcf/feature-details/common-security-scenarios.md)  
  
 [Enlaces y seguridad](../../../../docs/framework/wcf/feature-details/bindings-and-security.md)  
  
 [Capacidades de seguridad con enlaces personalizados](../../../../docs/framework/wcf/feature-details/security-capabilities-with-custom-bindings.md)  
  
 [Extensión de la seguridad](../../../../docs/framework/wcf/extending/extending-security.md)  
  
 [Autorización](../../../../docs/framework/wcf/feature-details/authorization-in-wcf.md)  
  
## <a name="see-also"></a>Vea también  
 [Programación básica de WCF](../../../../docs/framework/wcf/basic-wcf-programming.md)  
 [Modelo de seguridad de Windows Server AppFabric](http://go.microsoft.com/fwlink/?LinkID=201279&clcid=0x409)
