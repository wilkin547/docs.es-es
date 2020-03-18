---
title: Uso del paquete de compatibilidad de Windows para trasladar código a .NET Core
description: Obtenga información sobre el paquete de compatibilidad de Windows y cómo puede usarlo para migrar código existente de .NET Framework a .NET Core.
author: terrajobst
ms.date: 12/07/2018
ms.openlocfilehash: 91a653b2345d414c18ebdb6e8b7d6d49bbdbb83e
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/14/2020
ms.locfileid: "76733610"
---
# <a name="use-the-windows-compatibility-pack-to-port-code-to-net-core"></a>Uso del paquete de compatibilidad de Windows para trasladar código a .NET Core

Algunos de los problemas más comunes que se encuentran al trasladar código existente a .NET Core son las dependencias con API y las tecnologías que solo se encuentran en .NET Framework. El *paquete de compatibilidad de Windows* proporciona muchas de estas tecnologías, por lo que es mucho más fácil crear aplicaciones de .NET Core y bibliotecas de .NET Standard.

El paquete de compatibilidad es una [extensión lógica de .NET Standard 2.0](../whats-new/dotnet-core-2-0.md#api-changes-and-library-support) que aumenta considerablemente el conjunto de API. El código existente se compila prácticamente sin modificaciones. Para mantener su promesa de "el conjunto de API que proporcionan todas las implementaciones de .NET", .NET Standard no incluye tecnologías que no puedan funcionar en todas las plataformas, como el Registro, Instrumental de administración de Windows (WMI) o las API de emisión de la reflexión. El paquete de compatibilidad de Windows está un nivel por encima de .NET Standard y proporciona acceso a estas tecnologías que solo son de Windows. Es especialmente útil para los clientes que quieren migrar a .NET Core pero piensan permanecer en Windows, al menos como primer paso. En ese escenario, la posibilidad de usar tecnologías solo de Windows elimina el obstáculo de la migración.

## <a name="package-contents"></a>Contenido del paquete

El paquete de compatibilidad de Windows se proporciona mediante el [paquete NuGet Microsoft.Windows.Compatibility](https://www.nuget.org/packages/Microsoft.Windows.Compatibility) y se puede hacer referencia a él desde proyectos para .NET Core o .NET Standard.

Proporciona unas 20.000 API, incluidas API solo de Windows y API de varias plataformas de las siguientes áreas tecnológicas:

- Páginas de códigos
- CodeDom
- Configuración
- Servicios de directorio
- Dibujo
- ODBC
- Permisos
- Puertos
- Listas de control de acceso (ACL) de Windows
- Windows Communication Foundation (WCF)
- Criptografía de Windows
- Registro de eventos de Windows
- Instrumental de administración de Windows (WMI)
- Contadores de rendimiento de Windows
- Registro de Windows
- Memoria caché de tiempo de ejecución de Windows
- servicios de Windows

Para más información, vea las [especificaciones del paquete de compatibilidad](https://github.com/dotnet/designs/blob/master/accepted/compat-pack/compat-pack.md).

## <a name="get-started"></a>Primeros pasos

1. Antes de migrar, asegúrese de echar un vistazo al [proceso de migración](index.md).

2. Al migrar código existente a .NET Core o .NET Standard, instale el [paquete NuGet Microsoft.Windows.Compatibility](https://www.nuget.org/packages/Microsoft.Windows.Compatibility).

   Si quiere permanecer en Windows, ya está listo.

3. Si quiere ejecutar la aplicación .NET Core o la biblioteca de .NET Standard en Linux o macOS, use el [analizador de API](../../standard/analyzers/api-analyzer.md) para informarse de qué API no funcionan en varias plataformas.

4. Quite esas API, reemplácelas con alternativas multiplataforma o restrínjalas con una comprobación de plataforma, como:

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
