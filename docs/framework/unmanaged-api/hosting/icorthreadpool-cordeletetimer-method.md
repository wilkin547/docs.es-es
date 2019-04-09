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
ms.openlocfilehash: 098c23dd0ddff4342aa4cefbaa4e149ed95a1cb3
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59178352"
---
# <a name="icorthreadpoolcordeletetimer-method"></a><span data-ttu-id="23f5d-102">ICorThreadpool::CorDeleteTimer (Método)</span><span class="sxs-lookup"><span data-stu-id="23f5d-102">ICorThreadpool::CorDeleteTimer Method</span></span>
<span data-ttu-id="23f5d-103">Este método es compatible con la infraestructura de .NET Framework y no está diseñado para utilizarse directamente desde el código.</span><span class="sxs-lookup"><span data-stu-id="23f5d-103">This method supports the .NET Framework infrastructure and is not intended to be used directly from your code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="23f5d-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="23f5d-104">Syntax</span></span>  
  
```  
HRESULT CorDeleteTimer (  
    [in]  HANDLE Timer,  
    [in]  HANDLE CompletionEvent,  
    [out] BOOL*  result  
);  
```  
  
## <a name="requirements"></a><span data-ttu-id="23f5d-105">Requisitos</span><span class="sxs-lookup"><span data-stu-id="23f5d-105">Requirements</span></span>  
 <span data-ttu-id="23f5d-106">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="23f5d-106">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="23f5d-107">**Encabezado**: MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="23f5d-107">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="23f5d-108">**Biblioteca:** Incluye como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="23f5d-108">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 **<span data-ttu-id="23f5d-109">Versiones de .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="23f5d-109">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="23f5d-110">Vea también</span><span class="sxs-lookup"><span data-stu-id="23f5d-110">See also</span></span>

- [<span data-ttu-id="23f5d-111">ICorThreadpool (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="23f5d-111">ICorThreadpool Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorthreadpool-interface.md)
