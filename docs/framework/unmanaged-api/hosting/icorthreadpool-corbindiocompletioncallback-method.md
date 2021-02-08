---
description: 'Más información sobre: ICorThreadpool:: Corbindiocompletioncallback ((método)'
title: ICorThreadpool::CorBindIoCompletionCallback (Método)
ms.date: 03/30/2017
api_name:
- ICorThreadpool.CorBindIoCompletionCallback
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorBindIoCompletionCallback
helpviewer_keywords:
- CorBindIoCompletionCallback method [.NET Framework hosting]
- ICorThreadpool::CorBindIoCompletionCallback method [.NET Framework hosting]
ms.assetid: 2b159225-f09c-42f1-aa7c-44087e121249
topic_type:
- apiref
ms.openlocfilehash: 9f9e62fd8947c3ab80c4434814ee7e95b5327a24
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99799439"
---
# <a name="icorthreadpoolcorbindiocompletioncallback-method"></a><span data-ttu-id="036e4-103">ICorThreadpool::CorBindIoCompletionCallback (Método)</span><span class="sxs-lookup"><span data-stu-id="036e4-103">ICorThreadpool::CorBindIoCompletionCallback Method</span></span>

<span data-ttu-id="036e4-104">Este método es compatible con la infraestructura de .NET Framework y no está diseñado para utilizarse directamente desde el código.</span><span class="sxs-lookup"><span data-stu-id="036e4-104">This method supports the .NET Framework infrastructure and is not intended to be used directly from your code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="036e4-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="036e4-105">Syntax</span></span>  
  
```cpp  
HRESULT CorBindIoCompletionCallback (  
    [in] HANDLE                          fileHandle,  
    [in] LPOVERLAPPED_COMPLETION_ROUTINE callback  
);  
```  
  
## <a name="requirements"></a><span data-ttu-id="036e4-106">Requisitos</span><span class="sxs-lookup"><span data-stu-id="036e4-106">Requirements</span></span>  

 <span data-ttu-id="036e4-107">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="036e4-107">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="036e4-108">**Encabezado:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="036e4-108">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="036e4-109">**Biblioteca:** Se incluye como un recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="036e4-109">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="036e4-110">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="036e4-110">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="036e4-111">Vea también</span><span class="sxs-lookup"><span data-stu-id="036e4-111">See also</span></span>

- [<span data-ttu-id="036e4-112">ICorThreadpool (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="036e4-112">ICorThreadpool Interface</span></span>](icorthreadpool-interface.md)
