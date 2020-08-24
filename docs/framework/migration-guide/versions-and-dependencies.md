---
title: Versiones de .NET Framework y sistema operativo Windows
description: Obtenga información sobre las características clave de cada versión de .NET Framework, incluidas las versiones del CLR subyacentes y las versiones instaladas por el sistema operativo Windows.
ms.date: 01/17/2020
helpviewer_keywords:
- versions, .NET Framework
ms.assetid: f75a72de-e2f2-4a7a-9574-3f278684ea90
ms.openlocfilehash: fe652e4cc3a996586d01cdfc4c5749decb51e9db
ms.sourcegitcommit: 8bfeb5930ca48b2ee6053f16082dcaf24d46d221
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/18/2020
ms.locfileid: "88557352"
---
# <a name="net-framework-versions-and-dependencies"></a>Versiones y dependencias de .NET Framework

Cada versión de .NET Framework contiene Common Language Runtime (CLR), las bibliotecas de clases base y otras bibliotecas administradas. En este artículo se describen las características principales de cada versión de .NET Framework, se proporciona información sobre las versiones de CLR subyacentes y los entornos de desarrollo asociados, y se identifican las versiones que instala el sistema operativo Windows (SO).

Cada versión de .NET Framework incorpora nuevas características, pero mantiene otras de versiones anteriores.

CLR se identifica mediante su propio número de versión. El número de versión de .NET Framework aumenta con cada nueva publicación, pero la versión de CLR no siempre se incrementa. Por ejemplo, en .NET Framework 4, 4.5 y versiones posteriores se incluye CLR 4, mientras que en .NET Framework 2.0, 3.0 y 3.5 se incluye CLR 2.0. (No existe la versión 3 de CLR).

> [!TIP]
>
> - Para obtener una lista completa de los sistemas operativos compatibles, consulte [Requisitos del sistema](../get-started/system-requirements.md).
> - Para descargas, consulte [Install the .NET Framework for developers](../install/guide-for-developers.md) (Instalar .NET Framework para desarrolladores).
> - Para obtener información sobre cómo determinar qué versiones de .NET Framework hay instaladas en un equipo, consulte [Procedimiento para determinar qué versiones de .NET Framework están instaladas](how-to-determine-which-versions-are-installed.md).

## <a name="version-information"></a>Información de la versión

En las tablas siguientes se resume el historial de versiones de .NET Framework y se relaciona cada versión con Visual Studio, Windows y Windows Server. Visual Studio admite múltiples versiones (multi-targeting), por lo que no está limitado a la versión de .NET Framework que se muestra.

- El icono de marca de verificación ✔️ denota las versiones del sistema operativo en las que .NET Framework está instalado de forma predeterminada.
- El icono de signo más ➕ denota las versiones del sistema operativo en las que no está instalado .NET Framework, pero en las que se puede instalar.
- El asterisco **\*** denota las versiones del sistema operativo en las que .NET Framework (preinstalado o no) debe estar habilitado [en el Panel de control](../install/dotnet-35-windows-10.md) o, en el caso de Windows Server, mediante el Administrador del servidor.

