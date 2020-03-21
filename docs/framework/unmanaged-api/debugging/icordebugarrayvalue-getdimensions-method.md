---
title: ICorDebugArrayValue::GetDimensions (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugArrayValue.GetDimensions
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugArrayValue::GetDimensions
helpviewer_keywords:
- ICorDebugArrayValue::GetDimensions method [.NET Framework debugging]
- GetDimensions method [.NET Framework debugging]
ms.assetid: 6c116592-134b-4ef2-a319-680e92d013aa
topic_type:
- apiref
ms.openlocfilehash: 35e043c56977bf644efe1dd9cee1409f50cc877f
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79179026"
---
# <a name="icordebugarrayvaluegetdimensions-method"></a><span data-ttu-id="eadee-102">ICorDebugArrayValue::GetDimensions (Método)</span><span class="sxs-lookup"><span data-stu-id="eadee-102">ICorDebugArrayValue::GetDimensions Method</span></span>
<span data-ttu-id="eadee-103">Obtiene el número de elementos de cada dimensión de esta matriz.</span><span class="sxs-lookup"><span data-stu-id="eadee-103">Gets the number of elements in each dimension of this array.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="eadee-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="eadee-104">Syntax</span></span>  
  
```cpp  
HRESULT GetDimensions (  
    [in] ULONG32         cdim,  
    [out, size_is(cdim), length_is(cdim)]
        ULONG32          dims[]  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="eadee-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="eadee-105">Parameters</span></span>  
 `cdim`  
 <span data-ttu-id="eadee-106">[en] El número de dimensiones de este ICorDebugArrayValue objeto.</span><span class="sxs-lookup"><span data-stu-id="eadee-106">[in] The number of dimensions of this ICorDebugArrayValue object.</span></span>  
  
 <span data-ttu-id="eadee-107">Este valor también es `dims` el tamaño de la matriz porque su `ICorDebugArrayValue` tamaño es igual al número de dimensiones del objeto.</span><span class="sxs-lookup"><span data-stu-id="eadee-107">This value is also the size of the `dims` array because its size is equal to the number of dimensions of the `ICorDebugArrayValue` object.</span></span>  
  
 `dims`  
 <span data-ttu-id="eadee-108">[fuera] Matriz de enteros, cada uno de los cuales especifica el `ICorDebugArrayValue` número de elementos de una dimensión de este objeto.</span><span class="sxs-lookup"><span data-stu-id="eadee-108">[out] An array of integers, each of which specifies the number of elements in a dimension in this `ICorDebugArrayValue` object.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="eadee-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="eadee-109">Requirements</span></span>  
 <span data-ttu-id="eadee-110">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="eadee-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="eadee-111">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="eadee-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="eadee-112">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="eadee-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="eadee-113">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="eadee-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
