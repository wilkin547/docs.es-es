---
title: StrongNameFreeBuffer (Función)
ms.date: 03/30/2017
api_name:
- StrongNameFreeBuffer
api_location:
- mscoree.dll
- mscorsn.dll
- clr.dll
- mscorwks.dll
- mscoreei.dll
api_type:
- DLLExport
f1_keywords:
- StrongNameFreeBuffer
helpviewer_keywords:
- StrongNameFreeBuffer function [.NET Framework strong naming]
ms.assetid: eda21ecf-4734-4f92-aaba-9f34884385db
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: f308f6c1f977fad8fa102f30756f0e43c779cc8a
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/06/2019
ms.locfileid: "57472062"
---
# <a name="strongnamefreebuffer-function"></a><span data-ttu-id="6c89f-102">StrongNameFreeBuffer (Función)</span><span class="sxs-lookup"><span data-stu-id="6c89f-102">StrongNameFreeBuffer Function</span></span>
<span data-ttu-id="6c89f-103">Libera la memoria asignada mediante una llamada anterior a una función de nombre seguro como [StrongNameGetPublicKey](../../../../docs/framework/unmanaged-api/strong-naming/strongnamegetpublickey-function.md), [StrongNameTokenFromPublicKey](../../../../docs/framework/unmanaged-api/strong-naming/strongnametokenfrompublickey-function.md) o [StrongNameSignatureGeneration](../../../../docs/framework/unmanaged-api/strong-naming/strongnamesignaturegeneration-function.md).</span><span class="sxs-lookup"><span data-stu-id="6c89f-103">Frees memory that was allocated with a previous call to a strong name function such as [StrongNameGetPublicKey](../../../../docs/framework/unmanaged-api/strong-naming/strongnamegetpublickey-function.md), [StrongNameTokenFromPublicKey](../../../../docs/framework/unmanaged-api/strong-naming/strongnametokenfrompublickey-function.md), or [StrongNameSignatureGeneration](../../../../docs/framework/unmanaged-api/strong-naming/strongnamesignaturegeneration-function.md).</span></span>  
  
 <span data-ttu-id="6c89f-104">Esta función está desusada.</span><span class="sxs-lookup"><span data-stu-id="6c89f-104">This function has been deprecated.</span></span> <span data-ttu-id="6c89f-105">Use la [ICLRStrongName](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamefreebuffer-method.md) método en su lugar.</span><span class="sxs-lookup"><span data-stu-id="6c89f-105">Use the [ICLRStrongName::StrongNameFreeBuffer](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamefreebuffer-method.md) method instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6c89f-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="6c89f-106">Syntax</span></span>  
  
```  
VOID StrongNameFreeBuffer (   
   [in] BYTE   *pbMemory  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="6c89f-107">Parámetros</span><span class="sxs-lookup"><span data-stu-id="6c89f-107">Parameters</span></span>  
 `pbMemory`  
 <span data-ttu-id="6c89f-108">[in] Un puntero a la memoria que se va a liberar.</span><span class="sxs-lookup"><span data-stu-id="6c89f-108">[in] A pointer to the memory to free.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6c89f-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="6c89f-109">Requirements</span></span>  
 <span data-ttu-id="6c89f-110">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6c89f-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6c89f-111">**Encabezado**: StrongName.h</span><span class="sxs-lookup"><span data-stu-id="6c89f-111">**Header:** StrongName.h</span></span>  
  
 <span data-ttu-id="6c89f-112">**Biblioteca:** Incluye como recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="6c89f-112">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="6c89f-113">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6c89f-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6c89f-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="6c89f-114">See also</span></span>
- [<span data-ttu-id="6c89f-115">StrongNameFreeBuffer (método)</span><span class="sxs-lookup"><span data-stu-id="6c89f-115">StrongNameFreeBuffer Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamefreebuffer-method.md)
- [<span data-ttu-id="6c89f-116">ICLRStrongName (interfaz)</span><span class="sxs-lookup"><span data-stu-id="6c89f-116">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
