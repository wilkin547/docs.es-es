---
title: WCF y ASP.NET Web API
ms.date: 03/30/2017
ms.assetid: 08ceded3-fd9a-4467-9715-c4cbd9c7228e
ms.openlocfilehash: e058b2ea5e9188c365c679ae46c4d7c9de45e4b9
ms.sourcegitcommit: 700ea803fb06c5ce98de017c7f76463ba33ff4a9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/19/2020
ms.locfileid: "77452570"
---
# <a name="wcf-and-aspnet-web-api"></a>WCF y ASP.NET Web API
WCF es el modelo de programación unificado de Microsoft para compilar aplicaciones orientadas a servicios. Permite a los desarrolladores compilar soluciones de transacción seguras y confiables que se integran en diferentes plataformas y que interactúan con las inversiones existentes. [ASP.net web API](https://www.asp.net/web-api) es un marco que facilita la creación de servicios http que llegan a una amplia gama de clientes, incluidos exploradores y dispositivos móviles. ASP.NET Web API es una plataforma ideal para compilar aplicaciones de RESTful en .NET Framework. En este tema se incluyen indicaciones para ayudarle a decidir qué tecnología se adapta mejor a sus necesidades.  
  
## <a name="choosing-which-technology-to-use"></a>Elegir la tecnología que se va a usar  
 En la tabla siguiente se describen las características principales de cada tecnología.  
  
|WCF|ASP.NET Web API|  
|---------|---------------------|  
|Habilita los servicios de compilación que admiten varios protocolos de transporte (HTTP, TCP, UDP y transportes personalizados) y permite cambiar entre ellos.|Sólo HTTP. Modelo de programación de primera clase para HTTP. Más adecuado para el acceso desde varios exploradores, dispositivos móviles, etc., lo que permite un alcance amplio.|  
|Habilita servicios de compilación que admiten varias codificaciones (texto, MTOM y binario) del mismo tipo de mensaje y permite cambiar entre ellas.|Permite compilar API web que admiten una amplia variedad de tipos de medios, incluso XML, JSON, etc.|  
|Admite servicios de compilación con estándares WS-* como mensajería confiable, transacciones o seguridad de mensajes.|Usa el protocolo básico y formatos como HTTP, WebSockets, SSL, JSON y XML. No hay compatibilidad para protocolos de nivel superior como la mensajería confiable o las transacciones.|  
|Admite patrones de intercambio de mensajes de solicitud-respuesta, unidireccionales y dúplex.|HTTP es solicitud/respuesta, pero se pueden admitir patrones adicionales mediante la integración de [signalr](https://github.com/SignalR/SignalR) y WebSockets.|  
|Los servicios WCF SOAP se pueden describir en WSDL lo que permite que las herramientas automatizadas generen servidores proxy de cliente incluso para los servicios con esquemas complejos.|Existen varias formar de describir una API web, desde páginas de ayuda HTML generadas automáticamente que describen fragmentos de código hasta metadatos estructurados para API integradas OData.|  
|Se suministra con el .NET Framework.|Se suministra con .NET Framework pero es de código abierto y también está disponible fuera de banda como descarga independiente.|  
  
 Use WCF para crear servicios Web confiables y seguros a los que se pueda tener acceso a través de diversos transportes. Use ASP.NET Web API para crear servicios basados en HTTP que sean accesibles desde una gran variedad de clientes. Use ASP.NET Web API si crea y diseña nuevos servicios de tipo REST. Aunque WCF proporciona cierta compatibilidad para escribir servicios de tipo REST, la compatibilidad para REST en ASP.NET Web API es más completa y todas las futuras mejoras de las características de REST se llevarán a cabo en ASP.NET Web API. Si ya tiene un servicio WCF y quiere exponer extremos de REST adicionales, use WCF y <xref:System.ServiceModel.WebHttpBinding>.  
  
## <a name="see-also"></a>Consulte también

- [¿Qué es Windows Communication Foundation?](whats-wcf.md)
- [Conceptos básicos de Windows Communication Foundation](fundamental-concepts.md)
