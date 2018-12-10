---
title: F#Guía de estilo
description: Obtenga información sobre los cinco principios del buen F# código.
ms.date: 12/10/2018
ms.openlocfilehash: 7718df596bde9004fb9ba6143146f1f475d25683
ms.sourcegitcommit: e6ad58812807937b03f5c581a219dcd7d1726b1d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/10/2018
ms.locfileid: "53168967"
---
# <a name="f-style-guide"></a>F#Guía de estilo

Los siguientes artículos describen las directrices para dar formato a F# código e instrucciones temático para características del lenguaje y cómo debe usarse.

Esta guía se ha formulado según el uso de F# en grandes bases de datos con un amplio grupo de programadores. Esta guía suele lleva al uso correcto de F# y minimiza las frustraciones cuando cambian los requisitos para los programas con el tiempo.

## <a name="five-principles-of-good-f-code"></a>Cinco principios del buen F# código

Tenga los siguientes principios en cuenta cada vez que escriba F# código, especialmente en sistemas que cambiará con el tiempo. Cada parte de las instrucciones de otros artículos proviene de estos cinco puntos.

1. **Buena F# código es sucinto, expresivo y que admite composición**

    F#tiene muchas características que le permiten expresar acciones en menos líneas de código y volver a usar la funcionalidad genérica. El F# biblioteca principal también contiene muchos tipos útiles y funciones para trabajar con colecciones comunes de datos. Composición de sus propias funciones y los de la F# biblioteca básica (u otras bibliotecas) son una parte de la rutina idiomático F# de programación. Como norma general, si puede expresar una solución a un problema en menos líneas de código, otros desarrolladores (o su futura self) será puedan apreciarse. Se recomienda encarecidamente también usa una biblioteca como FSharp.Core, el [grandes bibliotecas de .NET](https://docs.microsoft.com/dotnet/api/) que F# se ejecuta, o un paquete de terceros en [NuGet](https://www.nuget.org/) cuando necesite realizar una tarea no trivial.

2. **Buena F# código es interoperable**

    Interoperación puede tomar varias formas, incluyendo usar código en diferentes idiomas. Los límites del código que interoperan con los otros llamadores son piezas fundamentales para realizar correctamente, incluso si los llamadores estén además en F#. Al escribir F#, siempre se debe pensar acerca de cómo otro código llamará en el código que se va a escribir, incluido si lo hacen desde otro lenguaje como C#. El [ F# pautas de diseño de componentes](component-design-guidelines.md) describir en detalle la interoperabilidad.

3. **Buena F# código hace que el uso de la programación de objetos, el objeto no orientación**

    F#es totalmente compatible con la programación con objetos en. NET, incluidos [clases](../language-reference/classes.md), [interfaces](../language-reference/interfaces.md), [modificadores de acceso](../language-reference/access-control.md), [clasesabstractas](../language-reference/abstract-classes.md), y así sucesivamente. Para código funcional más complicada, como las funciones que debe ser compatible con contexto, los objetos pueden encapsular fácilmente información contextual de maneras que no las funciones. Características como [parámetros opcionales](../language-reference/members/methods.md#optional-arguments) y dosificar [sobrecarga](../language-reference/members/methods.md#overloaded-methods) puede facilitar el consumo de esta funcionalidad para los autores de llamadas.

4. **Buena F# código funciona bien sin exponer mutación**

    No es ningún secreto para escribir código de alto rendimiento, debe usar mutación. Es cómo funcionan los equipos, después de todo. Dicho código suele ser propensas a errores y difícil de realizar correctamente. Evitar la exposición de mutación a los llamadores. En su lugar, [compilar una interfaz funcional que oculta una implementación basada en mutación](conventions.md#performance) cuando el rendimiento es crítico.

5. **Buena F# código es dispone de herramientas**

    Las herramientas son muy valiosos para trabajar grandes bases de datos, y puede escribir F# código de modo que puedan usar de forma más eficaz con F# las herramientas de lenguaje. Un ejemplo es asegurarse de que no abusar con un estilo libre de punto de programación, por lo que pueden inspeccionar los valores intermedios con un depurador. Otro ejemplo es usar [comentarios de documentación XML](../language-reference/xml-documentation.md) describir construcciones de forma que la información sobre herramientas en editores puede mostrar dichos comentarios en el sitio de llamada. Siempre pensar cómo el código se leerá, navegar, depurar y manipular con otros programadores con sus herramientas.

## <a name="next-steps"></a>Pasos siguientes

El [ F# instrucciones de formato de código](formatting.md) proporcionan instrucciones sobre cómo dar formato al código para que resulte fácil de leer.

El [ F# las convenciones de codificación](conventions.md) proporcionan instrucciones para F# expresiones que le ayudarán al mantenimiento a largo plazo de mayor tamaño de programación F# códigos base.

El [ F# pautas de diseño de componentes](component-design-guidelines.md) proporcionan instrucciones para crear F# componentes, como bibliotecas.