| | |
| - | - |
| [.NET Framework 4.8](#net-framework-48) | [.NET Framework 4.7.2](#net-framework-472) | [.NET Framework 4.7.1](#net-framework-471) | [.NET Framework 4.7](#net-framework-47) |
| [.NET Framework 4.6.2](#net-framework-462) | [.NET Framework 4.6.1](#net-framework-461) | [.NET Framework 4.6](#net-framework-46) | [.NET Framework 4.5.2](#net-framework-452) |
| [.NET Framework 4.5.1](#net-framework-451) | [.NET Framework 4.5](#net-framework-45) | [.NET Framework 4](#net-framework-4) | [.NET Framework 3.5](#net-framework-35) |
| [.NET Framework 3.0](#net-framework-30) | [.NET Framework 2.0](#net-framework-20) | [.NET Framework 1.1](#net-framework-11) | [.NET Framework 1.0](#net-framework-10) |

### <a name="net-framework-48"></a>.NET Framework 4.8

- [Características nuevas](../whats-new/index.md#whats-new-in-net-framework-48)
- [Novedades de accesibilidad](../whats-new/whats-new-in-accessibility.md#whats-new-in-accessibility-in-net-framework-48)
- [Notas de la versión](https://github.com/Microsoft/dotnet/tree/master/releases/net48/README.md)

|||
|-|-|
|**Versión de CRL**|4|
|**Versiones de Windows**|✔️ Actualización de mayo de 2019 de Windows 10<br/>➕ Actualización de octubre de 2018 de Windows 10 (versión 1809)<br/>➕ Actualización de abril de 2018 de Windows 10 (versión 1803)<br/>➕ Windows 10 Fall Creators Update (versión 1709)<br/>➕ Windows 10 Creators Update (versión 1703)<br/>➕ Actualización de aniversario de Windows 10 (versión 1607)<br/>➕ 8.1<br/>➕7|
|**Versiones de Windows Server**|➕ Windows Server 2019<br/>➕ Windows Server, versión 1809<br/>➕ Windows Server, versión 1803<br/>➕ 2016<br/>➕ 2012 R2<br/>➕ 2012<br/>➕ 2008 R2 SP1|
|**Para determinar la versión de .NET instalada**|Use `Release` DWORD:<br/>- 528040 (Actualización de mayo de 2019 de Windows 10)<br/>- 528049 (resto de versiones del sistema operativo)<br/>(Consulte las [instrucciones](how-to-determine-which-versions-are-installed.md))|

### <a name="net-framework-472"></a>.NET Framework 4.7.2

- [Características nuevas](../whats-new/index.md#whats-new-in-net-framework-472)
- [Novedades de accesibilidad](../whats-new/whats-new-in-accessibility.md#whats-new-in-accessibility-in-net-framework-472)
- [Notas de la versión](https://github.com/Microsoft/dotnet/tree/master/releases/net472/README.md)

|||
|-|-|
|**Versión de CRL**|4|
|**Incluido en la versión de Visual Studio**|2019<sup>1</sup>|
|**Versiones de Windows**|✔️ Actualización de octubre de 2018 de Windows 10 (versión 1809)<br/>✔️ Actualización de abril de 2018 de Windows 10 (versión 1803)<br/>➕ Windows 10 Fall Creators Update (versión 1709)<br/>➕ Windows 10 Creators Update (versión 1703)<br/>➕ Actualización de aniversario de Windows 10 (versión 1607)<br/>➕ 8.1<br/>➕7|
|**Versiones de Windows Server**|✔️ Windows Server 2019<br/>✔️ Windows Server, versión 1809<br/>✔️ Windows Server, versión 1803<br/>➕ Windows Server, versión 1709<br/>➕ 2016<br/>➕ 2012 R2<br/>➕ 2012<br/>➕ 2008 R2 SP1|
|**Para determinar la versión de .NET instalada**|Use `Release` DWORD:<br/>- 461814 (Actualización de octubre de 2018 de Windows 10)<br/>-461808 (actualización de Windows del 10 de abril de 2018 y Windows Server, versión 1803)<br/>- 461814 (resto de versiones del sistema operativo)<br/>(Consulte las [instrucciones](how-to-determine-which-versions-are-installed.md))|

<sup>1</sup> Requiere la instalación del **desarrollo de escritorio de .NET**, **ASP.NET y el desarrollo web**, **el desarrollo de Azure**, **el desarrollo de Office/SharePoint**, **el desarrollo móvil con .NET** o las cargas de trabajo de **desarrollo multiplataforma de .NET Core**.

### <a name="net-framework-471"></a>.NET Framework 4.7.1

- [Características nuevas](../whats-new/index.md#whats-new-in-net-framework-471)
- [Novedades de accesibilidad](../whats-new/whats-new-in-accessibility.md#whats-new-in-accessibility-in-net-framework-471)
- [Notas de la versión](https://github.com/Microsoft/dotnet/tree/master/releases/net471/README.md)

|||
|-|-|
|**Versión de CRL**|4|
|**Versiones de Windows**|✔️ Windows 10 Fall Creators Update (versión 1709)<br/>➕ Windows 10 Creators Update (versión 1703)<br/>➕ Actualización de aniversario de Windows 10 (versión 1607)<br/>➕ 8.1<br/>➕7|
|**Versiones de Windows Server**|➕ Windows Server, versión 1803<br/>✔️ Windows Server, versión 1709<br/>➕ 2016<br/>➕ 2012 R2<br/>➕ 2012<br/>➕ 2008 R2 SP1|
|**Para determinar la versión de .NET instalada**|Use `Release` DWORD:<br/>- 461308 (Windows 10 Creators Update y Windows Server, versión 1709)<br/>- 461310 (resto de versiones del sistema operativo)<br/>(Consulte las [instrucciones](how-to-determine-which-versions-are-installed.md))|

### <a name="net-framework-47"></a>.NET Framework 4.7

- [Características nuevas](../whats-new/index.md#whats-new-in-net-framework-47)
- [Notas de la versión](https://github.com/Microsoft/dotnet/tree/master/releases/net47/README.md)

|||
|-|-|
|**Versión de CRL**|4|
|**Versiones de Windows**|✔️ Windows 10 Creators Update (versión 1703)<br/>➕ Actualización de aniversario de Windows 10 (versión 1607)<br/>➕ 8.1<br/>➕7|
|**Versiones de Windows Server**|➕ 2016<br/>➕ 2012 R2<br/>➕ 2012<br/>➕ 2008 R2 SP1|
|**Para determinar la versión de .NET instalada**|Use `Release` DWORD:<br/>- 460798 (Windows 10 Creators Update)<br/>- 460805 (resto de versiones del sistema operativo)<br/>(Consulte las [instrucciones](how-to-determine-which-versions-are-installed.md))|

### <a name="net-framework-462"></a>.NET Framework 4.6.2

- [Características nuevas](../whats-new/index.md#whats-new-in-net-framework-462)
- [Notas de la versión](https://github.com/Microsoft/dotnet/tree/master/releases/net462/README.md)

|||
|-|-|
|**Versión de CRL**|4|
|**Versiones de Windows**|✔️ Actualización de aniversario de Windows 10 (versión 1607)<br/>➕ Actualización de noviembre de Windows 10 (versión 1511)<br/>➕ 10<br/>➕ 8.1<br />➕ 7|
|**Versiones de Windows Server**|✔️ 2016<br /><br/>➕ 2012 R2<br />➕ 2012<br />➕ 2008 R2 SP1|
|**Para determinar la versión de .NET instalada**|Use `Release` DWORD:<br /><br/>- 394802 (Actualización de aniversario de Windows 10 y Windows Server 2016)<br/>- 394806 (resto de versiones del sistema operativo)<br /><br/>(Consulte las [instrucciones](how-to-determine-which-versions-are-installed.md))|

### <a name="net-framework-461"></a>.NET Framework 4.6.1

- [Características nuevas](../whats-new/index.md#whats-new-in-net-framework-461)
- [Notas de la versión](https://github.com/Microsoft/dotnet/tree/master/releases/net461/README.md)

|||
|-|-|
|**Versión de CRL**|4|
|**Incluido en la versión de Visual Studio**|2017<sup>1</sup>|
|**Versiones de Windows**|✔️ Actualización de noviembre de Windows 10 (versión 1511)<br/>➕ 10<br />➕ 8.1<br />➕ 8<br />➕ 7|
|**Versiones de Windows Server**|➕ 2012 R2<br />➕ 2012<br />➕ 2008 R2 SP1|
|**Para determinar la versión de .NET instalada**|Use `Release` DWORD:<br /><br/>- 394254 (Actualización de noviembre de Windows 10)<br />- 394271 (resto de versiones del sistema operativo)<br /><br/>(Consulte las [instrucciones](how-to-determine-which-versions-are-installed.md))|

<sup>1</sup> Requiere la instalación del **desarrollo de escritorio de .NET**, **ASP.NET y el desarrollo web**, **el desarrollo de Azure**, **el desarrollo de Office/SharePoint**, **el desarrollo móvil con .NET** o las cargas de trabajo de **desarrollo multiplataforma de .NET Core**.

### <a name="net-framework-46"></a>.NET Framework 4.6

- [Características nuevas](../whats-new/index.md#whats-new-in-net-2015)
- [Notas de la versión](https://github.com/Microsoft/dotnet/tree/master/releases/net46/README.md)

|||
|-|-|
|**Versión de CRL**|4|
|**Incluido en la versión de Visual Studio**|2015|
|**Versiones de Windows**|✔️ 10<br /><br />➕ 8.1<br />➕ 8<br />➕ 7<br />➕ Vista|
|**Versiones de Windows Server**|➕ 2012 R2<br />➕ 2012<br />➕ 2008 R2 SP1<br />➕ 2008 SP2|
|**Para determinar la versión de .NET instalada**|Use `Release` DWORD:<br /><br />- 393295 (Windows 10)<br />- 393297 (resto de versiones del sistema operativo)<br /><br />(Consulte las [instrucciones](how-to-determine-which-versions-are-installed.md))|

### <a name="net-framework-452"></a>.NET Framework 4.5.2

- [Características nuevas](../whats-new/index.md#whats-new-in-net-framework-452)
- [Notas de la versión](https://github.com/Microsoft/dotnet/tree/master/releases/net452/README.md)

|||
|-|-|
|**Versión de CRL**|4|
|**Versiones de Windows**|➕ 8.1<br />➕ 8<br />➕ 7<br />➕ Vista|
|**Versiones de Windows Server**|➕ 2012 R2<br />➕ 2012<br />➕ 2008 R2 SP1<br />➕ 2008 SP2|
|**Para determinar la versión de .NET instalada**|Use `Release` DWORD: 379893<br /><br />(Consulte las [instrucciones](how-to-determine-which-versions-are-installed.md))|

### <a name="net-framework-451"></a>.NET Framework 4.5.1

- [Características nuevas](../whats-new/index.md#whats-new-in-net-framework-451)
- [Notas de la versión](https://github.com/Microsoft/dotnet/tree/master/releases/net451/README.md)

|||
|-|-|
|**Versión de CRL**|4|
|**Incluido en la versión de Visual Studio**|2013|
|**Versiones de Windows**|✔️ 8.1<br /><br />➕ 8<br />➕ 7<br />➕ Vista|
|**Versiones de Windows Server**|✔️ 2012 R2<br /><br />➕ 2012<br />➕ 2008 R2 SP1<br />➕ 2008 SP2|
|**Para determinar la versión de .NET instalada**|Use `Release` DWORD:<br /><br />- 378675 (Windows 8.1)<br />- 378758 (todas las demás)<br /><br />(Consulte las [instrucciones](how-to-determine-which-versions-are-installed.md))|

### <a name="net-framework-45"></a>.NET Framework 4.5

- [Características nuevas](../whats-new/index.md#whats-new-in-net-framework-45)
- [Notas de la versión](https://github.com/Microsoft/dotnet/tree/master/releases/net45/README.md)

|||
|-|-|
|**Versión de CRL**|4|
|**Incluido en la versión de Visual Studio**|2012|
|**Versiones de Windows**|✔️ 8<br />➕ 7<br />➕ Vista|
|**Versiones de Windows Server**|✔️ 2012<br />➕ 2008 R2 SP1<br />➕ 2008 SP2|
|**Para determinar la versión de .NET instalada**|Use `Release` DWORD: 378389<br /><br />(Consulte las [instrucciones](how-to-determine-which-versions-are-installed.md))|

### <a name="net-framework-4"></a>.NET Framework 4

[Características nuevas](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/ms171868(v=vs.100))

|||
|-|-|
|**Versión de CRL**|4|
|**Incluido en la versión de Visual Studio**|2010|
|**Versiones de Windows**|➕ 7<br />➕ Vista|
|**Versiones de Windows Server**|➕ 2008 R2 SP1<br />➕ 2008 SP2<br />➕ 2003|
|**Para determinar la versión de .NET instalada**|Consulte las [instrucciones](how-to-determine-which-versions-are-installed.md)|

### <a name="net-framework-35"></a>.NET Framework 3,5

[Características nuevas](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2008/ms171868\(v=vs.90\)):

- LINQ
- Árboles de expresión
- Compatibilidad de ASP.NET mejorada con el desarrollo en AJAX
- HashSet (colecciones)
- DateTimeOffset
- Integración de WPF y WF
- Conexión de redes punto a punto
- Complementos de extensibilidad

|||
|-|-|
|**Versión de CRL**|2.0|
|**Incluido en la versión de Visual Studio**|2008|
|**Versiones de Windows**|✔️ 10\*<br/>✔️ 8.1\*<br />✔️ 8\*<br />✔️ 7<br /><br />➕ Vista|
|**Versiones de Windows Server**|➕ Windows Server, versión 1803\*<br/>➕ Windows Server, versión 1709\*<br/>➕ 2016\*<br/>➕ 2012 R2\*<br />➕ 2012\*<br /><br />✔️2008 R2 SP1\*<br /><br/>➕ 2008 SP2<br />➕ 2003|
|**Para determinar la versión de .NET instalada**|Consulte las [instrucciones](how-to-determine-which-versions-are-installed.md)|

### <a name="net-framework-30"></a>.NET Framework 3.0

[Características nuevas](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2008/bb822048(v=vs.90)):

- Windows Presentation Foundation
- Windows Communication Foundation
- Windows Workflow Foundation
- Windows CardSpace

|||
|-|-|
|**Versión de CRL**|2.0|
|**Versiones de Windows**|✔️ Vista|
|**Versiones de Windows Server**|✔️ 2008 R2 SP1*<br />✔️ 2008 SP2\*<br /><br />➕ 2003|
|**Para determinar la versión de .NET instalada**|Consulte las [instrucciones](how-to-determine-which-versions-are-installed.md).|

### <a name="net-framework-20"></a>.NET Framework 2.0

[Características nuevas](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2008/t357fb32%28v%3dvs.90%29):

- Genéricos
- Depurador: Editar y continuar
- Escalabilidad y rendimiento mejorados
- implementación de ClickOnce
- Nuevos controles y compatibilidad con una amplia gama de exploradores en ASP.NET 2.0
- compatibilidad con la programación de 64 bits

|||
|-|-|
|**Versión de CRL**|2.0|
|**Incluido en la versión de Visual Studio**|2005|
|**Versiones de Windows**|N/D|
|**Versiones de Windows Server**|✔️ 2008 R2 SP1<br />✔️ 2008 SP2<br />✔️ 2003|
|**Para determinar la versión de .NET instalada**|Consulte las [instrucciones](how-to-determine-which-versions-are-installed.md)|

### <a name="net-framework-11"></a>.NET Framework 1.1

[Características nuevas](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2008/h88tthh0%28v%3dvs.90%29):

- Controles móviles de ASP.NET
- Ejecución simultánea
- Compatibilidad de IPv6

|||
|-|-|
|**Versión de CRL**|1.1|
|**Incluido en la versión de Visual Studio**|2003|
|**Versiones de Windows**|N/D|
|**Versiones de Windows Server**|✔️ 2003|
|**Para determinar la versión de .NET instalada**|Consulte las [instrucciones](how-to-determine-which-versions-are-installed.md)|

### <a name="net-framework-10"></a>.NET Framework 1.0

|||
|-|-|
|**Versión de CRL**|1.0|
|**Incluido en la versión de Visual Studio**|Visual Studio .NET|
|**Versiones de Windows**|N/D|
|**Versiones de Windows Server**|N/D|
|**Para determinar la versión de .NET instalada**|Consulte las [instrucciones](how-to-determine-which-versions-are-installed.md)|

> [!NOTE]
>
> - .NET Framework debe estar habilitado en este sistema operativo a través del [Panel de Control (para Windows) o el Administrador del servidor (para Windows Server)](../install/dotnet-35-windows-10.md#enable-the-net-framework-35-in-control-panel).
> - Por lo general, no conviene desinstalar ninguna de las versiones de .NET Framework instaladas en el equipo, ya que una determinada aplicación podría depender de una versión concreta y dejar de funcionar si se quita esa versión. Puede cargar varias versiones de .NET Framework en un único equipo simultáneamente. Esto significa que puede instalar .NET Framework sin tener que desinstalar las versiones anteriores. Para más información, consulte [Introducción](../get-started/index.md).

## <a name="remarks-for-version-45-and-later"></a>Notas de la versión 4.5 y posteriores

.NET Framework 4.5 es una actualización en contexto que reemplaza .NET Framework 4 en el equipo y, de forma similar, .NET Framework 4.5.1, 4.5.2, 4.6, 4.6.1, 4.6.2, 4.7, 4.7.1, 4.7.2 y 4.8 son actualizaciones en contexto de .NET Framework 4.5. Una actualización en contexto significa que se usa la misma versión del entorno de ejecución, pero las versiones de ensamblado se actualizan e incluyen nuevos tipos y miembros. Después de instalar una de estas actualizaciones, las aplicaciones de .NET Framework 4, .NET Framework 4.5, .NET Framework 4.6 o .NET Framework 4.7 deberían seguir ejecutándose sin que haya que volver a compilarlas. Sin embargo, esto no es aplicable a la inversa. No se recomienda ejecutar aplicaciones destinadas a una versión posterior de .NET Framework en versiones anteriores. Por ejemplo, no se recomienda ejecutar una aplicación destinada a .NET Framework 4.6 en .NET Framework 4.5.

Se aplican las directrices siguientes:

- En Visual Studio, puede elegir .NET Framework 4.5 como marco de destino en un proyecto (se establece la propiedad <xref:Microsoft.Build.Tasks.GetReferenceAssemblyPaths.TargetFrameworkMoniker%2A?displayProperty=nameWithType>) para compilar el proyecto como un ensamblado o ejecutable de .NET Framework 4.5. Este ensamblado o ejecutable puede usarse luego en cualquier equipo que tenga instalado .NET Framework 4.5, 4.5.1, 4.5.2, 4.6, 4.6.1, 4.6.2, 4.7, 4.7.1, 4.7.2 o 4.8.

- En Visual Studio, puede elegir .NET Framework 4.5.1 como plataforma de destino en un proyecto para compilarlo como un ensamblado o ejecutable de .NET Framework 4.5.1. Ejecute este ensamblado o ejecutable solo en equipos que tengan instalado .NET Framework 4.5.1 o posteriores. Un archivo ejecutable que tenga como destino .NET Framework 4.5.1 no podrá ejecutarse en un equipo que solo tenga instalada una versión anterior de .NET Framework, como .NET Framework 4.5. Se le pedirá al usuario que instale .NET Framework 4.5.1. Además, no se debe llamar a los ensamblados de .NET Framework 4.5.1 desde una aplicación que tenga como destino una versión anterior de .NET Framework, como .NET Framework 4.5.

  > [!NOTE]
  > .NET Framework 4.5.1 y .NET Framework 4.5 se usan aquí solo a modo de ejemplo. El principio que se ha descrito es válido para cualquier aplicación destinada a una versión de .NET Framework posterior a la instalada en el sistema en el que se ejecuta.

Es posible que algunos cambios en .NET Framework requieran cambios en el código de la aplicación. Consulte [Compatibilidad de aplicaciones](application-compatibility.md) antes de ejecutar las aplicaciones existentes con .NET Framework 4.5 o versiones posteriores. Para obtener más información sobre la instalación de la versión actual, consulte [Install the .NET Framework for developers](../install/guide-for-developers.md) (Instalar .NET Framework para desarrolladores). Para obtener información sobre el soporte técnico de .NET Framework, consulte [Directiva de ciclo soporte técnico oficial de .NET Framework](https://dotnet.microsoft.com/platform/support/policy/dotnet-framework) en el sitio web de .NET.

## <a name="remarks-for-older-versions"></a>Notas para las versiones anteriores

Las versiones 2.0, 3.0 y 3.5 de .NET Framework están compiladas con la misma versión de CLR (CLR 2.0). Estas versiones representan niveles sucesivos de una única instalación. Cada versión se compila incrementalmente sobre las versiones anteriores. No es posible ejecutar las versiones 2.0, 3.0 y 3.5 en paralelo en un equipo. Cuando se instala la versión 3.5, se obtienen automáticamente los niveles 2.0 y 3.0, y las aplicaciones que se compilaron para las versiones 2.0, 3.0 y 3.5 pueden ejecutarse en la versión 3.5. Sin embargo, .NET Framework 4 finaliza este enfoque de capas. En esta versión, así como en versiones posteriores (.NET Framework 4.5, 4.5.1, 4.5.2, 4.6, 4.6.1, 4.6.2, 4.7, 4.7.1, 4.7.2 y 4.8) también se representan niveles sucesivos de una única instalación. A partir de .NET Framework 4, puede usar el hospedaje en paralelo en el mismo proceso para ejecutar varias versiones de CLR en un único proceso. Para más información, consulte [Ensamblados y ejecución simultánea](../../standard/assembly/side-by-side-execution.md).

Además, si la aplicación tiene como destino la versión 2.0, 3.0 o 3.5, es posible que los usuarios tengan que habilitar .NET Framework 3.5 en un equipo con Windows 8, Windows 8.1 o Windows 10 para poder ejecutar la aplicación. Para obtener más información, consulte [Install the .NET Framework 3.5 on Windows 10, Windows 8.1, and Windows 8](../install/dotnet-35-windows-10.md) (Instalar .NET Framework 3.5 en Windows 10, Windows 8.1 y Windows 8).

## <a name="next-steps"></a>Pasos siguientes

- Si no está familiarizado con .NET Framework, consulte la [introducción](../get-started/overview.md) a los principales conceptos y características.

- Consulte las nuevas características y mejoras de .NET Framework 4.5 y sus versiones secundarias en [Novedades de .NET Framework](../whats-new/index.md).

- Para más información sobre la migración de la aplicación a una versión más reciente de .NET Framework, consulte la [guía de migración](index.md).

- Para obtener información sobre cómo determinar qué versiones o actualizaciones están instaladas en un equipo, consulte [Cómo: Determinar qué versiones de .NET Framework están instaladas](how-to-determine-which-versions-are-installed.md) y [Cómo: Determinar qué actualizaciones de .NET Framework están instaladas](how-to-determine-which-net-framework-updates-are-installed.md).

## <a name="see-also"></a>Consulte también

- [Compatibilidad de versiones](version-compatibility.md)
| [Directiva de soporte técnico oficial de .NET Framework](https://dotnet.microsoft.com/platform/support/policy/dotnet-framework)
- [Solución de problemas en instalaciones y desinstalaciones bloqueadas de .NET Framework](../install/troubleshoot-blocked-installations-and-uninstallations.md)
