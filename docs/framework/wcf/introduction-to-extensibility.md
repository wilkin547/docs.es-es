---
title: "Introducci&#243;n a la extensibilidad | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "extensibilidad [WCF]"
  - "WCF [WCF], extensibilidad"
  - "Windows Communication Foundation [WCF], extensibilidad"
ms.assetid: ef56c251-d63c-4b3f-944f-b0c67bfb0f68
caps.latest.revision: 7
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 7
---
# Introducci&#243;n a la extensibilidad
El modelo de aplicación [!INCLUDE[indigo1](../../../includes/indigo1-md.md)] está diseñado para resolver la mayor parte de los requisitos de comunicación de cualquier aplicación distribuida.  No obstante, siempre hay escenarios con los que el modelo de aplicación predeterminado y las implementaciones proporcionadas por sistema no son compatibles.  El modelo de extensibilidad [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] está diseñado para admitir escenarios personalizados permitiéndole modificar el comportamiento del sistema en cada nivel, incluso hasta el punto de reemplazar todo el modelo de aplicación.  Este tema describe las distintas áreas de extensión e indica dónde obtener más información acerca de cada una de ellas.  
  
## Áreas que pueden extenderse  
 Puede extenderse:  
  
-   El tiempo de ejecución de la aplicación.  De este modo se extiende la distribución y el procesamiento de mensajes para la aplicación.  Esta área también incluye la extensión del sistema de seguridad, el sistema de metadatos, el sistema de serialización, y los enlaces y elementos de enlace que conectan la aplicación con el sistema del canal subyacente.  
  
-   El canal y su tiempo de ejecución.  Así se extiende el sistema que funciona en el nivel de mensaje, proporcionando compatibilidad con el protocolo, el transporte y la codificación.  
  
-   El tiempo de ejecución del host.  Se extiende la relación del dominio de aplicación de hospedaje al tiempo de ejecución del canal y de la aplicación.  
  
### Extender el tiempo de ejecución de la aplicación  
 En aplicaciones [!INCLUDE[indigo2](../../../includes/indigo2-md.md)], existe una diferencia entre los mensajes destinados a un canal correspondiente y los mensajes destinados a la propia aplicación.  Los mensajes del canal admiten alguna funcionalidad relacionada con el canal, como establecer una conversación segura o una sesión de confianza.  Estos mensajes no están disponibles para el tiempo de ejecución de la aplicación; se procesan antes de que se implique el nivel de la aplicación.  
  
 Los mensajes de la aplicación contienen datos destinados a un cliente u operación del servicio que usted o su cliente creó.  Estos mensajes están disponibles para el sistema de extensión del nivel de la aplicación en forma de mensaje u objeto, dependiendo de sus necesidades.  
  
 Todos los mensajes atraviesan el sistema del canal; solo los mensajes de la aplicación se pasan desde el sistema del canal a la aplicación.  Para crear una nueva funcionalidad en el nivel del canal, debe extender el sistema del canal.  Para crear una nueva funcionalidad en el nivel de la aplicación, debe extender el tiempo de ejecución del servicio o del cliente \(los distribuidores y generadores de canales, respectivamente\).  [!INCLUDE[crabout](../../../includes/crabout-md.md)] extender el tiempo de ejecución de la aplicación, vea [Extensión de ServiceHost y la capa de modelos de servicios](../../../docs/framework/wcf/extending/extending-servicehost-and-the-service-model-layer.md).  
  
#### Extensión de la seguridad  
 Para crear mecanismos de seguridad personalizados, como tokens y credenciales, debe extender el sistema de seguridad.  [!INCLUDE[crdefault](../../../includes/crdefault-md.md)] [Extensión de la seguridad](../../../docs/framework/wcf/extending/extending-security.md).  
  
#### Extensión de metadatos  
 Para exponer sus metadatos de manera diferente a la predeterminada, es necesario extender el sistema de metadatos.  [!INCLUDE[crdefault](../../../includes/crdefault-md.md)] [Extensión del sistema de metadatos](../../../docs/framework/wcf/extending/extending-the-metadata-system.md).  
  
#### Extender la serialización  
 Para crear los codificadores personalizados, proporcionar suplentes de datos u otro trabajo que implique la personalización de datos transferidos, es necesario extender el sistema de serialización.  [!INCLUDE[crdefault](../../../includes/crdefault-md.md)] [Extensión de codificadores y serializadores](../../../docs/framework/wcf/extending/extending-encoders-and-serializers.md).  
  
#### Extensión de enlaces  
 Para asociar canales de transporte o de protocolo con el nivel de aplicación, debe extender el sistema de enlace.  [!INCLUDE[crdefault](../../../includes/crdefault-md.md)] [Extensión de enlaces](../../../docs/framework/wcf/extending/extending-bindings.md).  
  
### Extender el sistema del canal  
 Para crear canales compatibles con transportes personalizados o la funcionalidad de un protocolo, vea [Extensión de la capa de canales](../../../docs/framework/wcf/extending/extending-the-channel-layer.md).  
  
### Extensión del servicio de hospedaje del sistema  
 Para modificar el modelo de la aplicación de todo el servicio, es necesario extender la clase <xref:System.ServiceModel.ServiceHostBase?displayProperty=fullName>.  [!INCLUDE[crdefault](../../../includes/crdefault-md.md)] [Extensión de ServiceHost y la capa de modelos de servicios](../../../docs/framework/wcf/extending/extending-servicehost-and-the-service-model-layer.md).  
  
 Para modificar la relación entre el dominio de aplicación de hospedaje y el host del servicio, es necesario extender la clase <xref:System.ServiceModel.Activation.ServiceHostFactory?displayProperty=fullName>.  [!INCLUDE[crdefault](../../../includes/crdefault-md.md)] [Extensión del hospedaje mediante ServiceHostFactory](../../../docs/framework/wcf/extending/extending-hosting-using-servicehostfactory.md).  
  
## Vea también  
 [Extensión de WCF](../../../docs/framework/wcf/extending/extending-wcf.md)