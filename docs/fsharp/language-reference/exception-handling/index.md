---
title: Control de excepciones (F#)
description: 'Obtenga información acerca de los conceptos básicos del control de excepciones en F # y busque vínculos a expresiones y funciones de control de excepciones.'
ms.date: 05/16/2016
ms.openlocfilehash: fc89feb0d21bc823cb105e435413f8309cd6174c
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33564331"
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
|[Exceptions: The `try...with` Expression](the-try-with-expression.md) (Excepciones: la expresión `try...with`)|Describe la construcción de lenguaje que admite el control de excepciones.|
|[Exceptions: The `try...finally` Expression](the-try-finally-expression.md) (Excepciones: la expresión `try...finally`)|Describe la construcción de lenguaje que permite ejecutar código de limpieza cuando se desenreda la pila al producirse una excepción.|
|[Exceptions: the `raise` Function](the-raise-Function.md) (Excepciones: la función `raise`)|Describe cómo iniciar un objeto de excepción.|
|[Exceptions: the `failwith` Function](the-failwith-function.md) (Excepciones: la función `failwith`)|Describe cómo generar una excepción general de F#.|
|[Exceptions: the `invalidArg` Function](the-invalidArg-function.md) (Excepciones: la función `invalidArg`)|Describe cómo generar una excepción de argumento no válido.|
