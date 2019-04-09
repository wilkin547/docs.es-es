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
ms.openlocfilehash: 9687f6139d67a2387091367c2c72167e03be4eee
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59080662"
---
# <a name="iclrdatatargetgetcurrentthreadid-method"></a><span data-ttu-id="6443e-102">ICLRDataTarget::GetCurrentThreadID (Método)</span><span class="sxs-lookup"><span data-stu-id="6443e-102">ICLRDataTarget::GetCurrentThreadID Method</span></span>
<span data-ttu-id="6443e-103">Obtiene el identificador de sistema operativo para el subproceso actual.</span><span class="sxs-lookup"><span data-stu-id="6443e-103">Gets the operating system identifier for the current thread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6443e-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="6443e-104">Syntax</span></span>  
  
```  
HRESULT GetCurrentThreadID (  
    [out] ULONG32    *threadID  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="6443e-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="6443e-105">Parameters</span></span>  
 `threadID`  
 <span data-ttu-id="6443e-106">[out] Un puntero al identificador del sistema operativo del subproceso actual para el proceso de destino.</span><span class="sxs-lookup"><span data-stu-id="6443e-106">[out] A pointer to the operating system identifier of the current thread for the target process.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="6443e-107">Comentarios</span><span class="sxs-lookup"><span data-stu-id="6443e-107">Remarks</span></span>  
 <span data-ttu-id="6443e-108">Si no hay ningún subproceso actual durante el proceso de destino, el `GetCurrentThreadID` método puede producir un error.</span><span class="sxs-lookup"><span data-stu-id="6443e-108">If there is no current thread for the target process, the `GetCurrentThreadID` method may fail.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6443e-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="6443e-109">Requirements</span></span>  
 <span data-ttu-id="6443e-110">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6443e-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6443e-111">**Encabezado**: ClrData.idl, ClrData.h</span><span class="sxs-lookup"><span data-stu-id="6443e-111">**Header:** ClrData.idl, ClrData.h</span></span>  
  
 <span data-ttu-id="6443e-112">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="6443e-112">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="6443e-113">Versiones de .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="6443e-113">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="6443e-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="6443e-114">See also</span></span>

- [<span data-ttu-id="6443e-115">ICLRDataTarget (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="6443e-115">ICLRDataTarget Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget-interface.md)
