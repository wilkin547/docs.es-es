---
title: ICLRDataTarget::GetCurrentThreadID (Método)
ms.date: 03/30/2017
api_name:
- ICLRDataTarget.GetCurrentThreadID
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICLRDataTarget::GetCurrentThreadID
helpviewer_keywords:
- GetCurrentThreadID method, ICLRDataTarget interface [.NET Framework debugging]
- ICLRDataTarget::GetCurrentThreadID method [.NET Framework debugging]
ms.assetid: dc9a0a6c-d592-4fb7-86ed-62684da3b0e1
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 45a409bda8861701e68d3ea1a956a4c35ce88ddd
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/10/2019
ms.locfileid: "67738782"
---
# <a name="iclrdatatargetgetcurrentthreadid-method"></a><span data-ttu-id="e159c-102">ICLRDataTarget::GetCurrentThreadID (Método)</span><span class="sxs-lookup"><span data-stu-id="e159c-102">ICLRDataTarget::GetCurrentThreadID Method</span></span>
<span data-ttu-id="e159c-103">Obtiene el identificador de sistema operativo para el subproceso actual.</span><span class="sxs-lookup"><span data-stu-id="e159c-103">Gets the operating system identifier for the current thread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e159c-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="e159c-104">Syntax</span></span>  
  
```cpp  
HRESULT GetCurrentThreadID (  
    [out] ULONG32    *threadID  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e159c-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="e159c-105">Parameters</span></span>  
 `threadID`  
 <span data-ttu-id="e159c-106">[out] Un puntero al identificador del sistema operativo del subproceso actual para el proceso de destino.</span><span class="sxs-lookup"><span data-stu-id="e159c-106">[out] A pointer to the operating system identifier of the current thread for the target process.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e159c-107">Comentarios</span><span class="sxs-lookup"><span data-stu-id="e159c-107">Remarks</span></span>  
 <span data-ttu-id="e159c-108">Si no hay ningún subproceso actual durante el proceso de destino, el `GetCurrentThreadID` método puede producir un error.</span><span class="sxs-lookup"><span data-stu-id="e159c-108">If there is no current thread for the target process, the `GetCurrentThreadID` method may fail.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e159c-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="e159c-109">Requirements</span></span>  
 <span data-ttu-id="e159c-110">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e159c-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e159c-111">**Encabezado**: ClrData.idl, ClrData.h</span><span class="sxs-lookup"><span data-stu-id="e159c-111">**Header:** ClrData.idl, ClrData.h</span></span>  
  
 <span data-ttu-id="e159c-112">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e159c-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e159c-113">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e159c-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e159c-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="e159c-114">See also</span></span>

- [<span data-ttu-id="e159c-115">ICLRDataTarget (interfaz)</span><span class="sxs-lookup"><span data-stu-id="e159c-115">ICLRDataTarget Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget-interface.md)
