---
title: ICorThreadpool::CorSetMaxThreads (Método)
ms.date: 03/30/2017
api_name:
- ICorThreadpool.CorSetMaxThreads
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorSetMaxThreads
helpviewer_keywords:
- ICorThreadpool::CorSetMaxThreads method [.NET Framework hosting]
- CorSetMaxThreads method [.NET Framework hosting]
ms.assetid: 4a846238-df4e-4060-ba3b-5173f6a51e85
topic_type:
- apiref
ms.openlocfilehash: 7f972bcfedd028d85debbbd60968a57c4d64ee0c
ms.sourcegitcommit: c76c8b2c39ed2f0eee422b61a2ab4c05ca7771fa
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/21/2020
ms.locfileid: "83760360"
---
# <a name="icorthreadpoolcorsetmaxthreads-method"></a><span data-ttu-id="7a43c-102">ICorThreadpool::CorSetMaxThreads (Método)</span><span class="sxs-lookup"><span data-stu-id="7a43c-102">ICorThreadpool::CorSetMaxThreads Method</span></span>
<span data-ttu-id="7a43c-103">Este método es compatible con la infraestructura de .NET Framework y no está diseñado para utilizarse directamente desde el código.</span><span class="sxs-lookup"><span data-stu-id="7a43c-103">This method supports the .NET Framework infrastructure and is not intended to be used directly from your code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7a43c-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="7a43c-104">Syntax</span></span>  
  
```cpp  
HRESULT CorSetMaxThreads (  
    [in] DWORD MaxWorkerThreads,  
    [in] DWORD MaxIOCompletionThreads  
);  
```  
  
## <a name="requirements"></a><span data-ttu-id="7a43c-105">Requisitos</span><span class="sxs-lookup"><span data-stu-id="7a43c-105">Requirements</span></span>  
 <span data-ttu-id="7a43c-106">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7a43c-106">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7a43c-107">**Encabezado:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="7a43c-107">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="7a43c-108">**Biblioteca:** Se incluye como recurso en MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="7a43c-108">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="7a43c-109">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7a43c-109">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7a43c-110">Consulte también:</span><span class="sxs-lookup"><span data-stu-id="7a43c-110">See also</span></span>

- [<span data-ttu-id="7a43c-111">ICorThreadpool (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="7a43c-111">ICorThreadpool Interface</span></span>](icorthreadpool-interface.md)
