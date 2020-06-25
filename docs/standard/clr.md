---
title: 'Introducción a Common Language Runtime (CLR): .NET Framework'
description: Introducción a Common Language Runtime (CLR), el entorno de tiempo de ejecución de .NET. CLR ejecuta código y proporciona servicios para facilitar el proceso de desarrollo.
ms.date: 04/02/2019
ms.technology: dotnet-standard
helpviewer_keywords:
- compiling source code, runtime functionality
- code, execution
- managed data
- runtime
- common language runtime
- metadata, runtime functionality
- .NET Framework, common language runtime
- language compilers
- managed code
- source code execution
- code, runtime functionality
ms.assetid: 059a624e-f7db-4134-ba9f-08b676050482
ms.custom: updateeachrelease
ms.openlocfilehash: ef455ac1c49c1f457d0fa432db91b5375c045840
ms.sourcegitcommit: 5fd4696a3e5791b2a8c449ccffda87f2cc2d4894
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/15/2020
ms.locfileid: "84769215"
---
# <a name="common-language-runtime-clr-overview"></a>Introducción a Common Language Runtime

.NET Framework proporciona un entorno en tiempo de ejecución denominado Common Language Runtime, que ejecuta el código y proporciona servicios que facilitan el proceso de desarrollo.

Los compiladores y las herramientas exponen la funcionalidad de Common Language Runtime y permiten escribir código con las ventajas que proporciona este entorno de ejecución administrado. El código desarrollado con un compilador de lenguaje orientado al tiempo de ejecución se denomina código administrado. Este código se beneficia de características como: la integración entre lenguajes, el control de excepciones entre lenguajes, la seguridad mejorada, la compatibilidad con la implementación y las versiones, un modelo simplificado de interacción y servicios de generación de perfiles y depuración.

