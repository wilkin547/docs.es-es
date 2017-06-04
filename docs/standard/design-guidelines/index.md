---
title: "Instrucciones de dise&#241;o de Framework | Microsoft Docs"
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
  - "bibliotecas, biblioteca de clases de .NET Framework"
  - "clase de instrucciones de diseño de la biblioteca [.NET Framework], acerca de"
  - "instrucciones de diseño de bibliotecas de clases [.NET Framework]"
ms.assetid: 5fbcaf4f-ea2a-4d20-b0d6-e61dee202b4b
caps.latest.revision: 14
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 14
---
# Instrucciones de dise&#241;o de Framework
Esta sección proporciona instrucciones para diseñar bibliotecas que extensión e interactúan con .NET Framework. El objetivo es ayudar a los diseñadores de bibliotecas a garantizar la coherencia de la API y facilidad de uso al proporcionar un modelo de programación unificado que es independiente del lenguaje de programación utilizado para el desarrollo. Se recomienda que siga estas directrices de diseño al desarrollar clases y componentes que extiendan .NET Framework. Diseño de biblioteca incoherente negativamente afecta a la productividad del desarrollador y desalienta la adopción.  
  
 Las instrucciones se organizan como recomendaciones sencillas como precedidas con los términos de `Do`, `Consider`, `Avoid`, y `Do not`. Estas directrices están diseñadas para ayudar a los diseñadores de la biblioteca de clases a comprender las ventajas y desventajas de las distintas soluciones. Puede haber situaciones donde buen diseño de bibliotecas requiera saltarse estas instrucciones de diseño. Estos casos deben ser infrecuentes, y es importante que tenga un motivo claro y atractivo para su decisión.  
  
 Estas instrucciones son fragmentos tomadas de la libreta de *las directrices de diseño de Framework: convenciones, expresiones idiomáticas y patrones para las bibliotecas .NET de reutilizable, 2nd Edition*, Krzysztof Cwalina y Brad Abrams.  
  
## En esta sección  
 [Instrucciones de nomenclatura](../../../docs/standard/design-guidelines/naming-guidelines.md)  
 Proporciona directrices para asignar nombres a los ensamblados, espacios de nombres, tipos y miembros de bibliotecas de clases.  
  
 [Instrucciones de diseño de tipos](../../../docs/standard/design-guidelines/type.md)  
 Proporciona instrucciones para utilizar clases estáticas y abstractas, interfaces, enumeraciones, estructuras y otros tipos.  
  
 [Instrucciones de diseño de miembros](../../../docs/standard/design-guidelines/member.md)  
 Proporciona directrices para diseñar y utilizar propiedades, métodos, constructores, campos, eventos, operadores y parámetros.  
  
 [Diseñar extensibilidad](../../../docs/standard/design-guidelines/designing-for-extensibility.md)  
 Se tratan los mecanismos de extensibilidad, como crear subclases, uso de eventos, los miembros virtuales y devoluciones de llamada y explica cómo elegir los mecanismos que satisfagan los requisitos del marco de trabajo.  
  
 [Instrucciones de diseño para excepciones](../../../docs/standard/design-guidelines/exceptions.md)  
 Describe las instrucciones de diseño para diseñar, iniciar y detectar excepciones.  
  
 [Instrucciones de uso](../../../docs/standard/design-guidelines/usage-guidelines.md)  
 Describe instrucciones para utilizar tipos comunes, como matrices, atributos y colecciones, admitir la serialización y la sobrecarga de operadores de igualdad.  
  
 [Patrones de diseño comunes](../../../docs/standard/design-guidelines/common-design-patterns.md)  
 Proporciona directrices para elegir e implemente las propiedades de dependencia y el patrón dispose.  
  
 *Partes © 2009, 2005 Microsoft Corporation. Todos los derechos reservados.*  
  
 *Reimpreso con permiso de Pearson Education, Inc. de [las directrices de diseño de Framework: convenciones, expresiones idiomáticas y patrones para las bibliotecas .NET de reutilizable, 2nd Edition](http://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) Krzysztof Cwalina y Brad Abrams, publicado el 22 de octubre de 2008 por Addison\-Wesley Professional como parte de la serie de desarrollo de Microsoft Windows.*  
  
## Vea también  
 [Información general](../../../docs/framework/get-started/overview.md)   
 [Guía básica de .NET Framework](http://msdn.microsoft.com/es-es/0b46b7c6-9163-4f99-8e58-0d1ee7da8c67)   
 [Guía de desarrollo](../../../docs/framework/development-guide.md)