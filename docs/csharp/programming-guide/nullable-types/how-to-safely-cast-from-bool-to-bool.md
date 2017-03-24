---
title: "C&#243;mo: Convertir con seguridad de bool? en bool (Gu&#237;a de programaci&#243;n de C#) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "conversión [C#], tipos que aceptan valores NULL"
  - "tipos que aceptan valores NULL [C#], convertir bool? a bool"
ms.assetid: e06e4274-a443-422d-8ef1-9dbf9df55237
caps.latest.revision: 9
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 9
---
# C&#243;mo: Convertir con seguridad de bool? en bool (Gu&#237;a de programaci&#243;n de C#)
El tipo `bool?`, que acepta valores NULL, puede tener tres valores diferentes: `true`, `false` y `null`.  Por consiguiente, el tipo `bool?` no se puede utilizar en instrucciones condicionales con `if`, `for` o `while`.  Por ejemplo, el código siguiente provoca un error del compilador.  
  
```  
bool? b = null;  
if (b) // Error CS0266.  
{  
}  
```  
  
 Esto no está permitido porque el significado de `null` en el contexto de una instrucción condicional es incierto.  Para utilizar un tipo `bool?` en una instrucción condicional, compruebe primero su propiedad <xref:System.Nullable%601.HasValue%2A> para asegurarse de que su valor no es `null`, y, a continuación, conviértalo a `bool`.  Para obtener más información, vea [bool](../../../csharp/language-reference/keywords/bool.md).  Si convierte un tipo `bool?` que tiene un valor `null`, se producirá una excepción <xref:System.InvalidOperationException> durante la comprobación de instrucciones condicionales.  En el ejemplo siguiente se muestra una manera segura de convertir `bool?` en `bool`:  
  
## Ejemplo  
  
```c#  
bool? test = null;  
// Other code that may or may not  
// give a value to test.  
if(!test.HasValue) //check for a value  
{  
    // Assume that IsInitialized  
    // returns either true or false.  
    test = IsInitialized();  
}  
if((bool)test) //now this cast is safe  
{  
   // Do something.  
}  
```  
  
## Vea también  
 [Guía de programación de C\#](../../../csharp/programming-guide/index.md)   
 [Palabras clave de literales](../../../csharp/language-reference/keywords/literal-keywords.md)   
 [Tipos que aceptan valores NULL](../../../csharp/programming-guide/nullable-types/index.md)   
 [Operador ??](../../../csharp/language-reference/operators/null-conditional-operator.md)