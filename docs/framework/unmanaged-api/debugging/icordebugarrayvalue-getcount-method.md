---
title: ICorDebugArrayValue::GetCount (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugArrayValue.GetCount
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugArrayValue::GetCount
helpviewer_keywords:
- ICorDebugArrayValue::GetCount method [.NET Framework debugging]
- GetCount method, ICorDebugArrayValue interface [.NET Framework debugging]
ms.assetid: 44cd98cf-2127-4d46-8c6a-da4e857bb6b0
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: aa72f82d2fc78110fc2bee8edd265916996aa884
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33403151"
---
# <a name="icordebugarrayvaluegetcount-method"></a><span data-ttu-id="a8b18-102">ICorDebugArrayValue::GetCount (Método)</span><span class="sxs-lookup"><span data-stu-id="a8b18-102">ICorDebugArrayValue::GetCount Method</span></span>
<span data-ttu-id="a8b18-103">Obtiene el número total de elementos de la matriz.</span><span class="sxs-lookup"><span data-stu-id="a8b18-103">Gets the total number of elements in the array.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a8b18-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="a8b18-104">Syntax</span></span>  
  
```  
HRESULT GetCount (  
    [out] ULONG32 *pnCount  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="a8b18-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="a8b18-105">Parameters</span></span>  
 `pnCount`  
 <span data-ttu-id="a8b18-106">[out] Un puntero al número total de elementos de la matriz.</span><span class="sxs-lookup"><span data-stu-id="a8b18-106">[out] A pointer to the total number of elements in the array.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a8b18-107">Requisitos</span><span class="sxs-lookup"><span data-stu-id="a8b18-107">Requirements</span></span>  
 <span data-ttu-id="a8b18-108">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a8b18-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a8b18-109">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="a8b18-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="a8b18-110">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a8b18-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a8b18-111">**Versiones de .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a8b18-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
