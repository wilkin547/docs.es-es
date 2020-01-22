---
ms.openlocfilehash: 47e8e15a64236d8ade2febb1add81fa4e5c030d9
ms.sourcegitcommit: ed3f926b6cdd372037bbcc214dc8f08a70366390
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/16/2020
ms.locfileid: "76116155"
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

  - 3.0
  - 2.2
  - 2.1

### <a name="examples"></a>Ejemplos

- Instalación del SDK de .NET Core 2.2: `dotnet-sdk-2.2`
- Instalación del runtime de ASP.NET Core 3.1: `aspnetcore-runtime-3.1`
- Instalación del entorno de ejecución de ASP.NET Core 2.1: `dotnet-runtime-2.1`

### <a name="troubleshoot"></a>Solucionar problemas

Si la combinación de paquetes no funciona, no está disponible. Por ejemplo, no hay un SDK de ASP.NET Core; los componentes del SDK se incluyen en el SDK de .NET Core. El valor `aspnetcore-sdk-2.2` es no es correcto y debe ser `dotnet-sdk-2.2`.
