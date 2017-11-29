---
title: "INotifySink2::OnSyncCallExit (Método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: INotifySink2.OnSyncCallExit
api_location: diasymreader.dll
api_type: COM
f1_keywords: INotifySink2::OnSyncCallExit
helpviewer_keywords:
- INotifySink2::OnSyncCallExit method [.NET Framework debugging]
- OnSyncCallExit method [.NET Framework debugging]
ms.assetid: d9d7600e-a8f5-443a-96de-67d26e130f2d
topic_type: apiref
caps.latest.revision: "7"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 8034717826316fe8ae4679c19e5002ca2c22c6fb
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="inotifysink2onsynccallexit-method"></a><span data-ttu-id="caa94-102">INotifySink2::OnSyncCallExit (Método)</span><span class="sxs-lookup"><span data-stu-id="caa94-102">INotifySink2::OnSyncCallExit Method</span></span>
<span data-ttu-id="caa94-103">Se invoca cuando se sale de una llamada.</span><span class="sxs-lookup"><span data-stu-id="caa94-103">Gets invoked when exiting a call.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="caa94-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="caa94-104">Syntax</span></span>  
  
```  
HRESULT OnSyncCallExit  
(  
    [in]  CALL_ID   in_CallID,  
    [out, size_is(, *out_pBufferSize)] BYTE**  out_ppBuffer,  
    [out] DWORD*    out_pBufferSize  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="caa94-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="caa94-105">Parameters</span></span>  
 `in_CallID`  
 <span data-ttu-id="caa94-106">[in] Identificador de la llamada está saliendo.</span><span class="sxs-lookup"><span data-stu-id="caa94-106">[in] ID of the call being exited.</span></span> <span data-ttu-id="caa94-107">Vea [CALL_ID (estructura)](../../../../docs/framework/unmanaged-api/diagnostics/call-id-structure.md).</span><span class="sxs-lookup"><span data-stu-id="caa94-107">See [CALL_ID Structure](../../../../docs/framework/unmanaged-api/diagnostics/call-id-structure.md).</span></span>  
  
 `out_ppBuffer`  
 <span data-ttu-id="caa94-108">[out] Búfer de la llamada.</span><span class="sxs-lookup"><span data-stu-id="caa94-108">[out] Call buffer.</span></span>  
  
 `out_pBufferSize`  
 <span data-ttu-id="caa94-109">[out] Tamaño del búfer de llamada, en bytes.</span><span class="sxs-lookup"><span data-stu-id="caa94-109">[out] Size of the call buffer, in bytes.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="caa94-110">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="caa94-110">Return Value</span></span>  
 <span data-ttu-id="caa94-111">S_OK si el método tiene éxito.</span><span class="sxs-lookup"><span data-stu-id="caa94-111">S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="caa94-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="caa94-112">Requirements</span></span>  
 <span data-ttu-id="caa94-113">**Encabezado:** ProtocolNotify2.idl</span><span class="sxs-lookup"><span data-stu-id="caa94-113">**Header:** ProtocolNotify2.idl</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="caa94-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="caa94-114">See Also</span></span>  
 [<span data-ttu-id="caa94-115">INotifySink2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="caa94-115">INotifySink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/inotifysink2-interface.md)  
 [<span data-ttu-id="caa94-116">INotifySource2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="caa94-116">INotifySource2 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/inotifysource2-interface.md)  
 [<span data-ttu-id="caa94-117">INotifyConnection2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="caa94-117">INotifyConnection2 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/inotifyconnection2-interface.md)
