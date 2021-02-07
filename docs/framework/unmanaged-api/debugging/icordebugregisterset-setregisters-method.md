---
description: 'Más información acerca de: ICorDebugRegisterSet:: Setregisters ((método)'
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
ms.openlocfilehash: 7a83d9d01a392d7ed435292f45ee0c75765ced36
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99690683"
---
# <a name="icordebugregistersetsetregisters-method"></a><span data-ttu-id="08561-103">ICorDebugRegisterSet::SetRegisters (Método)</span><span class="sxs-lookup"><span data-stu-id="08561-103">ICorDebugRegisterSet::SetRegisters Method</span></span>

<span data-ttu-id="08561-104">`SetRegisters` no se implementa en la versión .NET Framework 2,0.</span><span class="sxs-lookup"><span data-stu-id="08561-104">`SetRegisters` is not implemented in the .NET Framework version 2.0.</span></span> <span data-ttu-id="08561-105">No llame a este método.</span><span class="sxs-lookup"><span data-stu-id="08561-105">Do not call this method.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="08561-106">Use las operaciones de nivel superior como [ICorDebugILFrame:: setip](icordebugilframe-setip-method.md) o [ICorDebugNativeFrame:: setip](icordebugnativeframe-setip-method.md).</span><span class="sxs-lookup"><span data-stu-id="08561-106">Use the higher-level operations such as [ICorDebugILFrame::SetIP](icordebugilframe-setip-method.md) or [ICorDebugNativeFrame::SetIP](icordebugnativeframe-setip-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="08561-107">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="08561-107">Syntax</span></span>  
  
```cpp  
HRESULT SetRegisters (  
    [in] ULONG64   mask,  
    [in] ULONG32   regCount,  
    [in, size_is(regCount)] CORDB_REGISTER regBuffer[]  
);  
```  
  
## <a name="requirements"></a><span data-ttu-id="08561-108">Requisitos</span><span class="sxs-lookup"><span data-stu-id="08561-108">Requirements</span></span>  

 <span data-ttu-id="08561-109">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="08561-109">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="08561-110">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="08561-110">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="08561-111">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="08561-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="08561-112">**.NET Framework versiones:** 1,1, 1,0</span><span class="sxs-lookup"><span data-stu-id="08561-112">**.NET Framework Versions:** 1.1, 1.0</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="08561-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="08561-113">See also</span></span>

- [<span data-ttu-id="08561-114">ICorDebugRegisterSet (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="08561-114">ICorDebugRegisterSet Interface</span></span>](icordebugregisterset-interface.md)
- [<span data-ttu-id="08561-115">ICorDebugRegisterSet2 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="08561-115">ICorDebugRegisterSet2 Interface</span></span>](icordebugregisterset2-interface.md)
