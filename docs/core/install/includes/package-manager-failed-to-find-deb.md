---
ms.openlocfilehash: 3275865cf7f4669ba7deaacea320136d02f64dda
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99804206"
---

Si recibe un mensaje de error similar a **No se puede encontrar el paquete {dotnet-package}** o **No se han podido instalar algunos paquetes**, ejecute los comandos siguientes.

Hay dos marcadores de posición en el siguiente conjunto de comandos.

- `{dotnet-package}`\
Representa el paquete de .NET que va a instalar, como `aspnetcore-runtime-3.1`. Se usa en el comando `sudo apt-get install` siguiente.

- `{os-version}`\
Representa la versión de distribución en la que se encuentra. Se usa en el comando `wget` siguiente. La versión de distribución es el valor numérico, como `20.04` en Ubuntu o `10` en Debian.

Primero, pruebe a purgar la lista de paquetes:

```bash
sudo dpkg --purge packages-microsoft-prod && sudo dpkg -i packages-microsoft-prod.deb
sudo apt-get update
```

Después, intente volver a instalar .NET. Si eso no funciona, puede ejecutar una instalación manual con los comandos siguientes:
