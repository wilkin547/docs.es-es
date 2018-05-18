---
title: 'Guía de estilo de F #'
description: 'Obtenga información acerca de los cinco principios de buen código F #.'
ms.date: 05/14/2018
ms.openlocfilehash: 317fc2c101449b0500a54dd9fea3d426757af5cd
ms.sourcegitcommit: 89c93d05c2281b4c834f48f6c8df1047e1410980
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/15/2018
---
# <a name="f-style-guide"></a>Guía de estilo de F #

Los artículos siguientes describen directrices de formato de código F # e interesa a instrucciones para las características del lenguaje y cómo debería usarse.

Esta guía se ha Formula según el uso de F # en grandes dotarlo de un amplio grupo de programadores. En general, esta guía conduce al uso correcto de F # y minimiza frustraciones cuando cambian los requisitos para los programas con el tiempo.

## <a name="five-principles-of-good-f-code"></a>Cinco principios de buen código F #

Debe mantener los siguientes principios presente siempre al que escribir código de F #, especialmente en sistemas que cambian con el tiempo. Cada parte de las instrucciones de más artículos proviene de estos cinco puntos.

1. **Código de F # buena es concisas y expresivas**

    F # tiene muchas características que permiten expresar acciones en menos líneas de código y volver a funcionalidad genérica. La biblioteca básica de F # también contiene muchos tipos útiles y funciones para trabajar con colecciones comunes de datos. Como norma general, si puede expresar una solución a un problema en menos líneas de código, otros desarrolladores (o su futuro self) será ganancia que puedan. Se recomienda encarecidamente también que se usa una biblioteca como FSharp.Core, el [grandes bibliotecas de .NET](https://docs.microsoft.com/dotnet/api/) que F # se ejecuta en, o un paquete de aplicaciones de terceros en [NuGet](https://www.nuget.org/) cuando necesite realizar una tarea no trivial.

2. **Código de F # buena es interoperable**

    Interoperación puede tomar varias formas, incluyendo utilizar código en distintos idiomas. Los límites del código que interoperan con los otros llamadores son partes esenciales para realizar correctamente. Al escribir F #, debe siempre adelantarse acerca de cómo otro código llamará en el código que está escribiendo, incluido si lo hacen desde otro lenguaje como C#. El [directrices de diseño del componente de F #](component-design-guidelines.md) describen la interoperabilidad con detalle.

3. **Buen código F # hace uso de la programación de objetos, no objetos orientación**

    F # es totalmente compatible con la programación con objetos en. NET, incluidos los [clases](../language-reference/classes.md), [interfaces](../language-reference/interfaces.md), [los modificadores de acceso](../language-reference/access-control.md), [clasesabstractas](../language-reference/abstract-classes.md), y así sucesivamente. Para código funcional más complicada, como las funciones que debe ser compatible con contexto, objetos pueden encapsular fácilmente información contextual de maneras que no funciones. Características como [parámetros opcionales](../language-reference/members/methods.md#optional-arguments) y [sobrecarga](../language-reference/members/methods.md#overloaded-methods) también ayudan a consumo de esta funcionalidad para los llamadores.

4. **Buen código F # realiza también sin exponer mutaciones**

    No es ningún secreto para escribir código de alto rendimiento, debe usar mutación. Es cómo funcionan los equipos, después de todo. Este código no es a menudo son propensos a errores y difícil de realizar correctamente. Evitar exponer mutación a los llamadores. Buscar una interfaz funcional a través de una implementación basada en mutación.

5. **Código de F # buena es herramientas**

    Herramientas son muy valiosas para trabajar grandes bases de código, puede escribir código de F #, que puede utilizar de forma más eficaz con herramientas de lenguaje F #. Un ejemplo es asegurarse de que no abusar con un estilo libre de punto de programación, por lo que pueden inspeccionar los valores intermedios con un depurador. Otro ejemplo es usar [comentarios de documentación XML](../language-reference/xml-documentation.md) con descripciones de construcciones de modo que la información sobre herramientas en el editor puede mostrar los comentarios en el sitio de llamada. Siempre pensar en cómo el código se puede leer, navegado, depurar y manipulado por otros programadores con sus herramientas.

## <a name="next-steps"></a>Pasos siguientes

El [instrucciones de formato de F #](formatting.md) ofrecen orientación sobre cómo dar formato de código para que resulte fácil de leer.

El [convenciones de código de F #](conventions.md) proporcionan instrucciones para expresiones que le ayudarán al mantenimiento a largo plazo de mayor F # de programación de F # dotarlo.

El [directrices de diseño del componente de F #](component-design-guidelines.md) es un conjunto completo de instrucciones para crear componentes de F #, como las bibliotecas.