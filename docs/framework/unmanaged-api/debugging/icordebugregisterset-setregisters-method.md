---
title: ICorDebugRegisterSet::SetRegisters (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugRegisterSet.SetRegisters
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugRegisterSet::SetRegisters
helpviewer_keywords:
- SetRegisters method, ICorDebugRegisterSet interface [.NET Framework debugging]
- ICorDebugRegisterSet::SetRegisters method [.NET Framework debugging]
ms.assetid: ac6244b9-54ba-475f-b72a-abed6afc46ec
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: d17c353d8e2358a1651ba3fbbb1dd718cc681f7b
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59123810"
---
# <a name="icordebugregistersetsetregisters-method"></a><span data-ttu-id="16381-102">ICorDebugRegisterSet::SetRegisters (Método)</span><span class="sxs-lookup"><span data-stu-id="16381-102">ICorDebugRegisterSet::SetRegisters Method</span></span>
<span data-ttu-id="16381-103">`SetRegisters` no se implementa en la versión 2.0 de .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="16381-103">`SetRegisters` is not implemented in the .NET Framework version 2.0.</span></span> <span data-ttu-id="16381-104">No llame a este método.</span><span class="sxs-lookup"><span data-stu-id="16381-104">Do not call this method.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="16381-105">Use las operaciones de nivel superior como [ICorDebugILFrame:: SetIP](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe-setip-method.md) o [ICorDebugNativeFrame](../../../../docs/framework/unmanaged-api/debugging/icordebugnativeframe-setip-method.md).</span><span class="sxs-lookup"><span data-stu-id="16381-105">Use the higher-level operations such as [ICorDebugILFrame::SetIP](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe-setip-method.md) or [ICorDebugNativeFrame::SetIP](../../../../docs/framework/unmanaged-api/debugging/icordebugnativeframe-setip-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="16381-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="16381-106">Syntax</span></span>  
  
```  
HRESULT SetRegisters (  
    [in] ULONG64   mask,  
    [in] ULONG32   regCount,  
    [in, size_is(regCount)] CORDB_REGISTER regBuffer[]  
);  
```  
  
## <a name="requirements"></a><span data-ttu-id="16381-107">Requisitos</span><span class="sxs-lookup"><span data-stu-id="16381-107">Requirements</span></span>  
 <span data-ttu-id="16381-108">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="16381-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="16381-109">**Encabezado**: CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="16381-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="16381-110">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="16381-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="16381-111">**Versiones de .NET framework:** 1.1, 1.0</span><span class="sxs-lookup"><span data-stu-id="16381-111">**.NET Framework Versions:** 1.1, 1.0</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="16381-112">Vea también</span><span class="sxs-lookup"><span data-stu-id="16381-112">See also</span></span>

- [<span data-ttu-id="16381-113">ICorDebugRegisterSet (interfaz)</span><span class="sxs-lookup"><span data-stu-id="16381-113">ICorDebugRegisterSet Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset-interface.md)
- [<span data-ttu-id="16381-114">ICorDebugRegisterSet2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="16381-114">ICorDebugRegisterSet2 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset2-interface.md)
