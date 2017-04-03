---
title: Expresiones de C# | Un paseo por el lenguaje C#
description: "Las expresiones, los operandos y los operadores son bloques de construcción del lenguaje C#."
keywords: ".NET, csharp, expresión, operador, operanddo"
author: BillWagner
ms.author: wiwagn
ms.date: 11/06/2016
ms.topic: article
ms.prod: .net
ms.technology: devlang-csharp
ms.devlang: csharp
ms.assetid: 20d5eb10-7381-47b9-ad90-f1cc895aa27e
translationtype: Human Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: ce5f71ab3e797015a26dddbf0579c84dec580750
ms.lasthandoff: 03/13/2017

---

# <a name="expressions"></a>Expresiones

Las *expresiones* se construyen con *operandos* y *operadores*. Los operadores de una expresión indican qué operaciones se aplican a los operandos. Ejemplos de operadores incluyen `+`, `-`, `*`, `/` y `new`. Algunos ejemplos de operandos son literales, campos, variables locales y expresiones.

Cuando una expresión contiene varios operadores, la *precedencia* de los operadores controla el orden en que se evalúan los operadores individuales. Por ejemplo, la expresión `x + y * z` se evalúa como `x + (y * z)` porque el operador `*` tiene mayor precedencia que el operador `+`.

Cuando un operando se encuentra entre dos operadores con la misma precedencia, la *asociatividad* de los operadores controla el orden en que se realizan las operaciones:

*    Excepto los operadores de asignación, todos los operadores binarios son *asociativos a la izquierda*, lo que significa que las operaciones se realizan de izquierda a derecha. Por ejemplo, `x + y + z` se evalúa como `(x + y) + z`.
*    Los operadores de asignación y el operador condicional (`?:`) son *asociativos a la derecha*, lo que significa que las operaciones se realizan de derecha a izquierda. Por ejemplo, `x = y = z` se evalúa como `x = (y = z)`.

La precedencia y la asociatividad pueden controlarse mediante paréntesis. Por ejemplo, `x + y * z` primero multiplica `y` por `z` y luego suma el resultado a `x`, pero `(x + y) * z` primero suma `x` y `y` y luego multiplica el resultado por `z`.

La mayoría de los operadores se pueden *sobrecargar*. La sobrecarga de operador permite la especificación de implementaciones de operadores definidas por el usuario para operaciones donde uno o ambos operandos son de un tipo de struct o una clase definidos por el usuario.

A continuación se resumen los operadores de C#, con las categorías de operador en orden de precedencia de mayor a menor. Los operadores de la misma categoría tienen la misma precedencia. En cada categoría, hay una lista de expresiones de esa categoría junto con la descripción de ese tipo de expresión.

* Principal
    - `x.m`: acceso a miembros.
    - `x(...)`: invocación de método y delegado.
    - `x[...]`: acceso a matriz e indexador.
    - `x++`: postincremento.
    - `x--`: postdecremento.
    - `new T(...)`: creación de objetos y delegados.
    - `new T(...){...}`: creación de objetos con inicializador.
    - `new {...}`: inicializador de objetos anónimos.
    - `new T[...]`: creación de matriz.
    - `typeof(T)`: obtener el objeto @System.Type para `T`.
    - `checked(x)`: evaluar expresión en contexto comprobado.
    - `unchecked(x)`: evaluar expresión en contexto no comprobado.
    - `default(T)`: obtener valor predeterminado de tipo `T`.
    - `delegate {...}`: función anónima (método anónimo).
* Unario
    - `+x`: identidad.
    - `-x`: negación.
    - `!x`: negación lógica.
    - `~x`: negación bit a bit.
    - `++x`: preincremento.
    - `--x`: predecremento.
    - `(T)x`: convertir explícitamente `x` en el tipo `T`.
    - `await x`: esperar asincrónicamente a que finalice `x`.
* Multiplicativo
    - `x * y`: multiplicación.
    - `x / y`: división.
    - `x % y`: aviso.
* Aditivo
    - `x + y`: suma, concatenación de cadenas, combinación de delegados.
    - `x – y`: resta, eliminación de delegados.
* Shift
    - `x << y`: desplazamiento a la izquierda.
    - `x >> y`: desplazamiento a la derecha.
* Comprobación de tipos y relacional
    - `x < y`: menor que.
    - `x > y`: mayor que.
    - `x <= y`: menor o igual que.
    - `x >= y`: mayor o igual que.
    - `x is T`: volver a ejecutar `true` si `x` es una `T`, de lo contrario `false`.
    - `x as T`: volver a ejecutar `x` con tipo `T`, o `null` si `x` no es una `T`.
* Igualdad
    - `x == y`: igual que.
    - `x != y`: no igual que.
* AND lógico
    - `x & y`: AND bit a bit entero, AND lógico booleano.
* XOR lógico
    - `x ^ y`: XOR bit a bit entero, XOR lógico booleano.
* OR lógico
    - `x | y`: OR bit a bit entero, OR lógico booleano.
* AND condicional
    - `x && y`: evalúa `y` solo si `x` no es `false`.
* OR condicional
    - `x || y`: evalúa `y` solo si `x` no es `true`.
* Uso combinado de NULL
    - `x ?? y`: se evalúa como `y` si `x` es null, de lo contrario, como `x`.
* Condicional
    - `x ? y : z`: se evalúa como `y` si `x` es `true` o `z` si `x` es `false`.
* Asignación o función anónima
    - `x = y`: asignación.
    - `x op= y`: asignación compuesta; operadores admitidos son:
        - `*=`   `/=`   `%=`   `+=`   `-=`   `<<=`   `>>=`   `&=`  `^=`  `|=`
    - `(T x) => y`: función anónima (expresión lambda).

>[!div class="step-by-step"]
[Anterior](types-and-variables.md)
[Siguiente](statements.md)

