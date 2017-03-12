---
title: "Diferencias entre plantillas de C++ y tipos gen&#233;ricos de C# (Gu&#237;a de programaci&#243;n de C#) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "genéricos [C#], plantillas de C++"
ms.assetid: 1da6beeb-d4a4-4da0-87b7-0cfbe04920b7
caps.latest.revision: 14
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 14
---
# Diferencias entre plantillas de C++ y tipos gen&#233;ricos de C# (Gu&#237;a de programaci&#243;n de C#)
Los tipos genéricos de C\# y las plantillas de C\+\+ son ambas características de lenguaje que proporcionan compatibilidad con los tipos parametrizados.  Sin embargo, hay muchas diferencias entre ellas.  En el aspecto sintáctico, los tipos genéricos de C\# son un enfoque más simple de los tipos parametrizados sin la complejidad de las plantillas de C\+\+.  Además, C\# no intenta proporcionar toda la funcionalidad que brindan las plantillas de C\+\+.  En lo que a la implementación se refiere, la diferencia principal es que las sustituciones de tipo genérico de C\# se realizan en tiempo de ejecución y la información de tipo genérico se conserva en los objetos de los que se han creado instancias.  Para obtener más información, vea [Genéricos en el motor en tiempo de ejecución](../../../csharp/programming-guide/generics/generics-in-the-run-time.md).  
  
 A continuación se exponen las diferencias clave entre los tipos genéricos de C\# y las plantillas de C\+\+:  
  
-   Los tipos genéricos de C\# no proporcionan la misma cantidad de flexibilidad que las plantillas de C\+\+.  Por ejemplo, no es posible llamar a los operadores aritméticos de una clase genérica de C\#, aunque es posible llamar a los operadores definidos por el usuario.  
  
-   C\# no permite parámetros de plantilla sin tipo, como `template C<int i> {}`.  
  
-   C\# no admite la especialización explícita; es decir, una implementación personalizada de una plantilla para un tipo específico.  
  
-   C\# no admite la especialización parcial: una implementación personalizada para un subconjunto de argumentos de tipo.  
  
-   C\# no permite el uso del parámetro de tipo como clase base para el tipo genérico.  
  
-   C\# no permite que los parámetros de tipo tengan tipos predeterminados.  
  
-   En C\#, un parámetro de tipo genérico no puede ser genérico en sí mismo, aunque los tipos construidos se pueden utilizar como genéricos.  C\+\+ permite los parámetros de plantilla.  
  
-   C\+\+ permite código que podría no ser válido para todos los parámetros de tipo de la plantilla, en la cual se busca el tipo específico utilizado como parámetro de tipo.  C\# requiere que el código de una clase se escriba de tal forma que funcione con cualquier tipo que cumpla con las restricciones.  Por ejemplo, en C\+\+ es posible escribir una función que usa los operadores aritméticos `+` y `-` en objetos del parámetro de tipo, lo cual producirá un error en el momento de crear una instancia de la plantilla con un tipo que no admita esos operadores.  C\# no permite esto; las únicas construcciones de lenguaje permitidas son aquéllas que se pueden deducir de las restricciones.  
  
## Vea también  
 [Guía de programación de C\#](../../../csharp/programming-guide/index.md)   
 [Introducción a los genéricos](../../../csharp/programming-guide/generics/introduction-to-generics.md)   
 [Plantillas](/visual-cpp/cpp/templates-cpp)