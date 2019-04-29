---
title: INotifySink2::OnSyncCallExit (Método)
ms.date: 03/30/2017
api_name:
- INotifySink2.OnSyncCallExit
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- INotifySink2::OnSyncCallExit
helpviewer_keywords:
- INotifySink2::OnSyncCallExit method [.NET Framework debugging]
- OnSyncCallExit method [.NET Framework debugging]
ms.assetid: d9d7600e-a8f5-443a-96de-67d26e130f2d
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 9144ab7fc74bdb5b980b4ff1e1a903653bd056f6
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61940379"
---
# <a name="inotifysink2onsynccallexit-method"></a><span data-ttu-id="a3c8d-102">INotifySink2::OnSyncCallExit (Método)</span><span class="sxs-lookup"><span data-stu-id="a3c8d-102">INotifySink2::OnSyncCallExit Method</span></span>
<span data-ttu-id="a3c8d-103">Se invoca cuando se sale de una llamada.</span><span class="sxs-lookup"><span data-stu-id="a3c8d-103">Gets invoked when exiting a call.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a3c8d-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="a3c8d-104">Syntax</span></span>  
  
```  
HRESULT OnSyncCallExit  
(  
    [in]  CALL_ID   in_CallID,  
    [out, size_is(, *out_pBufferSize)] BYTE**  out_ppBuffer,  
    [out] DWORD*    out_pBufferSize  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a3c8d-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="a3c8d-105">Parameters</span></span>  
 `in_CallID`  
 <span data-ttu-id="a3c8d-106">[in] Identificador de la llamada está saliendo.</span><span class="sxs-lookup"><span data-stu-id="a3c8d-106">[in] ID of the call being exited.</span></span> <span data-ttu-id="a3c8d-107">Consulte [CALL_ID (estructura)](../../../../docs/framework/unmanaged-api/diagnostics/call-id-structure.md).</span><span class="sxs-lookup"><span data-stu-id="a3c8d-107">See [CALL_ID Structure](../../../../docs/framework/unmanaged-api/diagnostics/call-id-structure.md).</span></span>  
  
 `out_ppBuffer`  
 <span data-ttu-id="a3c8d-108">[out] Búfer de la llamada.</span><span class="sxs-lookup"><span data-stu-id="a3c8d-108">[out] Call buffer.</span></span>  
  
 `out_pBufferSize`  
 <span data-ttu-id="a3c8d-109">[out] Tamaño del búfer de llamada, en bytes.</span><span class="sxs-lookup"><span data-stu-id="a3c8d-109">[out] Size of the call buffer, in bytes.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="a3c8d-110">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="a3c8d-110">Return Value</span></span>  
 <span data-ttu-id="a3c8d-111">S_OK si el método tiene éxito.</span><span class="sxs-lookup"><span data-stu-id="a3c8d-111">S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a3c8d-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="a3c8d-112">Requirements</span></span>  
 <span data-ttu-id="a3c8d-113">**Encabezado**: ProtocolNotify2.idl</span><span class="sxs-lookup"><span data-stu-id="a3c8d-113">**Header:** ProtocolNotify2.idl</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a3c8d-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="a3c8d-114">See also</span></span>

- [<span data-ttu-id="a3c8d-115">INotifySink2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="a3c8d-115">INotifySink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/inotifysink2-interface.md)
- [<span data-ttu-id="a3c8d-116">INotifySource2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="a3c8d-116">INotifySource2 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/inotifysource2-interface.md)
- [<span data-ttu-id="a3c8d-117">INotifyConnection2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="a3c8d-117">INotifyConnection2 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/inotifyconnection2-interface.md)
