---
title: ICorDebugILFrame::CanSetIP (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugILFrame.CanSetIP
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugILFrame::CanSetIP
helpviewer_keywords:
- CanSetIP method, ICorDebugILFrame interface [.NET Framework debugging]
- ICorDebugILFrame::CanSetIP method [.NET Framework debugging]
ms.assetid: 16caf02f-c71e-486c-90b0-f0e54357d8f0
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 75b28dafae2861a2d33363f95a46bf1abf4cda35
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/10/2019
ms.locfileid: "67756581"
---
# <a name="icordebugilframecansetip-method"></a><span data-ttu-id="1b99e-102">ICorDebugILFrame::CanSetIP (Método)</span><span class="sxs-lookup"><span data-stu-id="1b99e-102">ICorDebugILFrame::CanSetIP Method</span></span>
<span data-ttu-id="1b99e-103">Obtiene un valor HRESULT que indica si es seguro establecer el puntero de instrucción en la ubicación de desplazamiento especificada en el código de lenguaje intermedio de Microsoft (MSIL).</span><span class="sxs-lookup"><span data-stu-id="1b99e-103">Gets an HRESULT that indicates whether it is safe to set the instruction pointer to the specified offset location in Microsoft Intermediate Language (MSIL) code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1b99e-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="1b99e-104">Syntax</span></span>  
  
```cpp  
HRESULT CanSetIP (  
    [in] ULONG32   nOffset  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="1b99e-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="1b99e-105">Parameters</span></span>  
 `nOffset`  
 <span data-ttu-id="1b99e-106">[in] El valor deseado para el puntero de instrucción.</span><span class="sxs-lookup"><span data-stu-id="1b99e-106">[in] The desired setting for the instruction pointer.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="1b99e-107">Comentarios</span><span class="sxs-lookup"><span data-stu-id="1b99e-107">Remarks</span></span>  
 <span data-ttu-id="1b99e-108">Use la `CanSetIP` método antes de llamar a la [ICorDebugILFrame:: SetIP](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe-setip-method.md) método.</span><span class="sxs-lookup"><span data-stu-id="1b99e-108">Use the `CanSetIP` method before calling the [ICorDebugILFrame::SetIP](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe-setip-method.md) method.</span></span> <span data-ttu-id="1b99e-109">Si `CanSetIP` devuelve un valor HRESULT distinto de S_OK, todavía se puede llamar `ICorDebugILFrame::SetIP`, pero no hay ninguna garantía de que el depurador continuará la ejecución correcta y segura del código que se está depurando.</span><span class="sxs-lookup"><span data-stu-id="1b99e-109">If `CanSetIP` returns any HRESULT other than S_OK, you can still invoke `ICorDebugILFrame::SetIP`, but there is no guarantee that the debugger will continue the safe and correct execution of the code being debugged.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1b99e-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="1b99e-110">Requirements</span></span>  
 <span data-ttu-id="1b99e-111">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1b99e-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1b99e-112">**Encabezado**: CorDebug.idl, [Cordebug], h</span><span class="sxs-lookup"><span data-stu-id="1b99e-112">**Header:** CorDebug.idl, CorDebug,h</span></span>  
  
 <span data-ttu-id="1b99e-113">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="1b99e-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="1b99e-114">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1b99e-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
