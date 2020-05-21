---
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
ms.openlocfilehash: c3ebe0bcd546feeeb0aa8c962f2b4c8b0562cb6f
ms.sourcegitcommit: c76c8b2c39ed2f0eee422b61a2ab4c05ca7771fa
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/21/2020
ms.locfileid: "83760451"
---
# <a name="icorthreadpoolcorbindiocompletioncallback-method"></a><span data-ttu-id="5a6bb-102">ICorThreadpool::CorBindIoCompletionCallback (Método)</span><span class="sxs-lookup"><span data-stu-id="5a6bb-102">ICorThreadpool::CorBindIoCompletionCallback Method</span></span>
<span data-ttu-id="5a6bb-103">Este método es compatible con la infraestructura de .NET Framework y no está diseñado para utilizarse directamente desde el código.</span><span class="sxs-lookup"><span data-stu-id="5a6bb-103">This method supports the .NET Framework infrastructure and is not intended to be used directly from your code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5a6bb-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="5a6bb-104">Syntax</span></span>  
  
```cpp  
HRESULT CorBindIoCompletionCallback (  
    [in] HANDLE                          fileHandle,  
    [in] LPOVERLAPPED_COMPLETION_ROUTINE callback  
);  
```  
  
## <a name="requirements"></a><span data-ttu-id="5a6bb-105">Requisitos</span><span class="sxs-lookup"><span data-stu-id="5a6bb-105">Requirements</span></span>  
 <span data-ttu-id="5a6bb-106">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5a6bb-106">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5a6bb-107">**Encabezado:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="5a6bb-107">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="5a6bb-108">**Biblioteca:** Se incluye como recurso en MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="5a6bb-108">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="5a6bb-109">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5a6bb-109">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5a6bb-110">Consulte también:</span><span class="sxs-lookup"><span data-stu-id="5a6bb-110">See also</span></span>

- [<span data-ttu-id="5a6bb-111">ICorThreadpool (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="5a6bb-111">ICorThreadpool Interface</span></span>](icorthreadpool-interface.md)
