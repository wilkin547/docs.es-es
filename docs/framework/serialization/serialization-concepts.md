---
title: "Conceptos de la serializaci&#243;n | Microsoft Docs"
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
ms.assetid: e1ff4740-20a1-4c76-a8ad-d857db307054
caps.latest.revision: 4
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 4
---
# Conceptos de la serializaci&#243;n
¿Por qué desearía utilizar la serialización?Las dos razones más importantes son conservar así el estado de un objeto a los medios de almacenamiento, de manera que una copia exacta se puede recrear en una copia intermedia posterior y para enviar por valor el objeto de un dominio de aplicación a otro.Por ejemplo, la serialización se utiliza para guardar el estado de sesión en ASP.NET y copiar los objetos en el Portapapeles en Windows Forms.La comunicación remota se utiliza también para pasar por valor los objetos de un dominio de aplicación a otro.  
  
## En esta sección  
 [Almacenamiento persistente](../../../docs/framework/serialization/persistent-storage.md)  
 Describe la necesidad de serializar un objeto.  
  
 [Calcular las referencias por valor](../../../docs/framework/serialization/marshal-by-value.md)  
 Describe el proceso de cálculo de referencias por valor.  
  
## Secciones relacionadas  
 [Serialización binaria](../../../docs/framework/serialization/binary-serialization.md)  
 Describe el mecanismo de la serialización binaria que está incluido con Common Language Runtime.  
  
 [Remote Objects](http://msdn.microsoft.com/es-es/515686e6-0a8d-42f7-8188-73abede57c58)  
 Describe los diversos métodos de comunicaciones disponibles en .NET Framework para las comunicaciones remotas.  
  
 [Serialización de SOAP y XML](../../../docs/framework/serialization/xml-and-soap-serialization.md)  
 Describe el mecanismo de la serialización XML y SOAP que está incluido con Common Language Runtime.