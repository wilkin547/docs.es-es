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
ms.openlocfilehash: 9bfc6491a1d18c81a44a7d9c5084f744c9b76281
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "62040916"
---
# <a name="strongnamefreebuffer-function"></a><span data-ttu-id="2ae5a-102">StrongNameFreeBuffer (Función)</span><span class="sxs-lookup"><span data-stu-id="2ae5a-102">StrongNameFreeBuffer Function</span></span>
<span data-ttu-id="2ae5a-103">Libera la memoria asignada mediante una llamada anterior a una función de nombre seguro como [StrongNameGetPublicKey](../../../../docs/framework/unmanaged-api/strong-naming/strongnamegetpublickey-function.md), [StrongNameTokenFromPublicKey](../../../../docs/framework/unmanaged-api/strong-naming/strongnametokenfrompublickey-function.md) o [StrongNameSignatureGeneration](../../../../docs/framework/unmanaged-api/strong-naming/strongnamesignaturegeneration-function.md).</span><span class="sxs-lookup"><span data-stu-id="2ae5a-103">Frees memory that was allocated with a previous call to a strong name function such as [StrongNameGetPublicKey](../../../../docs/framework/unmanaged-api/strong-naming/strongnamegetpublickey-function.md), [StrongNameTokenFromPublicKey](../../../../docs/framework/unmanaged-api/strong-naming/strongnametokenfrompublickey-function.md), or [StrongNameSignatureGeneration](../../../../docs/framework/unmanaged-api/strong-naming/strongnamesignaturegeneration-function.md).</span></span>  
  
 <span data-ttu-id="2ae5a-104">Esta función está desusada.</span><span class="sxs-lookup"><span data-stu-id="2ae5a-104">This function has been deprecated.</span></span> <span data-ttu-id="2ae5a-105">Use la [ICLRStrongName](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamefreebuffer-method.md) método en su lugar.</span><span class="sxs-lookup"><span data-stu-id="2ae5a-105">Use the [ICLRStrongName::StrongNameFreeBuffer](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamefreebuffer-method.md) method instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2ae5a-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="2ae5a-106">Syntax</span></span>  
  
```  
VOID StrongNameFreeBuffer (   
   [in] BYTE   *pbMemory  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="2ae5a-107">Parámetros</span><span class="sxs-lookup"><span data-stu-id="2ae5a-107">Parameters</span></span>  
 `pbMemory`  
 <span data-ttu-id="2ae5a-108">[in] Un puntero a la memoria que se va a liberar.</span><span class="sxs-lookup"><span data-stu-id="2ae5a-108">[in] A pointer to the memory to free.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2ae5a-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="2ae5a-109">Requirements</span></span>  
 <span data-ttu-id="2ae5a-110">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2ae5a-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2ae5a-111">**Encabezado**: StrongName.h</span><span class="sxs-lookup"><span data-stu-id="2ae5a-111">**Header:** StrongName.h</span></span>  
  
 <span data-ttu-id="2ae5a-112">**Biblioteca:** Incluye como recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="2ae5a-112">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="2ae5a-113">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2ae5a-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2ae5a-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="2ae5a-114">See also</span></span>

- [<span data-ttu-id="2ae5a-115">StrongNameFreeBuffer (método)</span><span class="sxs-lookup"><span data-stu-id="2ae5a-115">StrongNameFreeBuffer Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamefreebuffer-method.md)
- [<span data-ttu-id="2ae5a-116">ICLRStrongName (interfaz)</span><span class="sxs-lookup"><span data-stu-id="2ae5a-116">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
