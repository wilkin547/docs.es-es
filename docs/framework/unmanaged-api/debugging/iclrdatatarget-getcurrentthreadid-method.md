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
ms.openlocfilehash: 35515d7c2b82ec2c42461406363964e0b60eb243
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/28/2020
ms.locfileid: "76785469"
---
# <a name="iclrdatatargetgetcurrentthreadid-method"></a><span data-ttu-id="228fa-102">ICLRDataTarget::GetCurrentThreadID (Método)</span><span class="sxs-lookup"><span data-stu-id="228fa-102">ICLRDataTarget::GetCurrentThreadID Method</span></span>
<span data-ttu-id="228fa-103">Obtiene el identificador del sistema operativo para el subproceso actual.</span><span class="sxs-lookup"><span data-stu-id="228fa-103">Gets the operating system identifier for the current thread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="228fa-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="228fa-104">Syntax</span></span>  
  
```cpp  
HRESULT GetCurrentThreadID (  
    [out] ULONG32    *threadID  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="228fa-105">Parameters</span><span class="sxs-lookup"><span data-stu-id="228fa-105">Parameters</span></span>  
 `threadID`  
 <span data-ttu-id="228fa-106">enuncia Puntero al identificador del sistema operativo del subproceso actual para el proceso de destino.</span><span class="sxs-lookup"><span data-stu-id="228fa-106">[out] A pointer to the operating system identifier of the current thread for the target process.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="228fa-107">Notas</span><span class="sxs-lookup"><span data-stu-id="228fa-107">Remarks</span></span>  
 <span data-ttu-id="228fa-108">Si no hay ningún subproceso actual para el proceso de destino, se puede producir un error en el método `GetCurrentThreadID`.</span><span class="sxs-lookup"><span data-stu-id="228fa-108">If there is no current thread for the target process, the `GetCurrentThreadID` method may fail.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="228fa-109">Requisitos de</span><span class="sxs-lookup"><span data-stu-id="228fa-109">Requirements</span></span>  
 <span data-ttu-id="228fa-110">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="228fa-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="228fa-111">**Encabezado:** ClrData. idl, ClrData. h</span><span class="sxs-lookup"><span data-stu-id="228fa-111">**Header:** ClrData.idl, ClrData.h</span></span>  
  
 <span data-ttu-id="228fa-112">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="228fa-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="228fa-113">**.NET Framework versiones:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="228fa-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="228fa-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="228fa-114">See also</span></span>

- [<span data-ttu-id="228fa-115">ICLRDataTarget (interfaz)</span><span class="sxs-lookup"><span data-stu-id="228fa-115">ICLRDataTarget Interface</span></span>](iclrdatatarget-interface.md)
