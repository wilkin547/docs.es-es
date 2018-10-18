---
title: Publicación de un paquete de NuGet
description: Prácticas recomendadas para la publicación de las bibliotecas de .NET en NuGet.
author: jamesnk
ms.author: mairaw
ms.date: 10/02/2018
ms.openlocfilehash: 0602712311411ef3d59825bec8c5e550bc8d8265
ms.sourcegitcommit: d88024e6d6d8b242feae5f4007a709379355aa24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/16/2018
ms.locfileid: "49370324"
---
# <a name="publishing-a-nuget-package"></a>Publicación de un paquete de NuGet

Paquetes de NuGet se publican y se consume desde repositorios de paquetes. Aunque NuGet.org es más ampliamente repositorio utilizan y conocen, hay muchos lugares para publicar paquetes de NuGet:

* **[NuGet.org](https://www.nuget.org/)**  es el repositorio principal en línea para los paquetes de NuGet. Todos los paquetes en NuGet.org están disponibles públicamente para todos los usuarios. De forma predeterminada, Visual Studio tiene NuGet.org como un origen del paquete y para muchos desarrolladores NuGet.org es el repositorio de paquetes solo con que podrá interactuar. NuGet.org es el mejor lugar para publicar los paquetes estables y paquetes de versión preliminar que desee que los comentarios de la Comunidad en.

* **[MyGet](https://myget.org/)**  repositorio service admite [fuentes de distribución de paquete personalizado gratuito para proyectos de código abierto](https://www.myget.org/opensource). Una fuente personalizada pública de MyGet es un lugar ideal para publicar paquetes de versión preliminar creados por el servicio de integración continua. MyGet también proporciona fuentes privadas comercialmente.

* Un **[fuente local](/nuget/hosting-packages/local-feeds)** permite tratar una carpeta como un repositorio de paquetes y hace que el `*.nupkg` archivos en la carpeta accesible mediante NuGet. Una fuente local es útil para probar un paquete de NuGet antes de publicarlo en NuGet.org.

> [!NOTE]
> NuGet.org [no permite un paquete que se va a eliminar](/nuget/policies/deleting-packages) después de que se cargue. Un paquete puede ser dados de baja para que no sea visible públicamente en la interfaz de usuario, pero la `*.nupkg` puede descargarse en la restauración. Además, nuget.org no admite versiones de paquetes duplicados. Para corregir un paquete de NuGet con un error que tendrá que quitar de la lista el paquete incorrecto, incremente el número de versión y publique una nueva versión del paquete.

**HACER ✔️** [publicar los paquetes estables y paquetes de versión preliminar](/nuget/create-packages/publish-a-package) desea que los comentarios de la Comunidad en NuGet.org.

**Considere la posibilidad de ✔️** publicar paquetes de versión preliminar en un MyGet fuente desde una compilación de integración continua.

**Considere la posibilidad de ✔️** probar paquetes en su entorno de desarrollo mediante una fuente local o MyGet. Compruebe las obras de paquete, a continuación, publicarlo en NuGet.org.

## <a name="nugetorg-security"></a>Seguridad de NuGet.org

Es importante que los actores no válidos no se puede acceder a su cuenta de NuGet y cargar una versión de la biblioteca malintencionada. NuGet.org ofrece notificaciones de correo electrónico y la autenticación de dos fases cuando se publica un paquete. Habilitar estas características tras iniciar sesión en NuGet.org en el **configuración de la cuenta** página.

![texto alternativo](./media/publish-nuget-package/nuget-2fa.png "seguridad de la cuenta de NuGet")

**HACER ✔️** usar una cuenta de Microsoft para iniciar sesión NuGet.

**HACER ✔️** habilitar la autenticación en dos fases para acceder a NuGet.

**HACER ✔️** Habilitar notificación por correo electrónico cuando se publica un paquete.

>[!div class="step-by-step"]
[Anterior](./sourcelink.md)
[Siguiente](./versioning.md)
