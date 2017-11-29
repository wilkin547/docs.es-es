---
title: "IDebuggerInfo::IsDebuggerAttached (Método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IDebuggerInfo.IsDebuggerAttached
api_location: mscoree.dll
api_type: COM
f1_keywords: IsDebuggerAttached
helpviewer_keywords:
- IDebuggerInfo::IsDebuggerAttached method [.NET Framework hosting]
- IsDebuggerAttached method, IDebuggerInfo interface [.NET Framework hosting]
ms.assetid: 6e21872f-602f-411a-a423-bff5cdf27000
topic_type: apiref
caps.latest.revision: "6"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: a6e1f11939bc4f11b1fb49dc44f129176143fbca
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="idebuggerinfoisdebuggerattached-method"></a><span data-ttu-id="13a8b-102">IDebuggerInfo::IsDebuggerAttached (Método)</span><span class="sxs-lookup"><span data-stu-id="13a8b-102">IDebuggerInfo::IsDebuggerAttached Method</span></span>
<span data-ttu-id="13a8b-103">Obtiene un valor que indica si un depurador administrado está asociado a este proceso.</span><span class="sxs-lookup"><span data-stu-id="13a8b-103">Gets a value that indicates whether a managed debugger is attached to this process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="13a8b-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="13a8b-104">Syntax</span></span>  
  
```  
HRESULT IsDebuggerAttached (  
    [out] BOOL *pbAttached  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="13a8b-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="13a8b-105">Parameters</span></span>  
 `pbAttached`  
 <span data-ttu-id="13a8b-106">[out] Un puntero a un valor que es `true` si un depurador administrado está asociado al proceso; en caso contrario, `false`.</span><span class="sxs-lookup"><span data-stu-id="13a8b-106">[out] A pointer to a value that is `true` if a managed debugger is attached to the process; otherwise, `false`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="13a8b-107">Requisitos</span><span class="sxs-lookup"><span data-stu-id="13a8b-107">Requirements</span></span>  
 <span data-ttu-id="13a8b-108">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="13a8b-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="13a8b-109">**Encabezado:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="13a8b-109">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="13a8b-110">**Biblioteca:** incluye como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="13a8b-110">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="13a8b-111">**Versiones de .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="13a8b-111">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="13a8b-112">Vea también</span><span class="sxs-lookup"><span data-stu-id="13a8b-112">See Also</span></span>  
 [<span data-ttu-id="13a8b-113">IDebuggerInfo (interfaz)</span><span class="sxs-lookup"><span data-stu-id="13a8b-113">IDebuggerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/idebuggerinfo-interface.md)
