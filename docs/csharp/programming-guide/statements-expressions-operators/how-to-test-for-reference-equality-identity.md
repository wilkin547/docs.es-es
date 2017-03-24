---
title: "C&#243;mo: Probar la igualdad de referencias (identidad) (Gu&#237;a de programaci&#243;n de C#) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "identidad de objetos [C#]"
  - "igualdad de referencia [C#]"
ms.assetid: 91307fda-267b-4fd2-a338-2aada39ee791
caps.latest.revision: 13
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 13
---
# C&#243;mo: Probar la igualdad de referencias (identidad) (Gu&#237;a de programaci&#243;n de C#)
No tiene que implementar ninguna lógica personalizada para admitir las comparaciones de igualdad de referencias en los tipos.  Esta funcionalidad se proporciona para todos los tipos mediante el método <xref:System.Object.ReferenceEquals%2A?displayProperty=fullName> estático.  
  
 En el ejemplo siguiente se muestra cómo determinar si dos variables tienen *igualdad de referencia*, lo que significa que hacen referencia al mismo objeto en la memoria.  
  
 En el ejemplo también se muestra por qué <xref:System.Object.ReferenceEquals%2A?displayProperty=fullName> siempre devuelve `false` para los tipos de valor y por qué no se debe usar <xref:System.Object.ReferenceEquals%2A> para determinar la igualdad entre cadenas.  
  
## Ejemplo  
 [!code-cs[csProgGuideObjects#90](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/how-to-test-for-reference-equality-identity_1.cs)]  
  
 La implementación de `Equals` en la clase base universal <xref:System.Object?displayProperty=fullName> también realiza una comprobación de la igualdad de referencias; sin embargo, es mejor no seguir este procedimiento porque, en el caso de que una clase invalide el método, los resultados podrían no ser los esperados.  Lo mismo se cumple para los operadores `==` y `!=`.  Cuando se usan en tipos de referencia, el comportamiento predeterminado de \=\= y `!=` consiste en realizar una comprobación de la igualdad de referencias.  Sin embargo, las clases derivadas pueden sobrecargar el operador para realizar una comprobación de la igualdad de valores.  Para minimizar las posibilidades de error, lo mejor es usar siempre <xref:System.Object.ReferenceEquals%2A> cuando deba determinarse si dos objetos tienen igualdad de referencia.  
  
 El runtime siempre aplica el método Intern a las cadenas constantes dentro del mismo ensamblado.  Es decir, solo se conserva una instancia de cada cadena literal única.  Sin embargo, el runtime no garantiza que se vaya a aplicar el método Intern a las cadenas creadas en tiempo de ejecución, ni tampoco que dicho método se aplique a dos cadenas constantes iguales en distintos ensamblados.  
  
## Vea también  
 [Comparaciones de igualdad](../../../csharp/programming-guide/statements-expressions-operators/equality-comparisons.md)