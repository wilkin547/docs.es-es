---
title: "override (Referencia de C#) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
f1_keywords: 
  - "override"
  - "override_CSharpKeyword"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "override (palabra clave) [C#]"
ms.assetid: dd1907a8-acf8-46d3-80b9-c2ca4febada8
caps.latest.revision: 26
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 26
---
# override (Referencia de C#)
El modificador `override` es necesario para ampliar o modificar la implementación abstracta o virtual de un método, propiedad, indizador o evento heredado.  
  
## Ejemplo  
 En este ejemplo, la clase `Square` debe proporcionar una implementación de invalidación de `Area` porque ésta se hereda de la clase abstracta `ShapesClass`:  
  
 [!code-cs[csrefKeywordsModifiers#1](../../../csharp/language-reference/keywords/codesnippet/CSharp/override_1.cs)]  
  
 Un método `override` proporciona una nueva implementación de un miembro que se hereda de una clase base.  El método invalidado por una declaración `override` se conoce como método base invalidado.  El método base reemplazado debe tener la misma firma que el método `override`.  Para obtener más información sobre la herencia, vea [Herencia](../../../csharp/programming-guide/classes-and-structs/inheritance.md).  
  
 No se puede reemplazar un método estático o no virtual.  El método base reemplazado debe ser `virtual`, `abstract` u `override`.  
  
 Una declaración `override` no puede cambiar la accesibilidad del método `virtual`.  El método `override` y el método `virtual` deben tener el mismo [modificador de nivel de acceso](../../../csharp/language-reference/keywords/access-modifiers.md).  
  
 No se pueden usar los modificadores `new`, `static` o `virtual` para modificar un método `override`.  
  
 Una declaración de propiedad de invalidación debe especificar exactamente el mismo modificador de acceso, tipo y nombre que la propiedad heredada, y la propiedad invalidada debe ser `virtual`, `abstract` u `override`.  
  
 Para obtener más información sobre cómo utilizar la palabra clave `override`, vea [Control de versiones con las palabras clave Override y New](../../../csharp/programming-guide/classes-and-structs/versioning-with-the-override-and-new-keywords.md) y [Saber cuándo utilizar las palabras clave Override y New \(Guía de programación de C\#\)](../../../csharp/programming-guide/classes-and-structs/knowing-when-to-use-override-and-new-keywords.md).  
  
## Ejemplo  
 Este ejemplo define una clase base denominada `Employee` y una clase derivada denominada `SalesEmployee`.  La clase `SalesEmployee` incluye una propiedad adicional, `salesbonus`, e invalida el método `CalculatePay` para tenerlo en cuenta.  
  
 [!code-cs[csrefKeywordsModifiers#9](../../../csharp/language-reference/keywords/codesnippet/CSharp/override_2.cs)]  
  
## Especificación del lenguaje C\#  
 [!INCLUDE[CSharplangspec](../../../csharp/language-reference/keywords/includes/csharplangspec-md.md)]  
  
## Vea también  
 [Referencia de C\#](../../../csharp/language-reference/index.md)   
 [Guía de programación de C\#](../../../csharp/programming-guide/index.md)   
 [Herencia](../../../csharp/programming-guide/classes-and-structs/inheritance.md)   
 [Palabras clave de C\#](../../../csharp/language-reference/keywords/index.md)   
 [Modificadores](../../../csharp/language-reference/keywords/modifiers.md)   
 [abstractas](../../../csharp/language-reference/keywords/abstract.md)   
 [virtual](../../../csharp/language-reference/keywords/virtual.md)   
 [new](../../../csharp/language-reference/keywords/new.md)   
 [Polimorfismo](../../../csharp/programming-guide/classes-and-structs/polymorphism.md)