---
title: Árboles de expresión
description: Obtenga información sobre los árboles de expresión en .NET Core y cómo usarlos para representar código como estructuras que pueda examinar, modificar y ejecutar.
ms.date: 06/20/2016
ms.technology: csharp-advanced-concepts
ms.assetid: aceb4719-0d5a-4b19-b01f-b51063bcc54f
ms.openlocfilehash: e1026ef70860da519b688a9d67181b88d03f6f0b
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/14/2020
ms.locfileid: "79145844"
---
# <a name="expression-trees"></a>Árboles de expresión

Si ha usado LINQ, tiene experiencia con una extensa biblioteca donde los tipos `Func` forman parte del conjunto de API. (Si no está familiarizado con LINQ, probablemente quiera leer [el tutorial de LINQ](linq/index.md) y el artículo sobre [expresiones lambda](./programming-guide/statements-expressions-operators/lambda-expressions.md) antes de este). Los *árboles de expresión* proporcionan una interacción más amplia con los argumentos que son funciones.

Escribe argumentos de función, normalmente con expresiones lambda, cuando crea consultas LINQ. En una consulta LINQ habitual, esos argumentos de función se transforman en un delegado que crea el compilador.

Cuando quiera tener una interacción mayor, necesita usar los *árboles de expresión*.
Los árboles de expresión representan el código como una estructura que puede examinar, modificar o ejecutar. Estas herramientas le proporcionan la capacidad de manipular el código durante el tiempo de ejecución. Puede escribir código que examine la ejecución de algoritmos o inserte nuevas características. En escenarios más avanzados, puede modificar la ejecución de algoritmos e incluso convertir expresiones de C# en otra forma para su ejecución en otro entorno.

Probablemente ya ha escrito código que use árboles de expresión. Las API de LINQ de Entity Framework admiten árboles de expresión como argumentos para el patrón de expresión de consulta LINQ.
Eso permite que [Entity Framework](/ef/) convierta la consulta que ha escrito en C# en SQL que se ejecuta en el motor de base de datos. Otro ejemplo es [Moq](https://github.com/Moq/moq), que es un marco simulado popular de .NET.

En las secciones restantes de este tutorial exploraremos lo que son los árboles de expresión, examinaremos las clases de marco que admiten los árboles de expresión y le mostraremos cómo trabajar con ellos. Obtendrá información sobre cómo leer árboles de expresión, cómo crearlos, cómo crear árboles de expresión modificados y cómo ejecutar el código representado en ellos. Después de esta lectura, estará listo para usar estas estructuras para crear algoritmos muy adaptables.

1. [Árboles de expresiones en detalle](expression-trees-explained.md)

    Comprenda la estructura y los conceptos de los *árboles de expresión*.

2. [Tipos de marco que admiten árboles de expresión](expression-classes.md)

    Obtenga información sobre las estructuras y las clases que definen y manipulan los árboles de expresión.

3. [Ejecución de expresiones](expression-trees-execution.md)

    Obtenga información sobre cómo convertir un árbol de expresión representado como una expresión lambda en un delegado y ejecutar el delegado resultante.

4. [Interpretación de expresiones](expression-trees-interpreting.md)

    Obtenga información sobre cómo recorrer y examinar *árboles de expresión* para entender qué código representa el árbol de expresión.

5. [Generación de expresiones](expression-trees-building.md)

    Obtenga información sobre cómo construir los nodos de un árbol de expresión y crear árboles de expresión.

6. [Traducción de expresiones](expression-trees-translating.md)

    Obtenga información sobre cómo crear una copia modificada de un árbol de expresión, o convertir un árbol de expresión en un formato diferente.

7. [Resumen](expression-trees-summary.md)

    Revise la información sobre los árboles de expresión.
