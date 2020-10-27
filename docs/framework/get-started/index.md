---
title: Introducción a .NET Framework
description: Empiece a usar .NET Framework, un entorno de ejecución runtime que administra aplicaciones. Contiene Common Language Runtime (CLR) y una extensa biblioteca de clases.
ms.date: 10/21/2020
helpviewer_keywords:
- .NET Framework, getting started
- getting started [.NET Framework]
ms.assetid: c693fd34-88fe-4d90-b332-19eeadf3b7e7
ms.openlocfilehash: 02480641af5ad2c973f7dbbbc233d3d89ff4617e
ms.sourcegitcommit: 870bc4b4087510f6fba3c7b1c0d391f02bcc1f3e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/23/2020
ms.locfileid: "92471681"
---
# <a name="get-started-with-net-framework"></a>Introducción a .NET Framework

.NET Framework es un entorno de ejecución runtime que administra aplicaciones cuyo destino es .NET Framework. Incorpora Common Language Runtime, que proporciona la administración de la memoria y otros servicios del sistema, y una biblioteca de clases completa, que permite a los programadores aprovechar el código estable y fiable de todas las áreas principales del desarrollo de aplicaciones.

[!INCLUDE [net-framework-future](../../../includes/net-framework-future.md)]

## <a name="what-is-net-framework"></a>¿Qué es .NET Framework?

.NET Framework es un entorno de ejecución administrado para Windows que proporciona diversos servicios a las aplicaciones en ejecución. Consta de dos componentes principales: Common Language Runtime (CLR), que es el motor de ejecución que controla las aplicaciones en ejecución, y la biblioteca de clases de .NET Framework, que proporciona una biblioteca de código probado y reutilizable al que pueden llamar los desarrolladores desde sus propias aplicaciones. Los servicios que ofrece .NET Framework a las aplicaciones en ejecución son los siguientes:

- Administración de la memoria. En muchos lenguajes de programación, los programadores son responsables de asignar y liberar memoria y de administrar la vida útil de los objetos. En las aplicaciones de .NET Framework, CLR proporciona estos servicios en nombre de la aplicación.

- Sistema de tipos comunes. En los lenguajes de programación tradicionales, el compilador define los tipos básicos, lo que complica la interoperabilidad entre lenguajes. En .NET Framework, los tipos básicos los define el sistema de tipos de .NET Framework y son comunes a todos los lenguajes que tienen como destino .NET Framework.

- Biblioteca de clases extensa. En lugar de tener que escribir cantidades extensas de código para controlar operaciones comunes de programación de bajo nivel, los programadores usan una biblioteca de tipos accesible en todo momento y sus miembros desde la biblioteca de clases de .NET Framework.

- Marcos y tecnologías de desarrollo. .NET Framework incluye bibliotecas para determinadas áreas de desarrollo de aplicaciones, como ASP.NET para aplicaciones web, ADO.NET para el acceso a los datos, Windows Communication Foundation para las aplicaciones orientadas a servicios y Windows Presentation Foundation para las aplicaciones de escritorio de Windows.

- Interoperabilidad de lenguajes. Los compiladores de lenguajes cuya plataforma de destino es .NET Framework emiten un código intermedio denominado Lenguaje intermedio común (CIL), que, a su vez, se compila en tiempo de ejecución a través de Common Language Runtime. Con esta característica, las rutinas escritas en un lenguaje son accesibles para otros lenguajes, de modo que los programadores puedan centrarse en crear aplicaciones en su lenguaje preferido.

- Compatibilidad de versiones. Con raras excepciones, las aplicaciones que se desarrollan con una versión determinada de .NET Framework se ejecutan sin modificaciones en una versión posterior.

- Ejecución en paralelo. .NET Framework ayuda a resolver conflictos entre versiones y permite que varias versiones de Common Language Runtime coexistan en el mismo equipo. Esto significa que pueden coexistir varias versiones de las aplicaciones, y que una aplicación se puede ejecutar en la versión de .NET Framework con la que se compiló. La ejecución en paralelo se aplica a los grupos de la versión de .NET Framework 1.0/1.1, 2.0/3.0/3.5 y 4/4.5.x/4.6.x/4.7.x/4.8.

- Compatibilidad con múltiples versiones (multi-targeting). Al establecer [.NET Standard](../../standard/net-standard.md) como destino, los desarrolladores crear bibliotecas de clases que funcionan en varias plataformas de .NET Framework compatibles con esa versión del estándar. Por ejemplo, las bibliotecas que tienen .NET Standard 2.0 como destino pueden usarlas las aplicaciones que tienen como destino .NET Framework 4.6.1, .NET Core 2.0 y UWP 10.0.16299.

<a name="ForUsers"></a>
## <a name="net-framework-for-users"></a>.NET Framework para usuarios

Si no desarrolla aplicaciones de .NET Framework pero las usa, no es necesario que tenga conocimientos específicos de .NET Framework o de su funcionamiento. En general, .NET Framework es completamente transparente para los usuarios.

Si usa el sistema operativo Windows, es posible que .NET Framework ya esté instalado en el equipo. Además, si instala una aplicación que requiera .NET Framework, el programa de instalación de la aplicación puede instalar una versión concreta de .NET Framework en el equipo. En algunos casos, puede aparecer un cuadro de diálogo en el que se le pida que instale .NET Framework. Si acaba de intentar ejecutar una aplicación cuando se muestra este cuadro de diálogo y si el equipo tiene acceso a Internet, puede ir a una página web que le permita instalar la versión de .NET Framework que falte. Para más información, consulte la [guía de instalación](../install/index.md).

