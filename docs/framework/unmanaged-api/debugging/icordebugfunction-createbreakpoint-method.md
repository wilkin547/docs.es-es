---
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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 695ce7f25813a191c74bec6563fc7f8ae8d1143d
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/06/2019
ms.locfileid: "57496123"
---
# <a name="icordebugfunctioncreatebreakpoint-method"></a><span data-ttu-id="81fdf-102">ICorDebugFunction::CreateBreakpoint (Método)</span><span class="sxs-lookup"><span data-stu-id="81fdf-102">ICorDebugFunction::CreateBreakpoint Method</span></span>
<span data-ttu-id="81fdf-103">Crea un punto de interrupción al principio de esta función.</span><span class="sxs-lookup"><span data-stu-id="81fdf-103">Creates a breakpoint at the beginning of this function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="81fdf-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="81fdf-104">Syntax</span></span>  
  
```  
HRESULT CreateBreakpoint (  
    [out] ICorDebugFunctionBreakpoint **ppBreakpoint  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="81fdf-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="81fdf-105">Parameters</span></span>  
 `ppBreakpoint`  
 <span data-ttu-id="81fdf-106">[out] Un puntero a la dirección de un objeto ICorDebugFunctionBreakpoint que representa el nuevo punto de interrupción para la función.</span><span class="sxs-lookup"><span data-stu-id="81fdf-106">[out] A pointer to the address of an ICorDebugFunctionBreakpoint object that represents the new breakpoint for the function.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="81fdf-107">Requisitos</span><span class="sxs-lookup"><span data-stu-id="81fdf-107">Requirements</span></span>  
 <span data-ttu-id="81fdf-108">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="81fdf-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="81fdf-109">**Encabezado**: CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="81fdf-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="81fdf-110">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="81fdf-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="81fdf-111">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="81fdf-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
