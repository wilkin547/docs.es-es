---
ms.openlocfilehash: db89539982c1afe0df374027d54826f3265f0fee
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/09/2020
ms.locfileid: "84602775"
---

### <a name="install-the-sdk"></a>Instalación del SDK

El SDK de .NET Core permite desarrollar aplicaciones con .NET Core. Para instalar el SDK de .NET Core, ejecute los siguientes comandos.

```bash
sudo zypper install dotnet-sdk-3.1
```

### <a name="install-the-runtime"></a>Instalación de la instancia en tiempo de ejecución

.NET Core Runtime le permite ejecutar aplicaciones que se realizaron con .NET Core que no incluían el entorno de ejecución. Los siguientes comandos instalan el entorno de ejecución de ASP.NET Core, que es el entorno de ejecución más compatible con .NET Core. En el terminal, ejecute los comandos siguientes.

```bash
sudo zypper install aspnetcore-runtime-3.1
```

Una alternativa al entorno de ejecución de ASP.NET Core es instalar la instancia de .NET Core Runtime que no incluye compatibilidad con ASP.NET Core. Reemplace `aspnetcore-runtime-2.1` en los comandos anteriores por `dotnet-runtime-3.1`.

```bash
sudo zypper install dotnet-runtime-3.1
```
