---
description: 'Más información sobre: Idebuggerinfo (:: Isdebuggerattached ((método)'
title: IDebuggerInfo::IsDebuggerAttached (Método)
ms.date: 03/30/2017
api_name:
- IDebuggerInfo.IsDebuggerAttached
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IsDebuggerAttached
helpviewer_keywords:
- IDebuggerInfo::IsDebuggerAttached method [.NET Framework hosting]
- IsDebuggerAttached method, IDebuggerInfo interface [.NET Framework hosting]
ms.assetid: 6e21872f-602f-411a-a423-bff5cdf27000
topic_type:
- apiref
ms.openlocfilehash: a17a7f5f1cef1d0c7025f4051e59767ce09ec421
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99709816"
---
# <a name="idebuggerinfoisdebuggerattached-method"></a><span data-ttu-id="5c11f-103">IDebuggerInfo::IsDebuggerAttached (Método)</span><span class="sxs-lookup"><span data-stu-id="5c11f-103">IDebuggerInfo::IsDebuggerAttached Method</span></span>

<span data-ttu-id="5c11f-104">Obtiene un valor que indica si un depurador administrado está asociado a este proceso.</span><span class="sxs-lookup"><span data-stu-id="5c11f-104">Gets a value that indicates whether a managed debugger is attached to this process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5c11f-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="5c11f-105">Syntax</span></span>  
  
```cpp  
HRESULT IsDebuggerAttached (  
    [out] BOOL *pbAttached  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="5c11f-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="5c11f-106">Parameters</span></span>  

 `pbAttached`  
 <span data-ttu-id="5c11f-107">enuncia Un puntero a un valor que es `true` si un depurador administrado está asociado al proceso; de lo contrario, `false` .</span><span class="sxs-lookup"><span data-stu-id="5c11f-107">[out] A pointer to a value that is `true` if a managed debugger is attached to the process; otherwise, `false`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5c11f-108">Requisitos</span><span class="sxs-lookup"><span data-stu-id="5c11f-108">Requirements</span></span>  

 <span data-ttu-id="5c11f-109">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5c11f-109">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5c11f-110">**Encabezado:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="5c11f-110">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="5c11f-111">**Biblioteca:** Se incluye como un recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="5c11f-111">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="5c11f-112">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5c11f-112">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5c11f-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="5c11f-113">See also</span></span>

- [<span data-ttu-id="5c11f-114">IDebuggerInfo (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="5c11f-114">IDebuggerInfo Interface</span></span>](idebuggerinfo-interface.md)
