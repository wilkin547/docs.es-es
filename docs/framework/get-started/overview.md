---
title: Información general acerca de .NET Framework
description: Consulte la información general sobre .NET Framework, que es una tecnología que admite la creación y ejecución de servicios web y aplicaciones Windows.
ms.date: 03/30/2017
helpviewer_keywords:
- application development [.NET Framework]
- common language runtime
- common language runtime, about
- common language runtime, overview
ms.assetid: 29848c96-fc36-462d-8072-ba223a40b697
ms.openlocfilehash: 3577a3ad13d9ef6935a1bed8a29e3d594857928e
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/15/2020
ms.locfileid: "90557767"
---
# <a name="overview-of-net-framework"></a>Información general acerca de .NET Framework

.NET Framework es una tecnología que admite la creación y ejecución de servicios web y aplicaciones Windows. El diseño de .NET Framework está enfocado a cumplir los objetivos siguientes:

- Proporcionar un entorno coherente de programación orientada a objetos, en el que el código de los objetos se pueda almacenar y ejecutar de forma local, ejecutar de forma local pero distribuida en Internet o ejecutar de forma remota.

- Proporcionar un entorno de ejecución de código que reduzca lo máximo posible la implementación de software y los conflictos de versiones.

- Ofrecer un entorno de ejecución de código que promueva la ejecución segura del mismo, incluso del creado por terceras personas desconocidas o que no son de plena confianza.

- Proporcionar un entorno de ejecución de código que elimine los problemas de rendimiento de los entornos en los que se utilizan scripts o intérpretes de comandos.

- Ofrecer al programador una experiencia coherente entre tipos de aplicaciones muy diferentes, como las basadas en Windows o en Web.

- Basar toda la comunicación en estándares del sector para asegurar que el código de .NET Framework se puede integrar con otros tipos de código.

> [!NOTE]
> Para una introducción general a .NET Framework para usuarios y desarrolladores, consulte [Introducción](index.md).

.NET Framework consta de dos componentes principales: Common Language Runtime (CLR) y la biblioteca de clases de .NET Framework. Common Language Runtime es el fundamento de .NET Framework. El tiempo de ejecución se puede considerar como un agente que administra el código en tiempo de ejecución y proporciona servicios centrales, como la administración de memoria, la administración de subprocesos y la comunicación remota, al tiempo que aplica una seguridad de tipos estricta y otras formas de especificación del código que promueven su seguridad y solidez. De hecho, el concepto de administración de código es un principio básico del motor en tiempo de ejecución. El código destinado al tiempo de ejecución se denomina código administrado, a diferencia del resto de código, que se conoce como código no administrado. La biblioteca de clases es una colección completa orientada a objetos de tipos reutilizables que se puede emplear para desarrollar aplicaciones que abarcan desde las tradicionales herramientas de interfaz gráfica de usuario (GUI) o de línea de comandos hasta aplicaciones basadas en las innovaciones más recientes proporcionadas por ASP.NET, como formularios Web Forms y servicios web XML.

.NET Framework puede hospedarse en componentes no administrados que cargan Common Language Runtime en sus procesos e inician la ejecución de código administrado, con lo que se crea un entorno de software que usa características administradas y no administradas. En .NET Framework no solo se ofrecen varios hosts de tiempo de ejecución, sino que también se admite el desarrollo de estos hosts por parte de terceros.

Por ejemplo, ASP.NET hospeda el motor en tiempo de ejecución para proporcionar un entorno de servidor escalable para el código administrado. ASP.NET trabaja directamente con el tiempo de ejecución para habilitar aplicaciones de ASP.NET y servicios web XML, que se tratan más adelante en este artículo.

Internet Explorer es un ejemplo de aplicación no administrada que hospeda el tiempo de ejecución (en forma de una extensión de tipo MIME). Al usar Internet Explorer para hospedar el motor en tiempo de ejecución, puede incrustar componentes administrados o controles de Windows Forms en documentos HTML. Al hospedar el tiempo de ejecución de esta manera se hace posible el uso de código móvil administrado, pero con mejoras significativas que solo el código administrado puede ofrecer, como la ejecución con confianza parcial y el almacenamiento aislado de archivos.

En la ilustración siguiente se muestra la relación de Common Language Runtime y la biblioteca de clases con las aplicaciones y el sistema en su conjunto. En la ilustración se representa igualmente cómo funciona el código administrado dentro de una arquitectura mayor.

![Captura de pantalla que muestra cómo funciona el código administrado dentro de una arquitectura más amplia.](./media/overview/language-runtime-class-library-relationship.gif)

En las siguientes secciones se describen con más detalle las características principales de .NET Framework.

## <a name="features-of-the-common-language-runtime"></a>Características de Common Language Runtime

Common Language Runtime administra la memoria, ejecución de subprocesos, ejecución de código, comprobación de la seguridad del código, compilación y demás servicios del sistema. Estas características son intrínsecas del código administrado que se ejecuta en Common Language Runtime.

Con respecto a la seguridad, los componentes administrados reciben grados de confianza diferentes en función de una serie de factores, entre los que se incluye su origen (como Internet, red empresarial o equipo local). Esto significa que un componente administrado puede ser capaz o no de realizar operaciones de acceso a archivos, operaciones de acceso al Registro y otras funciones delicadas, incluso si se usa en la misma aplicación activa.

