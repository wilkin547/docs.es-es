---
title: Novedades de C# 7.2
description: "Información general sobre las nuevas características de C# 7.2."
keywords: "Diseño del lenguaje C#, 7.2, Visual Studio 2017"
author: billwagner
ms.author: wiwagn
ms.date: 08/16/2017
ms.topic: article
ms.prod: .net
ms.devlang: devlang-csharp
ms.openlocfilehash: a580a4a3a0a49e97ea8fb96699d1d978a9bc0a64
ms.sourcegitcommit: 7e99f66ef09d2903e22c789c67ff5a10aa953b2f
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/18/2017
---
# <a name="whats-new-in-c-72"></a>Novedades de C# 7.2

C# 7.2 es otra versión de punto que agrega un número de características útiles.
Un tema para esta versión funciona más eficazmente con tipos de valor al evitar la copia innecesaria o asignaciones. 

Las características restantes son pequeños, nice tienen.

7.2 C# usa el [selección de la versión de idioma](csharp-7-1.md#language-version-selection) elemento de configuración para seleccionar la versión de idioma de compilador.

Las nuevas características de lenguaje en esta versión son:

* [Semántica de referencia con tipos de valor](#reference-semantics-with-value-types)
  - Una combinación de mejoras de sintaxis que permiten trabajar con tipos de valor mediante la semántica de referencia.
* [No son finales argumentos con nombre](#non-trailing-named-arguments)
  - Argumentos con nombre pueden ir seguidos de argumentos posicionales.
* [Carácter de subrayado inicial en literales numéricos](#leading-underscores-in-numeric-literals)
  - Literales numéricos ahora pueden tener caracteres de subrayado iniciales antes de los dígitos impresos.
* [`private protected`modificador de acceso](#private-protected)
  - El `private protected` modificador de acceso permite el acceso para las clases derivadas en el mismo ensamblado.

## <a name="reference-semantics-with-value-types"></a>Semántica de referencia con tipos de valor

Características de lenguaje incluidas en 7.2 permiten trabajar con tipos de valor al usar la semántica de referencia. Están diseñadas para aumentar el rendimiento, pues minimiza las copias de los tipos de valor sin incurrir en las asignaciones de memoria asociadas al uso de tipos de referencia. Las características incluyen:

 - El `in` modificador de parámetros, para especificar que un argumento se pasa por referencia pero no modifica el método llamado.
 - El `ref readonly` modificador en el método devuelve, para indicar que un método devuelve su valor por referencia, pero no permite operaciones de escritura en ese objeto.
 - El `readonly struct` declaración, para indicar que un struct es inmutable y se debe pasar como un `in` parámetro a sus métodos de miembro.
 - El `ref struct` declaración, para indicar que un tipo de estructura tiene acceso directo a memoria administrada y siempre debe ser pila asignada.

Puede obtener más información acerca de todos los cambios en [con semántica de referencias a tipos de valor](../reference-semantics-with-value-types.md).

## <a name="non-trailing-named-arguments"></a>No son finales argumentos con nombre

Llamadas de método ahora pueden usar argumentos con nombre que preceden a los argumentos posicionales cuando los argumentos con nombre se encuentran en las posiciones correctas. Para obtener más información, consulte [argumentos opcionales y con nombre](../programming-guide/classes-and-structs/named-and-optional-arguments.md).

## <a name="leading-underscores-in-numeric-literals"></a>Carácter de subrayado inicial en literales numéricos

La implementación de la compatibilidad con separadores de dígitos en C# 7.0 no permitió la `_` a ser el primer carácter del valor literal. Hex y literales numéricos binarios ahora pueden empezar con un `_`. 

Por ejemplo:

```csharp
int binaryValue = 0b_0101_0101;
```

## `private protected`

Por último, un nuevo modificador de acceso compuestos: `private protected` indica que las clases derivadas que se declaran en el mismo ensamblado puede tener acceso a un miembro. Mientras `protected internal` permite el acceso a las clases derivadas o las clases que se encuentran en el mismo ensamblado, `private protected` limita el acceso a los tipos derivados que se declaran en el mismo ensamblado.

Para obtener más información, consulte [los modificadores de acceso](../language-reference/keywords/access-modifiers.md) en la referencia del lenguaje.
