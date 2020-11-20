---
ms.openlocfilehash: 2cd5459ab7f2c8c96638bf27dd30980282036925
ms.sourcegitcommit: bc9c63541c3dc756d48a7ce9d22b5583a18cf7fd
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/11/2020
ms.locfileid: "94506936"
---

### <a name="install-the-sdk"></a>Instalación del SDK

El SDK de .NET permite desarrollar aplicaciones con .NET. Si instala el SDK de .NET, no necesita instalar el entorno de ejecución correspondiente. Para instalar el SDK de .NET, ejecute los comandos siguientes:

```bash
sudo dnf install dotnet-sdk-5.0
```

### <a name="install-the-runtime"></a>Instalación de la instancia en tiempo de ejecución

El entorno de ejecución de ASP.NET Core le permite ejecutar aplicaciones creadas con .NET en las que no se ha proporcionado el entorno de ejecución. Los comandos siguientes instalan el entorno de ejecución de ASP.NET Core, el más compatible con .NET. En el terminal, ejecute los comandos siguientes:

```bash
sudo dnf install aspnetcore-runtime-5.0
```

Una alternativa al entorno de ejecución de ASP.NET Core es instalar el de .NET, que no incluye compatibilidad con ASP.NET Core; en el comando anterior, reemplace `aspnetcore-runtime-5.0` por `dotnet-runtime-5.0`:

```bash
sudo dnf install dotnet-runtime-5.0
```