En general, no debería desinstalar ninguna versión de .NET Framework instalada en el equipo. Hay dos motivos para ello:

- Si una aplicación que usa depende de una versión específica de .NET Framework, podría dañarse al quitarla.

- Algunas versiones de .NET Framework son actualizaciones locales de versiones anteriores. Por ejemplo, .NET Framework 3.5 es una actualización local de la versión 2.0, mientras que .NET Framework 4.8 lo es de las versiones 4 a 4.7.2. Para más información, consulte [Versiones y dependencias de .NET Framework](../migration-guide/versions-and-dependencies.md).

En versiones de Windows anteriores a Windows 8, si decide quitar .NET Framework, use siempre la opción **Programas y características** del Panel de control para desinstalarlo. No quite nunca una versión de .NET Framework manualmente. En Windows 8 y versiones posteriores, .NET Framework es un componente del sistema operativo y no se puede desinstalar de forma independiente.

Se pueden usar varias versiones de .NET Framework en un único equipo al mismo tiempo. Esto significa que no tiene que desinstalar las versiones anteriores para instalar una versión posterior.

## <a name="net-framework-for-developers"></a>.NET Framework para desarrolladores

Si es desarrollador, elija cualquier lenguaje de programación compatible con .NET Framework para crear sus aplicaciones. Dado que .NET Framework proporciona independencia e interoperabilidad entre lenguajes, puede interactuar con otras aplicaciones y componentes de .NET Framework independientemente del lenguaje con el que se desarrollaron.

Para desarrollar aplicaciones o componentes de .NET Framework, haga lo siguiente:

1. Si no está preinstalado en el sistema operativo, instale la versión de .NET Framework que tendrá como destino su aplicación. La versión de producción más reciente es .NET Framework 4.8. Está preinstalada en la actualización de mayo de 2019 de Windows 10, y se puede descargar en versiones anteriores del sistema operativo Windows. Para información sobre los requisitos de sistema de .NET Framework, consulte [Requisitos del sistema](system-requirements.md). Para información sobre la instalación de otras versiones de .NET Framework, consulte [Guía de instalación](../install/guide-for-developers.md). Se publican paquetes adicionales de .NET Framework independientes, lo que significa que están disponibles a un ritmo diferente a cualquier ciclo de lanzamiento estándar o programado. Para información sobre estos paquetes, consulte [.NET Framework y versiones fuera de banda](the-net-framework-and-out-of-band-releases.md).

2. Seleccione el lenguaje o los lenguajes compatibles con la versión de .NET Framework que quiera usar para desarrollar aplicaciones. Hay varios lenguajes disponibles, como [Visual Basic](../../visual-basic/index.yml), [C#](../../csharp/index.yml), [F#](../../fsharp/index.yml) y [C++/CLI](/cpp/dotnet/dotnet-programming-with-cpp-cli-visual-cpp), de Microsoft. (Un lenguaje de programación que permita desarrollar aplicaciones de .NET Framework cumple las [especificaciones de Common Language Infrastructure (CLI)](https://visualstudio.microsoft.com/license-terms/ecma-c-common-language-infrastructure-standards/)).

3. Seleccione e instale el entorno de desarrollo que usará para crear aplicaciones y que admita el lenguaje o los lenguajes de programación elegidos. El entorno de desarrollo integrado de Microsoft (IDE) para las aplicaciones de .NET Framework es [Visual Studio](https://visualstudio.microsoft.com/vs/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link). Está disponible en una gran variedad de ediciones.

Para obtener más información sobre el desarrollo de aplicaciones destinadas a .NET Framework, consulte la [Guía de desarrollo](../development-guide.md).

## <a name="related-articles"></a>Artículos relacionados

| Title | Descripción |
| ----- |------------ |
| [Información general](overview.md) | Proporciona información detallada para los desarrolladores que compilan aplicaciones cuyo destino es .NET Framework. |
| [Guía de instalación](../install/index.md) | Proporciona información sobre cómo instalar .NET Framework. |
| [.NET Framework y versiones fuera de banda](the-net-framework-and-out-of-band-releases.md) | Describe las versiones fuera de banda de .NET Framework y cómo utilizarlas en la aplicación. |
| [Requisitos del sistema](system-requirements.md) | Muestra los requisitos de hardware y software para ejecutar .NET Framework. |
| [.NET Core y código abierto](net-core-and-open-source.md) | Describe qué es .NET Core con respecto a .NET Framework y cómo acceder a los proyectos de .NET Core de código abierto. |
| [Documentación de .NET Core](../../core/introduction.md) | Contiene la documentación de referencia de API y conceptual de .NET Core. |
| [.NET Standard](../../standard/net-standard.md) | Describe .NET Standard, una especificación con versiones que las implementaciones individuales de .NET admiten con el fin de garantizar que hay un conjunto coherente de API disponible en varias plataformas.

## <a name="see-also"></a>Vea también

- [Guía de .NET Framework](../index.yml)
- [Novedades](../whats-new/index.md)
- [Explorador de API de .NET](../../../api/index.md)
- [Guía de desarrollo](../development-guide.md)
