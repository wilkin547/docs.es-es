---
title: "ICorDebugILFrame::CanSetIP (Método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugILFrame.CanSetIP
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugILFrame::CanSetIP
helpviewer_keywords:
- CanSetIP method, ICorDebugILFrame interface [.NET Framework debugging]
- ICorDebugILFrame::CanSetIP method [.NET Framework debugging]
ms.assetid: 16caf02f-c71e-486c-90b0-f0e54357d8f0
topic_type: apiref
caps.latest.revision: "13"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: bbb5b0a8038445372b5e404fac554c0726353bf6
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="icordebugilframecansetip-method"></a><span data-ttu-id="f3375-102">ICorDebugILFrame::CanSetIP (Método)</span><span class="sxs-lookup"><span data-stu-id="f3375-102">ICorDebugILFrame::CanSetIP Method</span></span>
<span data-ttu-id="f3375-103">Obtiene un valor HRESULT que indica si es seguro establecer el puntero de instrucción en la ubicación de desplazamiento especificada en el código de lenguaje intermedio de Microsoft (MSIL).</span><span class="sxs-lookup"><span data-stu-id="f3375-103">Gets an HRESULT that indicates whether it is safe to set the instruction pointer to the specified offset location in Microsoft Intermediate Language (MSIL) code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f3375-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="f3375-104">Syntax</span></span>  
  
```  
HRESULT CanSetIP (  
    [in] ULONG32   nOffset  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="f3375-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="f3375-105">Parameters</span></span>  
 `nOffset`  
 <span data-ttu-id="f3375-106">[in] El valor deseado para el puntero de instrucción.</span><span class="sxs-lookup"><span data-stu-id="f3375-106">[in] The desired setting for the instruction pointer.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f3375-107">Comentarios</span><span class="sxs-lookup"><span data-stu-id="f3375-107">Remarks</span></span>  
 <span data-ttu-id="f3375-108">Use la `CanSetIP` método antes de llamar a la [ICorDebugILFrame:: SetIP](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe-setip-method.md) método.</span><span class="sxs-lookup"><span data-stu-id="f3375-108">Use the `CanSetIP` method before calling the [ICorDebugILFrame::SetIP](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe-setip-method.md) method.</span></span> <span data-ttu-id="f3375-109">Si `CanSetIP` devuelve un valor HRESULT distinto de S_OK, todavía se puede llamar `ICorDebugILFrame::SetIP`, pero no hay ninguna garantía de que el depurador continuará la ejecución correcta y seguro para la ejecución del código que se está depurando.</span><span class="sxs-lookup"><span data-stu-id="f3375-109">If `CanSetIP` returns any HRESULT other than S_OK, you can still invoke `ICorDebugILFrame::SetIP`, but there is no guarantee that the debugger will continue the safe and correct execution of the code being debugged.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f3375-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="f3375-110">Requirements</span></span>  
 <span data-ttu-id="f3375-111">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f3375-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f3375-112">**Encabezado:** CorDebug.idl, [Cordebug], h</span><span class="sxs-lookup"><span data-stu-id="f3375-112">**Header:** CorDebug.idl, CorDebug,h</span></span>  
  
 <span data-ttu-id="f3375-113">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f3375-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f3375-114">**Versiones de .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f3375-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
