---
title: "ICorDebugArrayValue::GetBaseIndicies (Método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- ICorDebugArrayValue.GetBaseIndicies
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugArrayValue::GetBaseIndicies
helpviewer_keywords:
- ICorDebugArrayValue::GetBaseIndicies method [.NET Framework debugging]
- GetBaseIndicies method [.NET Framework debugging]
ms.assetid: 868b339b-acdb-4fe0-91c7-b85f4fba99eb
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 820d81b4538c3cf2bf6fa123df2012ea06e2d978
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugarrayvaluegetbaseindicies-method"></a><span data-ttu-id="0e328-102">ICorDebugArrayValue::GetBaseIndicies (Método)</span><span class="sxs-lookup"><span data-stu-id="0e328-102">ICorDebugArrayValue::GetBaseIndicies Method</span></span>
<span data-ttu-id="0e328-103">Obtiene el índice de base de cada dimensión de la matriz.</span><span class="sxs-lookup"><span data-stu-id="0e328-103">Gets the base index of each dimension in the array.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0e328-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="0e328-104">Syntax</span></span>  
  
```  
HRESULT GetBaseIndicies (  
    [in] ULONG32          cdim,  
    [out, size_is(cdim), length_is(cdim)]   
        ULONG32           indicies[]  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="0e328-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="0e328-105">Parameters</span></span>  
 `cdim`  
 <span data-ttu-id="0e328-106">[in] El número de dimensiones de este `ICorDebugArrayValue` objeto.</span><span class="sxs-lookup"><span data-stu-id="0e328-106">[in] The number of dimensions of this `ICorDebugArrayValue` object.</span></span> <span data-ttu-id="0e328-107">Este valor también es el tamaño de la `indicies` matriz porque su tamaño es igual al número de dimensiones de la `ICorDebugArrayValue` objeto.</span><span class="sxs-lookup"><span data-stu-id="0e328-107">This value is also the size of the `indicies` array because its size is equal to the number of dimensions of the `ICorDebugArrayValue` object.</span></span>  
  
 `indicies`  
 <span data-ttu-id="0e328-108">[out] Una matriz de enteros, cada uno de los cuales es el índice de base (es decir, el índice inicial) de una dimensión de este `ICorDebugArrayValue` objeto.</span><span class="sxs-lookup"><span data-stu-id="0e328-108">[out] An array of integers, each of which is the base index (that is, the starting index) of a dimension of this `ICorDebugArrayValue` object.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0e328-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="0e328-109">Requirements</span></span>  
 <span data-ttu-id="0e328-110">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0e328-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0e328-111">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="0e328-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="0e328-112">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="0e328-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="0e328-113">**Versiones de .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0e328-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
