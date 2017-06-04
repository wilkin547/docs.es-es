---
title: "Elegir entre clases y structs | Microsoft Docs"
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
  - "instrucciones de diseño clases biblioteca [.NET Framework], estructuras"
  - "instrucciones de diseño clases biblioteca [.NET Framework], clases"
  - "estructuras [.NET Framework], frente a clases"
  - "clases [.NET Framework], instrucciones de diseño"
  - "Escriba las instrucciones de diseño de estructuras"
  - "estructuras [.NET Framework], instrucciones de diseño"
  - "clases [.NET Framework], estructuras"
  - "Escriba las instrucciones de diseño de clases"
ms.assetid: f8b8ec9b-0ba7-4dea-aadf-a93395cd804f
caps.latest.revision: 11
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 11
---
# Elegir entre clases y structs
Una de las decisiones de diseño básicos que enfrenta cada diseñador framework es si va a diseñar un tipo como una clase \(un tipo de referencia\) o como una estructura \(tipo de valor\). Buena comprensión de las diferencias en el comportamiento de los tipos de referencia y tipos de valor es fundamental para tomar esta decisión.  
  
 La primera diferencia entre tipos de referencia y tipos de valor que se tendrá en cuenta es que los tipos de referencia se asignan en el montón y recolección, mientras que los tipos de valor se asignan en la pila o en línea en que contienen tipos y se desasignan cuando se desenreda la pila o cuando su tipo contenedor se ha cancelado la asignación. Por lo tanto, las asignaciones y cancelaciones de asignación de tipos de valor son en general más barato que las asignaciones y cancelaciones de asignación de tipos de referencia.  
  
 A continuación, matrices de tipos de referencia asignan fuera de línea, lo que significa que la matriz de elementos son únicamente de las referencias a las instancias del tipo de referencia que residen en el montón. Matrices de tipo de valor se asignan en línea, lo que significa que los elementos de la matriz son las instancias reales del tipo de valor. Por lo tanto, las asignaciones y desasignaciones de matrices de tipo de valor son mucho más baratos que las asignaciones y desasignaciones de matrices de tipo de referencia. Además, en la mayoría de los casos matrices de tipo de valor presentan mucho mejor grado de emplazamiento de referencia.  
  
 La diferencia siguiente está relacionada con el uso de memoria. Tipos de valor obtengan conversión boxing cuando se convierte a un tipo de referencia o una de las interfaces que implementan. Obtienen la conversión unboxing cuando se convierte al tipo de valor. Como casillas son objetos que se asignan en el montón y la recolección, demasiado conversión boxing y unboxing puede tener un impacto negativo en el montón, el recolector de elementos no utilizados y, en última instancia, el rendimiento de la aplicación.  En cambio, se produce ninguna conversión boxing tal como tipos de referencia se convierten.  
  
 A continuación, las asignaciones de tipo de referencia copia la referencia, mientras que las asignaciones de tipo de valor copie el valor completo. Por lo tanto, las asignaciones de tipos de referencia grandes son más baratas que las asignaciones de tipos de valor grande.  
  
 Por último, los tipos de referencia se pasan por referencia, mientras que los tipos de valor se pasan por valor. Cambios a una instancia de un tipo de referencia afectan a todas las referencias que señala a la instancia. Instancias de tipo de valor se copian cuando se pasan por valor. Cuando se modifica una instancia de un tipo de valor, por supuesto no afecta ninguna de sus copias. Porque las copias no se crean explícitamente por el usuario, pero se crean implícitamente cuando los argumentos se pasan o devuelven los valores se devuelven los tipos de valor que se pueden cambiar pueden resultar confusos para muchos usuarios. Por lo tanto, los tipos de valor deben ser inmutables.  
  
 Como regla general, la mayoría de los tipos en un marco de trabajo debe ser clases. Sin embargo, existen algunas situaciones en que las características de un tipo de valor facilitan más adecuado usar structs.  
  
 **✓ considere** definir una estructura en lugar de una clase si las instancias del tipo son pequeños y normalmente corta duración o suelen estar incrustadas en otros objetos.  
  
 **Evitar X** definir un struct a menos que el tipo tiene todas las características siguientes:  
  
-   Representa lógicamente un valor único, de forma similar a los tipos primitivos \(`int`, `double`, etc..\).  
  
-   Tiene un tamaño de instancia inferior a 16 bytes.  
  
-   Es inmutable.  
  
-   No tiene que aplicar la conversión boxing con frecuencia.  
  
 En los demás casos, debe definir los tipos como clases.  
  
 *Partes © 2009, 2005 Microsoft Corporation. Todos los derechos reservados.*  
  
 *Reimpreso con permiso de Pearson Education, Inc. de [las directrices de diseño de Framework: convenciones, expresiones idiomáticas y patrones para las bibliotecas .NET de reutilizable, 2nd Edition](http://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) Krzysztof Cwalina y Brad Abrams, publicado el 22 de octubre de 2008 por Addison\-Wesley Professional como parte de la serie de desarrollo de Microsoft Windows.*  
  
## Vea también  
 [Instrucciones de diseño de tipos](../../../docs/standard/design-guidelines/type.md)   
 [Instrucciones de diseño de Framework](../../../docs/standard/design-guidelines/index.md)