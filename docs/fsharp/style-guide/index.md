---
title: 'Guía de estilo de F #'
description: 'Obtenga información acerca de los cinco principios del buen código de F #.'
ms.date: 05/14/2018
ms.openlocfilehash: 1d0f4e2a946f0cc91f376ba624f847549a830bc7
ms.sourcegitcommit: db8b83057d052c1f9f249d128b08d4423af0f7c2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/02/2018
ms.locfileid: "34235910"
---
# <a name="f-style-guide"></a>Guía de estilo de F #

Los artículos siguientes describen las directrices para el código de formato F # y orientación temático para características del lenguaje y cómo debe usarse.

Esta guía ha sido Formula según el uso de F # en grandes bases de datos con un amplio grupo de programadores. Esta guía generalmente conduce a un uso correcto de F # y minimiza las frustraciones cuando cambian los requisitos para los programas con el tiempo.

## <a name="five-principles-of-good-f-code"></a>Cinco principios del buen código de F #

Debe tener los siguientes principios en cuenta cualquier momento de que escribir código de F #, especialmente en sistemas que cambiarán con el tiempo. Cada parte de las instrucciones de otros artículos proviene de estos cinco puntos.

1. **Buen código de F # es concisas y expresivas**

    F # tiene muchas características que le permiten expresar acciones en menos líneas de código y volver a usar la funcionalidad genérica. La biblioteca básica de F # también contiene muchos tipos útiles y funciones para trabajar con colecciones comunes de datos. Como norma general, si puede expresar una solución a un problema en menos líneas de código, otros desarrolladores (o su futura self) será puedan apreciarse. Se recomienda encarecidamente también usa una biblioteca como FSharp.Core, el [grandes bibliotecas de .NET](https://docs.microsoft.com/dotnet/api/) que F # se ejecuta, o un paquete de terceros en [NuGet](https://www.nuget.org/) cuando necesite realizar una tarea no trivial.

2. **Es interoperable buen código de F #**

    Interoperación puede tomar varias formas, incluyendo usar código en diferentes idiomas. Los límites del código que interoperan con los otros llamadores son piezas fundamentales para realizar correctamente. Al escribir F #, se deben siempre esté pensando acerca de cómo otro código llamará en el código que se va a escribir, incluido si lo hacen desde otro lenguaje como C#. El [instrucciones de diseño del componente de F #](component-design-guidelines.md) describir en detalle la interoperabilidad.

3. **Buen código de F # hace que el uso de la programación de objetos, el objeto no orientación**

    F # es totalmente compatible con la programación con objetos en. NET, incluidos [clases](../language-reference/classes.md), [interfaces](../language-reference/interfaces.md), [modificadores de acceso](../language-reference/access-control.md), [clasesabstractas](../language-reference/abstract-classes.md), y así sucesivamente. Para código funcional más complicada, como las funciones que debe ser compatible con contexto, los objetos pueden encapsular fácilmente información contextual de maneras que no las funciones. Características como [parámetros opcionales](../language-reference/members/methods.md#optional-arguments) y dosificar [sobrecarga](../language-reference/members/methods.md#overloaded-methods) puede facilitar el consumo de esta funcionalidad para los autores de llamadas.

4. **Lleva a cabo también sin exponer mutación buen código de F #**

    No es ningún secreto para escribir código de alto rendimiento, debe usar mutación. Es cómo funcionan los equipos, después de todo. Dicho código suele ser propensas a errores y difícil de realizar correctamente. Evitar la exposición de mutación a los llamadores. En su lugar, [compilar una interfaz funcional que oculta una implementación basada en mutación](conventions.md#performance) cuando el rendimiento es crítico.

5. **Buen código de F # es dispone de herramientas**

    Las herramientas son un valor incalculable para trabajar grandes bases de datos, y puede escribir código F # de modo que puedan usar de forma más eficaz con las herramientas de lenguaje F #. Un ejemplo es asegurarse de que no abusar con un estilo libre de punto de programación, por lo que pueden inspeccionar los valores intermedios con un depurador. Otro ejemplo es usar [comentarios de documentación XML](../language-reference/xml-documentation.md) describir construcciones de forma que la información sobre herramientas en editores puede mostrar dichos comentarios en el sitio de llamada. Siempre pensar cómo el código se leerá, navegar, depurar y manipular con otros programadores con sus herramientas.

## <a name="next-steps"></a>Pasos siguientes

El [instrucciones de formato del código de F #](formatting.md) proporcionan instrucciones sobre cómo dar formato al código para que resulte fácil de leer.

El [convenciones de código de F #](conventions.md) proporcionan instrucciones para expresiones que le ayudarán al mantenimiento a largo plazo de F # mayor de programación en F # códigos base.

El [instrucciones de diseño del componente de F #](component-design-guidelines.md) proporcionan instrucciones para crear componentes de F #, como bibliotecas.
