---
title: Control de excepciones (F#)
description: Control de excepciones (F#)
keywords: "visual f#, f#, programación funcional"
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: .net
ms.technology: devlang-fsharp
ms.devlang: fsharp
ms.assetid: ad475c4a-d94e-47d9-b27b-3ff000b65f8e
translationtype: Human Translation
ms.sourcegitcommit: 0a01ec92a90d99fafaacbd3f71f5177e5cf94a68
ms.openlocfilehash: d95aca8c511524f0b9af67b34a5999f885cf3aaf
ms.lasthandoff: 04/05/2017

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
