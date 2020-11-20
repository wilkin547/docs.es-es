---
ms.openlocfilehash: ab1006f706439bcf5129854da3d14538e5b690a2
ms.sourcegitcommit: bc9c63541c3dc756d48a7ce9d22b5583a18cf7fd
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/11/2020
ms.locfileid: "94506883"
---

Los paquetes agregados a las fuentes del administrador de paquetes se denominan con un formato susceptible de intrusiones: `{product}-{type}-{version}`.

- **product**\
Tipo de producto .NET que se va a instalar. Las opciones válidas son:

  - dotnet
  - aspnetcore

- **type**\
Elige el SDK o el entorno de ejecución. Las opciones válidas son:

  - sdk
  - motor en tiempo de ejecución

- **version**\
Versión del SDK o del entorno de ejecución que se va a instalar. En este artículo se proporcionarán siempre las instrucciones para la última versión admitida. Las opciones válidas son cualquier versión de lanzamiento, como las siguientes:

  - 5.0
  - 3.1
  - 3.0
  - 2.1

  Es posible que el SDK o el entorno de ejecución que intenta descargar no esté disponible para su distribución de Linux. Para obtener una lista de las distribuciones admitidas, consulte [Dependencias y requisitos de .NET Core](../linux.md).

### <a name="examples"></a>Ejemplos

- Instalación del entorno de ejecución de ASP.NET Core 5.0: `aspnetcore-runtime-5.0`
- Instalación del entorno de ejecución de ASP.NET Core 2.1: `dotnet-runtime-2.1`
- Instalación del SDK de .NET 5.0: `dotnet-sdk-5.0`
- Instalación del SDK de .NET Core 3.1: `dotnet-sdk-3.1`

### <a name="package-missing"></a>Falta el paquete

Si la combinación de paquete y versión no funciona, no está disponible. Por ejemplo, no hay un SDK de ASP.NET Core; los componentes del SDK se incluyen en el SDK de .NET. El valor `aspnetcore-sdk-2.2` es no es correcto y debe ser `dotnet-sdk-2.2`. Para obtener una lista de las distribuciones de Linux compatibles con .NET, vea [Dependencias y requisitos de .NET](../linux.md).
