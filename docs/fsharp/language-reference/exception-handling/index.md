---
title: Control de excepciones
description: Conozca los aspectos básicos del control de excepciones en F# y encuentre vínculos a las expresiones y funciones de control de excepciones.
ms.date: 05/16/2016
ms.openlocfilehash: 187236ca380c7de0b3714160f6c3703f8fb93d5a
ms.sourcegitcommit: fa38fe76abdc8972e37138fcb4dfdb3502ac5394
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/19/2018
ms.locfileid: "53614446"
---
# <a name="exception-handling"></a>Control de excepciones

Esta sección contiene información sobre la compatibilidad con el control de excepciones del lenguaje F#.

## <a name="exception-handling-basics"></a>Fundamentos del control de excepciones
El control de excepciones es la manera estándar de controlar las condiciones de error en .NET Framework. Por tanto, cualquier lenguaje de .NET debe admitir este mecanismo, incluso F#. Una *excepción* es un objeto que encapsula la información sobre un error. Cuando se producen errores, se generan excepciones y se detiene la ejecución regular. En su lugar, el tiempo de ejecución busca un controlador adecuado para la excepción. La búsqueda se inicia en la función actual y continúa hasta la pila a través de los niveles de llamadores hasta que se encuentra un controlador coincidente. Después, se ejecuta el controlador.

Además, cuando se desenreda la pila, el tiempo de ejecución ejecuta cualquier código en bloques `finally`, para garantizar que los objetos se limpien correctamente durante el proceso de desenredo.

## <a name="related-topics"></a>Temas relacionados

|Título|Descripción|
|-----|-----------|
|[Tipos de excepción](exception-types.md)|Describe cómo declarar un tipo de excepción.|
|[Excepciones: El `try...with` expresión](the-try-with-expression.md)|Describe la construcción de lenguaje que admite el control de excepciones.|
|[Excepciones: El `try...finally` expresión](the-try-finally-expression.md)|Describe la construcción de lenguaje que permite ejecutar código de limpieza cuando se desenreda la pila al producirse una excepción.|
|[Exceptions: the `raise` Function](the-raise-Function.md) (Excepciones: la función `raise`)|Describe cómo iniciar un objeto de excepción.|
|[Excepciones: El `failwith` (función)](the-failwith-function.md)|Describe cómo generar una excepción general de F#.|
|[Excepciones: El `invalidArg` (función)](the-invalidArg-function.md)|Describe cómo generar una excepción de argumento no válido.|