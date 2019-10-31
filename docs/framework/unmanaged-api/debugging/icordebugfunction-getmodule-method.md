---
title: ICorDebugFunction::GetModule (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugFunction.GetModule
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugFunction::GetModule
helpviewer_keywords:
- ICorDebugFunction::GetModule method [.NET Framework debugging]
- GetModule method, ICorDebugFunction interface [.NET Framework debugging]
ms.assetid: 5031a5d3-2564-412a-9007-e36d4631308a
topic_type:
- apiref
ms.openlocfilehash: e49bf6a7db9edb9e5ae489cc0655eea54406643d
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73137881"
---
# <a name="icordebugfunctiongetmodule-method"></a><span data-ttu-id="d88aa-102">ICorDebugFunction::GetModule (Método)</span><span class="sxs-lookup"><span data-stu-id="d88aa-102">ICorDebugFunction::GetModule Method</span></span>
<span data-ttu-id="d88aa-103">Obtiene el módulo en el que se define esta función.</span><span class="sxs-lookup"><span data-stu-id="d88aa-103">Gets the module in which this function is defined.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d88aa-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="d88aa-104">Syntax</span></span>  
  
```cpp  
HRESULT GetModule (  
    [out] ICorDebugModule **ppModule  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d88aa-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="d88aa-105">Parameters</span></span>  
 `ppModule`  
 <span data-ttu-id="d88aa-106">enuncia Puntero a la dirección de un objeto ICorDebugModule que representa el módulo en el que se define esta función.</span><span class="sxs-lookup"><span data-stu-id="d88aa-106">[out] A pointer to the address of an ICorDebugModule object that represents the module in which this function is defined.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d88aa-107">Requisitos</span><span class="sxs-lookup"><span data-stu-id="d88aa-107">Requirements</span></span>  
 <span data-ttu-id="d88aa-108">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d88aa-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d88aa-109">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="d88aa-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="d88aa-110">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d88aa-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="d88aa-111">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d88aa-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
