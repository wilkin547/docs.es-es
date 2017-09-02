---
title: "Expresiones de valor predeterminado (Guía de programación de C#)"
description: Las expresiones de valor predeterminado generan el valor predeterminado de cualquier tipo de referencia o valor.
ms.date: 2017-08-23
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
helpviewer_keywords:
- generics [C#], default keyword
- default keyword [C#], generic programming
ms.assetid: b9daf449-4e64-496e-8592-6ed2c8875a98
caps.latest.revision: 22
author: BillWagner
ms.author: wiwagn
ms.translationtype: HT
ms.sourcegitcommit: 0dc2fcee3903b80816c98bab47e2b9a2e5ef78b0
ms.openlocfilehash: 7b5b53d7ed92c6f6377a3e494daf1d02a4cf0934
ms.contentlocale: es-es
ms.lasthandoff: 08/28/2017

---
# <a name="default-value-expressions-c-programming-guide"></a>Expresiones de valor predeterminado (Guía de programación de C#)

Una expresión de valor predeterminado genera el valor predeterminado de un tipo. Las expresiones de valor predeterminado son particularmente útiles en clases y métodos genéricos. Un problema que aparece tras usar elementos genéricos es cómo asignar un valor predeterminado a un `T` de tipo parametrizado cuando no conoce la información siguiente de antemano:

- Si `T` es un tipo de referencia o un tipo de valor.
- Si `T` es un tipo de valor, un valor numérico o una estructura definida por el usuario.

 Dada una variable `t` de un `T` de tipo parametrizado, la instrucción `t = null` solo es válida si `T` es un tipo de referencia. La asignación `t = 0` solo funciona para los tipos de valor numérico, pero no para las estructuras. La solución consiste en usar una expresión de valor predeterminado, que devuelve `null` para los tipos de referencia (tipos de clase y de interfaz) y cero para los tipos de valor numérico. Para las estructuras definidas por el usuario, devuelve la estructura inicializada con el patrón de bit cero, lo que produce 0 o `null` para cada miembro dependiendo de si es un tipo de valor o referencia. Para los tipos de valor que aceptan valores NULL, `default` devuelve un <xref:System.Nullable%601?displayProperty=fullName>, que se inicializa como cualquier estructura.

La expresión `default(T)` no se limita a métodos y clases genéricas. Las expresiones de valor predeterminado pueden usarse con cualquier tipo administrado. Cualquiera de estas expresiones es válida:

 [!code-cs[csProgGuideGenerics#1](../../../../samples/snippets/csharp/programming-guide/statements-expressions-operators/default-value-expressions.cs)]

 El ejemplo siguiente de la clase `GenericList<T>` muestra cómo usar el operador `default(T)` en una clase genérica. Para obtener más información, vea [Información general de genéricos](../generics/introduction-to-generics.md).

 [!code-cs[csProgGuideGenerics#2](../../../../samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideGenerics/CS/Generics.cs#Snippet41)]

## <a name="default-literal-and-type-inference"></a>Literal e inferencia de tipo predeterminados

A partir de C# 7.1, el literal `default` puede usarse para las expresiones de valor predeterminado cuando el compilador puede deducir el tipo de expresión. El literal `default` genera el mismo valor que el equivalente `default(T)` cuando se deduce el tipo `T`. Esto puede simplificar el código disminuyendo la redundancia al declarar un tipo más de una vez. El literal `default` puede usarse en cualquiera de las ubicaciones siguientes:

- inicializador de variable
- asignación de variables
- Declarar el valor predeterminado de un parámetro opcional
- Proporcionar el valor de un argumento de método de llamada
- Devolver la instrucción (o una expresión de un miembro con cuerpo de expresión)

El ejemplo siguiente muestra varios usos del literal `default` en una expresión de valor predeterminado:

[!code-cs[csProgGuideGenerics#3](../../../../samples/snippets/csharp/programming-guide/statements-expressions-operators/default-literal.cs)]

## <a name="see-also"></a>Vea también

 <xref:System.Collections.Generic> [Guía de programación de C#](../index.md)   
 [Genéricos](../generics/index.md)   
 [Métodos genéricos](../generics/generic-methods.md)   
 [Genéricos](~/docs/standard/generics/index.md)   