Además, el motor en tiempo de ejecución impone la solidez del código mediante la implementación de una infraestructura estricta de comprobación de tipos y código denominada CTS (Common Type System, Sistema de tipos común). CTS garantiza que todo el código administrado es autodescriptivo. Los diversos compiladores de lenguaje de Microsoft y de otros fabricantes generan código administrado que se atiene al CTS. Esto significa que el código administrado puede consumir otros tipos e instancias administrados, al tiempo que se exige fidelidad de tipos y seguridad de tipos estrictamente.

Además, el entorno administrado del motor en tiempo de ejecución elimina muchos problemas de software comunes. Por ejemplo, el motor en tiempo de ejecución controla automáticamente la disposición de los objetos, administra las referencias a éstos y los libera cuando ya no se utilizan. Esta administración automática de la memoria soluciona los dos errores más comunes de las aplicaciones: la fuga de memoria y las referencias no válidas a la memoria.

Además, el motor en tiempo de ejecución aumenta la productividad del programador. Por ejemplo, los desarrolladores pueden crear aplicaciones en el lenguaje que prefieran y seguir sacando todo el provecho del tiempo de ejecución, la biblioteca de clases y los componentes escritos en otros lenguajes por otros colegas. El proveedor de un compilador puede elegir destinarlo al motor en tiempo de ejecución. Los compiladores de lenguajes que se destinan a .NET Framework hacen que las características de .NET Framework estén disponibles para el código existente escrito en dicho lenguaje, lo que facilita enormemente el proceso de migración de las aplicaciones existentes.

Aunque el motor en tiempo de ejecución está diseñado para el software del futuro, también es compatible con el software actual y el software antiguo. La interoperabilidad entre el código administrado y no administrado permite que los desarrolladores continúen utilizando los componentes COM y las DLL que necesiten.

El motor en tiempo de ejecución está diseñado para mejorar el rendimiento. Aunque Common Language Runtime proporciona muchos servicios estándar de motor en tiempo de ejecución, el código administrado nunca se interpreta. Una característica denominada compilación JIT (Just-In-Time) permite ejecutar todo el código administrado en el lenguaje de máquina nativo del sistema en el que se ejecuta. Mientras tanto, el administrador de memoria evita que la memoria se pueda fragmentar y aumenta la zona de referencia de la memoria para mejorar aún más el rendimiento.

Por último, el tiempo de ejecución se puede hospedar en aplicaciones de servidor de gran rendimiento, como Microsoft SQL Server e Internet Information Services (IIS). Esta infraestructura permite utilizar código administrado para escribir lógica empresarial, al tiempo que se disfruta del superior rendimiento de los mejores servidores empresariales del sector que puedan hospedar el motor en tiempo de ejecución.

## <a name="net-framework-class-library"></a>Biblioteca de clases de .NET Framework

La biblioteca de clases de .NET Framework es una colección de tipos reutilizables que se integran estrechamente con Common Language Runtime. La biblioteca de clases está orientada a objetos, lo que proporciona tipos de los que su propio código administrado deriva funciones. Esto hace que los tipos de .NET Framework sean fáciles de usar y reduce el tiempo asociado con el aprendizaje de las nuevas características de .NET Framework. Además, los componentes de terceros se integran sin dificultades con las clases de .NET Framework.

Por ejemplo, las clases de colección de .NET Framework implementan un conjunto de interfaces que le permiten desarrollar sus propias clases de colección. Estas se combinan a la perfección con las clases de .NET Framework.

Como en cualquier biblioteca de clases orientada a objetos, los tipos de .NET Framework permiten realizar diversas tareas de programación comunes, como son la administración de cadenas, la recolección de datos, la conectividad de bases de datos y el acceso a archivos. Además de estas tareas habituales, la biblioteca de clases incluye tipos adecuados para diversos escenarios de desarrollo especializados. Use .NET Framework para desarrollar los siguientes tipos de aplicaciones y servicios:

- Aplicaciones de consola. Consulte [Compilar aplicaciones de consola](../../standard/building-console-apps.md).

- Aplicaciones de GUI de Windows (Windows Forms). Consulte [Windows Forms](/dotnet/desktop/winforms/).

- Aplicaciones de Windows Presentation Foundation (WPF). Vea [Windows Presentation Foundation](/dotnet/desktop/wpf/).

- Aplicaciones ASP.NET. Vea [Aplicaciones web con ASP.NET](../develop-web-apps-with-aspnet.md).

- Servicios de Windows. Vea [Introducción a las aplicaciones de servicios de Windows](../windows-services/introduction-to-windows-service-applications.md).

- Aplicaciones orientadas a servicios mediante Windows Communication Foundation (WCF). Vea [Aplicaciones orientadas a servicios con WCF](../wcf/index.md).

- Aplicaciones habilitadas para el flujo de trabajo mediante Windows Workflow Foundation (WF). Vea [Windows Workflow Foundation](../windows-workflow-foundation/index.md).

Las clases de Windows Forms son un conjunto completo de tipos reutilizables que simplifican enormemente el desarrollo de GUI para Windows. Si escribe una aplicación de formularios Web Forms de ASP.NET, puede usar las clases de formularios Web Forms.

## <a name="see-also"></a>Vea también

- [Requisitos del sistema](system-requirements.md)
- [Guía de instalación](../install/index.md)
- [Guía de desarrollo](../development-guide.md)
- [Herramientas](../tools/index.md)
- [Ejemplos y tutoriales de .NET](../../samples-and-tutorials/index.md)
- [Explorador de API de .NET](../../../api/index.md)
