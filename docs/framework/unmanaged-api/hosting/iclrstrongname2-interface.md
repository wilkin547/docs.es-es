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
ms.openlocfilehash: 9715369f4cf1b2a7078be14a2fc597f735ab6fd3
ms.sourcegitcommit: c76c8b2c39ed2f0eee422b61a2ab4c05ca7771fa
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/21/2020
ms.locfileid: "83763168"
---
# <a name="iclrstrongname2-interface"></a><span data-ttu-id="97a50-102">ICLRStrongName2 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="97a50-102">ICLRStrongName2 Interface</span></span>
<span data-ttu-id="97a50-103">Proporciona la capacidad de crear nombres seguros mediante el grupo SHA-2 de algoritmos de hash seguro (SHA-256, SHA-384 y SHA-512).</span><span class="sxs-lookup"><span data-stu-id="97a50-103">Provides the ability to create strong names using the SHA-2 group of Secure Hash Algorithms (SHA-256, SHA-384, and SHA-512).</span></span>  
  
## <a name="methods"></a><span data-ttu-id="97a50-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="97a50-104">Methods</span></span>  
  
|<span data-ttu-id="97a50-105">Método</span><span class="sxs-lookup"><span data-stu-id="97a50-105">Method</span></span>|<span data-ttu-id="97a50-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="97a50-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="97a50-107">StrongNameGetPublicKeyEx (Método)</span><span class="sxs-lookup"><span data-stu-id="97a50-107">StrongNameGetPublicKeyEx Method</span></span>](strongnamegetpublickeyex-method.md)|<span data-ttu-id="97a50-108">Obtiene la clave pública de un par de claves pública y privada, y especifica un algoritmo hash y un algoritmo de firma.</span><span class="sxs-lookup"><span data-stu-id="97a50-108">Gets the public key from a public/private key pair, and specifies a hash algorithm and a signature algorithm.</span></span>|  
|[<span data-ttu-id="97a50-109">StrongNameSignatureVerificationEx2 (Método)</span><span class="sxs-lookup"><span data-stu-id="97a50-109">StrongNameSignatureVerificationEx2 Method</span></span>](strongnamesignatureverificationex2-method.md)|<span data-ttu-id="97a50-110">Comprueba la firma de un ensamblado con nombre seguro y proporciona una asignación de la clave ECMA a una clave real.</span><span class="sxs-lookup"><span data-stu-id="97a50-110">Verifies the signature of a strongly named assembly, and provides a mapping from the ECMA key to a real key.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="97a50-111">Observaciones</span><span class="sxs-lookup"><span data-stu-id="97a50-111">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="97a50-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="97a50-112">Requirements</span></span>  
 <span data-ttu-id="97a50-113">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="97a50-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="97a50-114">**Encabezado:** Metahost. h</span><span class="sxs-lookup"><span data-stu-id="97a50-114">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="97a50-115">**Biblioteca:** Se incluye como recurso en MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="97a50-115">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="97a50-116">**.NET Framework versiones:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="97a50-116">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>
