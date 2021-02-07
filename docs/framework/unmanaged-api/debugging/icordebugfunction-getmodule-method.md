---
description: 'Más información acerca de: ICorDebugFunction:: GetModule (método)'
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
ms.openlocfilehash: 62087cdf0443b2ef495461aab74cfa047b95efca
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99692477"
---
# <a name="icordebugfunctiongetmodule-method"></a><span data-ttu-id="f4db4-103">ICorDebugFunction::GetModule (Método)</span><span class="sxs-lookup"><span data-stu-id="f4db4-103">ICorDebugFunction::GetModule Method</span></span>

<span data-ttu-id="f4db4-104">Obtiene el módulo en el que se define esta función.</span><span class="sxs-lookup"><span data-stu-id="f4db4-104">Gets the module in which this function is defined.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f4db4-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="f4db4-105">Syntax</span></span>  
  
```cpp  
HRESULT GetModule (  
    [out] ICorDebugModule **ppModule  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f4db4-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="f4db4-106">Parameters</span></span>  

 `ppModule`  
 <span data-ttu-id="f4db4-107">enuncia Puntero a la dirección de un objeto ICorDebugModule que representa el módulo en el que se define esta función.</span><span class="sxs-lookup"><span data-stu-id="f4db4-107">[out] A pointer to the address of an ICorDebugModule object that represents the module in which this function is defined.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f4db4-108">Requisitos</span><span class="sxs-lookup"><span data-stu-id="f4db4-108">Requirements</span></span>  

 <span data-ttu-id="f4db4-109">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f4db4-109">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f4db4-110">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="f4db4-110">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="f4db4-111">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f4db4-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f4db4-112">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f4db4-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