> [!NOTE]
> Los compiladores y las herramientas pueden generar resultados que Common Language Runtime puede consumir porque el sistema de tipos, el formato de metadatos y el entorno en tiempo de ejecución (el sistema de ejecución virtual) están todos definidos según un estándar público, la especificación Common Language Infrastructure de ECMA. Para obtener más información, consulte [ECMA C# and Common Language Infrastructure Specifications](https://visualstudio.microsoft.com/license-terms/ecma-c-common-language-infrastructure-standards/) (Especificaciones de ECMA C# y Common Language Infrastructure).

Para permitir al motor en tiempo de ejecución proporcionar servicios al código administrado, los compiladores de lenguajes deben emitir metadatos que describen los tipos, los miembros y las referencias del código. Los metadatos se almacenan con el código; cada archivo ejecutable portable (PE) de Common Language Runtime cargable contiene metadatos. El motor en tiempo de ejecución utiliza los metadatos para localizar y cargar clases, colocar instancias en memoria, resolver invocaciones a métodos, generar código nativo, exigir mecanismos de seguridad y establecer los límites del contexto en tiempo de ejecución.

El tiempo de ejecución controla automáticamente la disposición de los objetos y administra las referencias a éstos, liberándolos cuando ya no se utilizan. Los objetos cuya duración se administra de esta forma se denominan datos administrados. La recolección de elementos no utilizados elimina pérdidas de memoria así como otros errores habituales de programación. Con un código administrado se pueden utilizar datos administrados, datos no administrados o estos dos tipos de datos en una aplicación .NET Framework. Como los compiladores de lenguajes proporcionan sus propios tipos, como tipos primitivos, no siempre se sabe (o no es necesario saber) si los datos se están administrando.

Common Language Runtime facilita el diseño de los componentes y de las aplicaciones cuyos objetos interactúan entre lenguajes distintos. Los objetos escritos en lenguajes diferentes pueden comunicarse entre sí, lo que permite integrar sus comportamientos de forma precisa. Por ejemplo, puede definir una clase y, a continuación, utilizar un lenguaje diferente para derivar una clase de la clase original o llamar a un método de la clase original. También se puede pasar al método de una clase una instancia de una clase escrita en un lenguaje diferente. Esta integración entre lenguajes diferentes es posible porque los compiladores y las herramientas de lenguajes orientados al motor en tiempo de ejecución utilizan un sistema de tipos común definido por el motor en tiempo de ejecución, y los lenguajes siguen las reglas en tiempo de ejecución para definir nuevos tipos, así como para crear, utilizar, almacenar y enlazar tipos.

Como parte de los metadatos, todos los componentes administrados contienen información sobre los componentes y los recursos utilizados en su compilación. El motor en tiempo de ejecución utiliza esta información para garantizar que el componente o la aplicación contiene las versiones especificadas de todo lo necesario, por lo que hay menos posibilidades de que la ejecución del código se interrumpa debido a una dependencia inadecuada. La información de registro y los datos de estado ya no se almacenan en el Registro, donde puede ser difícil establecer y mantener datos. En su lugar, la información sobre tipos definidos por el usuario (y sus dependencias) se almacena con el código como metadatos y, de este modo, las tareas de replicación y eliminación de componentes es mucho menos complicada.

Las herramientas y los compiladores de lenguajes exponen la funcionalidad del motor en tiempo de ejecución de forma que resulte útil e intuitiva para los programadores. Esto significa que algunas características en tiempo de ejecución pueden ser más evidentes en un entorno que en otro. El funcionamiento del motor en tiempo de ejecución depende de las herramientas y los compiladores utilizados. Por ejemplo, un programador de Visual Basic observará que con Common Language Runtime, el lenguaje Visual Basic contiene más características orientadas a objetos que antes. El motor en tiempo de ejecución ofrece las siguientes ventajas:

- Mejoras en el rendimiento.

- Capacidad para utilizar fácilmente componentes desarrollados en otros lenguajes.

- Tipos extensibles que proporciona una biblioteca de clases

- Características del lenguaje como herencia, interfaces y sobrecarga para la programación orientada a objetos.

- Compatibilidad con subprocesamiento libre explícito que permite la creación de aplicaciones multiproceso escalables.

- Compatibilidad con el control de excepciones estructurado.

- Compatibilidad con atributos personalizados.

- Recolección de elementos no utilizados.

- Emplee delegados en lugar de punteros a funciones para mayor seguridad y protección de tipos. Para más información acerca de los delegados, consulte [Common Type System](base-types/common-type-system.md).

## <a name="clr-versions"></a>Versiones de CLR

El número de versión de .NET Framework no se corresponde necesariamente con el número de versión del CLR que incluye. Para obtener una lista de las versiones de .NET Framework y sus versiones de CLR correspondientes, consulte [Versiones y dependencias de .NET Framework](../framework/migration-guide/versions-and-dependencies.md). Las versiones de .NET Core tienen una versión de producto única, es decir, no hay ninguna versión independiente de CLR. Para obtener una lista de las versiones de .NET Core, consulte [Descarga de .NET Core](https://dotnet.microsoft.com/download/dotnet-core).

## <a name="related-topics"></a>Temas relacionados

|Title|Descripción|
|-----------|-----------------|
|[Proceso de ejecución administrada](managed-execution-process.md)|Describe los pasos requeridos para aprovechar al máximo las ventajas de Common Language Runtime.|
|[Administración automática de la memoria](automatic-memory-management.md)|Describe cómo asigna y libera memoria el recolector de elementos no utilizados.|
|[Información general acerca de .NET Framework](../framework/get-started/overview.md)|Describe conceptos clave de .NET Framework como Common Type System (CTS), interoperabilidad entre lenguajes, ejecución administrada, dominios de aplicación y ensamblados.|
|[Sistema de tipos comunes](./base-types/common-type-system.md)|Describe cómo declarar, usar y administrar tipos en el motor en tiempo de ejecución para permitir la integración entre lenguajes.|
