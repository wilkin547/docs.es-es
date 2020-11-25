---
title: ICorThreadpool::CorCreateTimer (Método)
ms.date: 03/30/2017
api_name:
- ICorThreadpool.CorCreateTimer
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorCreateTimer
helpviewer_keywords:
- CorCreateTimer method [.NET Framework hosting]
- ICorThreadpool::CorCreateTimer method [.NET Framework hosting]
ms.assetid: 0d56ef25-30f1-4499-8a1f-76e7654ec614
topic_type:
- apiref
ms.openlocfilehash: 3eac575e18c7371754401da6498d85ba7ed6c8cf
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95717625"
---
# <a name="icorthreadpoolcorcreatetimer-method"></a><span data-ttu-id="0fc5a-102">ICorThreadpool::CorCreateTimer (Método)</span><span class="sxs-lookup"><span data-stu-id="0fc5a-102">ICorThreadpool::CorCreateTimer Method</span></span>

<span data-ttu-id="0fc5a-103">Este método es compatible con la infraestructura de .NET Framework y no está diseñado para utilizarse directamente desde el código.</span><span class="sxs-lookup"><span data-stu-id="0fc5a-103">This method supports the .NET Framework infrastructure and is not intended to be used directly from your code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0fc5a-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="0fc5a-104">Syntax</span></span>  
  
```cpp  
HRESULT CorCreateTimer (  
    [in]  HANDLE*             phNewTimer,  
    [in]  WAITORTIMERCALLBACK Callback,  
    [in]  PVOID               Parameter,  
    [in]  DWORD               DueTime,  
    [in]  DWORD               Period,  
    [out] BOOL*               result  
);  
```  
  
## <a name="requirements"></a><span data-ttu-id="0fc5a-105">Requisitos</span><span class="sxs-lookup"><span data-stu-id="0fc5a-105">Requirements</span></span>  

 <span data-ttu-id="0fc5a-106">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0fc5a-106">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0fc5a-107">**Encabezado:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="0fc5a-107">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="0fc5a-108">**Biblioteca:** Se incluye como un recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="0fc5a-108">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="0fc5a-109">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0fc5a-109">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0fc5a-110">Consulte también</span><span class="sxs-lookup"><span data-stu-id="0fc5a-110">See also</span></span>

- [<span data-ttu-id="0fc5a-111">ICorThreadpool (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="0fc5a-111">ICorThreadpool Interface</span></span>](icorthreadpool-interface.md)
