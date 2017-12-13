---
title: "Herramienta de búsqueda de clave privada (FindPrivateKey.exe)"
ms.date: 09/11/2017
ms.prod: .net-framework
ms.technology: dotnet-clr
ms.topic: article
ms.assetid: b8846a95-3fcc-4e8c-b9c0-128d975a6307
caps.latest.revision: "13"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 2d515077106b8f0527d045d5ef7fb6d7c0c7aa62
ms.sourcegitcommit: 9bee08539b1886c9d57fa3d5bd8a58dfdd7cad94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/12/2017
---
# <a name="find-private-key-tool-findprivatekeyexe"></a><span data-ttu-id="1c747-102">Herramienta de búsqueda de clave privada (FindPrivateKey.exe)</span><span class="sxs-lookup"><span data-stu-id="1c747-102">Find Private Key Tool (FindPrivateKey.exe)</span></span>

<span data-ttu-id="1c747-103">Esta herramienta de línea de comandos se puede utilizar para recuperar una clave privada de un almacén de certificados.</span><span class="sxs-lookup"><span data-stu-id="1c747-103">This command-line tool can be used to retrieve a private key from a certificate store.</span></span> <span data-ttu-id="1c747-104">Por ejemplo, *FindPrivateKey.exe* puede usarse para buscar la ubicación y el nombre del archivo de clave privada asociado con un certificado X.509 concreto en el almacén de certificados.</span><span class="sxs-lookup"><span data-stu-id="1c747-104">For example, *FindPrivateKey.exe* can be used to find the location and name of the private key file associated with a specific X.509 certificate in the certificate store.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="1c747-105">La herramienta FindPrivateKey se entrega como ejemplo de WCF.</span><span class="sxs-lookup"><span data-stu-id="1c747-105">The FindPrivateKey tool is shipped as a WCF sample.</span></span> <span data-ttu-id="1c747-106">Para obtener más información sobre dónde encontrar el ejemplo y cómo compilarlo, vea [FindPrivateKey](./samples/findprivatekey.md).</span><span class="sxs-lookup"><span data-stu-id="1c747-106">For more information about where to find the sample and how to build it, see [FindPrivateKey](./samples/findprivatekey.md).</span></span>

## <a name="syntax"></a><span data-ttu-id="1c747-107">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="1c747-107">Syntax</span></span>

```
FindPrivateKey<storeName> <storeLocation> [{ {-n <subjectName>} | {-t <thumbprint>} } [-f | -d | -a]]
```

## <a name="remarks"></a><span data-ttu-id="1c747-108">Comentarios</span><span class="sxs-lookup"><span data-stu-id="1c747-108">Remarks</span></span>

<span data-ttu-id="1c747-109">Las tablas siguientes describen los argumentos y las opciones que se pueden utilizar con la herramienta de búsqueda de clave privada (FindPrivateKey.exe).</span><span class="sxs-lookup"><span data-stu-id="1c747-109">The following tables describe the arguments and the options that can be used with the Find Private Key tool (FindPrivateKey.exe).</span></span>

|<span data-ttu-id="1c747-110">Argumento</span><span class="sxs-lookup"><span data-stu-id="1c747-110">Argument</span></span>|<span data-ttu-id="1c747-111">Descripción</span><span class="sxs-lookup"><span data-stu-id="1c747-111">Description</span></span>|
|--------------|-----------------|
|`storeName`|<span data-ttu-id="1c747-112">Nombre del almacén de certificados.</span><span class="sxs-lookup"><span data-stu-id="1c747-112">Name of the certificate store.</span></span>|
|`storeLocation`|<span data-ttu-id="1c747-113">Ubicación del almacén de certificados.</span><span class="sxs-lookup"><span data-stu-id="1c747-113">The location of the certificate store.</span></span>|

|<span data-ttu-id="1c747-114">Opción</span><span class="sxs-lookup"><span data-stu-id="1c747-114">Option</span></span>|<span data-ttu-id="1c747-115">Descripción</span><span class="sxs-lookup"><span data-stu-id="1c747-115">Description</span></span>|
|------------|-----------------|
|<span data-ttu-id="1c747-116">`/n <`*subjectName*`>`</span><span class="sxs-lookup"><span data-stu-id="1c747-116">`/n <` *subjectName* `>`</span></span>|<span data-ttu-id="1c747-117">Especifica el nombre de sujeto del certificado.</span><span class="sxs-lookup"><span data-stu-id="1c747-117">Specifies the subject name of the certificate.</span></span>|
|<span data-ttu-id="1c747-118">`/t <`*huella digital*`>`</span><span class="sxs-lookup"><span data-stu-id="1c747-118">`/t <` *thumbprint* `>`</span></span>|<span data-ttu-id="1c747-119">Especifica la huella digital del certificado.</span><span class="sxs-lookup"><span data-stu-id="1c747-119">Specifies the thumbprint of the certificate.</span></span> <span data-ttu-id="1c747-120">Utilice Certmgr.exe para recuperar la huella digital del certificado.</span><span class="sxs-lookup"><span data-stu-id="1c747-120">Use Certmgr.exe to retrieve the thumbprint of the certificate.</span></span>|
|`/f`|<span data-ttu-id="1c747-121">Sólo genera el nombre de archivo.</span><span class="sxs-lookup"><span data-stu-id="1c747-121">Outputs the file name only.</span></span>|
|`/d`|<span data-ttu-id="1c747-122">Sólo genera el directorio.</span><span class="sxs-lookup"><span data-stu-id="1c747-122">Outputs the directory only.</span></span>|
|`/a`|<span data-ttu-id="1c747-123">Genera el nombre de archivo absoluto.</span><span class="sxs-lookup"><span data-stu-id="1c747-123">Outputs the absolute file name.</span></span>|

## <a name="examples"></a><span data-ttu-id="1c747-124">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="1c747-124">Examples</span></span>

<span data-ttu-id="1c747-125">El comando siguiente recupera la clave privada para John Doe:</span><span class="sxs-lookup"><span data-stu-id="1c747-125">The following command retrieves the private key for John Doe:</span></span>

```
FindPrivateKey My CurrentUser -n "CN=John Doe"
```

<span data-ttu-id="1c747-126">El comando siguiente recupera la clave privada para el equipo local:</span><span class="sxs-lookup"><span data-stu-id="1c747-126">The following command retrieves the private key for the local machine:</span></span>

```
FindPrivateKey My LocalMachine -t "03 33 98 63 d0 47 e7 48 71 33 62 64 76 5c 4c 9d 42 1d 6b 52" –a
```