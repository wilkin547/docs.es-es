---
title: IObjectHandle::Unwrap (Método)
ms.date: 03/30/2017
api_name:
- IObjectHandle.Unwrap
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- Unwrap
helpviewer_keywords:
- Unwrap method [.NET Framework hosting]
- IObjectHandle::Unwrap method [.NET Framework hosting]
ms.assetid: 794c6f8e-ed58-416b-b756-e864f2c958f7
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: da25055917743481f5a8314023ed94d552fe49ce
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54526423"
---
# <a name="iobjecthandleunwrap-method"></a><span data-ttu-id="4ceca-102">IObjectHandle::Unwrap (Método)</span><span class="sxs-lookup"><span data-stu-id="4ceca-102">IObjectHandle::Unwrap Method</span></span>
<span data-ttu-id="4ceca-103">Desencapsula un objeto de cálculo de referencias por valor desde el direccionamiento indirecto.</span><span class="sxs-lookup"><span data-stu-id="4ceca-103">Unwraps a marshal-by-value object from indirection.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4ceca-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="4ceca-104">Syntax</span></span>  
  
```  
HRESULT Unwrap (  
    [out, retval] VARIANT *ppv  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="4ceca-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="4ceca-105">Parameters</span></span>  
 `ppv`  
 <span data-ttu-id="4ceca-106">[out] Un puntero al objeto que se debe desencapsular.</span><span class="sxs-lookup"><span data-stu-id="4ceca-106">[out] A pointer to the object to be unwrapped.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4ceca-107">Requisitos</span><span class="sxs-lookup"><span data-stu-id="4ceca-107">Requirements</span></span>  
 <span data-ttu-id="4ceca-108">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4ceca-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4ceca-109">**Encabezado**: MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="4ceca-109">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="4ceca-110">**Biblioteca:** Incluye como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="4ceca-110">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="4ceca-111">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4ceca-111">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4ceca-112">Vea también</span><span class="sxs-lookup"><span data-stu-id="4ceca-112">See also</span></span>

