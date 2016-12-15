---
title: "C&#243;mo: Saber las diferencias entre pasar a un m&#233;todo un struct y una referencia a clase (Gu&#237;a de programaci&#243;n de C#) | Microsoft Docs"
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
  - "métodos [C#], pasar clases y structs"
  - "pasar parámetros [C#], structs y clases"
  - "structs [C#], pasar como parámetro de método"
ms.assetid: 9c1313a6-32a8-4ea7-a59f-450f66af628b
caps.latest.revision: 25
caps.handback.revision: 25
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# C&#243;mo: Saber las diferencias entre pasar a un m&#233;todo un struct y una referencia a clase (Gu&#237;a de programaci&#243;n de C#)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

El ejemplo siguiente muestra cómo pasar [struct](../../../csharp/language-reference/keywords/struct.md) a un método diferencia de pasar una instancia de [clase](../../../csharp/language-reference/keywords/class.md) a un método.  En el ejemplo, los dos argumentos \(struct e instancia de clase\) se pasan por valor, y ambos métodos cambie el valor de un campo de argumento.  Sin embargo, los resultados de los dos métodos no son iguales porque se pasan qué cuando se pasa un struct diferencia se pasa de qué cuando se pasa una instancia de una clase.  
  
 Dado que un struct es [tipo de valor](../../../csharp/language-reference/keywords/value-types.md), al [pase un struct por valor](../../../csharp/programming-guide/classes-and-structs/passing-value-type-parameters.md) a un método, el método recibe y funciona en una copia del argumento de struct.  El método no tiene ningún acceso a struct original en el método de llamada y por tanto no puede cambiarlo de ningún modo.  El método sólo puede cambiar la copia.  
  
 Una instancia de clase es [tipo de referencia](../../../csharp/language-reference/keywords/reference-types.md), no un tipo de valor.  cuando [un tipo de referencia se pasa por valor](../../../csharp/programming-guide/classes-and-structs/passing-reference-type-parameters.md) a un método, el método recibe una copia de la referencia a la instancia de clase.  Es decir, el método recibe una copia de la dirección de la instancia, no una copia de la propia instancia.  La instancia de clase en el método de llamada tiene una dirección, el parámetro en el método denominado tiene una copia de la dirección, y ambas direcciones hacen referencia al mismo objeto.  Dado que el parámetro contiene sólo una copia de la dirección, el método denominado no puede cambiar la dirección de la instancia de clase en el método de llamada.  Sin embargo, el método denominado puede utilizar la dirección para obtener acceso a los miembros de clase que tanto la dirección original y la copia hace referencia.  Si el método denominado cambia a un miembro de clase, la instancia de clase original en la llamada del método los cambios también.  
  
 El resultado del ejemplo siguiente muestra la diferencia.  El valor del campo de `willIChange` de la instancia de clase se cambia por la llamada al método `ClassTaker` porque el método utiliza la dirección del parámetro para encontrar el campo especificado de la instancia de clase.  El campo de `willIChange` struct en el método de llamada no se cambia por la llamada al método `StructTaker` porque el valor del argumento es una copia del struct propia, no una copia de la dirección.  `StructTaker` cambia la copia, y se perderá la copia cuando la llamada a `StructTaker` se completa.  
  
## Ejemplo  
 [!code-cs[csProgGuideObjects#32](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/how-to-know-the-difference-passing-a-struct-and-passing-a-class-to-a-method_1.cs)]  
  
## Vea también  
 [Guía de programación de C\#](../../../csharp/programming-guide/index.md)   
 [Clases](../../../csharp/programming-guide/classes-and-structs/classes.md)   
 [Structs](../../../csharp/programming-guide/classes-and-structs/structs.md)   
 [Pasar parámetros](../../../csharp/programming-guide/classes-and-structs/passing-parameters.md)