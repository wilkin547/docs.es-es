---
description: 'Más información sobre: INotifySink2:: OnSyncCallOut ((método)'
title: INotifySink2::OnSyncCallOut (Método)
ms.date: 03/30/2017
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
ms.openlocfilehash: 03028b138a7d95c618ae20530f66aa692d314cab
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99800245"
---
# <a name="inotifysink2onsynccallout-method"></a><span data-ttu-id="038ef-103">INotifySink2::OnSyncCallOut (Método)</span><span class="sxs-lookup"><span data-stu-id="038ef-103">INotifySink2::OnSyncCallOut Method</span></span>

<span data-ttu-id="038ef-104">Se invoca cuando se realiza una llamada.</span><span class="sxs-lookup"><span data-stu-id="038ef-104">Gets invoked when a call is out.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="038ef-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="038ef-105">Syntax</span></span>  
  
```cpp  
HRESULT OnSyncCallOut  
(  
    [in]  CALL_ID  in_CallID,  
    [out, size_is(, *out_pBufferSize)] BYTE**  out_ppBuffer,  
    [out] DWORD*   out_pBufferSize  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="038ef-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="038ef-106">Parameters</span></span>  

 `in_CallID`  
 <span data-ttu-id="038ef-107">de IDENTIFICADOR de la llamada que está fuera. Vea [estructura de CALL_ID](call-id-structure.md).</span><span class="sxs-lookup"><span data-stu-id="038ef-107">[in] ID of the call that is out. See [CALL_ID Structure](call-id-structure.md).</span></span>  
  
 `out_ppBuffer`  
 <span data-ttu-id="038ef-108">enuncia Búfer de llamadas.</span><span class="sxs-lookup"><span data-stu-id="038ef-108">[out] Call buffer.</span></span>  
  
 `out_pBufferSize`  
 <span data-ttu-id="038ef-109">enuncia Tamaño del búfer de llamadas, en bytes.</span><span class="sxs-lookup"><span data-stu-id="038ef-109">[out] Size of the call buffer, in bytes.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="038ef-110">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="038ef-110">Return Value</span></span>  

 <span data-ttu-id="038ef-111">S_OK si el método se ejecuta correctamente.</span><span class="sxs-lookup"><span data-stu-id="038ef-111">S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="038ef-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="038ef-112">Requirements</span></span>  

 <span data-ttu-id="038ef-113">**Encabezado:** ProtocolNotify2. idl</span><span class="sxs-lookup"><span data-stu-id="038ef-113">**Header:** ProtocolNotify2.idl</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="038ef-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="038ef-114">See also</span></span>

- [<span data-ttu-id="038ef-115">INotifySink2 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="038ef-115">INotifySink2 Interface</span></span>](inotifysink2-interface.md)
- [<span data-ttu-id="038ef-116">INotifySource2 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="038ef-116">INotifySource2 Interface</span></span>](inotifysource2-interface.md)
- [<span data-ttu-id="038ef-117">INotifyConnection2 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="038ef-117">INotifyConnection2 Interface</span></span>](inotifyconnection2-interface.md)
