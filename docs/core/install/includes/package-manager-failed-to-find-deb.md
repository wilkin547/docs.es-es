---
ms.openlocfilehash: aba7b473af7685aa45f7e093a2f75311687593df
ms.sourcegitcommit: bc9c63541c3dc756d48a7ce9d22b5583a18cf7fd
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/11/2020
ms.locfileid: "94506982"
---

Si recibe un mensaje de error similar a **No se puede encontrar el paquete {dotnet-package}** o **No se han podido instalar algunos paquetes**, ejecute los comandos siguientes.

Hay dos marcadores de posición en el siguiente conjunto de comandos.

- `{dotnet-package}`\
Representa el paquete de .NET que va a instalar, como `aspnetcore-runtime-3.1`. Se usa en el comando `sudo apt-get install` siguiente.

- `{os-version}`\
Representa la versión de Linux en la que está. Se usa en el comando `wget` siguiente.

Primero, pruebe a purgar la lista de paquetes:

```bash
sudo dpkg --purge packages-microsoft-prod && sudo dpkg -i packages-microsoft-prod.deb
sudo apt-get update
```

Después, intente volver a instalar .NET. Si eso no funciona, puede ejecutar una instalación manual con los comandos siguientes:
