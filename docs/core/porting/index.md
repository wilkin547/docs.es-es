---
title: Portabilidad de .NET Framework a .NET 5
description: Comprenda el proceso de portabilidad y descubra herramientas que le pueden resultar útiles al realizar la portabilidad de un proyecto de .NET Framework a .NET 5 (y .NET Core 3.1).
author: adegeo
ms.date: 03/03/2020
no-loc:
- package.config
- PackageReference
ms.openlocfilehash: 8515689cf4a1be917f12bb8f3315cda89988d773
ms.sourcegitcommit: 46cfed35d79d70e08c313b9c664c7e76babab39e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/10/2021
ms.locfileid: "102605053"
---
# <a name="overview-of-porting-from-net-framework-to-net"></a>Introducción a la portabilidad de .NET Framework a .NET

En este artículo se proporciona información general sobre lo que debe tener en cuenta al realizar la portabilidad de código de .NET Framework a .NET (anteriormente denominado .NET Core). La portabilidad a .NET desde .NET Framework es relativamente sencilla para muchos proyectos. La complejidad de los proyectos determina la cantidad de trabajo que se realizará después de la migración inicial de los archivos del proyecto.

Los proyectos para los que el modelo de aplicación está disponible en .NET (por ejemplo, bibliotecas, aplicaciones de consola y aplicaciones de escritorio) apenas necesitan cambios. Los proyectos en los que se necesita un nuevo modelo de aplicación, como en la migración a ASP.NET Core desde ASP.NET, exigen más trabajo. Muchos patrones del modelo de aplicación anterior tienen equivalentes que se pueden usar durante la conversión.

## <a name="unavailable-technologies"></a>Tecnologías no disponibles

Hay algunas tecnologías en .NET Framework que no existen en .NET:

