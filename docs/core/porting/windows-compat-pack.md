---
title: Uso del paquete de compatibilidad de Windows para trasladar código
description: Obtenga información sobre el paquete de compatibilidad de Windows y cómo puede usarlo para realizar la migración de código existente de .NET Framework a .NET 5 y .NET Core 3.1.
author: terrajobst
ms.date: 03/04/2021
ms.openlocfilehash: 655657e38f564d84ea3e56b5374debc04b405eeb
ms.sourcegitcommit: c7f0beaa2bd66ebca86362ca17d673f7e8256ca6
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "104873645"
---
# <a name="use-the-windows-compatibility-pack-to-port-code-to-net-5"></a>Uso del paquete de compatibilidad de Windows para trasladar código a .NET 5+

Algunos de los problemas más comunes que se encuentran al trasladar código existente de .NET Framework a .NET son las dependencias de API y tecnologías que solo se encuentran en .NET Framework. El *paquete de compatibilidad de Windows* proporciona muchas de estas tecnologías, por lo que es mucho más fácil crear aplicaciones de .NET y bibliotecas de .NET Standard.

El paquete de compatibilidad es una [extensión lógica de .NET Standard 2.0](../whats-new/dotnet-core-2-0.md#api-changes-and-library-support) que aumenta considerablemente el conjunto de API. El código existente se compila prácticamente sin modificaciones. Para mantener su promesa de "el conjunto de API que proporcionan todas las implementaciones de .NET", .NET Standard no incluye tecnologías que no puedan funcionar en todas las plataformas, como el Registro, Instrumental de administración de Windows (WMI) o las API de emisión de la reflexión. El paquete de compatibilidad de Windows está un nivel por encima de .NET Standard y proporciona acceso a estas tecnologías que solo son de Windows. Es especialmente útil para los clientes que quieren cambiar a .NET pero piensan permanecer en Windows, al menos como primer paso. En ese escenario, se pueden usar tecnologías solo de Windows para eliminar el obstáculo de la migración.

## <a name="package-contents"></a>Contenido del paquete

El paquete de compatibilidad de Windows se proporciona mediante el [paquete NuGet Microsoft.Windows.Compatibility](https://www.nuget.org/packages/Microsoft.Windows.Compatibility) y se puede hacer referencia a él desde proyectos para .NET o .NET Standard.

Proporciona unas 20 000 API, incluidas API solo de Windows y de varias plataformas de las siguientes áreas tecnológicas:

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

Para más información, vea las [especificaciones del paquete de compatibilidad](https://github.com/dotnet/designs/blob/main/accepted/2018/compat-pack/compat-pack.md).

## <a name="get-started"></a>Introducción

1. Antes de migrar, asegúrese de echar un vistazo al [proceso de migración](index.md).

2. Al trasladar código existente a .NET o .NET Standard, instale el [paquete NuGet Microsoft.Windows.Compatibility](https://www.nuget.org/packages/Microsoft.Windows.Compatibility).

   Si quiere permanecer en Windows, ya está listo.

3. Si quiere ejecutar la aplicación de .NET o la biblioteca de .NET Standard en Linux o macOS, use el [analizador de API](../../standard/analyzers/api-analyzer.md) para informarse de las API que no funcionan entre plataformas.

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

## <a name="see-also"></a>Vea también

- [Introducción a la portabilidad de .NET Framework a .NET](index.md)
- [Migración de ASP.NET s ASP.NET Core](/aspnet/core/migration/proper-to-2x)
- [Migración a .NET de aplicaciones WPF para .NET Framework](/dotnet/desktop/wpf/migration/convert-project-from-net-framework?view=netdesktop-5.0&preserve-view=true)
- [Migración a .NET de aplicaciones de Windows Forms para .NET Framework](/dotnet/desktop/winforms/migration/?view=netdesktop-5.0&preserve-view=true)
- [Traslado de bibliotecas de .NET Framework a .NET](libraries.md)
