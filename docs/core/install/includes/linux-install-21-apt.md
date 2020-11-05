---
ms.openlocfilehash: 188fef66444cd60f59a3cb9619c0d86efd155f99
ms.sourcegitcommit: b1442669f1982d3a1cb18ea35b5acfb0fc7d93e4
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2020
ms.locfileid: "93135869"
---

### <a name="install-the-sdk"></a>Instalación del SDK

El SDK de .NET Core permite desarrollar aplicaciones con .NET Core. Si instala el SDK de .NET Core, no necesita instalar el entorno de ejecución correspondiente. Para instalar el SDK de .NET Core, ejecute los siguientes comandos:

```bash
sudo apt-get update; \
  sudo apt-get install -y apt-transport-https && \
  sudo apt-get update && \
  sudo apt-get install -y dotnet-sdk-2.1
```

> [!IMPORTANT]
> Si recibe un mensaje de error similar a **No se puede encontrar el paquete dotnet-sdk-2.1** , consulte la sección [Solución de problemas de APT](#apt-troubleshooting).

### <a name="install-the-runtime"></a>Instalación de la instancia en tiempo de ejecución

.NET Core Runtime le permite ejecutar aplicaciones que se realizaron con .NET Core que no incluían el entorno de ejecución. Los comandos siguientes instalan el entorno de ejecución de ASP.NET Core, el más compatible con .NET Core. En el terminal, ejecute los comandos siguientes.

```bash
sudo apt-get update; \
  sudo apt-get install -y apt-transport-https && \
  sudo apt-get update && \
  sudo apt-get install -y aspnetcore-runtime-2.1
```

> [!IMPORTANT]
> Si recibe un mensaje de error similar a **No se puede encontrar el paquete aspnetcore-runtime-2.1** , consulte la sección [Solución de problemas de APT](#apt-troubleshooting).

Una alternativa al entorno de ejecución de ASP.NET Core es instalar la instancia del de .NET Core, que no incluye compatibilidad con ASP.NET Core; en el comando anterior, reemplace `aspnetcore-runtime-2.1` por `dotnet-runtime-2.1`.

```bash
sudo apt-get install -y dotnet-runtime-2.1
```
