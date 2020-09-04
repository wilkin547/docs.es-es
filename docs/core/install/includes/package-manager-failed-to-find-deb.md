---
ms.openlocfilehash: 9d4c031eda291b0a8832c824789efdffe4084926
ms.sourcegitcommit: d579fb5e4b46745fd0f1f8874c94c6469ce58604
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/30/2020
ms.locfileid: "89132954"
---

Si recibe un mensaje de error similar a **No se puede encontrar el paquete {netcore-package}** o **No se han podido instalar algunos paquetes**, ejecute los comandos siguientes.

Hay dos marcadores de posición en el siguiente conjunto de comandos.

- `{dotnet-package}`\
Representa el paquete de .NET Core que va a instalar, como `aspnetcore-runtime-3.1`. Se usa en el comando `sudo apt-get install` siguiente.

- `{os-version}`\
Representa la versión de Linux en la que está. Se usa en el comando `wget` siguiente.

Primero, pruebe a purgar la lista de paquetes:

```bash
sudo dpkg --purge packages-microsoft-prod && sudo dpkg -i packages-microsoft-prod.deb
sudo apt-get update
```

Después, intente instalar .NET Core de nuevo. Si eso no funciona, puede ejecutar una instalación manual con los comandos siguientes:
