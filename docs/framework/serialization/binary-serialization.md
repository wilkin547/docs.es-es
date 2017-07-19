---
title: "Serializaci&#243;n binaria | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - "serialización binaria"
  - "serialización binaria, acerca de la serialización"
  - "deserialización"
  - "serialización, acerca de la serialización"
ms.assetid: 2b1ea3be-1152-4032-b2b3-07794054c405
caps.latest.revision: 5
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 5
---
# Serializaci&#243;n binaria
La serialización se puede definir como el proceso de almacenar el estado de un objeto a los medios de almacenamiento.Durante este proceso, los campos públicos y privados del objeto y el nombre de la clase, incluso el ensamblado que contiene la clase, se convierten en una secuencia de bytes, que se escribe a continuación en un flujo de datos.Cuando se deserializa el objeto como consecuencia, se crea un clon exacto del objeto original.  
  
 Al implementar un mecanismo de la serialización en un entorno orientado a objetos, tiene que realizar varios intercambios entre la facilidad de uso y la flexibilidad.El proceso se puede automatizar en gran medida, con tal de que sea proporcionado el control suficiente sobre el proceso.Por ejemplo, las situaciones se pueden presentar donde la serialización binaria simple no es suficiente, o podría haber una razón concreta para decidir qué campos en una clase necesitan ser serializados.Las secciones siguientes examinan el mecanismo de la serialización robusta proporcionado con .NET Framework y resaltan varias características importantes que le permiten personalizar el proceso para satisfacer sus necesidades.  
  
> [!NOTE]
>  El estado de un objeto UTF\-8 o UTF\-7 codificado no se conserva si el objeto se serializa y se deserializa utilizando distintas versiones de .NET Framework.  
  
## En esta sección  
 [Conceptos de la serialización](../../../docs/framework/serialization/serialization-concepts.md)  
 Describe dos escenarios en los que la serialización resulta útil: al almacenar datos persistentes y al pasar objetos a través de dominios de aplicaciones.  
  
 [Serialización básica](../../../docs/framework/serialization/basic-serialization.md)  
 Describe cómo utilizar los formateadores SOAP y binario para serializar los objetos.  
  
 [Serialización selectiva](../../../docs/framework/serialization/selective-serialization.md)  
 Describe cómo evitar que se serialicen algunos miembros de una clase.  
  
 [Serialización personalizada](../../../docs/framework/serialization/custom-serialization.md)  
 Describe cómo personalizar la serialización para una clase utilizando la interfaz <xref:System.Runtime.Serialization.ISerializable>.  
  
 [Pasos en el proceso de la serialización](../../../docs/framework/serialization/steps-in-the-serialization-process.md)  
 Describe la medida que toma la serialización cuando se llama al método <xref:System.Runtime.Serialization.Formatter.Serialize%2A> en un formateador.  
  
 [Serialización tolerante a versiones](../../../docs/framework/serialization/version-tolerant-serialization.md)  
 Explica cómo crear tipos serializables que se pueden modificar con el tiempo sin hacer que las aplicaciones produzcan las excepciones.  
  
 [Instrucciones de la serialización](../../../docs/framework/serialization/serialization-guidelines.md)  
 Proporciona algunas directrices general para decidir cuándo serializar un objeto.  
  
## Referencia  
 <xref:System.Runtime.Serialization>  
 Contiene clases que se pueden utilizar para serializar y deserializar objetos.  
  
## Secciones relacionadas  
 [Serialización de SOAP y XML](../../../docs/framework/serialization/xml-and-soap-serialization.md)  
 Describe el mecanismo de la serialización XML que está incluido con Common Language Runtime.  
  
 [Security and Serialization](../../../docs/framework/misc/security-and-serialization.md)  
 Describe las instrucciones de la codificación seguras que hay que seguir al escribir el código que realiza la serialización.  
  
 [Remote Objects](http://msdn.microsoft.com/es-es/515686e6-0a8d-42f7-8188-73abede57c58)  
 Describe los diversos métodos de comunicaciones disponibles en .NET Framework para las comunicaciones remotas.  
  
 [XML Web Services Created Using ASP.NET and XML Web Service Clients](http://msdn.microsoft.com/es-es/1e64af78-d705-4384-b08d-591a45f4379c)  
 Proporciona los temas que describen y explican cómo programar los servicios Web XML creados utilizando ASP.NET.