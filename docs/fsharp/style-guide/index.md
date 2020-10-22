---
title: Guía de estilo de F#
description: Aprenda los cinco principios del buen código de F#.
ms.date: 12/10/2018
ms.openlocfilehash: 9f47257626e04b09b546de2ae315d48d791678be
ms.sourcegitcommit: 67ebdb695fd017d79d9f1f7f35d145042d5a37f7
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/20/2020
ms.locfileid: "92223657"
---
# <a name="f-style-guide"></a>Guía de estilo de F#

En los artículos siguientes se describen las instrucciones de formato de código de F# e instrucciones temáticas de las características del lenguaje y cómo deben usarse.

Estas instrucciones se han formulado en función del uso de F# en códigos base de gran tamaño con un grupo de programadores diverso. Generalmente, estas instrucciones ayudan a usar F# correctamente y minimizan las frustraciones cuando los requisitos de los programas cambian con el tiempo.

## <a name="five-principles-of-good-f-code"></a>Cinco principios del buen código de F#

Tenga en cuenta los siguientes principios cada vez que escriba código de F#, especialmente en aquellos sistemas que cambien con el tiempo. Cada fragmento de las instrucciones incluidas en artículos adicionales se deriva de estos cinco puntos.

1. **El buen código de F# es conciso, expresivo y admite composición**

    F# tiene muchas características que le permiten expresar acciones en menos líneas de código y volver a usar la funcionalidad genérica. La biblioteca básica de F# también contiene muchos tipos y funciones útiles para trabajar con recopilaciones de datos comunes. La composición de sus propias funciones y las de la biblioteca básica de F# (u otras bibliotecas) forma parte de la programación de F# idiomático de rutinas. Como regla general, si puede expresar una solución a un problema en menos líneas de código, otros desarrolladores (o su yo futuro) se mostrarán apreciativos. También es muy recomendable que use una biblioteca como FSharp.Core, las [amplias bibliotecas de .NET](../../../api/index.md) en las que se ejecuta F# o un paquete de terceros en [NuGet](https://www.nuget.org/) cuando tenga que realizar una tarea no trivial.

2. **El buen código de F# es interoperable**

    La interoperación puede adoptar varias formas, incluido el uso del código en diversos lenguajes. Los límites del código con el que interoperan otros llamadores son elementos críticos para entenderlo, incluso si los llamadores también están en F#. Al escribir F#, siempre debería pensar en cómo llamará otro código al código que escribe, incluyendo si lo hacen desde otro lenguaje como C#. En las [instrucciones de diseño de componentes de F#](component-design-guidelines.md) se describen la interoperabilidad de forma detallada.

3. **El buen código de F# usa la programación de objetos, no la orientación del objeto**

    F# es totalmente compatible con la programación con objetos en .NET, incluidos [clases](../language-reference/classes.md), [interfaces](../language-reference/interfaces.md), [modificadores de acceso](../language-reference/access-control.md), [clases abstractas](../language-reference/abstract-classes.md), etc. Para un código funcional más complejo, por ejemplo, funciones que deben ser contextuales, los objetos pueden encapsular fácilmente información contextual de maneras en las que las funciones no pueden. Características como [parámetros opcionales](../language-reference/members/methods.md#optional-arguments) y el uso cuidadoso de la [sobrecarga](../language-reference/members/methods.md#overloaded-methods) pueden simplificar el consumo de esta funcionalidad para los llamadores.

4. **El buen código de F# funciona bien sin exponer la mutación**

    No es ningún secreto que, para escribir código de alto rendimiento, debe usar la mutación. Después de todo, así funcionan los equipos. Este código suele ser propenso a errores y difícil de entender. Evite exponer la mutación a los llamadores. En su lugar, [cree una interfaz funcional que oculte una implementación basada en mutaciones](conventions.md#performance) cuando el rendimiento sea crítico.

5. **El buen código de F# es manejable**

    Las herramientas resultan muy útiles para trabajar en códigos base de gran tamaño y puede escribir código de F# de modo que se pueda usar con mayor eficacia con herramientas de lenguaje F#. Un ejemplo es asegurarse de que no abusa con un estilo de programación sin puntos de modo que se puedan inspeccionar valores intermedios con un depurador. Otro ejemplo es usar [comentarios de documentación XML](../language-reference/xml-documentation.md) que describan construcciones de modo que la información sobre herramientas de los editores pueda mostrar esos comentarios en el sitio de llamada. Piense siempre en cómo leerán, depurarán, manipularán y navegarán por el código otros programadores con sus herramientas.

## <a name="next-steps"></a>Pasos siguientes

En las [instrucciones de formato de código de F#](formatting.md) se proporciona orientación sobre cómo dar formato al código para facilitar su lectura.

Las [convenciones de código de F#](conventions.md) proporcionan instrucciones para las expresiones de programación de F# que contribuirán al mantenimiento a largo plazo de códigos base de F# de mayor tamaño.

Las [instrucciones de diseño de componentes de F#](component-design-guidelines.md) proporcionan orientación para la creación de componentes de F#, como las bibliotecas.
