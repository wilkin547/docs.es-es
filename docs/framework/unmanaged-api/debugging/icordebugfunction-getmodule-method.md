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
ms.openlocfilehash: 1cefe84c482df3b20b5939e031ad76647f295d3e
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/06/2019
ms.locfileid: "57484632"
---
# <a name="icordebugfunctiongetmodule-method"></a><span data-ttu-id="f19cb-102">ICorDebugFunction::GetModule (Método)</span><span class="sxs-lookup"><span data-stu-id="f19cb-102">ICorDebugFunction::GetModule Method</span></span>
<span data-ttu-id="f19cb-103">Obtiene el módulo en el que se define esta función.</span><span class="sxs-lookup"><span data-stu-id="f19cb-103">Gets the module in which this function is defined.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f19cb-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="f19cb-104">Syntax</span></span>  
  
```  
HRESULT GetModule (  
    [out] ICorDebugModule **ppModule  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f19cb-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="f19cb-105">Parameters</span></span>  
 `ppModule`  
 <span data-ttu-id="f19cb-106">[out] Un puntero a la dirección de un objeto ICorDebugModule que representa el módulo en el que se define esta función.</span><span class="sxs-lookup"><span data-stu-id="f19cb-106">[out] A pointer to the address of an ICorDebugModule object that represents the module in which this function is defined.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f19cb-107">Requisitos</span><span class="sxs-lookup"><span data-stu-id="f19cb-107">Requirements</span></span>  
 <span data-ttu-id="f19cb-108">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f19cb-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f19cb-109">**Encabezado**: CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="f19cb-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="f19cb-110">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f19cb-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f19cb-111">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f19cb-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
