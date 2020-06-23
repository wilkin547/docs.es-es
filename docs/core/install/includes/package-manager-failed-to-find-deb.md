---
ms.openlocfilehash: 7d398df060c031ae891218b82a2712d74f4c33b7
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/09/2020
ms.locfileid: "84602751"
---

Si recibe un mensaje de error similar a **No se puede encontrar el paquete (netcore-package)** , ejecute los comandos siguientes.

Hay dos marcadores de posición en el siguiente conjunto de comandos.

- `{dotnet-package}`\
Representa el paquete de .NET Core que va a instalar, como `aspnetcore-runtime-3.1`. Se usa en el comando `sudo apt-get install` siguiente.

- `{os-version}`\
Representa la versión de Linux en la que está. Se usa en el comando `wget` siguiente.

Pruebe a purgar la lista de paquetes:

```bash
sudo dpkg --purge packages-microsoft-prod && sudo dpkg -i packages-microsoft-prod.deb
sudo apt-get update
sudo apt-get install {dotnet-package}
```

Si eso no funciona, puede ejecutar una instalación manual con los comandos siguientes:
