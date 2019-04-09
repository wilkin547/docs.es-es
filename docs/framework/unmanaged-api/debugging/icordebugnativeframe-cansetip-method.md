---
title: ICorDebugNativeFrame::CanSetIP (Método)
ms.date: 03/30/2017
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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: bd16db8c009fe81f2674a8bf9c7ad3a2a4827777
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59092856"
---
# <a name="icordebugnativeframecansetip-method"></a><span data-ttu-id="be53d-102">ICorDebugNativeFrame::CanSetIP (Método)</span><span class="sxs-lookup"><span data-stu-id="be53d-102">ICorDebugNativeFrame::CanSetIP Method</span></span>
<span data-ttu-id="be53d-103">Obtiene un valor HRESULT que indica si es seguro establecer el puntero de instrucción (IP) en la ubicación de desplazamiento especificada en código nativo.</span><span class="sxs-lookup"><span data-stu-id="be53d-103">Gets an HRESULT that indicates whether it is safe to set the instruction pointer (IP) to the specified offset location in native code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="be53d-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="be53d-104">Syntax</span></span>  
  
```  
HRESULT CanSetIP (  
    [in] ULONG32            nOffset  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="be53d-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="be53d-105">Parameters</span></span>  
 `nOffset`  
 <span data-ttu-id="be53d-106">[in] El valor deseado para el puntero de instrucción.</span><span class="sxs-lookup"><span data-stu-id="be53d-106">[in] The desired setting for the instruction pointer.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="be53d-107">Comentarios</span><span class="sxs-lookup"><span data-stu-id="be53d-107">Remarks</span></span>  
 <span data-ttu-id="be53d-108">Use la `CanSetIP` método antes de llamar a la [ICorDebugNativeFrame](../../../../docs/framework/unmanaged-api/debugging/icordebugnativeframe-setip-method.md) método.</span><span class="sxs-lookup"><span data-stu-id="be53d-108">Use the `CanSetIP` method prior to calling the [ICorDebugNativeFrame::SetIP](../../../../docs/framework/unmanaged-api/debugging/icordebugnativeframe-setip-method.md) method.</span></span> <span data-ttu-id="be53d-109">Si `CanSetIP` devuelve un valor HRESULT distinto de S_OK, todavía se puede llamar `ICorDebugNativeFrame::SetIP`, pero no hay ninguna garantía de que el depurador continuará la ejecución correcta y segura del código que se está depurando.</span><span class="sxs-lookup"><span data-stu-id="be53d-109">If `CanSetIP` returns any HRESULT other than S_OK, you can still invoke `ICorDebugNativeFrame::SetIP`, but there is no guarantee that the debugger will continue the safe and correct execution of the code being debugged.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="be53d-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="be53d-110">Requirements</span></span>  
 <span data-ttu-id="be53d-111">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="be53d-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="be53d-112">**Encabezado**: CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="be53d-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="be53d-113">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="be53d-113">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="be53d-114">Versiones de .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="be53d-114">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="be53d-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="be53d-115">See also</span></span>
