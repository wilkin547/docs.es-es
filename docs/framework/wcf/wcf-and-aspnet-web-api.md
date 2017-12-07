---
title: WCF y ASP.NET Web API
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 08ceded3-fd9a-4467-9715-c4cbd9c7228e
caps.latest.revision: "2"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 932db4ef12666d20ba497cc8f6d78b43c7670373
ms.sourcegitcommit: 5126483ef09c487296801bbac368dd8a55a6b709
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/07/2017
---
# <a name="wcf-and-aspnet-web-api"></a>WCF y ASP.NET Web API
WCF es el modelo de programación unificado de Microsoft para compilar aplicaciones orientadas a servicios. Permite a los desarrolladores compilar soluciones de transacción seguras y confiables que se integran en diferentes plataformas y que interactúan con las inversiones existentes. [ASP.NET Web API](http://www.asp.net/web-api) es un marco que facilita la creación de servicios HTTP que llegan a una amplia gama de clientes, incluidos los exploradores y dispositivos móviles. ASP.NET Web API es una plataforma ideal para compilar aplicaciones de RESTful en .NET Framework. En este tema se incluyen indicaciones para ayudarle a decidir qué tecnología se adapta mejor a sus necesidades.  
  
## <a name="choosing-which-technology-to-use"></a>Elegir la tecnología que se va a usar  
 En la tabla siguiente se describen las características principales de cada tecnología.  
  
|WCF|ASP.NET Web API|  
|---------|---------------------|  
|Habilita los servicios de compilación que admiten varios protocolos de transporte (HTTP, TCP, UDP y transportes personalizados) y permite cambiar entre ellos.|Sólo HTTP. Modelo de programación de primera clase para HTTP. Más adecuado para el acceso de varios exploradores, dispositivos móviles, habilitar etcetera alcanzar todo.|  
|Habilita servicios de compilación que admiten varias codificaciones (texto, MTOM y binario) del mismo tipo de mensaje y permite cambiar entre ellas.|Permite compilar API web que admiten una amplia variedad de tipos de medios, incluso XML, JSON, etc.|  
|Admite servicios de compilación con estándares WS-* como mensajería confiable, transacciones o seguridad de mensajes.|Usa el protocolo básico y formatos como HTTP, WebSockets, SSL, JSON y XML. No hay compatibilidad para protocolos de nivel superior como la mensajería confiable o las transacciones.|  
|Admite patrones de intercambio de mensajes de solicitud-respuesta, unidireccionales y dúplex.|HTTP es solicitud/respuesta, pero otros patrones que pueden ser compatibles mediante [SignalR](https://github.com/SignalR/SignalR) e integración de WebSockets.|  
|Los servicios WCF SOAP se pueden describir en WSDL lo que permite que las herramientas automatizadas generen servidores proxy de cliente incluso para los servicios con esquemas complejos.|Existen varias formar de describir una API web, desde páginas de ayuda HTML generadas automáticamente que describen fragmentos de código hasta metadatos estructurados para API integradas OData.|  
|Se incluye en .NET Framework.|Se incluye en .NET framework pero es código abierto y también está disponible fuera de banda como una descarga independiente.|  
  
 Use WCF para crear servicios web confiables y seguros que sean accesibles a través de una serie de transportes. Use ASP.NET Web API para crear servicios basados en HTTP que sean accesibles desde una gran variedad de clientes. Use ASP.NET Web API si crea y diseña nuevos servicios de tipo REST. Aunque WCF proporciona cierta compatibilidad para escribir servicios de tipo REST, la compatibilidad para REST en ASP.NET Web API es más completa y todas las futuras mejoras de las características de REST se llevarán a cabo en ASP.NET Web API. Si ya tiene un servicio WCF y quiere exponer extremos de REST adicionales, use WCF y <xref:System.ServiceModel.WebHttpBinding>.  
  
## <a name="see-also"></a>Vea también  
 [¿Qué es Windows Communication Foundation?](../../../docs/framework/wcf/whats-wcf.md)  
 [Conceptos básicos de Windows Communication Foundation](../../../docs/framework/wcf/fundamental-concepts.md)  
