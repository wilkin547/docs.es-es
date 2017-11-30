---
title: ICLRStrongName2 (Interfaz)
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICLRStrongName2
api_location: mscoree.dll
api_type: COM
f1_keywords: ICLRStrongName2
helpviewer_keywords: ICLRStrongName2 interface [.NET Framework hosting]
ms.assetid: 9f098a74-201e-4628-a468-8dee9ab99b4a
topic_type: apiref
caps.latest.revision: "5"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 9e9a88f1064c888d60e363be569d06458299143d
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="iclrstrongname2-interface"></a><span data-ttu-id="b6e17-102">ICLRStrongName2 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="b6e17-102">ICLRStrongName2 Interface</span></span>
<span data-ttu-id="b6e17-103">Proporciona la capacidad para crear nombres seguros mediante el grupo de SHA-2 de algoritmos de Hash seguro (SHA-256, SHA-384 y SHA-512).</span><span class="sxs-lookup"><span data-stu-id="b6e17-103">Provides the ability to create strong names using the SHA-2 group of Secure Hash Algorithms (SHA-256, SHA-384, and SHA-512).</span></span>  
  
## <a name="methods"></a><span data-ttu-id="b6e17-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="b6e17-104">Methods</span></span>  
  
|<span data-ttu-id="b6e17-105">Método</span><span class="sxs-lookup"><span data-stu-id="b6e17-105">Method</span></span>|<span data-ttu-id="b6e17-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="b6e17-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="b6e17-107">StrongNameGetPublicKeyEx (método)</span><span class="sxs-lookup"><span data-stu-id="b6e17-107">StrongNameGetPublicKeyEx Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/strongnamegetpublickeyex-method.md)|<span data-ttu-id="b6e17-108">Obtiene la clave pública de un par de claves pública y privada y especifica un algoritmo hash y un algoritmo de firma.</span><span class="sxs-lookup"><span data-stu-id="b6e17-108">Gets the public key from a public/private key pair, and specifies a hash algorithm and a signature algorithm.</span></span>|  
|[<span data-ttu-id="b6e17-109">StrongNameSignatureVerificationEx2 (método)</span><span class="sxs-lookup"><span data-stu-id="b6e17-109">StrongNameSignatureVerificationEx2 Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/strongnamesignatureverificationex2-method.md)|<span data-ttu-id="b6e17-110">Comprueba la firma de un ensamblado con nombre seguro y proporciona una asignación de la clave ECMA a una clave real.</span><span class="sxs-lookup"><span data-stu-id="b6e17-110">Verifies the signature of a strongly named assembly, and provides a mapping from the ECMA key to a real key.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b6e17-111">Comentarios</span><span class="sxs-lookup"><span data-stu-id="b6e17-111">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b6e17-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="b6e17-112">Requirements</span></span>  
 <span data-ttu-id="b6e17-113">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b6e17-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b6e17-114">**Encabezado:** MetaHost.h</span><span class="sxs-lookup"><span data-stu-id="b6e17-114">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="b6e17-115">**Biblioteca:** incluye como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="b6e17-115">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="b6e17-116">**Versiones de .NET framework:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b6e17-116">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>
