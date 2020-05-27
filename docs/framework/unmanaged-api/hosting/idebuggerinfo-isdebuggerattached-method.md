---
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
ms.openlocfilehash: 95b7a2f6d35104c3353853549dacc783355feb5b
ms.sourcegitcommit: d223616e7e6fe2139079052e6fcbe25413fb9900
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/22/2020
ms.locfileid: "83805336"
---
# <a name="idebuggerinfoisdebuggerattached-method"></a><span data-ttu-id="ea1f4-102">IDebuggerInfo::IsDebuggerAttached (Método)</span><span class="sxs-lookup"><span data-stu-id="ea1f4-102">IDebuggerInfo::IsDebuggerAttached Method</span></span>
<span data-ttu-id="ea1f4-103">Obtiene un valor que indica si un depurador administrado está asociado a este proceso.</span><span class="sxs-lookup"><span data-stu-id="ea1f4-103">Gets a value that indicates whether a managed debugger is attached to this process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ea1f4-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="ea1f4-104">Syntax</span></span>  
  
```cpp  
HRESULT IsDebuggerAttached (  
    [out] BOOL *pbAttached  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ea1f4-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="ea1f4-105">Parameters</span></span>  
 `pbAttached`  
 <span data-ttu-id="ea1f4-106">enuncia Un puntero a un valor que es `true` si un depurador administrado está asociado al proceso; de lo contrario, `false` .</span><span class="sxs-lookup"><span data-stu-id="ea1f4-106">[out] A pointer to a value that is `true` if a managed debugger is attached to the process; otherwise, `false`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ea1f4-107">Requisitos</span><span class="sxs-lookup"><span data-stu-id="ea1f4-107">Requirements</span></span>  
 <span data-ttu-id="ea1f4-108">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ea1f4-108">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ea1f4-109">**Encabezado:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="ea1f4-109">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="ea1f4-110">**Biblioteca:** Se incluye como recurso en MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="ea1f4-110">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="ea1f4-111">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ea1f4-111">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ea1f4-112">Consulte también</span><span class="sxs-lookup"><span data-stu-id="ea1f4-112">See also</span></span>

- [<span data-ttu-id="ea1f4-113">IDebuggerInfo (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="ea1f4-113">IDebuggerInfo Interface</span></span>](idebuggerinfo-interface.md)
