---
title: "INotifySink2::OnSyncCallReturn (Método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: INotifySink2.OnSyncCallReturn
api_location: diasymreader.dll
api_type: COM
f1_keywords: INotifySink2::OnSyncCallReturn
helpviewer_keywords:
- OnSyncCallReturn method [.NET Framework debugging]
- INotifySink2::OnSyncCallReturn method [.NET Framework debugging]
ms.assetid: c1bda761-6292-4750-a14b-7d5db8f33456
topic_type: apiref
caps.latest.revision: "7"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 8f09d9ced41ecfe933a22ac41ee7f2065f1afcc6
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="inotifysink2onsynccallreturn-method"></a><span data-ttu-id="3b825-102">INotifySink2::OnSyncCallReturn (Método)</span><span class="sxs-lookup"><span data-stu-id="3b825-102">INotifySink2::OnSyncCallReturn Method</span></span>
<span data-ttu-id="3b825-103">Se invoca cuando una llamada devuelve.</span><span class="sxs-lookup"><span data-stu-id="3b825-103">Gets invoked when a call returns.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3b825-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="3b825-104">Syntax</span></span>  
  
```  
HRESULT OnSyncCallReturn  
(  
    [in]  CALL_ID   in_CallID,  
    [in, size_is(in_BufferSize)] BYTE*  in_pBuffer,  
    [in]  DWORD     in_BufferSize  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="3b825-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="3b825-105">Parameters</span></span>  
 `in_CallID`  
 <span data-ttu-id="3b825-106">[in] Identificador de la llamada que se devuelven desde.</span><span class="sxs-lookup"><span data-stu-id="3b825-106">[in] ID of the call being returned from.</span></span> <span data-ttu-id="3b825-107">Vea [CALL_ID (estructura)](../../../../docs/framework/unmanaged-api/diagnostics/call-id-structure.md).</span><span class="sxs-lookup"><span data-stu-id="3b825-107">See [CALL_ID Structure](../../../../docs/framework/unmanaged-api/diagnostics/call-id-structure.md).</span></span>  
  
 `in_pBuffer`  
 <span data-ttu-id="3b825-108">[in] Búfer de la llamada.</span><span class="sxs-lookup"><span data-stu-id="3b825-108">[in] Call buffer.</span></span>  
  
 `in_BufferSize`  
 <span data-ttu-id="3b825-109">[in] Tamaño del búfer de llamada, en bytes.</span><span class="sxs-lookup"><span data-stu-id="3b825-109">[in] Size of the call buffer, in bytes.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="3b825-110">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="3b825-110">Return Value</span></span>  
 <span data-ttu-id="3b825-111">S_OK si el método tiene éxito.</span><span class="sxs-lookup"><span data-stu-id="3b825-111">S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3b825-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="3b825-112">Requirements</span></span>  
 <span data-ttu-id="3b825-113">**Encabezado:** ProtocolNotify2.idl</span><span class="sxs-lookup"><span data-stu-id="3b825-113">**Header:** ProtocolNotify2.idl</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3b825-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="3b825-114">See Also</span></span>  
 [<span data-ttu-id="3b825-115">INotifySink2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="3b825-115">INotifySink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/inotifysink2-interface.md)  
 [<span data-ttu-id="3b825-116">INotifySource2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="3b825-116">INotifySource2 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/inotifysource2-interface.md)  
 [<span data-ttu-id="3b825-117">INotifyConnection2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="3b825-117">INotifyConnection2 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/inotifyconnection2-interface.md)
