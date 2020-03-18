---
title: Novedades de C# 7.2
description: Información general sobre las nuevas características en C# 7.2.
ms.date: 08/16/2017
ms.openlocfilehash: 7febefb81bbea6f24690adb05488ad6a18bbf552
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/14/2020
ms.locfileid: "75694600"
---
# <a name="whats-new-in-c-72"></a>Novedades de C# 7.2

C# 7.2 es otra versión de punto que agrega varias características útiles.
Una de las ventajas de esta versión es que funciona mejor con tipos de valor, ya que evita copias o asignaciones innecesarias.

El resto de características son menos importantes, pero igualmente útiles.

C# 7.2 usa el elemento de configuración de [selección de versión de lenguaje](../language-reference/configure-language-version.md) para seleccionar la versión del lenguaje del compilador.

Las nuevas características de lenguaje de esta versión son las siguientes:

- [Técnicas para escribir código eficiente seguro](#safe-efficient-code-enhancements)
  - Una combinación de mejoras en la sintaxis que permiten trabajar con tipos de valor mediante la semántica de referencia.
- [Argumentos con nombre no finales](#non-trailing-named-arguments)
  - Los argumentos con nombre pueden ir seguidos de argumentos posicionales.
- [Caracteres de subrayado iniciales en literales numéricos](#leading-underscores-in-numeric-literals)
  - Los literales numéricos ahora pueden tener caracteres de subrayado iniciales antes de los dígitos impresos.
- [Modificador de acceso `private protected`](#private-protected-access-modifier)
  - El modificador de acceso `private protected` permite el acceso de clases derivadas en el mismo ensamblado.
- [Expresiones `ref` condicionales](#conditional-ref-expressions)
  - El resultado de una expresión condicional (`?:`) ahora puede ser una referencia.

En el resto de este artículo se proporciona información general sobre cada característica. Para cada característica, conocerá el razonamiento subyacente. Aprenderá la sintaxis. Puede explorar estas características en su entorno mediante la herramienta global `dotnet try`:

1. Instale la herramienta global [dotnet-try](https://github.com/dotnet/try/blob/master/README.md#setup).
1. Clone el repositorio [dotnet/try-samples](https://github.com/dotnet/try-samples).
1. Establezca el directorio actual en el subdirectorio *csharp7* para el repositorio *try-samples*.
1. Ejecute `dotnet try`.

## <a name="safe-efficient-code-enhancements"></a>Mejoras de código eficiente seguro

Las características de lenguaje que presenta la versión 7.2 permiten trabajar con tipos de valor usando la semántica de referencia. Están diseñadas para aumentar el rendimiento minimizando la copia de tipos de valor sin usar las asignaciones de memoria asociadas al uso de tipos de referencia. Las características incluyen:

- El modificador `in` en los parámetros para especificar que un argumento se pasa mediante una referencia sin que el método al que se realiza una llamada lo modifique. Agregar el modificador `in` a un argumento es un [cambio compatible con el origen](version-update-considerations.md#source-compatible-changes).
- El modificador `ref readonly` en las devoluciones de método para indicar que un método devuelve su valor mediante una referencia, pero que no permite operaciones de escritura en el objeto. Agregar el modificador `ref readonly` es un [cambio compatible con el origen](version-update-considerations.md#source-compatible-changes), si el resultado devuelto se asigna a un valor. Agregar el modificador `readonly` a una instrucción return `ref` existente es un [cambio incompatible](version-update-considerations.md#incompatible-changes). Requiere que los autores de las llamadas actualicen la declaración de las variables locales `ref` para incluir el modificador `readonly`.
- La declaración `readonly struct` para indicar que una estructura es fija y que debería pasarse como parámetro `in` a los métodos de su miembro. Agregar el modificador `readonly` a una declaración struct existente es un [cambio compatible con un elemento binario](version-update-considerations.md#binary-compatible-changes).
- La declaración `ref struct` para indicar que un tipo de estructura tiene acceso directo a la memoria administrada y que siempre debe estar asignada a la pila. Agregar el modificador `ref` a una declaración `struct` existente es un [cambio incompatible](version-update-considerations.md#incompatible-changes). Un elemento `ref struct` no puede ser un miembro de una clase o usarse en otras ubicaciones donde puede asignarse en el montón.

Puede leer más información sobre todos estos cambios en [Write safe efficient code](../write-safe-efficient-code.md) (Escribir código eficiente seguro).

## <a name="non-trailing-named-arguments"></a>Argumentos con nombre no finales

Las llamadas de método ya pueden usar argumentos con nombre que precedan a argumentos posicionales si están en la posición adecuada. Para obtener más información, vea [Argumentos opcionales y con nombre](../programming-guide/classes-and-structs/named-and-optional-arguments.md).

## <a name="leading-underscores-in-numeric-literals"></a>Caracteres de subrayado iniciales en literales numéricos

La implementación de la compatibilidad con separadores de dígitos en C# 7.0 no permitía que `_` fuera el primer carácter del valor literal. Los literales numéricos hexadecimales y binarios ya pueden empezar con un `_`.

Por ejemplo:

```csharp
int binaryValue = 0b_0101_0101;
```

## <a name="private-protected-access-modifier"></a>Modificador de acceso *private protected*

Presentamos un nuevo modificador de acceso compuesto: `private protected` indica que se puede tener acceso a un miembro mediante una clase o clases derivadas declaradas en un mismo ensamblado. Mientras que `protected internal` permite el acceso a las clases derivadas o clases que se encuentran en un mismo ensamblado, `private protected` limita el acceso a los tipos derivados que se declaran en un mismo ensamblado.

Para obtener más información, vea los [modificadores de acceso](../language-reference/keywords/access-modifiers.md) en el material de referencia del lenguaje.

## <a name="conditional-ref-expressions"></a>Expresiones `ref` condicionales

Por último, la expresión condicional puede producir un resultado de referencia en lugar de un resultado de valor. Por ejemplo, podría escribir lo siguiente para recuperar una referencia al primer elemento en una de dos matrices:

```csharp
ref var r = ref (arr != null ? ref arr[0] : ref otherArr[0]);
```

La variable `r` es una referencia al primer valor de `arr` o `otherArr`.

Para más información, vea el [operador condicional (?:)](../language-reference/operators/conditional-operator.md) en la referencia del lenguaje.
