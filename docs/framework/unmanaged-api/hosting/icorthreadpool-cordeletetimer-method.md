---
title: ICorThreadpool::CorDeleteTimer (Método)
ms.date: 03/30/2017
api_name:
- ICorThreadpool.CorDeleteTimer
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorDeleteTimer
helpviewer_keywords:
- ICorThreadpool::CorDeleteTimer method [.NET Framework hosting]
- CorDeleteTimer method [.NET Framework hosting]
ms.assetid: 74847c35-7ca1-466a-b750-b25e7b03d100
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: b7cba6db456d15ebcfedb305343962b37e5ca1a2
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54491966"
---
# <a name="icorthreadpoolcordeletetimer-method"></a><span data-ttu-id="dd315-102">ICorThreadpool::CorDeleteTimer (Método)</span><span class="sxs-lookup"><span data-stu-id="dd315-102">ICorThreadpool::CorDeleteTimer Method</span></span>
<span data-ttu-id="dd315-103">Este método es compatible con la infraestructura de .NET Framework y no está diseñado para utilizarse directamente desde el código.</span><span class="sxs-lookup"><span data-stu-id="dd315-103">This method supports the .NET Framework infrastructure and is not intended to be used directly from your code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="dd315-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="dd315-104">Syntax</span></span>  
  
```  
HRESULT CorDeleteTimer (  
    [in]  HANDLE Timer,  
    [in]  HANDLE CompletionEvent,  
    [out] BOOL*  result  
);  
```  
  
## <a name="requirements"></a><span data-ttu-id="dd315-105">Requisitos</span><span class="sxs-lookup"><span data-stu-id="dd315-105">Requirements</span></span>  
 <span data-ttu-id="dd315-106">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="dd315-106">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="dd315-107">**Encabezado**: MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="dd315-107">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="dd315-108">**Biblioteca:** Incluye como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="dd315-108">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="dd315-109">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="dd315-109">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dd315-110">Vea también</span><span class="sxs-lookup"><span data-stu-id="dd315-110">See also</span></span>
- [<span data-ttu-id="dd315-111">ICorThreadpool (interfaz)</span><span class="sxs-lookup"><span data-stu-id="dd315-111">ICorThreadpool Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorthreadpool-interface.md)
