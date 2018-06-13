---
title: ICorDebugFunction::GetClass (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugFunction.GetClass
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugFunction::GetClass
helpviewer_keywords:
- GetClass method, ICorDebugFunction interface [.NET Framework debugging]
- ICorDebugFunction::GetClass method [.NET Framework debugging]
ms.assetid: 27967230-144f-40d3-9e23-961d0241abd9
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 184e578efb549a1dc2e9ec1e30a29ff289b68719
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33411708"
---
# <a name="icordebugfunctiongetclass-method"></a><span data-ttu-id="053e0-102">ICorDebugFunction::GetClass (Método)</span><span class="sxs-lookup"><span data-stu-id="053e0-102">ICorDebugFunction::GetClass Method</span></span>
<span data-ttu-id="053e0-103">Obtiene un objeto ICorDebugClass que representa la clase de de que esta función es un miembro.</span><span class="sxs-lookup"><span data-stu-id="053e0-103">Gets an ICorDebugClass object that represents the class this function is a member of.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="053e0-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="053e0-104">Syntax</span></span>  
  
```  
HRESULT GetClass (  
    [out] ICorDebugClass **ppClass  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="053e0-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="053e0-105">Parameters</span></span>  
 `ppClass`  
 <span data-ttu-id="053e0-106">[out] Un puntero a la dirección de la `ICorDebugClass` objeto que representa la clase, o null, si esta función no es un miembro de una clase.</span><span class="sxs-lookup"><span data-stu-id="053e0-106">[out] A pointer to the address of the `ICorDebugClass` object that represents the class, or null, if this function is not a member of a class.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="053e0-107">Requisitos</span><span class="sxs-lookup"><span data-stu-id="053e0-107">Requirements</span></span>  
 <span data-ttu-id="053e0-108">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="053e0-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="053e0-109">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="053e0-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="053e0-110">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="053e0-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="053e0-111">**Versiones de .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="053e0-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
