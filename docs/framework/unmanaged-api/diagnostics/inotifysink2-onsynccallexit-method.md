---
description: 'Más información sobre: INotifySink2:: Onsynccallexit ((método)'
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
ms.openlocfilehash: 2de55c3b7956576049e4ad65b2cb6fbc69fa84af
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99800271"
---
# <a name="inotifysink2onsynccallexit-method"></a><span data-ttu-id="ccb99-103">INotifySink2::OnSyncCallExit (Método)</span><span class="sxs-lookup"><span data-stu-id="ccb99-103">INotifySink2::OnSyncCallExit Method</span></span>

<span data-ttu-id="ccb99-104">Se invoca cuando se sale de una llamada.</span><span class="sxs-lookup"><span data-stu-id="ccb99-104">Gets invoked when exiting a call.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ccb99-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="ccb99-105">Syntax</span></span>  
  
```cpp  
HRESULT OnSyncCallExit  
(  
    [in]  CALL_ID   in_CallID,  
    [out, size_is(, *out_pBufferSize)] BYTE**  out_ppBuffer,  
    [out] DWORD*    out_pBufferSize  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ccb99-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="ccb99-106">Parameters</span></span>  

 `in_CallID`  
 <span data-ttu-id="ccb99-107">de IDENTIFICADOR de la llamada que se va a salir.</span><span class="sxs-lookup"><span data-stu-id="ccb99-107">[in] ID of the call being exited.</span></span> <span data-ttu-id="ccb99-108">Vea [estructura de CALL_ID](call-id-structure.md).</span><span class="sxs-lookup"><span data-stu-id="ccb99-108">See [CALL_ID Structure](call-id-structure.md).</span></span>  
  
 `out_ppBuffer`  
 <span data-ttu-id="ccb99-109">enuncia Búfer de llamadas.</span><span class="sxs-lookup"><span data-stu-id="ccb99-109">[out] Call buffer.</span></span>  
  
 `out_pBufferSize`  
 <span data-ttu-id="ccb99-110">enuncia Tamaño del búfer de llamadas, en bytes.</span><span class="sxs-lookup"><span data-stu-id="ccb99-110">[out] Size of the call buffer, in bytes.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="ccb99-111">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="ccb99-111">Return Value</span></span>  

 <span data-ttu-id="ccb99-112">S_OK si el método se ejecuta correctamente.</span><span class="sxs-lookup"><span data-stu-id="ccb99-112">S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ccb99-113">Requisitos</span><span class="sxs-lookup"><span data-stu-id="ccb99-113">Requirements</span></span>  

 <span data-ttu-id="ccb99-114">**Encabezado:** ProtocolNotify2. idl</span><span class="sxs-lookup"><span data-stu-id="ccb99-114">**Header:** ProtocolNotify2.idl</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ccb99-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="ccb99-115">See also</span></span>

- [<span data-ttu-id="ccb99-116">INotifySink2 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="ccb99-116">INotifySink2 Interface</span></span>](inotifysink2-interface.md)
- [<span data-ttu-id="ccb99-117">INotifySource2 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="ccb99-117">INotifySource2 Interface</span></span>](inotifysource2-interface.md)
- [<span data-ttu-id="ccb99-118">INotifyConnection2 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="ccb99-118">INotifyConnection2 Interface</span></span>](inotifyconnection2-interface.md)
