---
description: 'Más información sobre: ICorDebugRegisterSet2:: Setregisters ((método)'
title: ICorDebugRegisterSet2::SetRegisters (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugRegisterSet2.SetRegisters
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugRegisterSet2::SetRegisters
helpviewer_keywords:
- ICorDebugRegisterSet2::SetRegisters method [.NET Framework debugging]
- SetRegisters method, ICorDebugRegisterSet2 interface [.NET Framework debugging]
ms.assetid: fe0ac7e7-c9e1-4ec1-9f4e-1c56d63d73ac
topic_type:
- apiref
ms.openlocfilehash: d58717be34e146def2a54bb49d6cd58dde7564c8
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99794759"
---
# <a name="icordebugregisterset2setregisters-method"></a><span data-ttu-id="cf4a5-103">ICorDebugRegisterSet2::SetRegisters (Método)</span><span class="sxs-lookup"><span data-stu-id="cf4a5-103">ICorDebugRegisterSet2::SetRegisters Method</span></span>

<span data-ttu-id="cf4a5-104">`SetRegisters` no se implementa en la versión .NET Framework 2,0.</span><span class="sxs-lookup"><span data-stu-id="cf4a5-104">`SetRegisters` is not implemented in the .NET Framework version 2.0.</span></span> <span data-ttu-id="cf4a5-105">No llame a este método.</span><span class="sxs-lookup"><span data-stu-id="cf4a5-105">Do not call this method.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="cf4a5-106">Use las operaciones de nivel superior como [ICorDebugILFrame:: setip](icordebugilframe-setip-method.md) o [ICorDebugNativeFrame:: setip](icordebugnativeframe-setip-method.md).</span><span class="sxs-lookup"><span data-stu-id="cf4a5-106">Use the higher-level operations such as [ICorDebugILFrame::SetIP](icordebugilframe-setip-method.md) or [ICorDebugNativeFrame::SetIP](icordebugnativeframe-setip-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cf4a5-107">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="cf4a5-107">Syntax</span></span>  
  
```cpp  
HRESULT SetRegisters (  
    [in] ULONG32 maskCount,  
    [in, size_is(maskCount)] BYTE mask[],  
    [in] ULONG32 regCount,  
    [in, size_is(regCount)] CORDB_REGISTER regBuffer[]  
);  
```  
  
## <a name="requirements"></a><span data-ttu-id="cf4a5-108">Requisitos</span><span class="sxs-lookup"><span data-stu-id="cf4a5-108">Requirements</span></span>  

 <span data-ttu-id="cf4a5-109">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="cf4a5-109">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="cf4a5-110">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="cf4a5-110">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="cf4a5-111">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="cf4a5-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="cf4a5-112">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="cf4a5-112">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cf4a5-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="cf4a5-113">See also</span></span>

- [<span data-ttu-id="cf4a5-114">ICorDebugRegisterSet2 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="cf4a5-114">ICorDebugRegisterSet2 Interface</span></span>](icordebugregisterset2-interface.md)
- [<span data-ttu-id="cf4a5-115">ICorDebugRegisterSet (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="cf4a5-115">ICorDebugRegisterSet Interface</span></span>](icordebugregisterset-interface.md)
