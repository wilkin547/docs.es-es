---
title: "this (Referencia de C#) | Microsoft Docs"
description: this keyword (C# Reference)
ms.custom: ""
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
f1_keywords: 
  - "this"
  - "this_CSharpKeyword"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "this (palabra clave) [C#]"
ms.assetid: d4f827fe-4710-410b-89b8-867dad44b8a3
caps.latest.revision: 19
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 19
---
# this (Referencia de C#)
La palabra clave `this` hace referencia a la instancia actual de la clase y también se utiliza como modificador del primer parámetro de un método de extensión.  
  
> [!NOTE]
>  En este artículo se analiza el uso de `this` con instancias de clase.  Para obtener más información sobre su uso en métodos de extensión, vea [Métodos de extensión](../../../csharp/programming-guide/classes-and-structs/extension-methods.md).  
  
 A continuación, se indican algunos usos comunes de `this`:  
  
-   Calificar miembros con el fin de evitar ambigüedades con nombres similares, por ejemplo:  
  
 [!code-cs[csrefKeywordsAccess#4](../../../csharp/language-reference/keywords/codesnippet/CSharp/this_1.cs)]  
  
-   Pasar un objeto como parámetro a otros métodos, por ejemplo, para:  
  
    ```  
    CalcTax(this);  
    ```  
  
-   Declarar indizadores, por ejemplo:  
  
 [!code-cs[csrefKeywordsAccess#5](../../../csharp/language-reference/keywords/codesnippet/CSharp/this_2.cs)]  
  
 Debido a que las funciones miembro estáticas existen en el nivel de clase y no como parte de un objeto, no tienen un puntero `this`.  Es un error hacer referencia a `this` en un método estático.  
  
## Ejemplo  
 En este ejemplo, `this` se utiliza para calificar los miembros de la clase `Employee`, `name` y `alias`, que presentan ambigüedad con nombres similares.  También se utiliza para pasar un objeto al método `CalcTax`, el cual pertenece a otra clase.  
  
 [!code-cs[csrefKeywordsAccess#3](../../../csharp/language-reference/keywords/codesnippet/CSharp/this_3.cs)]  
  
## Especificación del lenguaje C\#  
 [!INCLUDE[CSharplangspec](../../../csharp/language-reference/keywords/includes/csharplangspec-md.md)]  
  
## Vea también  
 [Referencia de C\#](../../../csharp/language-reference/index.md)   
 [Guía de programación de C\#](../../../csharp/programming-guide/index.md)   
 [Palabras clave de C\#](../../../csharp/language-reference/keywords/index.md)   
 [base](../../../csharp/language-reference/keywords/base.md)   
 [Métodos](../../../csharp/programming-guide/classes-and-structs/methods.md)