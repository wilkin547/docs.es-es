---
title: "ICorDebugNativeFrame::CanSetIP (Método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- ICorDebugNativeFrame.CanSetIP
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugNativeFrame::CanSetIP
helpviewer_keywords:
- ICorDebugNativeFrame::CanSetIP method [.NET Framework debugging]
- CanSetIP method, ICorDebugNativeFrame interface [.NET Framework debugging]
ms.assetid: 13258ac6-f4e4-4f66-8fc3-f1244417a3c3
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: b87ff9ae71b916a9a1141c2e5fedce7f79fbcd23
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugnativeframecansetip-method"></a><span data-ttu-id="d8322-102">ICorDebugNativeFrame::CanSetIP (Método)</span><span class="sxs-lookup"><span data-stu-id="d8322-102">ICorDebugNativeFrame::CanSetIP Method</span></span>
<span data-ttu-id="d8322-103">Obtiene un valor HRESULT que indica si es seguro establecer el puntero de instrucción (IP) a la ubicación de desplazamiento especificada en el código nativo.</span><span class="sxs-lookup"><span data-stu-id="d8322-103">Gets an HRESULT that indicates whether it is safe to set the instruction pointer (IP) to the specified offset location in native code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d8322-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="d8322-104">Syntax</span></span>  
  
```  
HRESULT CanSetIP (  
    [in] ULONG32            nOffset  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="d8322-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="d8322-105">Parameters</span></span>  
 `nOffset`  
 <span data-ttu-id="d8322-106">[in] El valor deseado para el puntero de instrucción.</span><span class="sxs-lookup"><span data-stu-id="d8322-106">[in] The desired setting for the instruction pointer.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d8322-107">Comentarios</span><span class="sxs-lookup"><span data-stu-id="d8322-107">Remarks</span></span>  
 <span data-ttu-id="d8322-108">Use la `CanSetIP` método antes de llamar a la [ICorDebugNativeFrame:: SetIP](../../../../docs/framework/unmanaged-api/debugging/icordebugnativeframe-setip-method.md) método.</span><span class="sxs-lookup"><span data-stu-id="d8322-108">Use the `CanSetIP` method prior to calling the [ICorDebugNativeFrame::SetIP](../../../../docs/framework/unmanaged-api/debugging/icordebugnativeframe-setip-method.md) method.</span></span> <span data-ttu-id="d8322-109">Si `CanSetIP` devuelve un valor HRESULT distinto de S_OK, todavía se puede llamar `ICorDebugNativeFrame::SetIP`, pero no hay ninguna garantía de que el depurador continuará la ejecución correcta y seguro para la ejecución del código que se está depurando.</span><span class="sxs-lookup"><span data-stu-id="d8322-109">If `CanSetIP` returns any HRESULT other than S_OK, you can still invoke `ICorDebugNativeFrame::SetIP`, but there is no guarantee that the debugger will continue the safe and correct execution of the code being debugged.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d8322-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="d8322-110">Requirements</span></span>  
 <span data-ttu-id="d8322-111">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d8322-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d8322-112">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="d8322-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="d8322-113">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d8322-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="d8322-114">**Versiones de .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d8322-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d8322-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="d8322-115">See Also</span></span>  
 
