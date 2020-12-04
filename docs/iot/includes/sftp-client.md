---
ms.openlocfilehash: 60e326af0d956ceb63b32e5d3ec2436fe09a7005
ms.sourcegitcommit: b201d177e01480a139622f3bf8facd367657a472
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/15/2020
ms.locfileid: "96594695"
---
[Con un cliente SFTP](https://www.raspberrypi.org/documentation/remote-access/ssh/sftp.md), copie los archivos de la ubicación de publicación en el equipo de desarrollo en una nueva carpeta de Raspberry PI.

Por ejemplo, para usar el `scp` comando para copiar archivos del equipo de desarrollo a Raspberry PI, abra un símbolo del sistema y ejecute lo siguiente:

```console
scp -r /publish-location/* pi@raspberrypi:/home/pi/deployment-location/
```

Donde:

- La `-r` opción indica `scp` a que copie los archivos de forma recursiva.
- */Publish-Location/* es la carpeta en la que publicó en el paso anterior.
- `pi@raspberypi` es el usuario y los nombres de host con el formato `<username>@<hostname>` .
- */Home/PI/Deployment-Location/* es la nueva carpeta de Raspberry PI.

> [!TIP]
> Las versiones recientes de Windows tienen OpenSSH, que incluye `scp` preinstalado.
