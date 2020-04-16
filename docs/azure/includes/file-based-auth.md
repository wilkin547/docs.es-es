---
ms.service: multiple
ms.date: 9/20/2018
ms.topic: include
ms.openlocfilehash: bfa7bcefff45bc325d7bba3aa2b9b3a8f0d439fa
ms.sourcegitcommit: 34dc3c0d0d0a1cc418abff259d9daa8078d00b81
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/19/2020
ms.locfileid: "81433161"
---
<span data-ttu-id="ca593-101">Cree un archivo de texto llamado `azureauth.json`.</span><span class="sxs-lookup"><span data-stu-id="ca593-101">Create a text file named `azureauth.json`.</span></span> <span data-ttu-id="ca593-102">Pegue la salida JSON de la creación de la entidad de servicio.</span><span class="sxs-lookup"><span data-stu-id="ca593-102">Paste the JSON output from when you created the service principal.</span></span>

<span data-ttu-id="ca593-103">Guarde este archivo en una ubicación segura en el sistema donde el código pueda leerlo.</span><span class="sxs-lookup"><span data-stu-id="ca593-103">Save this file in a secure location on your system where your code can read it.</span></span> <span data-ttu-id="ca593-104">Use PowerShell para establecer una variable de entorno denominada `AZURE_AUTH_LOCATION` con la ruta de acceso completa al archivo, por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="ca593-104">Use PowerShell to set an environment variable named `AZURE_AUTH_LOCATION` with the full path to the file, for example:</span></span>

```powershell
[Environment]::SetEnvironmentVariable("AZURE_AUTH_LOCATION", "C:\src\azureauth.json", "User")
```
