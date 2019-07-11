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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: d6bfde8a934da857e580c603bd1c0115a04a4070
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/10/2019
ms.locfileid: "67754634"
---
# <a name="icordebugfunctiongetmodule-method"></a><span data-ttu-id="12244-102">ICorDebugFunction::GetModule (Método)</span><span class="sxs-lookup"><span data-stu-id="12244-102">ICorDebugFunction::GetModule Method</span></span>
<span data-ttu-id="12244-103">Obtiene el módulo en el que se define esta función.</span><span class="sxs-lookup"><span data-stu-id="12244-103">Gets the module in which this function is defined.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="12244-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="12244-104">Syntax</span></span>  
  
```cpp  
HRESULT GetModule (  
    [out] ICorDebugModule **ppModule  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="12244-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="12244-105">Parameters</span></span>  
 `ppModule`  
 <span data-ttu-id="12244-106">[out] Un puntero a la dirección de un objeto ICorDebugModule que representa el módulo en el que se define esta función.</span><span class="sxs-lookup"><span data-stu-id="12244-106">[out] A pointer to the address of an ICorDebugModule object that represents the module in which this function is defined.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="12244-107">Requisitos</span><span class="sxs-lookup"><span data-stu-id="12244-107">Requirements</span></span>  
 <span data-ttu-id="12244-108">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="12244-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="12244-109">**Encabezado**: CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="12244-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="12244-110">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="12244-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="12244-111">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="12244-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
