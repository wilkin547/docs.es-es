---
title: Novedades de C# 7.2
description: "Información general sobre las nuevas características en C# 7.2."
keywords: "Diseño del lenguaje C#, 7.2, Visual Studio 2017,"
author: billwagner
ms.author: wiwagn
ms.date: 08/16/2017
ms.topic: article
ms.prod: .net
ms.devlang: devlang-csharp
ms.openlocfilehash: db22c9251fa5e9f5a9cb66af6ec8b193b88e0eb3
ms.sourcegitcommit: 83dd5ec003e788ccb3e33f3412a7af39ae347646
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/15/2018
---
# <a name="whats-new-in-c-72"></a>Novedades de C# 7.2

C# 7.2 es otra versión de punto que agrega varias características útiles.
Una de las ventajas de esta versión es que funciona mejor con tipos de valor, ya que evita copias o asignaciones innecesarias. 

El resto de características son menos importantes, pero igualmente útiles.

C# 7.2 usa el elemento de configuración de [selección de versión de lenguaje](csharp-7-1.md#language-version-selection) para seleccionar la versión del lenguaje del compilador.

Las nuevas características de lenguaje de esta versión son las siguientes:

* [Semántica de referencia con tipos de valor](#reference-semantics-with-value-types)
  - Una combinación de mejoras en la sintaxis que permiten trabajar con tipos de valor mediante la semántica de referencia.
* [Argumentos con nombre no finales](#non-trailing-named-arguments)
  - Los argumentos con nombre pueden ir seguidos de argumentos posicionales.
* [Caracteres de subrayado iniciales en literales numéricos](#leading-underscores-in-numeric-literals)
  - Los literales numéricos ahora pueden tener caracteres de subrayado iniciales antes de los dígitos impresos.
* [Modificador de acceso `private protected`](#private-protected-access-modifier)
  - El modificador de acceso `private protected` permite el acceso de clases derivadas en el mismo ensamblado.

## <a name="reference-semantics-with-value-types"></a>Semántica de referencia con tipos de valor

Las características de lenguaje que presenta la versión 7.2 permiten trabajar con tipos de valor usando la semántica de referencia. Están diseñadas para aumentar el rendimiento minimizando la copia de tipos de valor sin usar las asignaciones de memoria asociadas al uso de tipos de referencia. Las características incluyen:

 - El modificador `in` en los parámetros para especificar que un argumento se pasa mediante una referencia sin que el método al que se realiza una llamada lo modifique.
 - El modificador `ref readonly` en las devoluciones de método para indicar que un método devuelve su valor mediante una referencia, pero que no permite operaciones de escritura en el objeto.
 - La declaración `readonly struct` para indicar que una estructura es fija y que debería pasarse como parámetro `in` a los métodos de su miembro.
 - La declaración `ref struct` para indicar que un tipo de estructura tiene acceso directo a la memoria administrada y que siempre debe estar asignada a la pila.

Puede obtener más información sobre todos los cambios en [Semántica de referencia con tipos de valor](../reference-semantics-with-value-types.md).

## <a name="non-trailing-named-arguments"></a>Argumentos con nombre no finales

Las llamadas de método ya pueden usar argumentos con nombre que precedan a argumentos posicionales si están en la posición adecuada. Para obtener más información, vea [Argumentos opcionales y con nombre](../programming-guide/classes-and-structs/named-and-optional-arguments.md).

## <a name="leading-underscores-in-numeric-literals"></a>Caracteres de subrayado iniciales en literales numéricos

La implementación de la compatibilidad con separadores de dígitos en C# 7.0 no permitía que `_` fuera el primer carácter del valor literal. Los literales numéricos hexadecimales y binarios ya pueden empezar con un `_`. 

Por ejemplo:

```csharp
int binaryValue = 0b_0101_0101;
```

## <a name="private-protected-access-modifier"></a>Modificador de acceso _private protected_

Por último, presentamos un nuevo modificador de acceso compuesto: `private protected` indica que se puede tener acceso a un miembro mediante una clase o clases derivadas declaradas en un mismo ensamblado. Mientras que `protected internal` permite el acceso a las clases derivadas o clases que se encuentran en un mismo ensamblado, `private protected` limita el acceso a los tipos derivados que se declaran en un mismo ensamblado.

Para obtener más información, vea los [modificadores de acceso](../language-reference/keywords/access-modifiers.md) en el material de referencia del lenguaje.
