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
ms.openlocfilehash: 03ce49466587d3e214c32e2a5cca89cdd7a72038
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33405232"
---
# <a name="iclrdatatargetgetcurrentthreadid-method"></a><span data-ttu-id="c02a4-102">ICLRDataTarget::GetCurrentThreadID (Método)</span><span class="sxs-lookup"><span data-stu-id="c02a4-102">ICLRDataTarget::GetCurrentThreadID Method</span></span>
<span data-ttu-id="c02a4-103">Obtiene el identificador de sistema operativo para el subproceso actual.</span><span class="sxs-lookup"><span data-stu-id="c02a4-103">Gets the operating system identifier for the current thread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c02a4-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="c02a4-104">Syntax</span></span>  
  
```  
HRESULT GetCurrentThreadID (  
    [out] ULONG32    *threadID  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="c02a4-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="c02a4-105">Parameters</span></span>  
 `threadID`  
 <span data-ttu-id="c02a4-106">[out] Un puntero al identificador de sistema operativo del subproceso actual para el proceso de destino.</span><span class="sxs-lookup"><span data-stu-id="c02a4-106">[out] A pointer to the operating system identifier of the current thread for the target process.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c02a4-107">Comentarios</span><span class="sxs-lookup"><span data-stu-id="c02a4-107">Remarks</span></span>  
 <span data-ttu-id="c02a4-108">Si no hay ningún subproceso actual durante el proceso de destino, el `GetCurrentThreadID` método puede producir un error.</span><span class="sxs-lookup"><span data-stu-id="c02a4-108">If there is no current thread for the target process, the `GetCurrentThreadID` method may fail.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c02a4-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="c02a4-109">Requirements</span></span>  
 <span data-ttu-id="c02a4-110">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c02a4-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c02a4-111">**Encabezado:** ClrData.idl, ClrData.h</span><span class="sxs-lookup"><span data-stu-id="c02a4-111">**Header:** ClrData.idl, ClrData.h</span></span>  
  
 <span data-ttu-id="c02a4-112">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c02a4-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c02a4-113">**Versiones de .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c02a4-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c02a4-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="c02a4-114">See Also</span></span>  
 [<span data-ttu-id="c02a4-115">ICLRDataTarget (interfaz)</span><span class="sxs-lookup"><span data-stu-id="c02a4-115">ICLRDataTarget Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget-interface.md)
