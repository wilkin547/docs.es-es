---
title: when (Referencia de C#)
ms.date: 03/07/2017
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- when_CSharpKeyword
- when
helpviewer_keywords:
- when keyword [C#]
ms.assetid: dd543335-ae37-48ac-9560-bd5f047b9aea
caps.latest.revision: 
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: f453d9f4b443d7adeeb0ab628b4ddad1a0116e49
ms.sourcegitcommit: 7e99f66ef09d2903e22c789c67ff5a10aa953b2f
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/18/2017
---
 # <a name="when-c-reference"></a>when (Referencia de C#)

Puede usar la palabra clave contextual `when` para especificar una condición de filtro en dos contextos:

- En la instrucción `catch` de un bloque [try/catch](try-catch.md) o [try/catch/finally](try-catch-finally.md).
- En la etiqueta `case` de una instrucción [switch](switch.md).

## <a name="when-in-a-catch-statement"></a>`when` en una instrucción `catch`

A partir de C# 6, puede usarse `When` en una instrucción `catch` para especificar una condición que debe cumplirse para que el controlador de una excepción específica se ejecute. Su sintaxis es:

```csharp
catch ExceptionType [e] when (expr)
```
donde *expr* es una expresión que se evalúa como un valor booleano. Si devuelve `true`, el controlador de excepciones se ejecuta; si devuelve `false`, no se ejecuta. 

En el ejemplo siguiente se usa la palabra clave `when` para ejecutar condicionalmente controladores para una <xref:System.Net.Http.HttpRequestException> según el texto del mensaje de excepción.

 [!code-csharp[when-with-catch](../../../../samples/snippets/csharp/language-reference/keywords/when/catch.cs)]  
  
## <a name="when-in-a-switch-statement"></a>`when` en una instrucción `switch`

A partir de 7, las etiquetas `case` ya no tienen que ser mutuamente exclusivas y el orden con el que las etiquetas `case` aparecen en una instrucción `switch` puede determinar el bloque switch que se ejecuta. Puede usarse la palabra clave `when` para especificar una condición de filtro que haga que su etiqueta case asociada se cumpla únicamente si también se cumple la condición de filtro. Su sintaxis es:

```csharp
case (expr) when (when-condition):
```
donde *expr* es un patrón de constante o un patrón de tipo que se compara con la expresión match y *when-condition* es cualquier expresión booleana. 

En el ejemplo siguiente se usa la palabra clave `when` para probar objetos `Shape` que tienen un área de cero, así como para probar una serie de objetos `Shape` que tienen un área mayor que cero. 

 [!code-csharp[when-with-case#1](../../../../samples/snippets/csharp/language-reference/keywords/when/when.cs#1)]  

## <a name="see-also"></a>Vea también 
  [switch (Instrucción)](switch.md)  
  [try/catch (Instrucción)](try-catch.md)  
  [try/catch/finally (Instrucción)](try-catch-finally.md) 

