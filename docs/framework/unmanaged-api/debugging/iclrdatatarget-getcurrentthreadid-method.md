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
ms.openlocfilehash: 3a355822710394e9351f10be78dea283e2e9907c
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95703596"
---
# <a name="iclrdatatargetgetcurrentthreadid-method"></a><span data-ttu-id="fc35a-102">ICLRDataTarget::GetCurrentThreadID (Método)</span><span class="sxs-lookup"><span data-stu-id="fc35a-102">ICLRDataTarget::GetCurrentThreadID Method</span></span>

<span data-ttu-id="fc35a-103">Obtiene el identificador del sistema operativo para el subproceso actual.</span><span class="sxs-lookup"><span data-stu-id="fc35a-103">Gets the operating system identifier for the current thread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fc35a-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="fc35a-104">Syntax</span></span>  
  
```cpp  
HRESULT GetCurrentThreadID (  
    [out] ULONG32    *threadID  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="fc35a-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="fc35a-105">Parameters</span></span>  

 `threadID`  
 <span data-ttu-id="fc35a-106">enuncia Puntero al identificador del sistema operativo del subproceso actual para el proceso de destino.</span><span class="sxs-lookup"><span data-stu-id="fc35a-106">[out] A pointer to the operating system identifier of the current thread for the target process.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="fc35a-107">Comentarios</span><span class="sxs-lookup"><span data-stu-id="fc35a-107">Remarks</span></span>  

 <span data-ttu-id="fc35a-108">Si no hay ningún subproceso actual para el proceso de destino, se `GetCurrentThreadID` puede producir un error en el método.</span><span class="sxs-lookup"><span data-stu-id="fc35a-108">If there is no current thread for the target process, the `GetCurrentThreadID` method may fail.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fc35a-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="fc35a-109">Requirements</span></span>  

 <span data-ttu-id="fc35a-110">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="fc35a-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fc35a-111">**Encabezado:** ClrData. idl, ClrData. h</span><span class="sxs-lookup"><span data-stu-id="fc35a-111">**Header:** ClrData.idl, ClrData.h</span></span>  
  
 <span data-ttu-id="fc35a-112">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="fc35a-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="fc35a-113">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fc35a-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fc35a-114">Consulte también</span><span class="sxs-lookup"><span data-stu-id="fc35a-114">See also</span></span>

- [<span data-ttu-id="fc35a-115">ICLRDataTarget (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="fc35a-115">ICLRDataTarget Interface</span></span>](iclrdatatarget-interface.md)
