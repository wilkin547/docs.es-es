---
title: "Sugerencias para mejorar el rendimiento de .NET | Microsoft Docs"
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
  - "lenguaje C#, rendimiento"
  - "rendimiento [C#]"
  - "rendimiento [Visual Basic]"
  - "Visual Basic, rendimiento"
ms.assetid: ae275793-857d-4102-9095-b4c2a02d57f4
caps.latest.revision: 36
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
caps.handback.revision: 36
---
# Sugerencias para mejorar el rendimiento de .NET
El término *rendimiento* suele hacer referencia a la velocidad de ejecución de un programa.  En ocasiones, es posible incrementar la velocidad de ejecución si se siguen algunas reglas básicas en el código fuente.  En algunos programas, es importante examinar el código con detenimiento y usar generadores de perfiles para asegurarse de que se está ejecutando a la mayor velocidad posible.  En otros programas no es necesario realizar esta optimización, ya que el código se ejecuta a una velocidad aceptable según se escribe.  En este artículo se enumeran algunas áreas comunes donde el rendimiento puede verse afectado y sugerencias para mejorarlo, así como vínculos a temas adicionales de rendimiento.  Para obtener más información sobre cómo planear y medir el rendimiento, vea [Performance](../../../docs/framework/performance/index.md)  
  
## Conversión boxing y conversión unboxing  
 Es conveniente evitar el uso de tipos de valor en situaciones donde se les debe aplicar la conversión boxing un gran número de veces, por ejemplo en clases de colecciones no genéricas como <xref:System.Collections.ArrayList?displayProperty=fullName>.  Para evitar la conversión boxing de los tipos de valor, utilice colecciones genéricas como <xref:System.Collections.Generic.List%601?displayProperty=fullName>.  Las conversiones boxing y unboxing son procesos que consumen muchos recursos.  Cuando se aplica la conversión boxing a un tipo de valor, se debe crear un objeto completamente nuevo.  Esto puede llevar hasta 20 veces más que una asignación de referencias sencilla.  Al aplicar la conversión unboxing, el proceso de conversión puede llevar hasta cuatro veces más que una asignación.  Para obtener más información, vea [Conversión boxing y unboxing](../Topic/Boxing%20and%20Unboxing%20\(C%23%20Programming%20Guide\).md).  
  
## Cadenas  
 Al concatenar un número grande de variables de cadena, por ejemplo en un bucle ajustado, utilice <xref:System.Text.StringBuilder?displayProperty=fullName> en lugar del [operador \+](../Topic/+%20Operator%20\(C%23%20Reference\).md) de C\# o los [Operadores de concatenación](../Topic/Concatenation%20Operators%20\(Visual%20Basic\).md) de Visual Basic.  Para obtener más información, vea [Cómo: Concatenar varias cadenas](../Topic/How%20to:%20Concatenate%20Multiple%20Strings%20\(C%23%20Programming%20Guide\).md) y [Operadores de concatenación en Visual Basic](../Topic/Concatenation%20Operators%20in%20Visual%20Basic.md).  
  
## Destructores  
 No se deben utilizar destructores vacíos.  Cuando una clase contiene un destructor, se crea una entrada en la cola Finalize.  Cuando se llama al destructor, se invoca al recolector de elementos no utilizados para procesar la cola.  Si el destructor está vacío, simplemente se produce una pérdida de rendimiento.  Para obtener más información, vea [Destructores](../Topic/Destructors%20\(C%23%20Programming%20Guide\).md) y [Duración de los objetos: cómo se crean y destruyen](../Topic/Object%20Lifetime:%20How%20Objects%20Are%20Created%20and%20Destroyed%20\(Visual%20Basic\).md).  
  
## Otros recursos  
  
-   [Escribir código administrado más rápido: Saber qué cuestan las cosas](http://go.microsoft.com/fwlink/?LinkId=99294)  
  
-   [Escribir aplicaciones administradas de alto rendimiento: información básica](http://go.microsoft.com/fwlink/?LinkId=99295)  
  
-   [Recolector de elementos no utilizados y sugerencias sobre el rendimiento](http://go.microsoft.com/fwlink/?LinkId=99296)  
  
-   [Performance Tips and Tricks in .NET Applications](http://go.microsoft.com/fwlink/?LinkId=99297)  
  
-   [Análisis de herramientas de diagnóstico para .NET](http://go.microsoft.com/fwlink/?LinkId=112407)  
  
-   [Rico Mariani's Performance Tidbits](http://go.microsoft.com/fwlink/?LinkId=115679)  
  
## Vea también  
 [Performance](../../../docs/framework/performance/index.md)   
 [Programar los conceptos](../Topic/Programming%20Concepts.md)   
 [Guía de programación en Visual Basic](../Topic/Visual%20Basic%20Programming%20Guide.md)   
 [Guía de programación de C\#](../Topic/C%23%20Programming%20Guide.md)