- [Dominios de aplicación](net-framework-tech-unavailable.md#application-domains)

  No se admite la creación de dominios de aplicación adicionales. En el caso del aislamiento del código, use contenedores o procesos independientes como alternativa.

- [Comunicación remota](net-framework-tech-unavailable.md#remoting)

  Se usa para la comunicación entre dominios de aplicación, que ya no se admiten. Para la comunicación entre procesos, considere la posibilidad de usar mecanismos de comunicación entre procesos (IPC) como alternativa a la comunicación remota, como las clases <xref:System.IO.Pipes> o <xref:System.IO.MemoryMappedFiles.MemoryMappedFile>.

- [Seguridad de acceso del código (CAS)](net-framework-tech-unavailable.md#code-access-security-cas)

  CAS era una técnica de espacio aislado compatible con .NET Framework pero en desuso en .NET Framework 4.0. Se ha reemplazado por Transparencia de seguridad y no se admite en .NET. En su lugar, use los límites de seguridad que proporciona el sistema operativo, como la virtualización, los contenedores o las cuentas de usuario.

- [Transparencia de seguridad](net-framework-tech-unavailable.md#security-transparency)

  De forma similar a CAS, esta técnica de espacio aislado ya no se recomienda para las aplicaciones de .NET Framework y no se admite en .NET. En su lugar, use los límites de seguridad que proporciona el sistema operativo, como la virtualización, los contenedores o las cuentas de usuario.
  
- <xref:System.EnterpriseServices?displayProperty=fullName>

  <xref:System.EnterpriseServices?displayProperty=fullName> (COM+) no se admite en .NET.

- Windows Workflow Foundation (WF) y Windows Communication Foundation (WCF)

  WF y WCF no se admiten en .NET 5+ (incluido .NET Core). Para ver alternativas, consulte las páginas [CoreWF](https://github.com/UiPath/corewf) y [CoreWCF](https://github.com/CoreWCF/CoreWCF).

Para obtener más información sobre estas tecnologías no admitidas, vea [Tecnologías de .NET Framework no disponibles en .NET Core y .NET 5+](net-framework-tech-unavailable.md).

## <a name="windows-desktop-technologies"></a>Tecnologías de escritorio de Windows

En muchas aplicaciones creadas para .NET Framework se usa una tecnología de escritorio como Windows Forms o Windows Presentation Foundation (WPF). Tanto Windows Forms como WPF se han trasladado a .NET, pero siguen siendo tecnologías exclusivas de Windows.

Tenga en cuenta las dependencias siguientes antes de realizar la migración de una aplicación Windows Forms o WPF:

01. Los archivos del proyecto para .NET usan un formato diferente al de .NET Framework.
01. Es posible que en el proyecto se use una API que no esté disponible en .NET.
01. Es posible que los controles y las bibliotecas de terceros no se hayan migrado a .NET y solo estén disponibles para .NET Framework.
01. En el proyecto se usa una [tecnología que ya no está disponible](net-framework-tech-unavailable.md) en .NET.

.NET usa las versiones de código abierto de Windows Forms y WPF, e incluye mejoras con respecto a .NET Framework.

Para obtener tutoriales sobre cómo realizar la migración de la aplicación de escritorio a .NET 5, vea uno de los siguientes artículos:

- [Migración a .NET de aplicaciones WPF para .NET Framework](/dotnet/desktop/wpf/migration/convert-project-from-net-framework?view=netdesktop-5.0&preserve-view=true)
- [Migración a .NET de aplicaciones de Windows Forms para .NET Framework](/dotnet/desktop/winforms/migration/?view=netdesktop-5.0&preserve-view=true)

## <a name="windows-specific-apis"></a>API específicas de Windows

Las aplicaciones pueden seguir siendo bibliotecas nativas de invocación de plataforma en plataformas compatibles con .NET. Esta tecnología no está limitada a Windows. Pero si la biblioteca a la que hace referencia es específica de Windows, como _user32.dll_ o _kernal32.dll_, el código solo funciona en Windows. En cada plataforma en la que quiera ejecutar la aplicación, tendrá que buscar versiones específicas de la plataforma, o bien hacer que el código sea lo suficientemente genérico como para ejecutarse en todas las plataformas.

Al realizar la migración de una aplicación de .NET Framework a .NET, es probable que la aplicación use una biblioteca que se proporciona de forma distribuida con .NET Framework. Muchas API que estaban disponibles en .NET Framework no se han trasladado a .NET porque se basaban en tecnología específica de Windows, como el Registro de Windows o el modelo de dibujo de GDI+.

El **paquete de compatibilidad de Windows** proporciona una gran parte de la superficie de API de .NET Framework a .NET y se ofrece por medio del [paquete NuGet Microsoft.Windows.Compatibility](https://www.nuget.org/packages/Microsoft.Windows.Compatibility).

Para obtener más información, vea [Uso del paquete de compatibilidad de Windows para trasladar código a .NET](windows-compat-pack.md).

## <a name="net-framework-compatibility-mode"></a>Modo de compatibilidad de .NET Framework

El modo de compatibilidad de .NET Framework se introdujo en .NET Standard 2.0. Este modo de compatibilidad permite que los proyectos de .NET Standard y .NET 5+ (y .NET Core 3.1) hagan referencia a bibliotecas de .NET Framework solo en Windows. La acción de hacer referencias a bibliotecas de .NET Framework no funciona para todos los proyectos; por ejemplo, si la biblioteca usa API de Windows Presentation Foundation (WPF) pero desbloquea muchos escenarios de portabilidad. Para obtener más información, vea [Análisis de las dependencias para trasladar código desde .NET Framework a .NET](third-party-deps.md#net-framework-compatibility-mode).

## <a name="cross-platform"></a>Multiplataforma

.NET (antes conocido como .NET Core) está diseñado para ser multiplataforma. Si el código no depende de tecnologías específicas de Windows, puede ejecutarse en otras plataformas, como macOS, Linux y Android. Esto incluye tipos de proyecto como los siguientes:

- Bibliotecas
- Herramientas basadas en consola
- Automatización
- Sitios de ASP.NET

.NET Framework es un componente solo de Windows. Cuando el código usa tecnologías específicas de Windows o API, como Windows Forms y Windows Presentation Foundation (WPF), todavía se puede ejecutar en .NET, pero no en otros sistemas operativos.

Es posible que la biblioteca o la aplicación basada en consola se puedan usar entre plataformas sin demasiados cambios. Al realizar la migración a .NET, es posible que quiera tenerlo en cuenta y probar la aplicación en otras plataformas.

## <a name="the-future-of-net-standard"></a>El futuro de .NET Standard

[.NET Standard](https://github.com/dotnet/standard) es una especificación formal de las API de .NET que están disponibles en varias implementaciones de .NET. La finalidad de .NET Standard ha sido establecer una mayor uniformidad en el ecosistema de .NET. A partir de .NET 5, se ha adoptado otro enfoque para establecer la uniformidad, en el que se elimina la necesidad de .NET Standard en muchos escenarios. Para obtener más información, vea [.NET 5 y .NET Standard](../../standard/net-standard.md#net-5-and-net-standard).

.NET Standard 2.0 ha sido la última versión en la que se ha admitido .NET Framework.

## <a name="tools-to-assist-porting"></a>Herramientas para facilitar la migración

En lugar de realizar la migración manual de una aplicación de .NET Framework a .NET, puede usar distintas herramientas que faciliten la automatización de algunos aspectos de la migración. La portabilidad de un proyecto complejo es, en sí mismo, un proceso complejo. Estas herramientas pueden ayudarle en ese recorrido.

Aunque use una herramienta que le ayude a realizar la portabilidad de la aplicación, debe revisar la [sección Consideraciones de portabilidad](#considerations-when-porting) de este artículo.

### <a name="net-upgrade-assistant"></a>.NET Upgrade Assistant

[.NET Upgrade Assistant](upgrade-assistant-overview.md) (Asistente para actualización de .NET) es una herramienta de línea de comandos que se puede ejecutar en diferentes tipos de aplicaciones de .NET Framework. Está diseñado para facilitar la actualización de aplicaciones de .NET Framework a .NET 5. Después de ejecutar la herramienta, **en la mayoría de los casos, la aplicación necesitará más esfuerzo para completar la migración**. La herramienta incluye la instalación de analizadores que pueden ayudarle a completar la migración. Esta herramienta funciona en los siguientes tipos de aplicaciones de .NET Framework:

- Windows Forms
- WPF
- ASP.NET MVC
- Consola
- Bibliotecas de clases

Esta herramienta usa las otras que se enumeran en este artículo y guía el proceso de migración. Para obtener más información sobre la herramienta, vea [Información general de .NET Upgrade Assistant](upgrade-assistant-overview.md).

### <a name="try-convert"></a>try-convert

try-convert es una herramienta global de .NET que puede convertir un proyecto o una solución completa en el SDK de .NET, así como trasladar aplicaciones de escritorio a .NET 5. Pero esta herramienta no se recomienda si el proyecto tiene un proceso de compilación complicado, como tareas personalizadas, destinos o importaciones.

Para obtener más información, vea el [repositorio de try-convert en GitHub](https://github.com/dotnet/try-convert).

### <a name="net-portability-analyzer"></a>Analizador de portabilidad de .NET

El Analizador de portabilidad de .NET es una herramienta que analiza ensamblados y proporciona un informe detallado sobre las API de .NET que faltan para que las aplicaciones o bibliotecas sean portátiles en las plataformas .NET de destino.

Para usar el Analizador de portabilidad de .NET en Visual Studio, instale la [extensión desde el marketplace](https://marketplace.visualstudio.com/items?itemName=ConnieYau.NETPortabilityAnalyzer).

Para obtener más información, vea [Analizador de portabilidad de .NET](../../standard/analyzers/portability-analyzer.md).

### <a name="net-api-analyzer"></a>Analizador de API de .NET

El [Analizador de API de .NET](../../standard/analyzers/api-analyzer.md) analiza si utiliza o no una API que iniciará una excepción <xref:System.PlatformNotSupportedException> en tiempo de ejecución. Aunque esto no es habitual si va a realizar la portabilidad desde .NET Framework 4.7.2 o superior, es conveniente comprobarlo. Para obtener más información sobre las API que inician excepciones en .NET, vea [API que siempre inician excepciones en .NET Core](../compatibility/unsupported-apis.md).

El Analizador de API está disponible como un paquete NuGet [Microsoft.DotNet.Analyzers.Compatibility](https://www.nuget.org/packages/Microsoft.DotNet.Analyzers.Compatibility/) para agregar al proyecto.

Para más información, consulte [Analizador de API en .NET](../../standard/analyzers/api-analyzer.md).

## <a name="considerations-when-porting"></a>Consideraciones de portabilidad

Al realizar la portabilidad de la aplicación a .NET, tenga en cuenta las siguientes sugerencias en orden.

✔️ CONSIDERE la posibilidad de usar el [.NET Upgrade Assistant](upgrade-assistant-overview.md) para la migración de los proyectos. Aunque esta herramienta se encuentra en versión preliminar, automatiza la mayoría de los pasos manuales que se detallan en este artículo y ofrece un excelente punto de partida para continuar con la ruta de migración.

✔️ CONSIDERE la posibilidad de examinar primero las dependencias. Las dependencias deben tener como destino .NET 5, .NET Standard o .NET Core.

✔️ REALICE la migración desde un archivo _packages.config_ de NuGet a la configuración [PackageReference](/nuget/consume-packages/package-references-in-project-files) del archivo del proyecto. Use Visual Studio para [convertir el archivo _package.config_ ](/nuget/consume-packages/migrate-packages-config-to-package-reference#migration-steps).

✔️ CONSIDERE la posibilidad de actualizar al formato de archivo del proyecto más reciente incluso si todavía no puede realizar la portabilidad de la aplicación. En los proyectos de .NET Framework se usa un formato de proyecto obsoleto. Aunque el formato de proyecto más reciente, conocido como proyectos de estilo SDK, se ha creado para .NET Core y versiones posteriores, funciona con .NET Framework. Tener el archivo del proyecto en el formato más reciente le proporciona una buena base para realizar la portabilidad de la aplicación en el futuro.

✔️ CAMBIE el destino del proyecto de .NET Framework a .NET Framework 4.7.2 como mínimo. Así, se garantiza la disponibilidad de las alternativas de API más recientes en los casos en que .NET Standard no admite las API existentes.

✔️ CONSIDERE la posibilidad de seleccionar como destino .NET 5 en lugar de .NET Core 3.1. Aunque .NET Core 3.1. está en soporte a largo plazo (LTS), .NET 5 es la versión más reciente y .NET 6 estará en LTS cuando se publique.

✔️ SELECCIONE como destino .NET 5 para proyectos de **Windows Forms y WPF**. .NET 5 contiene muchas mejoras para las aplicaciones de escritorio.

✔️ CONSIDERE la posibilidad de seleccionar como destino .NET Standard 2.0 si va a realizar la migración de una biblioteca que también se puede usar con proyectos de .NET Framework. También puede seleccionar varios destinos para la biblioteca, como .NET Framework y .NET Standard.

✔️ AGREGUE una referencia al paquete [NuGet Microsoft.Windows.Compatibility](https://www.nuget.org/packages/Microsoft.Windows.Compatibility) si, después de la migración, obtiene errores de API que faltan. Una gran parte de la superficie de API de .NET Framework está disponible para .NET mediante el paquete NuGet.

## <a name="see-also"></a>Vea también

- [Información general sobre .NET Upgrade Assistant](upgrade-assistant-overview.md)
- [Migración de ASP.NET s ASP.NET Core](/aspnet/core/migration/proper-to-2x)
- [Migración a .NET de aplicaciones WPF para .NET Framework](/dotnet/desktop/wpf/migration/convert-project-from-net-framework?view=netdesktop-5.0&preserve-view=true)
- [Migración a .NET de aplicaciones de Windows Forms para .NET Framework](/dotnet/desktop/winforms/migration/?view=netdesktop-5.0&preserve-view=true)
- [Traslado de bibliotecas de .NET Framework a .NET](libraries.md)
- [Diferencias entre .NET 5 y .NET Framework en cuanto a aplicaciones de servidor](../../standard/choosing-core-framework-server.md)
