---
title: 'Migración a .NET Core: Uso del paquete de compatibilidad de Windows'
description: Obtenga información sobre el paquete de compatibilidad de Windows y cómo puede usarlo para migrar código existente de .NET Framework a .NET Core
author: terrajobst
ms.author: mairaw
ms.date: 11/13/2017
ms.openlocfilehash: 51b96d7828285964c1b0cbb835b8eb5ed92c47d6
ms.sourcegitcommit: bbf70abe6b46073148f78cbf0619de6092b5800c
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/04/2018
ms.locfileid: "34566178"
---
# <a name="using-the-windows-compatibility-pack"></a>Uso del paquete de compatibilidad de Windows

Uno de los problemas más comunes al que se enfrentan los desarrolladores al migrar el código existente a .NET Core es que dependen de API y tecnologías que solo existen en .NET Framework. El *paquete de compatibilidad de Windows* proporciona muchas de estas tecnologías para que compilar aplicaciones .NET Core y bibliotecas de .NET Standard sea mucho más viable para el código existente.

Este paquete es una [extensión lógica de .NET Standard 2.0](../whats-new/dotnet-core-2-0.md#api-changes-and-library-support) que aumenta considerablemente las compilaciones del conjunto de API y el código existente prácticamente sin modificaciones. Pero con el fin de mantener la promesa de .NET Standard ("es el conjunto de API que proporcionan todas las implementaciones de .NET"), no incluye tecnologías que no puedan funcionar en todas las plataformas, como el Registro, Windows Management Instrumentation (WMI) o las API de emisión de la reflexión.

El *paquete de compatibilidad de Windows* está un nivel por encima de .NET Standard y proporciona acceso a tecnologías que solo son de Windows. Es especialmente útil para los clientes que quieren migrar a .NET Core pero piensan permanecer en Windows como primer paso. En ese escenario, la imposibilidad de usar tecnologías solo de Windows es únicamente un escollo para la migración con cero ventajas arquitectónicas.

## <a name="package-contents"></a>Contenido del paquete

El *paquete de compatibilidad de Windows* se proporciona mediante el paquete NuGet [Microsoft.Windows.Compatibility](https://www.nuget.org/packages/Microsoft.Windows.Compatibility) y se puede hacer referencia a él desde proyectos para .NET Core o .NET Standard.

Proporciona unas 20.000 API, incluidas API solo de Windows y API de varias plataformas de las siguientes áreas tecnológicas:

* Páginas de códigos
* CodeDom
* Configuración
* Servicios de directorio
* Dibujo
* ODBC
* Permisos
* Puertos
* Listas de control de acceso (ACL) de Windows
* Windows Communication Foundation (WCF)
* Criptografía de Windows
* Registro de eventos de Windows
* Instrumental de administración de Windows (WMI)
* Contadores de rendimiento de Windows
* Registro de Windows
* Memoria caché de tiempo de ejecución de Windows
* servicios de Windows

Para más información, vea las [especificaciones del paquete de compatibilidad](https://github.com/dotnet/designs/blob/master/accepted/compat-pack/compat-pack.md).

## <a name="get-started"></a>Primeros pasos

1. Antes de migrar, asegúrese de echar un vistazo al [proceso de migración](index.md).

2. Al migrar código existente a .NET Core o .NET Standard, instale el paquete NuGet [Microsoft.Windows.Compatibility](https://www.nuget.org/packages/Microsoft.Windows.Compatibility).

3. Si quiere permanecer en Windows, ya está listo.

4. Si quiere ejecutar la aplicación .NET Core o la biblioteca de .NET Standard en Linux o macOS, use el [analizador de API](https://blogs.msdn.microsoft.com/dotnet/2017/10/31/introducing-api-analyzer/) para informarse de qué API no funcionan en varias plataformas.

5. Quite esas API, reemplácelas con alternativas multiplataforma o restrínjalas con una comprobación de plataforma, como:

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

Para ver una demostración, vaya al [vídeo de Channel 9 sobre el paquete de compatibilidad de Windows](https://channel9.msdn.com/Events/Connect/2017/T123).

