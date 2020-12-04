---
ms.openlocfilehash: 60e326af0d956ceb63b32e5d3ec2436fe09a7005
ms.sourcegitcommit: b201d177e01480a139622f3bf8facd367657a472
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/15/2020
ms.locfileid: "96594695"
---
<span data-ttu-id="f7072-101">[Con un cliente SFTP](https://www.raspberrypi.org/documentation/remote-access/ssh/sftp.md), copie los archivos de la ubicación de publicación en el equipo de desarrollo en una nueva carpeta de Raspberry PI.</span><span class="sxs-lookup"><span data-stu-id="f7072-101">[Using an SFTP client](https://www.raspberrypi.org/documentation/remote-access/ssh/sftp.md), copy the files from the publish location on the development computer to a new folder on the Raspberry Pi.</span></span>

<span data-ttu-id="f7072-102">Por ejemplo, para usar el `scp` comando para copiar archivos del equipo de desarrollo a Raspberry PI, abra un símbolo del sistema y ejecute lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="f7072-102">For example, to use the `scp` command to copy files from the development computer to your Raspberry Pi, open a command prompt and execute the following:</span></span>

```console
scp -r /publish-location/* pi@raspberrypi:/home/pi/deployment-location/
```

<span data-ttu-id="f7072-103">Donde:</span><span class="sxs-lookup"><span data-stu-id="f7072-103">Where:</span></span>

- <span data-ttu-id="f7072-104">La `-r` opción indica `scp` a que copie los archivos de forma recursiva.</span><span class="sxs-lookup"><span data-stu-id="f7072-104">The `-r` option instructs `scp` to copy files recursively.</span></span>
- <span data-ttu-id="f7072-105">*/Publish-Location/* es la carpeta en la que publicó en el paso anterior.</span><span class="sxs-lookup"><span data-stu-id="f7072-105">*/publish-location/* is the folder you published to in the previous step.</span></span>
- <span data-ttu-id="f7072-106">`pi@raspberypi` es el usuario y los nombres de host con el formato `<username>@<hostname>` .</span><span class="sxs-lookup"><span data-stu-id="f7072-106">`pi@raspberypi` is the user and host names in the format `<username>@<hostname>`.</span></span>
- <span data-ttu-id="f7072-107">*/Home/PI/Deployment-Location/* es la nueva carpeta de Raspberry PI.</span><span class="sxs-lookup"><span data-stu-id="f7072-107">*/home/pi/deployment-location/* is the new folder on the Raspberry Pi.</span></span>

> [!TIP]
> <span data-ttu-id="f7072-108">Las versiones recientes de Windows tienen OpenSSH, que incluye `scp` preinstalado.</span><span class="sxs-lookup"><span data-stu-id="f7072-108">Recent versions of Windows have OpenSSH, which includes `scp`, pre-installed.</span></span>
