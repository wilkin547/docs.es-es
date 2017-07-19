---
title: "Clases no selladas | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-standard"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - "sellados de clases [.NET Framework]"
  - "clases no selladas"
  - "herencia de clases"
ms.assetid: 9a3bd505-90f5-4053-9f0d-3cf5fa3d3ebf
caps.latest.revision: 9
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 9
---
# Clases no selladas
No se puede heredar clases selladas e impiden extensibilidad. En cambio, las clases que se pueden heredar de se denominan clases no selladas.  
  
 **✓ considere** utilizando clases no selladas con no agregan los miembros virtuales o protegidos como una excelente manera de proporcionar económica todavía muy apreciado extensibilidad a un marco.  
  
 A menudo los desarrolladores desean heredar de clases no selladas con el fin de agregar a miembros de comodidad como constructores personalizados, nuevos métodos o sobrecargas del método. Por ejemplo,  `System.Messaging.MessageQueue` está sellado y, por tanto, permite a los usuarios crear colas personalizadas el valor predeterminado para una ruta de acceso de cola determinado o agregar métodos personalizados que simplifican la API para escenarios específicos.  
  
 Las clases están selladas de forma predeterminada en los lenguajes de programación más y esto también es el valor predeterminado recomendado para la mayoría de las clases en marcos. La extensibilidad proporcionada por los tipos no sellados se valora mucho por los usuarios de framework y bastante económica proporcionar debido a los costos de prueba relativamente bajo asociados con tipos no sellados.  
  
 *Partes © 2009, 2005 Microsoft Corporation. Todos los derechos reservados.*  
  
 *Reimpreso con permiso de Pearson Education, Inc. de [las directrices de diseño de Framework: convenciones, expresiones idiomáticas y patrones para las bibliotecas .NET de reutilizable, 2nd Edition](http://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) Krzysztof Cwalina y Brad Abrams, publicado el 22 de octubre de 2008 por Addison\-Wesley Professional como parte de la serie de desarrollo de Microsoft Windows.*  
  
## Vea también  
 [Instrucciones de diseño de Framework](../../../docs/standard/design-guidelines/index.md)   
 [Diseñar extensibilidad](../../../docs/standard/design-guidelines/designing-for-extensibility.md)   
 [Sellar](../../../docs/standard/design-guidelines/sealing.md)