---
description: 'Más información sobre: ICorDebugFunction:: CreateBreakpoint (método)'
title: ICorDebugFunction::CreateBreakpoint (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugFunction.CreateBreakpoint
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugFunction::CreateBreakpoint
helpviewer_keywords:
- ICorDebugFunction::CreateBreakpoint method [.NET Framework debugging]
- CreateBreakpoint method, ICorDebugFunction interface [.NET Framework debugging]
ms.assetid: ffd0f708-0d21-4fae-a395-63b6c45828fa
topic_type:
- apiref
ms.openlocfilehash: 4d55a818352ff98b67c95d5ef15417f2e9e64d40
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99692633"
---
# <a name="icordebugfunctioncreatebreakpoint-method"></a><span data-ttu-id="9e9a3-103">ICorDebugFunction::CreateBreakpoint (Método)</span><span class="sxs-lookup"><span data-stu-id="9e9a3-103">ICorDebugFunction::CreateBreakpoint Method</span></span>

<span data-ttu-id="9e9a3-104">Crea un punto de interrupción al principio de esta función.</span><span class="sxs-lookup"><span data-stu-id="9e9a3-104">Creates a breakpoint at the beginning of this function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9e9a3-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="9e9a3-105">Syntax</span></span>  
  
```cpp  
HRESULT CreateBreakpoint (  
    [out] ICorDebugFunctionBreakpoint **ppBreakpoint  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="9e9a3-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="9e9a3-106">Parameters</span></span>  

 `ppBreakpoint`  
 <span data-ttu-id="9e9a3-107">enuncia Puntero a la dirección de un objeto ICorDebugFunctionBreakpoint que representa el nuevo punto de interrupción de la función.</span><span class="sxs-lookup"><span data-stu-id="9e9a3-107">[out] A pointer to the address of an ICorDebugFunctionBreakpoint object that represents the new breakpoint for the function.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9e9a3-108">Requisitos</span><span class="sxs-lookup"><span data-stu-id="9e9a3-108">Requirements</span></span>  

 <span data-ttu-id="9e9a3-109">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9e9a3-109">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9e9a3-110">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="9e9a3-110">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="9e9a3-111">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="9e9a3-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="9e9a3-112">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9e9a3-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
