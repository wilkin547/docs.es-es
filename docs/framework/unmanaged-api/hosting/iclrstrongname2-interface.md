---
title: ICLRStrongName2 (Interfaz)
ms.date: 03/30/2017
api_name:
- ICLRStrongName2
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRStrongName2
helpviewer_keywords:
- ICLRStrongName2 interface [.NET Framework hosting]
ms.assetid: 9f098a74-201e-4628-a468-8dee9ab99b4a
topic_type:
- apiref
ms.openlocfilehash: bc871c29f53a9ea4451a0fc1c747939724b0da87
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73092243"
---
# <a name="iclrstrongname2-interface"></a><span data-ttu-id="aa2c8-102">ICLRStrongName2 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="aa2c8-102">ICLRStrongName2 Interface</span></span>
<span data-ttu-id="aa2c8-103">Proporciona la capacidad de crear nombres seguros mediante el grupo SHA-2 de algoritmos de hash seguro (SHA-256, SHA-384 y SHA-512).</span><span class="sxs-lookup"><span data-stu-id="aa2c8-103">Provides the ability to create strong names using the SHA-2 group of Secure Hash Algorithms (SHA-256, SHA-384, and SHA-512).</span></span>  
  
## <a name="methods"></a><span data-ttu-id="aa2c8-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="aa2c8-104">Methods</span></span>  
  
|<span data-ttu-id="aa2c8-105">Método</span><span class="sxs-lookup"><span data-stu-id="aa2c8-105">Method</span></span>|<span data-ttu-id="aa2c8-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="aa2c8-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="aa2c8-107">StrongNameGetPublicKeyEx (método)</span><span class="sxs-lookup"><span data-stu-id="aa2c8-107">StrongNameGetPublicKeyEx Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/strongnamegetpublickeyex-method.md)|<span data-ttu-id="aa2c8-108">Obtiene la clave pública de un par de claves pública y privada, y especifica un algoritmo hash y un algoritmo de firma.</span><span class="sxs-lookup"><span data-stu-id="aa2c8-108">Gets the public key from a public/private key pair, and specifies a hash algorithm and a signature algorithm.</span></span>|  
|[<span data-ttu-id="aa2c8-109">StrongNameSignatureVerificationEx2 (método)</span><span class="sxs-lookup"><span data-stu-id="aa2c8-109">StrongNameSignatureVerificationEx2 Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/strongnamesignatureverificationex2-method.md)|<span data-ttu-id="aa2c8-110">Comprueba la firma de un ensamblado con nombre seguro y proporciona una asignación de la clave ECMA a una clave real.</span><span class="sxs-lookup"><span data-stu-id="aa2c8-110">Verifies the signature of a strongly named assembly, and provides a mapping from the ECMA key to a real key.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="aa2c8-111">Comentarios</span><span class="sxs-lookup"><span data-stu-id="aa2c8-111">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="aa2c8-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="aa2c8-112">Requirements</span></span>  
 <span data-ttu-id="aa2c8-113">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="aa2c8-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="aa2c8-114">**Encabezado:** Metahost. h</span><span class="sxs-lookup"><span data-stu-id="aa2c8-114">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="aa2c8-115">**Biblioteca:** Se incluye como recurso en MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="aa2c8-115">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="aa2c8-116">**Versiones de .NET Framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="aa2c8-116">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>
