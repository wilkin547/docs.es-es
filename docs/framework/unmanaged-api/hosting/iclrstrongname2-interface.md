---
description: 'Más información acerca de: interfaz Iclrstrongname2 ('
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
ms.openlocfilehash: 7442bd054af735e9f1b75b05feb8724dfa993f73
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99781797"
---
# <a name="iclrstrongname2-interface"></a><span data-ttu-id="f2102-103">ICLRStrongName2 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="f2102-103">ICLRStrongName2 Interface</span></span>

<span data-ttu-id="f2102-104">Proporciona la capacidad de crear nombres seguros mediante el grupo SHA-2 de algoritmos de hash seguro (SHA-256, SHA-384 y SHA-512).</span><span class="sxs-lookup"><span data-stu-id="f2102-104">Provides the ability to create strong names using the SHA-2 group of Secure Hash Algorithms (SHA-256, SHA-384, and SHA-512).</span></span>  
  
## <a name="methods"></a><span data-ttu-id="f2102-105">Métodos</span><span class="sxs-lookup"><span data-stu-id="f2102-105">Methods</span></span>  
  
|<span data-ttu-id="f2102-106">Método</span><span class="sxs-lookup"><span data-stu-id="f2102-106">Method</span></span>|<span data-ttu-id="f2102-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="f2102-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="f2102-108">StrongNameGetPublicKeyEx (Método)</span><span class="sxs-lookup"><span data-stu-id="f2102-108">StrongNameGetPublicKeyEx Method</span></span>](strongnamegetpublickeyex-method.md)|<span data-ttu-id="f2102-109">Obtiene la clave pública de un par de claves pública y privada, y especifica un algoritmo hash y un algoritmo de firma.</span><span class="sxs-lookup"><span data-stu-id="f2102-109">Gets the public key from a public/private key pair, and specifies a hash algorithm and a signature algorithm.</span></span>|  
|[<span data-ttu-id="f2102-110">StrongNameSignatureVerificationEx2 (Método)</span><span class="sxs-lookup"><span data-stu-id="f2102-110">StrongNameSignatureVerificationEx2 Method</span></span>](strongnamesignatureverificationex2-method.md)|<span data-ttu-id="f2102-111">Comprueba la firma de un ensamblado con nombre seguro y proporciona una asignación de la clave ECMA a una clave real.</span><span class="sxs-lookup"><span data-stu-id="f2102-111">Verifies the signature of a strongly named assembly, and provides a mapping from the ECMA key to a real key.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f2102-112">Observaciones</span><span class="sxs-lookup"><span data-stu-id="f2102-112">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f2102-113">Requisitos</span><span class="sxs-lookup"><span data-stu-id="f2102-113">Requirements</span></span>  

 <span data-ttu-id="f2102-114">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f2102-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f2102-115">**Encabezado:** Metahost. h</span><span class="sxs-lookup"><span data-stu-id="f2102-115">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="f2102-116">**Biblioteca:** Se incluye como un recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="f2102-116">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="f2102-117">**.NET Framework versiones:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f2102-117">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>
