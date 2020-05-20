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
ms.openlocfilehash: f81ef3f5959e279b3fbbd94d6c5e8a2d86a38e7f
ms.sourcegitcommit: 7b1497c1927cb449cefd313bc5126ae37df30746
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/16/2020
ms.locfileid: "83442025"
---
# <a name="inotifysink2onsynccallexit-method"></a><span data-ttu-id="1dea2-102">INotifySink2::OnSyncCallExit (Método)</span><span class="sxs-lookup"><span data-stu-id="1dea2-102">INotifySink2::OnSyncCallExit Method</span></span>
<span data-ttu-id="1dea2-103">Se invoca cuando se sale de una llamada.</span><span class="sxs-lookup"><span data-stu-id="1dea2-103">Gets invoked when exiting a call.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1dea2-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="1dea2-104">Syntax</span></span>  
  
```cpp  
HRESULT OnSyncCallExit  
(  
    [in]  CALL_ID   in_CallID,  
    [out, size_is(, *out_pBufferSize)] BYTE**  out_ppBuffer,  
    [out] DWORD*    out_pBufferSize  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="1dea2-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="1dea2-105">Parameters</span></span>  
 `in_CallID`  
 <span data-ttu-id="1dea2-106">de IDENTIFICADOR de la llamada que se va a salir.</span><span class="sxs-lookup"><span data-stu-id="1dea2-106">[in] ID of the call being exited.</span></span> <span data-ttu-id="1dea2-107">Vea [estructura de CALL_ID](call-id-structure.md).</span><span class="sxs-lookup"><span data-stu-id="1dea2-107">See [CALL_ID Structure](call-id-structure.md).</span></span>  
  
 `out_ppBuffer`  
 <span data-ttu-id="1dea2-108">enuncia Búfer de llamadas.</span><span class="sxs-lookup"><span data-stu-id="1dea2-108">[out] Call buffer.</span></span>  
  
 `out_pBufferSize`  
 <span data-ttu-id="1dea2-109">enuncia Tamaño del búfer de llamadas, en bytes.</span><span class="sxs-lookup"><span data-stu-id="1dea2-109">[out] Size of the call buffer, in bytes.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="1dea2-110">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="1dea2-110">Return Value</span></span>  
 <span data-ttu-id="1dea2-111">S_OK si el método se ejecuta correctamente.</span><span class="sxs-lookup"><span data-stu-id="1dea2-111">S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1dea2-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="1dea2-112">Requirements</span></span>  
 <span data-ttu-id="1dea2-113">**Encabezado:** ProtocolNotify2. idl</span><span class="sxs-lookup"><span data-stu-id="1dea2-113">**Header:** ProtocolNotify2.idl</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1dea2-114">Consulta también</span><span class="sxs-lookup"><span data-stu-id="1dea2-114">See also</span></span>

- [<span data-ttu-id="1dea2-115">INotifySink2 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="1dea2-115">INotifySink2 Interface</span></span>](inotifysink2-interface.md)
- [<span data-ttu-id="1dea2-116">INotifySource2 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="1dea2-116">INotifySource2 Interface</span></span>](inotifysource2-interface.md)
- [<span data-ttu-id="1dea2-117">INotifyConnection2 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="1dea2-117">INotifyConnection2 Interface</span></span>](inotifyconnection2-interface.md)
