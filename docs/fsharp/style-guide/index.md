---
title: Guía de estilo de F#
description: Conozca los cinco principios del buen código de F.
ms.date: 12/10/2018
ms.openlocfilehash: 9f47257626e04b09b546de2ae315d48d791678be
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/14/2020
ms.locfileid: "79401116"
---
# <a name="f-style-guide"></a>Guía de estilo de F#

En los artículos siguientes se describen las directrices para dar formato al código de F y a las instrucciones temáticas para las características del lenguaje y cómo se deben usar.

Esta guía se ha formulado sobre la base del uso de F en grandes bases de código con un grupo diverso de programadores. Esta guía generalmente conduce al uso exitoso de F y minimiza las frustraciones cuando los requisitos para los programas cambian con el tiempo.

## <a name="five-principles-of-good-f-code"></a>Cinco principios del buen código de F

Tenga en cuenta los siguientes principios cada vez que escriba código de F, especialmente en sistemas que cambiarán con el tiempo. Cada pieza de orientación en otros artículos proviene de estos cinco puntos.

1. **El buen código de F es sucinto, expresivo y componible**

    F- tiene muchas características que le permiten expresar acciones en menos líneas de código y reutilizar la funcionalidad genérica. La biblioteca principal de F - también contiene muchos tipos y funciones útiles para trabajar con colecciones comunes de datos. La composición de sus propias funciones y las de la biblioteca principal de F ( u otras bibliotecas) forma parte de la programación idiomática de F . Como regla general, si puede expresar una solución a un problema en menos líneas de código, otros desarrolladores (o su futuro yo) se apreciarán. También es muy recomendable que use una biblioteca como FSharp.Core, las [vastas bibliotecas](../../../api/index.md) de .NET en las que se ejecuta F, o un paquete de terceros en [NuGet](https://www.nuget.org/) cuando necesite realizar una tarea no trivial.

2. **Un buen código de F es interoperable**

    La interoperación puede adoptar varios formularios, incluido el consumo de código en diferentes idiomas. Los límites del código con los que interoperan otros llamadores son elementos críticos para obtener la razón, incluso si los llamadores también están en F . Al escribir F, siempre debe estar pensando en cómo otro código llamará al código que está escribiendo, incluso si lo hacen desde otro idioma como C. Las directrices de [diseño de componentes](component-design-guidelines.md) de FTM describen la interoperabilidad en detalle.

3. **Un buen código de F hace uso de la programación de objetos, no de la orientación de objetos**

    F tiene soporte completo para la programación con objetos en .NET, [incluidas clases, interfaces,](../language-reference/interfaces.md)modificadores de [acceso, clases](../language-reference/access-control.md) [abstractas,](../language-reference/abstract-classes.md)etc. [classes](../language-reference/classes.md) Para obtener código funcional más complicado, como funciones que deben tener en cuenta el contexto, los objetos pueden encapsular fácilmente información contextual de maneras que las funciones no pueden. Las características como los [parámetros opcionales](../language-reference/members/methods.md#optional-arguments) y el uso cuidadoso de [la sobrecarga](../language-reference/members/methods.md#overloaded-methods) pueden facilitar el consumo de esta funcionalidad a los llamadores.

4. **Un buen código De F funciona bien sin exponer la mutación**

    No es ningún secreto que para escribir código de alto rendimiento, debes usar la mutación. Después de todo, es cómo funcionan las computadoras. Este código es a menudo propenso a errores y difícil de hacer bien. Evite exponer la mutación a las personas que llaman. En su lugar, [cree una interfaz funcional que oculte una implementación basada en mutaciones](conventions.md#performance) cuando el rendimiento sea crítico.

5. **El buen código de F es útil**

    Las herramientas son invaluables para trabajar en grandes bases de código, y puede escribir código de F, de tal manera que se pueda usar de forma más eficaz con las herramientas de lenguaje de F. Un ejemplo es asegurarse de no exagerar con un estilo de programación sin puntos, de modo que los valores intermedios se puedan inspeccionar con un depurador. Otro ejemplo es el uso de [comentarios](../language-reference/xml-documentation.md) de documentación XML que describen construcciones de tal manera que la información sobre herramientas en los editores puede mostrar esos comentarios en el sitio de llamada. Piense siempre en cómo el código será leído, navegado, depurado y manipulado por otros programadores con sus herramientas.

## <a name="next-steps"></a>Pasos siguientes

Las [directrices](formatting.md) de formato de código de F - proporcionan instrucciones sobre cómo dar formato al código para que sea fácil de leer.

Las convenciones de [codificación](conventions.md) de F - proporcionan orientación para los modismos de programación de F - que ayudarán al mantenimiento a largo plazo de bases de código de F .

Las directrices de diseño de [componentes](component-design-guidelines.md) de F , proporcionan instrucciones para la creación de componentes de F, como bibliotecas.
