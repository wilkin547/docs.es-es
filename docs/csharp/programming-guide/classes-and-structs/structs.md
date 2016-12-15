---
title: "Structs (Gu&#237;a de programaci&#243;n de C#) | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "lenguaje C#, estructuras"
  - "structs [C#]"
ms.assetid: b7cf4ff2-0eb7-4e5c-93d5-b2196b4f5d89
caps.latest.revision: 31
caps.handback.revision: 31
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# Structs (Gu&#237;a de programaci&#243;n de C#)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

Los structs se definen mediante la palabra clave [struct](../../../csharp/language-reference/keywords/struct.md), por ejemplo:  
  
 [!code-cs[csProgGuideObjects#39](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/structs_1.cs)]  
  
 Casi todas los structs comparten la misma sintaxis que las clases, aunque están más limitadas que éstas:  
  
-   Dentro de una declaración de struct, los campos no se pueden inicializar a menos que se declaren como constantes o estáticos.  
  
-   Un struct no puede declarar un constructor predeterminado \(es decir, un constructor sin parámetros\) ni un destructor.  
  
-   Los structs se copian en la asignación.  Cuando se asigna un struct a una nueva variable, se copian todos los datos, y cualquier modificación que se realice en la nueva copia no afecta a los datos de la copia original.  Es importante tenerlo en cuenta a la hora de usar colecciones de tipos de valor como Dictionary\<string, myStruct\>.  
  
-   Los structs son tipos de valor y las clases son tipos de referencia.  
  
-   A diferencia de las clases, es posible crear instancias de los structs sin utilizar un operador `new`.  
  
-   Los structs pueden declarar constructores que tienen parámetros.  
  
-   Un struct no puede heredar de otro struct o clase, ni puede ser la base de una clase.  Todos los structs heredan directamente de `System.ValueType`, que hereda de `System.Object`.  
  
-   Un struct puede implementar interfaces.  
  
-   Un struct se puede utilizar como tipo que acepta valores null y se le puede asignar un valor null.  
  
## Secciones relacionadas  
 Para obtener más información:  
  
-   [Utilizar estructuras](../../../csharp/programming-guide/classes-and-structs/using-structs.md)  
  
-   [Constructores](../../../csharp/programming-guide/classes-and-structs/constructors.md)  
  
-   [Tipos que aceptan valores NULL](../../../csharp/programming-guide/nullable-types/index.md)  
  
-   [Cómo: Saber las diferencias entre pasar a un método un struct y una referencia a clase](../../../csharp/programming-guide/classes-and-structs/how-to-know-the-difference-passing-a-struct-and-passing-a-class-to-a-method.md)  
  
-   [Cómo: Implementar conversiones definidas por el usuario entre structs](../../../csharp/programming-guide/statements-expressions-operators/how-to-implement-user-defined-conversions-between-structs.md)  
  
-   [Más información sobre variables](http://go.microsoft.com/fwlink/?LinkId=221230) en [Principio Visual c\# 2010](http://go.microsoft.com/fwlink/?LinkId=221214)  
  
## Vea también  
 [Guía de programación de C\#](../../../csharp/programming-guide/index.md)   
 [Clases y structs](../../../csharp/programming-guide/classes-and-structs/index.md)   
 [Clases](../../../csharp/programming-guide/classes-and-structs/classes.md)