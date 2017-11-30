---
title: Migrar a .NET Core - mediante el paquete de compatibilidad de Windows
description: "Obtenga información sobre el paquete de compatibilidad de Windows y cómo puede utilizarlo para puerto código existente de .NET Framework a .NET Core"
keywords: . NET, .NET core, Windows, compatibilidad
author: terrajobst
ms.author: mairaw
ms.date: 11/13/2017
ms.topic: article
ms.prod: .net-core
ms.openlocfilehash: 5094baee77aba4d1e148f807d842a4a2d3405cf7
ms.sourcegitcommit: 86cf9b4c7104485a9870645705b9a1a4b6ca8e2b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/16/2017
---
# <a name="using-the-windows-compatibility-pack"></a>Con el paquete de compatibilidad de Windows

Uno de los problemas más comunes que se enfrentan los programadores al trasladar su código existente a .NET Core es que dependen de las API y las tecnologías que solo existen en .NET Framework. El *paquete de compatibilidad de Windows* consiste en proporcionar muchas de estas tecnologías para que compilar aplicaciones de .NET Core, así como bibliotecas estándar de .NET pasa a ser mucho más viable para código existente.

Este paquete es un valor lógico [extensión del estándar de .NET 2.0](../whats-new/index.md#api-changes-and-library-support) que significativamente aumenta conjunto de API y el código existente se compila con casi ninguna modificación. Pero con el fin de mantener la promesa de .NET estándar ("es el conjunto de API que proporcionan todas las implementaciones. NET"), esto no incluye tecnologías que no pueden funcionar en todas las plataformas, como el registro, Windows Management Instrumentation (WMI), o la emisión de reflexión API.

El *paquete de compatibilidad de Windows* se ubica en la parte superior del estándar de .NET y proporciona acceso a las tecnologías que sean sólo de Windows. Es especialmente útil para los clientes que desean migrar a .NET Core sino que planifique permanezca en Windows como primer paso. En ese caso, la imposibilidad de usar tecnologías solo de Windows es sólo un obstáculo de migración con cero ventajas arquitectónicas.

## <a name="package-contents"></a>Contenido del paquete

El *paquete de compatibilidad de Windows* se proporciona mediante el paquete de NuGet [Microsoft.Windows.Compatibility](https://www.nuget.org/packages/Microsoft.Windows.Compatibility) y puede hacer referencia desde proyectos destinados a .NET Core o .NET estándar.

Proporciona unos 20.000 API, incluidas las API de solo de Windows, así como entre plataformas de las siguientes áreas de tecnología:

* Páginas de códigos
* CodeDom
* Configuración
* Servicios de directorio
* dibujo
* ODBC
* Permisos
* Puertos
* Listas de Control de acceso (ACL) de Windows
* Windows Communication Foundation (WCF)
* Criptografía de Windows
* Registro de eventos de Windows
* Instrumental de administración de Windows (WMI)
* Contadores de rendimiento de Windows
* Registro de Windows
* Almacenamiento en caché de tiempo de ejecución de Windows
* servicios de Windows

Para obtener más información, consulte el [especificaciones del módulo de compatibilidad de](https://github.com/dotnet/designs/blob/master/accepted/compat-pack/compat-pack.md).

## <a name="get-started"></a>Primeros pasos

1. Antes de migrar, asegúrese de echar un vistazo a la [proceso de migración](index.md).

2. Al migrar código existente a .NET Core o .NET estándar, instale el paquete de NuGet [Microsoft.Windows.Compatibility](https://www.nuget.org/packages/Microsoft.Windows.Compatibility).

3. Si desea permanecer en Windows, que tiene todo listo.

4. Si desea ejecutar la aplicación de .NET Core o la biblioteca estándar de .NET en Linux o Mac OS, utilice la [API analizador](https://blogs.msdn.microsoft.com/dotnet/2017/10/31/introducing-api-analyzer/) para encontrar el uso de API que no funcionarán entre plataformas.

5. Quite los usos de estas API, reemplácelas con alternativas de multiplataforma o protegerse con una comprobación de la plataforma, como:

    ```csharp
    private static string GetLoggingPath()
    {
        // Verify the code is running on Windows.
        if (RuntimeInformation.IsOSPlatform(OSPlatform.Windows))
        {
            using (var key = Registry.CurrentUser.OpenSubKey(@"Software\Fabrikam\AssetManagement"))
            {
                if (key?.GetValue("LoggingDirectoryPath") is string configuredPath)
                    return configuredPath;
            }
        }

        // This is either not running on Windows or no logging path was configured,
        // so just use the path for non-roaming user-specific data files.
        var appDataPath = Environment.GetFolderPath(Environment.SpecialFolder.LocalApplicationData);
        return Path.Combine(appDataPath, "Fabrikam", "AssetManagement", "Logging");
    }
    ```

Para obtener una demostración, visite la [vídeo de Channel 9 del paquete de compatibilidad de Windows](https://channel9.msdn.com/Events/Connect/2017/T123).

