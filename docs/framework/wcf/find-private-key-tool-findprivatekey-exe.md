---
title: Herramienta de búsqueda de clave privada (FindPrivateKey.exe)
ms.date: 09/11/2017
ms.assetid: b8846a95-3fcc-4e8c-b9c0-128d975a6307
ms.openlocfilehash: 8f156cbb2f4fad8d51e356bd4dee2d72d9397ffb
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61929589"
---
# <a name="find-private-key-tool-findprivatekeyexe"></a><span data-ttu-id="47963-102">Herramienta de búsqueda de clave privada (FindPrivateKey.exe)</span><span class="sxs-lookup"><span data-stu-id="47963-102">Find Private Key Tool (FindPrivateKey.exe)</span></span>

<span data-ttu-id="47963-103">Esta herramienta de línea de comandos se puede utilizar para recuperar una clave privada de un almacén de certificados.</span><span class="sxs-lookup"><span data-stu-id="47963-103">This command-line tool can be used to retrieve a private key from a certificate store.</span></span> <span data-ttu-id="47963-104">Por ejemplo, *FindPrivateKey.exe* puede usarse para buscar la ubicación y el nombre del archivo de clave privado asociado con un certificado X.509 concreto en el almacén de certificados.</span><span class="sxs-lookup"><span data-stu-id="47963-104">For example, *FindPrivateKey.exe* can be used to find the location and name of the private key file associated with a specific X.509 certificate in the certificate store.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="47963-105">La herramienta FindPrivateKey se entrega como ejemplo de WCF.</span><span class="sxs-lookup"><span data-stu-id="47963-105">The FindPrivateKey tool is shipped as a WCF sample.</span></span> <span data-ttu-id="47963-106">Para obtener más información sobre dónde encontrar el ejemplo y cómo crearla, consulte [FindPrivateKey](./samples/findprivatekey.md).</span><span class="sxs-lookup"><span data-stu-id="47963-106">For more information about where to find the sample and how to build it, see [FindPrivateKey](./samples/findprivatekey.md).</span></span>

## <a name="syntax"></a><span data-ttu-id="47963-107">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="47963-107">Syntax</span></span>

```
FindPrivateKey<storeName> <storeLocation> [{ {-n <subjectName>} | {-t <thumbprint>} } [-f | -d | -a]]
```

## <a name="remarks"></a><span data-ttu-id="47963-108">Comentarios</span><span class="sxs-lookup"><span data-stu-id="47963-108">Remarks</span></span>

<span data-ttu-id="47963-109">Las tablas siguientes describen los argumentos y las opciones que se pueden utilizar con la herramienta de búsqueda de clave privada (FindPrivateKey.exe).</span><span class="sxs-lookup"><span data-stu-id="47963-109">The following tables describe the arguments and the options that can be used with the Find Private Key tool (FindPrivateKey.exe).</span></span>

|<span data-ttu-id="47963-110">Argumento</span><span class="sxs-lookup"><span data-stu-id="47963-110">Argument</span></span>|<span data-ttu-id="47963-111">Descripción</span><span class="sxs-lookup"><span data-stu-id="47963-111">Description</span></span>|
|--------------|-----------------|
|`storeName`|<span data-ttu-id="47963-112">Nombre del almacén de certificados.</span><span class="sxs-lookup"><span data-stu-id="47963-112">Name of the certificate store.</span></span>|
|`storeLocation`|<span data-ttu-id="47963-113">Ubicación del almacén de certificados.</span><span class="sxs-lookup"><span data-stu-id="47963-113">The location of the certificate store.</span></span>|

|<span data-ttu-id="47963-114">Opción</span><span class="sxs-lookup"><span data-stu-id="47963-114">Option</span></span>|<span data-ttu-id="47963-115">Descripción</span><span class="sxs-lookup"><span data-stu-id="47963-115">Description</span></span>|
|------------|-----------------|
|<span data-ttu-id="47963-116">`/n <` *subjectName* `>`</span><span class="sxs-lookup"><span data-stu-id="47963-116">`/n <` *subjectName* `>`</span></span>|<span data-ttu-id="47963-117">Especifica el nombre de sujeto del certificado.</span><span class="sxs-lookup"><span data-stu-id="47963-117">Specifies the subject name of the certificate.</span></span>|
|<span data-ttu-id="47963-118">`/t <` *Huella digital* `>`</span><span class="sxs-lookup"><span data-stu-id="47963-118">`/t <` *thumbprint* `>`</span></span>|<span data-ttu-id="47963-119">Especifica la huella digital del certificado.</span><span class="sxs-lookup"><span data-stu-id="47963-119">Specifies the thumbprint of the certificate.</span></span> <span data-ttu-id="47963-120">Utilice Certmgr.exe para recuperar la huella digital del certificado.</span><span class="sxs-lookup"><span data-stu-id="47963-120">Use Certmgr.exe to retrieve the thumbprint of the certificate.</span></span>|
|`/f`|<span data-ttu-id="47963-121">Sólo genera el nombre de archivo.</span><span class="sxs-lookup"><span data-stu-id="47963-121">Outputs the file name only.</span></span>|
|`/d`|<span data-ttu-id="47963-122">Sólo genera el directorio.</span><span class="sxs-lookup"><span data-stu-id="47963-122">Outputs the directory only.</span></span>|
|`/a`|<span data-ttu-id="47963-123">Genera el nombre de archivo absoluto.</span><span class="sxs-lookup"><span data-stu-id="47963-123">Outputs the absolute file name.</span></span>|

## <a name="examples"></a><span data-ttu-id="47963-124">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="47963-124">Examples</span></span>

<span data-ttu-id="47963-125">El comando siguiente recupera la clave privada para John Doe:</span><span class="sxs-lookup"><span data-stu-id="47963-125">The following command retrieves the private key for John Doe:</span></span>

```
FindPrivateKey My CurrentUser -n "CN=John Doe"
```

<span data-ttu-id="47963-126">El comando siguiente recupera la clave privada para el equipo local:</span><span class="sxs-lookup"><span data-stu-id="47963-126">The following command retrieves the private key for the local machine:</span></span>

```
FindPrivateKey My LocalMachine -t "03 33 98 63 d0 47 e7 48 71 33 62 64 76 5c 4c 9d 42 1d 6b 52" –a
```