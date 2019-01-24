---
title: INotifySink2::OnSyncCallReturn (Método)
ms.date: 03/30/2017
api_name:
- INotifySink2.OnSyncCallReturn
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- INotifySink2::OnSyncCallReturn
helpviewer_keywords:
- OnSyncCallReturn method [.NET Framework debugging]
- INotifySink2::OnSyncCallReturn method [.NET Framework debugging]
ms.assetid: c1bda761-6292-4750-a14b-7d5db8f33456
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: bc182687b12f5941996c17f4c09da44c49ef815c
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54694911"
---
# <a name="inotifysink2onsynccallreturn-method"></a><span data-ttu-id="bb581-102">INotifySink2::OnSyncCallReturn (Método)</span><span class="sxs-lookup"><span data-stu-id="bb581-102">INotifySink2::OnSyncCallReturn Method</span></span>
<span data-ttu-id="bb581-103">Se invoca cuando se devuelve una llamada.</span><span class="sxs-lookup"><span data-stu-id="bb581-103">Gets invoked when a call returns.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bb581-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="bb581-104">Syntax</span></span>  
  
```  
HRESULT OnSyncCallReturn  
(  
    [in]  CALL_ID   in_CallID,  
    [in, size_is(in_BufferSize)] BYTE*  in_pBuffer,  
    [in]  DWORD     in_BufferSize  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="bb581-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="bb581-105">Parameters</span></span>  
 `in_CallID`  
 <span data-ttu-id="bb581-106">[in] Identificador de la llamada que se devuelven desde.</span><span class="sxs-lookup"><span data-stu-id="bb581-106">[in] ID of the call being returned from.</span></span> <span data-ttu-id="bb581-107">Consulte [CALL_ID (estructura)](../../../../docs/framework/unmanaged-api/diagnostics/call-id-structure.md).</span><span class="sxs-lookup"><span data-stu-id="bb581-107">See [CALL_ID Structure](../../../../docs/framework/unmanaged-api/diagnostics/call-id-structure.md).</span></span>  
  
 `in_pBuffer`  
 <span data-ttu-id="bb581-108">[in] Búfer de la llamada.</span><span class="sxs-lookup"><span data-stu-id="bb581-108">[in] Call buffer.</span></span>  
  
 `in_BufferSize`  
 <span data-ttu-id="bb581-109">[in] Tamaño del búfer de llamada, en bytes.</span><span class="sxs-lookup"><span data-stu-id="bb581-109">[in] Size of the call buffer, in bytes.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="bb581-110">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="bb581-110">Return Value</span></span>  
 <span data-ttu-id="bb581-111">S_OK si el método tiene éxito.</span><span class="sxs-lookup"><span data-stu-id="bb581-111">S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="bb581-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="bb581-112">Requirements</span></span>  
 <span data-ttu-id="bb581-113">**Encabezado**: ProtocolNotify2.idl</span><span class="sxs-lookup"><span data-stu-id="bb581-113">**Header:** ProtocolNotify2.idl</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bb581-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="bb581-114">See also</span></span>
- [<span data-ttu-id="bb581-115">INotifySink2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="bb581-115">INotifySink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/inotifysink2-interface.md)
- [<span data-ttu-id="bb581-116">INotifySource2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="bb581-116">INotifySource2 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/inotifysource2-interface.md)
- [<span data-ttu-id="bb581-117">INotifyConnection2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="bb581-117">INotifyConnection2 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/inotifyconnection2-interface.md)
