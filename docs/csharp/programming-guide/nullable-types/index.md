---
title: "Tipos que aceptan valores NULL (Guía de programación de C#) | Microsoft Docs"
ms.date: 2017-05-15
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- nullable types [C#]
- C# language, nullable types
- types [C#], nullable
ms.assetid: e473cb01-28ca-42be-9cea-f717055d72c6
caps.latest.revision: 44
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
ms.translationtype: Human Translation
ms.sourcegitcommit: 829c604f9bafce03b7008cbb768371a1a08de222
ms.openlocfilehash: 2d13fdbef24ee16855261a3c1e26d7fca4f986f2
ms.contentlocale: es-es
ms.lasthandoff: 06/12/2017

---
<a id="nullable-types-c-programming-guide" class="xliff"></a>

# Tipos que aceptan valores NULL (Guía de programación de C#)
Los tipos que aceptan valores NULL son instancias de la estructura <xref:System.Nullable%601?displayProperty=fullName>. Un tipo que acepta valores NULL puede representar el intervalo de valores correcto para su tipo de valor subyacente, además de un valor `null` adicional correcto. Por ejemplo, a un valor `Nullable<Int32>`, también conocido como "Nullable of Int32", se le puede asignar cualquier valor comprendido entre -2147483648 y 2147483647, o se le puede asignar el valor `null`. A `Nullable<bool>` se le pueden asignar los valores [true](../../../csharp/language-reference/keywords/true.md), [false](../../../csharp/language-reference/keywords/false.md) o [null](../../../csharp/language-reference/keywords/null.md). La capacidad de asignar `null` a tipos numéricos y booleanos resulta especialmente útil cuando se trabaja con bases de datos y otros tipos de datos que contienen elementos a los que no se les puede asignar ningún valor. Por ejemplo, un campo booleano en una base de datos puede almacenar los valores `true` o `false`, o puede ser indefinido. 
  
[!code-cs[tipos que aceptan valores NULL](../../../../samples/snippets/csharp/programming-guide/nullable-types/nullable-ex1.cs)]  
  
Para obtener más ejemplos, vea [Utilizar tipos que aceptan valores NULL](../../../csharp/programming-guide/nullable-types/using-nullable-types.md).  
  
<a id="nullable-types-overview" class="xliff"></a>

## Información general sobre tipos que aceptan valores NULL  
 Los tipos que aceptan valores NULL tienen la siguientes características:  
  
-   Los tipos que aceptan valores NULL representan variables de tipo de valor a las que se puede asignar el valor `null`. No se puede crear un tipo que acepta valores NULL basado en un tipo de referencia. (Los tipos de referencia ya admiten el valor `null`).  
  
-   La sintaxis `T?` es una abreviatura de <xref:System.Nullable%601>, donde `T` es un tipo de valor. Las dos formas son intercambiables.  
  
-   Asigne un valor a un tipo que acepta valores NULL tal como lo haría para un tipo de valor normal, por ejemplo `int? x = 10;` o `double? d = 4.108`. A un tipo que acepta valores NULL también se le puede asignar el valor `null`: `int? x = null.`.  
  
-   Use el método <xref:System.Nullable%601.GetValueOrDefault%2A?displayProperty=fullName> para devolver el valor asignado, o bien el valor predeterminado para el tipo subyacente si el valor es `null`, por ejemplo, `int j = x.GetValueOrDefault();`.  
  
-   Use las propiedades de solo lectura <xref:System.Nullable%601.HasValue%2A> y <xref:System.Nullable%601.Value%2A> para probar si hay valores NULL y recuperar el valor, como se muestra en el ejemplo siguiente: `if(x.HasValue) j = x.Value;`  
  
    -   La propiedad `HasValue` devuelve `true` si la variable contiene un valor, o `false` si es `null`.  
  
    -   La propiedad `Value` devuelve un valor si se asigna uno. De lo contrario, se produce una excepción <xref:System.InvalidOperationException?displayProperty=fullName>.  
  
    -   El valor predeterminado de `HasValue` es `false`. La propiedad `Value` no tiene ningún valor predeterminado.  
  
    -   También puede utilizar los operadores `==` y `!=` con un tipo que acepta valores NULL, como se muestra en el ejemplo siguiente: `if (x != null) y = x;`  
  
-   Utilice el operador `??` para asignar un valor predeterminado que se aplicará cuando un tipo que acepta valores NULL cuyo valor actual es `null` se asigna a un tipo que no acepta valores NULL, por ejemplo `int? x = null; int y = x ?? -1;`  
  
-   No se permiten los tipos anidados que aceptan valores NULL. La línea siguiente no se compilará: `Nullable<Nullable<int>> n;`  
  
<a id="related-sections" class="xliff"></a>

## Secciones relacionadas  
 Para obtener más información:  
  
-   [Utilizar tipos que aceptan valores NULL](../../../csharp/programming-guide/nullable-types/using-nullable-types.md)  
  
-   [Aplicar la conversión boxing a tipos que aceptan valores NULL](../../../csharp/programming-guide/nullable-types/boxing-nullable-types.md)  
  
-   [Operador ??](../../../csharp/language-reference/operators/null-conditional-operator.md)  
  
<a id="c-language-specification" class="xliff"></a>

## Especificación del lenguaje C#  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
<a id="see-also" class="xliff"></a>

## Vea también  
 <xref:System.Nullable>   
 [Guía de programación de C#](../../../csharp/programming-guide/index.md)   
 [C#](../../../csharp/csharp.md)   
 [Referencia de C#](../../../csharp/language-reference/index.md)   
 [¿Qué significa exactamente "elevado"?](http://go.microsoft.com/fwlink/?LinkId=112382)

