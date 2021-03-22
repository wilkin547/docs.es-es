---
title: Información general sobre el Asistente para actualización de .NET
description: Introducción a la herramienta Asistente para actualización de .NET que ayuda a migrar desde .NET Framework y actualiza los proyectos a .NET 5.
author: ardalis
ms.date: 03/08/2021
ms.openlocfilehash: c667cfce40d4f740bc23606826eb2a058643b7be
ms.sourcegitcommit: 46cfed35d79d70e08c313b9c664c7e76babab39e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/10/2021
ms.locfileid: "102604780"
---
# <a name="overview-of-the-net-upgrade-assistant"></a>Información general sobre el Asistente para actualización de .NET

Es posible que tenga aplicaciones que se ejecutan actualmente en .NET Framework que le interesa portar a .NET 5. La herramienta Asistente para actualización de .NET puede ayudarle con este proceso. En este artículo se proporciona:

- Información general sobre el Asistente para actualización de .NET.
- Cómo instalar el Asistente para actualización de .NET.

## <a name="what-is-the-net-upgrade-assistant"></a>Qué es el Asistente para actualización de .NET.

El Asistente para actualización de .NET es una herramienta de línea de comandos que se puede ejecutar en diferentes tipos de aplicaciones .NET Framework. Está diseñado para facilitar la actualización de aplicaciones de .NET Framework a .NET 5. Después de ejecutar la herramienta, **en la mayoría de los casos, la aplicación necesitará más esfuerzo para completar la migración**. La herramienta incluye la instalación de analizadores que pueden ayudarle a completar la migración.

Actualmente, la herramienta admite los siguientes tipos de aplicaciones .NET Framework:

- Aplicaciones .NET Framework de Windows Forms
- Aplicaciones .NET Framework de WPF
- Aplicaciones .NET Framework de ASP.NET de MVC
- Aplicaciones de consola .NET Framework
- Bibliotecas de clases de .NET Framework

El Asistente para actualización de .NET está actualmente en versión preliminar y recibe actualizaciones frecuentes. Si detecta problemas con la herramienta, notifíquelos en el [repositorio de GitHub](https://github.com/dotnet/upgrade-assistant) de la herramienta.

## <a name="how-to-install-the-net-upgrade-assistant"></a>Cómo instalar el Asistente para actualización de .NET

El [Tutorial de introducción](https://aka.ms/dotnet-upgrade-assistant-install) le guía a través de la instalación y el uso del Asistente para actualización de .NET.

### <a name="prerequisites"></a>Requisitos previos

1. Esta herramienta usa MSBuild para trabajar con archivos de proyecto. Asegúrese de que hay instalada una versión reciente de MSBuild. Una manera fácil de hacerlo es [instalar Visual Studio 2019](https://visualstudio.microsoft.com/downloads/).
1. Esta herramienta depende de [try-convert](https://github.com/dotnet/try-convert). Para que la herramienta se ejecute correctamente, debe instalar la herramienta try-convert para convertir los archivos de proyecto al nuevo estilo de SDK. Si ya tiene instalado **try-convert**, puede que tenga que actualizarlo (ya que **upgrade-assistant** depende de la versión _0.7.212201_ o una versión posterior).
    1. Para instalar try-convert: `dotnet tool install -g try-convert`
    1. Para actualizar try-convert: `dotnet tool update -g try-convert`

### <a name="installation-steps"></a>Pasos de instalación

Para instalar la herramienta como de la CLI de .NET, ejecute lo siguiente:

```dotnet
dotnet tool install -g upgrade-assistant
```

Del mismo modo, puesto que el Asistente para actualización de .NET se instala como herramienta de la CLI de .NET, puede ejecutar lo siguiente para realizar la actualización fácilmente:

```dotnet
dotnet tool update -g upgrade-assistant
```

Para obtener instrucciones detalladas, consulte el archivo [README](https://github.com/dotnet/upgrade-assistant) del proyecto.

## <a name="see-also"></a>Vea también

- [Actualización de una aplicación de WPF a .NET 5 con el Asistente para actualización de .NET](upgrade-assistant-wpf-framework.md)
- [Actualización de una aplicación de Windows Forms a .NET 5 con el Asistente para actualización de .NET](upgrade-assistant-winforms-framework.md)
- [Actualización de una aplicación ASP.NET de MVC a .NET 5 con el Asistente para actualización de .NET](upgrade-assistant-aspnetmvc.md)
- [Repositorio de GitHub del Asistente para actualización de .NET](https://github.com/dotnet/upgrade-assistant)
