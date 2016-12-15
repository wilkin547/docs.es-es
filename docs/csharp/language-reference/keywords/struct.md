---
title: "struct (Referencia de C#) | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "struct_CSharpKeyword"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "struct (palabra clave) [C#]"
  - "structs [C#], struct (palabra clave)"
ms.assetid: ff3dd9b7-dc93-4720-8855-ef5558f65c7c
caps.latest.revision: 23
caps.handback.revision: 23
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# struct (Referencia de C#)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

Un tipo `struct` es un tipo de valor que normalmente se usa para encapsular pequeños grupos de variables relacionadas, como las coordenadas de un rectángulo o las características de un elemento en un inventario.  En el siguiente ejemplo se muestra una declaración de struct simple:  
  
```  
public struct Book  
{  
    public decimal price;  
    public string title;  
    public string author;  
}  
```  
  
## Comentarios  
 Los structs también pueden contener [constructores](../../../csharp/programming-guide/classes-and-structs/constructors.md), [constantes](../../../csharp/programming-guide/classes-and-structs/constants.md), [campos](../../../csharp/programming-guide/classes-and-structs/fields.md), [métodos](../../../csharp/programming-guide/classes-and-structs/methods.md), [propiedades](../../../csharp/programming-guide/classes-and-structs/properties.md), [indizadores](../../../csharp/programming-guide/indexers/index.md), [operadores](../../../csharp/programming-guide/statements-expressions-operators/operators.md), [eventos](../../../csharp/programming-guide/events/index.md) y [tipos anidados](../../../csharp/programming-guide/classes-and-structs/nested-types.md), aunque si se necesitan varios de estos miembros, puede considerar la posibilidad de crear su propio tipo de clase.  
  
 Para obtener ejemplos, vea [Utilizar estructuras](../../../csharp/programming-guide/classes-and-structs/using-structs.md).  
  
 Los structs pueden implementar una interfaz, pero no pueden heredar de otro struct.  Por ese motivo, los miembros de struct no se pueden declarar como `protected`.  
  
 Para obtener más información, vea [Structs](../../../csharp/programming-guide/classes-and-structs/structs.md).  
  
## Ejemplos  
 Para obtener más información y ejemplos, vea [Utilizar estructuras](../../../csharp/programming-guide/classes-and-structs/using-structs.md).  
  
## Especificación del lenguaje C\#  
 Para obtener ejemplos, vea [Utilizar estructuras](../../../csharp/programming-guide/classes-and-structs/using-structs.md).  
  
## Vea también  
 [Referencia de C\#](../../../csharp/language-reference/index.md)   
 [Guía de programación de C\#](../../../csharp/programming-guide/index.md)   
 [Palabras clave de C\#](../../../csharp/language-reference/keywords/index.md)   
 [Tabla de valores predeterminados](../../../csharp/language-reference/keywords/default-values-table.md)   
 [Tabla de tipos integrados](../../../csharp/language-reference/keywords/built-in-types-table.md)   
 [Tipos](../../../csharp/language-reference/keywords/types.md)   
 [Tipos de valor](../../../csharp/language-reference/keywords/value-types.md)   
 [clase](../../../csharp/language-reference/keywords/class.md)   
 [interfaz](../../../csharp/language-reference/keywords/interface.md)   
 [Clases y structs](../../../csharp/programming-guide/classes-and-structs/index.md)