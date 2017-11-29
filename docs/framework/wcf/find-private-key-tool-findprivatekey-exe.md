---
title: "Herramienta de búsqueda de clave privada (FindPrivateKey.exe)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: b8846a95-3fcc-4e8c-b9c0-128d975a6307
caps.latest.revision: "13"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 5e2110e129b293ffb04c8e3eb69a5c3bfe83c17b
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="find-private-key-tool-findprivatekeyexe"></a><span data-ttu-id="11bf1-102">Herramienta de búsqueda de clave privada (FindPrivateKey.exe)</span><span class="sxs-lookup"><span data-stu-id="11bf1-102">Find Private Key Tool (FindPrivateKey.exe)</span></span>
<span data-ttu-id="11bf1-103">Esta herramienta de línea de comandos se puede utilizar para recuperar una clave privada de un almacén de certificados.</span><span class="sxs-lookup"><span data-stu-id="11bf1-103">This command-line tool can be used to retrieve a private key from a certificate store.</span></span> <span data-ttu-id="11bf1-104">Por ejemplo, FindPrivateKey.exe se puede utilizar para buscar la ubicación y nombre del archivo de clave privada asociado a un certificado X.509 concreto en el almacén de certificados.</span><span class="sxs-lookup"><span data-stu-id="11bf1-104">For example, FindPrivateKey.exe can be used to find the location and name of the private key file associated with a specific X.509 certificate in the certificate store.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="11bf1-105">La herramienta FindPrivateKey se entrega como ejemplo de WCF.</span><span class="sxs-lookup"><span data-stu-id="11bf1-105">The FindPrivateKey tool is shipped as a WCF sample.</span></span> <span data-ttu-id="11bf1-106">Para obtener más información sobre dónde encontrar el ejemplo y cómo compilarlo, vea</span><span class="sxs-lookup"><span data-stu-id="11bf1-106">For more information about where to find the sample and how to build it, see</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="11bf1-107">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="11bf1-107">Syntax</span></span>  
  
```  
FindPrivateKey<storeName> <storeLocation> [{ {-n <subjectName>} | {-t <thumbprint>} } [-f | -d | -a]]  
```  
  
## <a name="remarks"></a><span data-ttu-id="11bf1-108">Comentarios</span><span class="sxs-lookup"><span data-stu-id="11bf1-108">Remarks</span></span>  
 <span data-ttu-id="11bf1-109">Las tablas siguientes describen los argumentos y las opciones que se pueden utilizar con la herramienta de búsqueda de clave privada (FindPrivateKey.exe).</span><span class="sxs-lookup"><span data-stu-id="11bf1-109">The following tables describe the arguments and the options that can be used with the Find Private Key tool (FindPrivateKey.exe).</span></span>  
  
|<span data-ttu-id="11bf1-110">Argumento</span><span class="sxs-lookup"><span data-stu-id="11bf1-110">Argument</span></span>|<span data-ttu-id="11bf1-111">Descripción</span><span class="sxs-lookup"><span data-stu-id="11bf1-111">Description</span></span>|  
|--------------|-----------------|  
|`storeName`|<span data-ttu-id="11bf1-112">Nombre del almacén de certificados.</span><span class="sxs-lookup"><span data-stu-id="11bf1-112">Name of the certificate store.</span></span>|  
|`storeLocation`|<span data-ttu-id="11bf1-113">Ubicación del almacén de certificados.</span><span class="sxs-lookup"><span data-stu-id="11bf1-113">The location of the certificate store.</span></span>|  
  
|<span data-ttu-id="11bf1-114">Opción</span><span class="sxs-lookup"><span data-stu-id="11bf1-114">Option</span></span>|<span data-ttu-id="11bf1-115">Descripción</span><span class="sxs-lookup"><span data-stu-id="11bf1-115">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="11bf1-116">`/n <`*subjectName*`>`</span><span class="sxs-lookup"><span data-stu-id="11bf1-116">`/n <` *subjectName* `>`</span></span>|<span data-ttu-id="11bf1-117">Especifica el nombre de sujeto del certificado.</span><span class="sxs-lookup"><span data-stu-id="11bf1-117">Specifies the subject name of the certificate.</span></span>|  
|<span data-ttu-id="11bf1-118">`/t <`*huella digital*`>`</span><span class="sxs-lookup"><span data-stu-id="11bf1-118">`/t <` *thumbprint* `>`</span></span>|<span data-ttu-id="11bf1-119">Especifica la huella digital del certificado.</span><span class="sxs-lookup"><span data-stu-id="11bf1-119">Specifies the thumbprint of the certificate.</span></span> <span data-ttu-id="11bf1-120">Utilice Certmgr.exe para recuperar la huella digital del certificado.</span><span class="sxs-lookup"><span data-stu-id="11bf1-120">Use Certmgr.exe to retrieve the thumbprint of the certificate.</span></span>|  
|`/f`|<span data-ttu-id="11bf1-121">Sólo genera el nombre de archivo.</span><span class="sxs-lookup"><span data-stu-id="11bf1-121">Outputs the file name only.</span></span>|  
|`/d`|<span data-ttu-id="11bf1-122">Sólo genera el directorio.</span><span class="sxs-lookup"><span data-stu-id="11bf1-122">Outputs the directory only.</span></span>|  
|`/a`|<span data-ttu-id="11bf1-123">Genera el nombre de archivo absoluto.</span><span class="sxs-lookup"><span data-stu-id="11bf1-123">Outputs the absolute file name.</span></span>|  
  
## <a name="examples"></a><span data-ttu-id="11bf1-124">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="11bf1-124">Examples</span></span>  
 <span data-ttu-id="11bf1-125">El comando siguiente recupera la clave privada para John Doe.</span><span class="sxs-lookup"><span data-stu-id="11bf1-125">The following command retrieves the private key for John Doe.</span></span>  
  
```  
FindPrivateKey My CurrentUser -n "CN=John Doe"  
```  
  
 <span data-ttu-id="11bf1-126">El comando siguiente recupera la clave privada para el equipo local.</span><span class="sxs-lookup"><span data-stu-id="11bf1-126">The following command retrieves the private key for the local machine.</span></span>  
  
```  
FindPrivateKey My LocalMachine -t "03 33 98 63 d0 47 e7 48 71 33 62 64 76 5c 4c 9d 42 1d 6b 52" –a  
```
