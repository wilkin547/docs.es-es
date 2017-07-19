---
title: "Instrucciones de dise&#241;o de tipos | Microsoft Docs"
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
  - "instrucciones de diseño de tipos"
  - "instrucciones de diseño de tipo, acerca de las instrucciones de diseño de tipo"
  - "instrucciones de diseño [.NET Framework] de bibliotecas de clases, escriba instrucciones de diseño"
  - "tipos [.NET Framework], instrucciones de diseño"
ms.assetid: 6b49314e-8bba-43ea-97ca-4e0255812f95
caps.latest.revision: 13
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 13
---
# Instrucciones de dise&#241;o de tipos
Desde la perspectiva CLR, hay dos categorías de tipos: tipos de referencia y tipos de valor, pero con el fin de obtener una explicación sobre el diseño de framework, dividimos tipos en grupos lógicos más, cada uno con sus propias reglas de diseño específicas.  
  
 Las clases son el caso general de tipos de referencia. Constituyen la mayor parte de los tipos en la mayoría de los marcos. Clases deben su popularidad, el amplio conjunto de características orientada a objetos que admiten y su aplicabilidad general. Las clases base y clases abstractas son grupos lógicos especiales relacionados con la extensibilidad.  
  
 Interfaces son tipos que se pueden implementar por tipos de referencia y tipos de valor. Por lo tanto pueden servir como raíces de polimórficas jerarquías de tipos de referencia y tipos de valor. Además, pueden utilizarse interfaces para simular la herencia múltiple, que no se admite de forma nativa por CLR.  
  
 Las estructuras son el caso general de los tipos de valor y deben ser reservadas para los tipos pequeños y sencillos, como primitivas del lenguaje.  
  
 Las enumeraciones son un caso especial de tipos de valor utilizados para definir corto conjuntos de valores, como los días de la semana, colores de la consola y así sucesivamente.  
  
 Las clases estáticas son tipos que pretende ser contenedores para los miembros estáticos. Se suelen usar para proporcionar accesos directos a otras operaciones.  
  
 Delegados, excepciones, atributos, matrices y colecciones de todos los casos especiales de tipos de referencia diseñados para usos específicos, y directrices de diseño y de uso se explican más adelante en este libro.  
  
 **✓ hacer** Asegúrese de que cada tipo es un conjunto bien definido de miembros relacionados, no sólo un conjunto aleatorio de funcionalidad no relacionado.  
  
## En esta sección  
 [Elegir entre clases y structs](../../../docs/standard/design-guidelines/choosing-between-class-and-struct.md)  
 [Diseño de clases abstractas](../../../docs/standard/design-guidelines/abstract-class.md)  
 [Diseño de clases estáticas](../../../docs/standard/design-guidelines/static-class.md)  
 [Diseño de la interfaz](../../../docs/standard/design-guidelines/interface.md)  
 [Diseño de estructura](../../../docs/standard/design-guidelines/struct.md)  
 [Diseño de enumeraciones](../../../docs/standard/design-guidelines/enum.md)  
 [Tipos anidados](../../../docs/standard/design-guidelines/nested-types.md)  
 *Partes © 2009, 2005 Microsoft Corporation. Todos los derechos reservados.*  
  
 *Reimpreso con permiso de Pearson Education, Inc. de [las directrices de diseño de Framework: convenciones, expresiones idiomáticas y patrones para las bibliotecas .NET de reutilizable, 2nd Edition](http://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) Krzysztof Cwalina y Brad Abrams, publicado el 22 de octubre de 2008 por Addison\-Wesley Professional como parte de la serie de desarrollo de Microsoft Windows.*  
  
## Vea también  
 [Instrucciones de diseño de Framework](../../../docs/standard/design-guidelines/index.md)