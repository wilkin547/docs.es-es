---
title: 'Expresiones de C#: un paseo por el lenguaje C#'
description: Las expresiones, los operandos y los operadores son bloques de construcción del lenguaje C#.
ms.date: 11/06/2016
ms.assetid: 20d5eb10-7381-47b9-ad90-f1cc895aa27e
ms.openlocfilehash: 4ffe947a4cb8c36a5925a4b3846486e44a9d8ec4
ms.sourcegitcommit: 859b2ba0c74a1a5a4ad0d59a3c3af23450995981
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/11/2019
ms.locfileid: "59480760"
---
# <a name="expressions"></a>Expresiones

Las *expresiones* se construyen con *operandos* y *operadores*. Los operadores de una expresión indican qué operaciones se aplican a los operandos. Ejemplos de operadores incluyen `+`, `-`, `*`, `/` y `new`. Algunos ejemplos de operandos son literales, campos, variables locales y expresiones.

Cuando una expresión contiene varios operadores, la *precedencia* de los operadores controla el orden en que se evalúan los operadores individuales. Por ejemplo, la expresión `x + y * z` se evalúa como `x + (y * z)` porque el operador `*` tiene mayor precedencia que el operador `+`.

Cuando un operando se encuentra entre dos operadores con la misma precedencia, la *asociatividad* de los operadores controla el orden en que se realizan las operaciones:

* Excepto los operadores de asignación, todos los operadores binarios son *asociativos a la izquierda*, lo que significa que las operaciones se realizan de izquierda a derecha. Por ejemplo, `x + y + z` se evalúa como `(x + y) + z`.
* Los operadores de asignación y el operador condicional (`?:`) son *asociativos a la derecha*, lo que significa que las operaciones se realizan de derecha a izquierda. Por ejemplo, `x = y = z` se evalúa como `x = (y = z)`.

La precedencia y la asociatividad pueden controlarse mediante paréntesis. Por ejemplo, `x + y * z` primero multiplica `y` por `z` y luego suma el resultado a `x`, pero `(x + y) * z` primero suma `x` y `y` y luego multiplica el resultado por `z`.

La mayoría de los operadores se pueden *sobrecargar*. La sobrecarga de operador permite la especificación de implementaciones de operadores definidas por el usuario para operaciones donde uno o ambos operandos son de un tipo de struct o una clase definidos por el usuario.

A continuación se resumen los operadores de C#, con las categorías de operador en orden de precedencia de mayor a menor. Los operadores de la misma categoría tienen la misma precedencia. En cada categoría, hay una lista de expresiones de esa categoría junto con la descripción de ese tipo de expresión.

* Principal
  - `x.m`: Acceso a miembros
  - `x(...)`: Invocación de método y delegado
  - `x[...]`: Acceso a matriz e indizador
  - `x++`: Postincremento
  - `x--`: Postdecremento
  - `new T(...)`: Creación de objetos y delegados
  - `new T(...){...}`: creación de objetos con inicializador
  - `new {...}`:  inicializador de objetos anónimos
  - `new T[...]`: creación de matriz
  - `typeof(T)`: obtener el objeto <xref:System.Type> para `T`
  - `checked(x)`: Evaluar expresión en contexto comprobado
  - `unchecked(x)`: Evaluar expresión en contexto no comprobado
  - `default(T)`: obtener valor predeterminado de tipo `T`
  - `delegate {...}`: Función anónima (método anónimo)
* Unario
  - `+x`: identidad
  - `-x`: Negación
  - `!x`: Negación lógica
  - `~x`: Negación bit a bit
  - `++x`: Preincremento
  - `--x`: Predecremento
  - `(T)x`: convertir explícitamente `x` en el tipo `T`
  - `await x`: esperar asincrónicamente a que finalice `x`
* Multiplicativo
  - `x * y`: Multiplicación
  - `x / y`: División
  - `x % y`: Resto
* Aditivo
  - `x + y`: Suma, concatenación de cadenas, combinación de delegados
  - `x – y`: Resta, eliminación de delegados
* Shift
  - `x << y`: Desplazamiento a la izquierda
  - `x >> y`: Desplazamiento a la derecha
* Comprobación de tipos y relacional
  - `x < y`: Menor que
  - `x > y`: Mayor que
  - `x <= y`: Menor o igual que
  - `x >= y`: Mayor o igual que
  - `x is T`: volver a ejecutar `true` si `x` es una `T`, de lo contrario `false`
  - `x as T`: volver a ejecutar `x` con tipo `T`, o `null` si `x` no es una `T`
* Igualdad
  - `x == y`: Igual
  - `x != y`: No igual
* AND lógico
  - `x & y`: AND bit a bit entero, AND lógico booleano
* XOR lógico
  - `x ^ y`: XOR bit a bit entero, XOR lógico booleano
* OR lógico
  - `x | y`: OR bit a bit entero, OR lógico booleano
* AND condicional
  - `x && y`: evalúa `y` solo si `x` no es `false`
* OR condicional
  - `x || y`: evalúa `y` solo si `x` no es `true`
* Uso combinado de NULL
  - `x ?? y`: se evalúa como `y` si `x` es NULL, de lo contrario, como `x`
* Condicional
  - `x ? y : z`: se evalúa como `y` si `x` es `true` o `z` si `x` es `false`
* Asignación o función anónima
  - `x = y`: Asignación
  - `x op= y`: asignación compuesta; los operadores admitidos son
    - `*=`   `/=`   `%=`   `+=`   `-=`   `<<=`   `>>=`   `&=`  `^=`  `|=`
  - `(T x) => y`: Función anónima (expresión lambda)

> [!div class="step-by-step"]
> [Anterior](types-and-variables.md)
> [Siguiente](statements.md)
