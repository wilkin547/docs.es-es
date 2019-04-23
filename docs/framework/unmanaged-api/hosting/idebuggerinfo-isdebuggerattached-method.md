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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 0708a3b501a99b5f71be5ba4c6cc4ea2b754d12a
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59191346"
---
# <a name="idebuggerinfoisdebuggerattached-method"></a><span data-ttu-id="9592f-102">IDebuggerInfo::IsDebuggerAttached (Método)</span><span class="sxs-lookup"><span data-stu-id="9592f-102">IDebuggerInfo::IsDebuggerAttached Method</span></span>
<span data-ttu-id="9592f-103">Obtiene un valor que indica si un depurador administrado está asociado a este proceso.</span><span class="sxs-lookup"><span data-stu-id="9592f-103">Gets a value that indicates whether a managed debugger is attached to this process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9592f-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="9592f-104">Syntax</span></span>  
  
```  
HRESULT IsDebuggerAttached (  
    [out] BOOL *pbAttached  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="9592f-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="9592f-105">Parameters</span></span>  
 `pbAttached`  
 <span data-ttu-id="9592f-106">[out] Un puntero a un valor que es `true` si un depurador administrado está asociado al proceso; de lo contrario, `false`.</span><span class="sxs-lookup"><span data-stu-id="9592f-106">[out] A pointer to a value that is `true` if a managed debugger is attached to the process; otherwise, `false`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9592f-107">Requisitos</span><span class="sxs-lookup"><span data-stu-id="9592f-107">Requirements</span></span>  
 <span data-ttu-id="9592f-108">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9592f-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9592f-109">**Encabezado**: MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="9592f-109">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="9592f-110">**Biblioteca:** Incluye como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="9592f-110">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="9592f-111">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9592f-111">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9592f-112">Vea también</span><span class="sxs-lookup"><span data-stu-id="9592f-112">See also</span></span>

- [<span data-ttu-id="9592f-113">IDebuggerInfo (interfaz)</span><span class="sxs-lookup"><span data-stu-id="9592f-113">IDebuggerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/idebuggerinfo-interface.md)
