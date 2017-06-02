---
title: "Dise&#241;o de clases abstractas | Microsoft Docs"
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
  - "Escriba instrucciones de diseño, clases abstractas"
  - "clases abstractas, instrucciones de diseño"
  - "instrucciones de diseño clases biblioteca [.NET Framework], clases"
  - "Resumen de clases [.NET Framework]"
  - "clases [.NET Framework], instrucciones de diseño"
  - "Escriba las instrucciones de diseño de clases"
ms.assetid: d3646e6d-5c1f-4922-8fb0-ec5effb30d60
caps.latest.revision: 13
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 13
---
# Dise&#241;o de clases abstractas
**X no** definir constructores internos públicos o protegidos en tipos abstractos.  
  
 Los constructores deben ser públicos sólo si los usuarios necesitan crear instancias del tipo. Porque no se puede crear instancias de un tipo abstracto, un tipo abstracto con un constructor público está correctamente diseñado y confuso para los usuarios.  
  
 **✓ hacer** definir un constructor interno o protegidos en clases abstractas.  
  
 Un constructor protegido es más común y permite la clase base para realizar su propia inicialización cuando se crean subtipos.  
  
 Un constructor interno puede utilizarse para limitar las implementaciones concretas de la clase abstracta para el ensamblado que define la clase.  
  
 **✓ hacer** proporcionar al menos un tipo concreto que herede de cada clase abstracta que realiza el envío.  
  
 Haciendo esto ayuda a validar el diseño de la clase abstracta. Por ejemplo,  <xref:System.IO.FileStream?displayProperty=fullName> es una implementación de la <xref:System.IO.Stream?displayProperty=fullName> clase abstracta.  
  
 *Partes © 2009, 2005 Microsoft Corporation. Todos los derechos reservados.*  
  
 *Reimpreso con permiso de Pearson Education, Inc. de [las directrices de diseño de Framework: convenciones, expresiones idiomáticas y patrones para las bibliotecas .NET de reutilizable, 2nd Edition](http://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) Krzysztof Cwalina y Brad Abrams, publicado el 22 de octubre de 2008 por Addison\-Wesley Professional como parte de la serie de desarrollo de Microsoft Windows.*  
  
## Vea también  
 [Instrucciones de diseño de tipos](../../../docs/standard/design-guidelines/type.md)   
 [Instrucciones de diseño de Framework](../../../docs/standard/design-guidelines/index.md)