---
description: 'Más información acerca de: herramienta de búsqueda de clave privada (FindPrivateKey.exe)'
title: Herramienta de búsqueda de clave privada (FindPrivateKey.exe)
ms.date: 09/11/2017
ms.assetid: b8846a95-3fcc-4e8c-b9c0-128d975a6307
ms.openlocfilehash: 1d87d19e17c1de89c13db6d7ca092eedf630e6ca
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99793290"
---
# <a name="find-private-key-tool-findprivatekeyexe"></a><span data-ttu-id="c1005-103">Herramienta de búsqueda de clave privada (FindPrivateKey.exe)</span><span class="sxs-lookup"><span data-stu-id="c1005-103">Find Private Key Tool (FindPrivateKey.exe)</span></span>

<span data-ttu-id="c1005-104">Esta herramienta de línea de comandos se puede utilizar para recuperar una clave privada de un almacén de certificados.</span><span class="sxs-lookup"><span data-stu-id="c1005-104">This command-line tool can be used to retrieve a private key from a certificate store.</span></span> <span data-ttu-id="c1005-105">Por ejemplo, *FindPrivateKey.exe* se puede utilizar para buscar la ubicación y el nombre del archivo de clave privada asociado a un certificado X. 509 concreto en el almacén de certificados.</span><span class="sxs-lookup"><span data-stu-id="c1005-105">For example, *FindPrivateKey.exe* can be used to find the location and name of the private key file associated with a specific X.509 certificate in the certificate store.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="c1005-106">La herramienta FindPrivateKey se entrega como ejemplo de WCF.</span><span class="sxs-lookup"><span data-stu-id="c1005-106">The FindPrivateKey tool is shipped as a WCF sample.</span></span> <span data-ttu-id="c1005-107">Para obtener más información sobre dónde encontrar el ejemplo y cómo compilarlo, vea [FindPrivateKey](./samples/findprivatekey.md).</span><span class="sxs-lookup"><span data-stu-id="c1005-107">For more information about where to find the sample and how to build it, see [FindPrivateKey](./samples/findprivatekey.md).</span></span>

## <a name="syntax"></a><span data-ttu-id="c1005-108">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="c1005-108">Syntax</span></span>

```console
FindPrivateKey<storeName> <storeLocation> [{ {-n <subjectName>} | {-t <thumbprint>} } [-f | -d | -a]]
```

## <a name="remarks"></a><span data-ttu-id="c1005-109">Observaciones</span><span class="sxs-lookup"><span data-stu-id="c1005-109">Remarks</span></span>

<span data-ttu-id="c1005-110">Las tablas siguientes describen los argumentos y las opciones que se pueden utilizar con la herramienta de búsqueda de clave privada (FindPrivateKey.exe).</span><span class="sxs-lookup"><span data-stu-id="c1005-110">The following tables describe the arguments and the options that can be used with the Find Private Key tool (FindPrivateKey.exe).</span></span>

|<span data-ttu-id="c1005-111">Argumento</span><span class="sxs-lookup"><span data-stu-id="c1005-111">Argument</span></span>|<span data-ttu-id="c1005-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="c1005-112">Description</span></span>|
|--------------|-----------------|
|`storeName`|<span data-ttu-id="c1005-113">Nombre del almacén de certificados.</span><span class="sxs-lookup"><span data-stu-id="c1005-113">Name of the certificate store.</span></span>|
|`storeLocation`|<span data-ttu-id="c1005-114">Ubicación del almacén de certificados.</span><span class="sxs-lookup"><span data-stu-id="c1005-114">The location of the certificate store.</span></span>|

|<span data-ttu-id="c1005-115">Opción</span><span class="sxs-lookup"><span data-stu-id="c1005-115">Option</span></span>|<span data-ttu-id="c1005-116">Descripción</span><span class="sxs-lookup"><span data-stu-id="c1005-116">Description</span></span>|
|------------|-----------------|
|<span data-ttu-id="c1005-117">`/n <`*subjectName*`>`</span><span class="sxs-lookup"><span data-stu-id="c1005-117">`/n <` *subjectName* `>`</span></span>|<span data-ttu-id="c1005-118">Especifica el nombre de sujeto del certificado.</span><span class="sxs-lookup"><span data-stu-id="c1005-118">Specifies the subject name of the certificate.</span></span>|
|<span data-ttu-id="c1005-119">`/t <`*huella digital*`>`</span><span class="sxs-lookup"><span data-stu-id="c1005-119">`/t <` *thumbprint* `>`</span></span>|<span data-ttu-id="c1005-120">Especifica la huella digital del certificado.</span><span class="sxs-lookup"><span data-stu-id="c1005-120">Specifies the thumbprint of the certificate.</span></span> <span data-ttu-id="c1005-121">Utilice Certmgr.exe para recuperar la huella digital del certificado.</span><span class="sxs-lookup"><span data-stu-id="c1005-121">Use Certmgr.exe to retrieve the thumbprint of the certificate.</span></span>|
|`/f`|<span data-ttu-id="c1005-122">Sólo genera el nombre de archivo.</span><span class="sxs-lookup"><span data-stu-id="c1005-122">Outputs the file name only.</span></span>|
|`/d`|<span data-ttu-id="c1005-123">Sólo genera el directorio.</span><span class="sxs-lookup"><span data-stu-id="c1005-123">Outputs the directory only.</span></span>|
|`/a`|<span data-ttu-id="c1005-124">Genera el nombre de archivo absoluto.</span><span class="sxs-lookup"><span data-stu-id="c1005-124">Outputs the absolute file name.</span></span>|

## <a name="examples"></a><span data-ttu-id="c1005-125">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="c1005-125">Examples</span></span>

<span data-ttu-id="c1005-126">El siguiente comando recupera la clave privada de John Doe:</span><span class="sxs-lookup"><span data-stu-id="c1005-126">The following command retrieves the private key for John Doe:</span></span>

```console
FindPrivateKey My CurrentUser -n "CN=John Doe"
```

<span data-ttu-id="c1005-127">El siguiente comando recupera la clave privada para el equipo local:</span><span class="sxs-lookup"><span data-stu-id="c1005-127">The following command retrieves the private key for the local machine:</span></span>

```console
FindPrivateKey My LocalMachine -t "03 33 98 63 d0 47 e7 48 71 33 62 64 76 5c 4c 9d 42 1d 6b 52" –a
```
