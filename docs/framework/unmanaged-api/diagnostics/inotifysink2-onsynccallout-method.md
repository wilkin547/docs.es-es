---
title: "INotifySink2::OnSyncCallOut (Método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- INotifySink2.OnSyncCallOut
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- INotifySink2::OnSyncCallOut
helpviewer_keywords:
- INotifySink2::OnSyncCallOut method [.NET Framework debugging]
- OnSyncCallOut method [.NET Framework debugging]
ms.assetid: 97f15656-8677-4079-8553-a1d8603355d6
topic_type:
- apiref
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 484027fe0ab8e5e416059678d2603080ed730be3
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="inotifysink2onsynccallout-method"></a><span data-ttu-id="bf56c-102">INotifySink2::OnSyncCallOut (Método)</span><span class="sxs-lookup"><span data-stu-id="bf56c-102">INotifySink2::OnSyncCallOut Method</span></span>
<span data-ttu-id="bf56c-103">Se invoca cuando una llamada está inactiva.</span><span class="sxs-lookup"><span data-stu-id="bf56c-103">Gets invoked when a call is out.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bf56c-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="bf56c-104">Syntax</span></span>  
  
```  
HRESULT OnSyncCallOut  
(  
    [in]  CALL_ID  in_CallID,  
    [out, size_is(, *out_pBufferSize)] BYTE**  out_ppBuffer,  
    [out] DWORD*   out_pBufferSize  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="bf56c-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="bf56c-105">Parameters</span></span>  
 `in_CallID`  
 <span data-ttu-id="bf56c-106">[in] Identificador de la llamada que está inactiva. Vea [CALL_ID (estructura)](../../../../docs/framework/unmanaged-api/diagnostics/call-id-structure.md).</span><span class="sxs-lookup"><span data-stu-id="bf56c-106">[in] ID of the call that is out. See [CALL_ID Structure](../../../../docs/framework/unmanaged-api/diagnostics/call-id-structure.md).</span></span>  
  
 `out_ppBuffer`  
 <span data-ttu-id="bf56c-107">[out] Búfer de la llamada.</span><span class="sxs-lookup"><span data-stu-id="bf56c-107">[out] Call buffer.</span></span>  
  
 `out_pBufferSize`  
 <span data-ttu-id="bf56c-108">[out] Tamaño del búfer de llamada, en bytes.</span><span class="sxs-lookup"><span data-stu-id="bf56c-108">[out] Size of the call buffer, in bytes.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="bf56c-109">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="bf56c-109">Return Value</span></span>  
 <span data-ttu-id="bf56c-110">S_OK si el método tiene éxito.</span><span class="sxs-lookup"><span data-stu-id="bf56c-110">S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="bf56c-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="bf56c-111">Requirements</span></span>  
 <span data-ttu-id="bf56c-112">**Encabezado:** ProtocolNotify2.idl</span><span class="sxs-lookup"><span data-stu-id="bf56c-112">**Header:** ProtocolNotify2.idl</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bf56c-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="bf56c-113">See Also</span></span>  
 [<span data-ttu-id="bf56c-114">INotifySink2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="bf56c-114">INotifySink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/inotifysink2-interface.md)  
 [<span data-ttu-id="bf56c-115">INotifySource2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="bf56c-115">INotifySource2 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/inotifysource2-interface.md)  
 [<span data-ttu-id="bf56c-116">INotifyConnection2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="bf56c-116">INotifyConnection2 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/inotifyconnection2-interface.md)
