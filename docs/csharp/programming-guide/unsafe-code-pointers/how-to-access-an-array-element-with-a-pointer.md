---
title: "C&#243;mo: Obtener acceso a un elemento de matriz con un puntero (Gu&#237;a de programaci&#243;n de C#) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "punteros [C#], acceso a matriz"
ms.assetid: 6c46f2af-a730-4855-8638-f136d9abaa12
caps.latest.revision: 16
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 16
---
# C&#243;mo: Obtener acceso a un elemento de matriz con un puntero (Gu&#237;a de programaci&#243;n de C#)
En un contexto no seguro, puede tener acceso a un elemento en memoria utilizando el acceso a elementos de puntero, como se muestra en el ejemplo siguiente:  
  
```  
 char* charPointer = stackalloc char[123];  
for (int i = 65; i < 123; i++)  
{  
    charPointer[i] = (char)i; //access array elements  
}  
```  
  
 La expresión entre corchetes debe poder convertirse implícitamente en `int`, `uint`, `long` o `ulong`.  La operación p\[e\] es equivalente a \*\(p\+e\).  Al igual que en C y C\+\+, el acceso al elemento de puntero no comprueba errores fuera de los límites.  
  
## Ejemplo  
 En este ejemplo, se asignan 123 ubicaciones de memoria a una matriz de caracteres, `charPointer`.  La matriz se utiliza para mostrar las letras en minúscula y en mayúscula en dos bucles [for](../../../csharp/language-reference/keywords/for.md).  
  
 Observe que la expresión `charPointer[i]` es equivalente a la expresión `*(charPointer + i)` y se puede obtener el mismo resultado utilizando cualquiera de las dos expresiones.  
  
 [!code-cs[csProgGuidePointers#11](../../../csharp/programming-guide/unsafe-code-pointers/codesnippet/CSharp/how-to-access-an-array-element-with-a-pointer_1.cs)]  
  
 [!code-cs[csProgGuidePointers#12](../../../csharp/programming-guide/unsafe-code-pointers/codesnippet/CSharp/how-to-access-an-array-element-with-a-pointer_2.cs)]  
  
  **Mayúsculas:**  
**ABCDEFGHIJKLMNOPQRSTUVWXYZ**  
**Minúsculas:**  
**abcdefghijklmnopqrstuvwxyz**   
## Vea también  
 [Guía de programación de C\#](../../../csharp/programming-guide/index.md)   
 [Expresiones de puntero](../../../csharp/programming-guide/unsafe-code-pointers/pointer-expressions.md)   
 [Tipos de puntero](../../../csharp/programming-guide/unsafe-code-pointers/pointer-types.md)   
 [Tipos](../../../csharp/language-reference/keywords/types.md)   
 [no seguras](../../../csharp/language-reference/keywords/unsafe.md)   
 [fixed \(Instrucción\)](../../../csharp/language-reference/keywords/fixed-statement.md)   
 [stackalloc](../../../csharp/language-reference/keywords/stackalloc.md)