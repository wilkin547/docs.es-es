---
title: WCF y ASP.NET Web API
ms.date: 03/30/2017
ms.assetid: 08ceded3-fd9a-4467-9715-c4cbd9c7228e
ms.openlocfilehash: d805c09bef45932ba006a213343429ae7c9303df
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61791274"
---
# <a name="wcf-and-aspnet-web-api"></a>WCF y ASP.NET Web API
WCF es el modelo de programación unificado de Microsoft para compilar aplicaciones orientadas a servicios. Permite a los desarrolladores compilar soluciones de transacción seguras y confiables que se integran en diferentes plataformas y que interactúan con las inversiones existentes. [ASP.NET Web API](https://www.asp.net/web-api) es un marco que facilita la creación de servicios HTTP que lleguen a una amplia gama de clientes, incluidos los exploradores y dispositivos móviles. ASP.NET Web API es una plataforma ideal para compilar aplicaciones de RESTful en .NET Framework. En este tema se incluyen indicaciones para ayudarle a decidir qué tecnología se adapta mejor a sus necesidades.  
  
## <a name="choosing-which-technology-to-use"></a>Elegir la tecnología que se va a usar  
 En la tabla siguiente se describen las características principales de cada tecnología.  
  
|WCF|ASP.NET Web API|  
|---------|---------------------|  
|Habilita los servicios de compilación que admiten varios protocolos de transporte (HTTP, TCP, UDP y transportes personalizados) y permite cambiar entre ellos.|Sólo HTTP. Modelo de programación de primera clase para HTTP. Más adecuado para el acceso desde varios exploradores, dispositivos móviles, habilitar etcetera amplio alcance.|  
|Habilita servicios de compilación que admiten varias codificaciones (texto, MTOM y binario) del mismo tipo de mensaje y permite cambiar entre ellas.|Permite compilar API web que admiten una amplia variedad de tipos de medios, incluso XML, JSON, etc.|  
|Admite servicios de compilación con estándares WS-* como mensajería confiable, transacciones o seguridad de mensajes.|Usa el protocolo básico y formatos como HTTP, WebSockets, SSL, JSON y XML. No hay compatibilidad para protocolos de nivel superior como la mensajería confiable o las transacciones.|  
|Admite patrones de intercambio de mensajes de solicitud-respuesta, unidireccionales y dúplex.|HTTP es solicitud/respuesta pero patrones adicionales se pueden admitir mediante [SignalR](https://github.com/SignalR/SignalR) e integración de WebSockets.|  
|Los servicios WCF SOAP se pueden describir en WSDL lo que permite que las herramientas automatizadas generen servidores proxy de cliente incluso para los servicios con esquemas complejos.|Existen varias formar de describir una API web, desde páginas de ayuda HTML generadas automáticamente que describen fragmentos de código hasta metadatos estructurados para API integradas OData.|  
|Se incluye en .NET Framework.|Se incluye en .NET framework pero es código abierto y también está disponible fuera de banda como una descarga independiente.|  
  
 Usar WCF para crear servicios web confiables y seguros que son accesibles a través de una variedad de transportes. Use ASP.NET Web API para crear servicios basados en HTTP que sean accesibles desde una gran variedad de clientes. Use ASP.NET Web API si crea y diseña nuevos servicios de tipo REST. Aunque WCF proporciona cierta compatibilidad para escribir servicios de tipo REST, la compatibilidad para REST en ASP.NET Web API es más completa y todas las futuras mejoras de las características de REST se llevarán a cabo en ASP.NET Web API. Si ya tiene un servicio WCF y quiere exponer extremos de REST adicionales, use WCF y <xref:System.ServiceModel.WebHttpBinding>.  
  
## <a name="see-also"></a>Vea también

- [¿Qué es Windows Communication Foundation?](../../../docs/framework/wcf/whats-wcf.md)
- [Conceptos básicos de Windows Communication Foundation](../../../docs/framework/wcf/fundamental-concepts.md)
