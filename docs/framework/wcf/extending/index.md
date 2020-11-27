---
title: Extensión de WCF
ms.date: 03/30/2017
helpviewer_keywords:
- WCF, extensibility
- extensibility [WCF]
- Windows Communication Foundation, extensibility
ms.assetid: c145e2f6-f402-41f5-8b5a-eee03978737b
ms.openlocfilehash: b82dd4fb6a5b41a0160df8680fb1ba65d9a5bd33
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96254602"
---
# <a name="extending-wcf"></a>Extensión de WCF

Windows Communication Foundation (WCF) permite modificar y extender los componentes en tiempo de ejecución para controlar y ampliar con precisión las aplicaciones basadas en servicio. Los temas de esta sección hacen profundizan en la arquitectura de la extensibilidad. Para obtener más información sobre la programación básica, vea [programación básica de WCF](../basic-wcf-programming.md).  
  
## <a name="in-this-section"></a>En esta sección  

 [Extensión de ServiceHost y la capa de modelos de servicios](extending-servicehost-and-the-service-model-layer.md)  
 El nivel de modelo de servicio es responsable de extraer los mensajes entrantes de los canales subyacentes, de modo que los traduce en código de aplicación en las invocaciones de método y devuelve los resultados al agente de llamada.  Las extensiones de modelo de servicio modifican o implementan la ejecución o comportamiento de la comunicación y características implicadas en la funcionalidad del distribuidor, comportamientos personalizados, interceptación de mensaje y parámetro, y otra funcionalidad de extensibilidad.  
  
 [Extensión de enlaces](extending-bindings.md)  
 Los enlaces son los objetos que describen los datos de comunicación exigidos para conectar a un punto de conexión. Las extensiones de enlace o enlaces personalizados implementan la funcionalidad de la comunicación personalizada exigida para admitir las características de la aplicación.  
  
 [Extensión de la capa de canales](extending-the-channel-layer.md)  
 El nivel del canal se encuentra bajo el nivel de modelo de servicio y es responsable para el intercambio de mensajes entre los clientes y servicios. Las extensiones de canal pueden implementar la nueva funcionalidad de protocolo, como la seguridad. Las extensiones del canal también transportan la funcionalidad, como implementar un nuevo transporte de red para llevar los mensajes SOAP.  
  
 [Extensión de la seguridad](extending-security.md)  
 La seguridad en WCF se compone de la seguridad de la transferencia (integridad, confidencialidad y autenticación), control de acceso (autorización) y auditoría. WCF usa las clases que se encuentran en el `IdentityModel` espacio de nombres para el control de acceso. Entender la arquitectura de seguridad le permite crear tipos de notificación personalizados para alojar los sistemas de control de acceso personalizados.  
  
 [Extensión del sistema de metadatos](extending-the-metadata-system.md)  
 El sistema de metadatos de WCF es un grupo de clases e interfaces que representan los metadatos necesarios para implementar aplicaciones basadas en servicio. Modifique o extienda las clases o implemente y configure las interfaces para exportar e importar metadatos personalizados, como las extensiones de Lenguaje de descripción de servicios Web (WSDL) o las aserciones personalizadas de WS-PolicyAttachments.  
  
 [Extensión de codificadores y serializadores](extending-encoders-and-serializers.md)  
 Los codificadores y serializadores traducen los datos de un formulario a otro. Los temas de esta sección exponen cómo extender las clases proporcionadas para cumplir los requisitos especiales.  
  
## <a name="reference"></a>Referencia  

 <xref:System.ServiceModel>  
  
 <xref:System.ServiceModel.Channels>  
  
 <xref:System.ServiceModel.Description>  
  
 <xref:System.IdentityModel.Claims>  
  
 <xref:System.IdentityModel.Policy>  
  
 <xref:System.IdentityModel.Selectors>  
  
 <xref:System.IdentityModel.Tokens>  
  
## <a name="related-sections"></a>Secciones relacionadas  

 [Programación básica de WCF](../basic-wcf-programming.md)  
  
 [Detalles de las características de WCF](../feature-details/index.md)  
  
 [Instrucciones y procedimientos recomendados](../guidelines-and-best-practices.md)
