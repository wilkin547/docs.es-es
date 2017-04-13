---
title: "Extensi&#243;n de ServiceHost y la capa de modelos de servicios | Microsoft Docs"
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
  - "extender los modelos de servicios [WCF]"
ms.assetid: 954c138a-1cd0-45a0-8abe-e4d2b8ff5400
caps.latest.revision: 12
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 12
---
# Extensi&#243;n de ServiceHost y la capa de modelos de servicios
El nivel de modelo de servicio es responsable de extraer los mensajes entrantes de los canales subyacentes, de modo que los traduce en código de aplicación en las invocaciones de método y devuelve los resultados al agente de llamada.Las extensiones de modelo de servicio modifican o implementan la ejecución o comportamiento de la comunicación y características implicadas en la funcionalidad del distribuidor o cliente, comportamientos personalizados, interceptación de mensaje y parámetro, y otra funcionalidad de extensibilidad.  
  
## En esta sección  
 [Extensión de clientes](../../../../docs/framework/wcf/extending/extending-clients.md)  
 Describe las interfaces que pueden interceptar y modificar el tiempo de ejecución del cliente, así como las clases en las que puede insertar sus extensiones personalizadas en aplicaciones cliente.Por ejemplo, puede realizar el registro de mensajes del cliente personalizado, realizar serialización del mensaje personalizada, etc.  
  
 [Extensión de distribuidores](../../../../docs/framework/wcf/extending/extending-dispatchers.md)  
 Describe las interfaces que pueden interceptar y modificar el tiempo de ejecución del servicio, así como las clases en las que puede insertar sus extensiones personalizadas en aplicaciones de servicio.Por ejemplo, puede realizar el registro de servicio personalizado, la validación de mensajes del lado de servicio, distribución personalizada, etc.  
  
 [Objetos extensibles](../../../../docs/framework/wcf/extending/extensible-objects.md)  
 Describe los cinco objetos extensibles y el modelo <xref:System.ServiceModel.IExtensibleObject%601>.El modelo de objeto extensible se utiliza para extender clases de tiempo de ejecución existentes con nueva funcionalidad o para agregar un nuevo estado a un objeto.Las extensiones, adjuntas a uno de los objetos extensibles, permiten que los comportamientos en fases muy diferentes de procesamiento tengan acceso al estado compartido y funcionalidad adjuntos a un objeto extensible común al que pueden tener acceso.  
  
 [Configuración y extensión del tiempo de ejecución con comportamientos](../../../../docs/framework/wcf/extending/configuring-and-extending-the-runtime-with-behaviors.md)  
 Para cambiar los valores en o insertar extensiones en el tiempo de ejecución [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)], utiliza comportamientos.WCF incluye comportamientos implementados por el sistema para controlar la limitación de peticiones, la creación de instancias y muchos otros aspectos de servicios y operaciones.En esta sección se describe cómo crear sus propios comportamientos personalizados y cómo hacer que estén disponibles para el uso tanto a nivel de programación como utilizando archivos de configuración.  
  
 [Extensión del hospedaje mediante ServiceHostFactory](../../../../docs/framework/wcf/extending/extending-hosting-using-servicehostfactory.md)  
 Describe cómo extender <xref:System.ServiceModel.ServiceHostBase?displayProperty=fullName>, <xref:System.ServiceModel.ServiceHost?displayProperty=fullName>y utilizar las clases <xref:System.ServiceModel.Activation.ServiceHostFactory?displayProperty=fullName> para personalizar el entorno del host.  
  
## Referencia  
  
## Secciones relacionadas