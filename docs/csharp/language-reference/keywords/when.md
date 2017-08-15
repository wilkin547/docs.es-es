---
title: when (Referencia de C#)
ms.date: 2017-03-07
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- when_CSharpKeyword
- when
dev_langs:
- CSharp
helpviewer_keywords:
- when keyword [C#]
ms.assetid: dd543335-ae37-48ac-9560-bd5f047b9aea
caps.latest.revision: 30
author: BillWagner
ms.author: wiwagn
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: ae869fa04d2dfb963694f258624c5cd594ff1184
ms.contentlocale: es-es
ms.lasthandoff: 07/28/2017

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

En el ejemplo siguiente se usa la palabra clave `when` para ejecutar condicionalmente controladores para una @System.Net.HttpRequestException según el texto del mensaje de excepción.

 [!code-cs[when-with-catch](../../../../samples/snippets/csharp/language-reference/keywords/when/catch.cs)]  
  
## <a name="when-in-a-switch-statement"></a>`when` en una instrucción `switch`

A partir de 7, las etiquetas `case` ya no tienen que ser mutuamente exclusivas y el orden con el que las etiquetas `case` aparecen en una instrucción `switch` puede determinar el bloque switch que se ejecuta. Puede usarse la palabra clave `when` para especificar una condición de filtro que haga que su etiqueta case asociada se cumpla únicamente si también se cumple la condición de filtro. Su sintaxis es:

```csharp
case (expr) when (when-condition):
```
donde *expr* es un patrón de constante o un patrón de tipo que se compara con la expresión match y *when-condition* es cualquier expresión booleana. 

En el ejemplo siguiente se usa la palabra clave `when` para probar objetos `Shape` que tienen un área de cero, así como para probar una serie de objetos `Shape` que tienen un área mayor que cero. 

 [!code-cs[when-with-case#1](../../../../samples/snippets/csharp/language-reference/keywords/when/when.cs#1)]  

## <a name="see-also"></a>Vea también 
  [switch (Instrucción)](switch.md)  
  [try/catch (Instrucción)](try-catch.md)  
  [try/catch/finally (Instrucción)](try-catch-finally.md) 


