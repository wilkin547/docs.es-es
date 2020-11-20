---
ms.openlocfilehash: cc394741e399f4fc54dd67f1736f7027badf4c7d
ms.sourcegitcommit: bc9c63541c3dc756d48a7ce9d22b5583a18cf7fd
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/11/2020
ms.locfileid: "94507105"
---

### <a name="install-the-sdk"></a>Instalación del SDK

El SDK de .NET permite desarrollar aplicaciones con .NET. Si instala el SDK de .NET, no necesita instalar el entorno de ejecución correspondiente. Para instalar el SDK de .NET, ejecute los comandos siguientes:

```bash
sudo yum install dotnet-sdk-5.0
```

### <a name="install-the-runtime"></a>Instalación de la instancia en tiempo de ejecución

El entorno de ejecución de ASP.NET Core le permite ejecutar aplicaciones creadas con .NET en las que no se ha proporcionado el entorno de ejecución. Los comandos siguientes instalan el entorno de ejecución de ASP.NET Core, el más compatible con .NET. En el terminal, ejecute los comandos siguientes:

```bash
sudo yum install aspnetcore-runtime-5.0
```

Una alternativa al entorno de ejecución de ASP.NET Core es instalar el de .NET, que no incluye compatibilidad con ASP.NET Core; en el comando anterior, reemplace `aspnetcore-runtime-5.0` por `dotnet-runtime-5.0`:

```bash
sudo yum install dotnet-runtime-5.0
```
