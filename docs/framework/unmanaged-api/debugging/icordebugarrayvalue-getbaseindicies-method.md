---
title: ICorDebugArrayValue::GetBaseIndicies (Método)
ms.date: 03/30/2017
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
ms.openlocfilehash: 7c6d1905cdbd12b960014e687034ea9d163b68d7
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79179037"
---
# <a name="icordebugarrayvaluegetbaseindicies-method"></a><span data-ttu-id="accca-102">ICorDebugArrayValue::GetBaseIndicies (Método)</span><span class="sxs-lookup"><span data-stu-id="accca-102">ICorDebugArrayValue::GetBaseIndicies Method</span></span>
<span data-ttu-id="accca-103">Obtiene el índice base de cada dimensión de la matriz.</span><span class="sxs-lookup"><span data-stu-id="accca-103">Gets the base index of each dimension in the array.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="accca-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="accca-104">Syntax</span></span>  
  
```cpp  
HRESULT GetBaseIndicies (  
    [in] ULONG32          cdim,  
    [out, size_is(cdim), length_is(cdim)]
        ULONG32           indicies[]  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="accca-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="accca-105">Parameters</span></span>  
 `cdim`  
 <span data-ttu-id="accca-106">[en] El número de `ICorDebugArrayValue` dimensiones de este objeto.</span><span class="sxs-lookup"><span data-stu-id="accca-106">[in] The number of dimensions of this `ICorDebugArrayValue` object.</span></span> <span data-ttu-id="accca-107">Este valor también es `indicies` el tamaño de la matriz porque su `ICorDebugArrayValue` tamaño es igual al número de dimensiones del objeto.</span><span class="sxs-lookup"><span data-stu-id="accca-107">This value is also the size of the `indicies` array because its size is equal to the number of dimensions of the `ICorDebugArrayValue` object.</span></span>  
  
 `indicies`  
 <span data-ttu-id="accca-108">[fuera] Matriz de enteros, cada uno de los cuales es el índice base (es decir, el índice inicial) de una dimensión de este `ICorDebugArrayValue` objeto.</span><span class="sxs-lookup"><span data-stu-id="accca-108">[out] An array of integers, each of which is the base index (that is, the starting index) of a dimension of this `ICorDebugArrayValue` object.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="accca-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="accca-109">Requirements</span></span>  
 <span data-ttu-id="accca-110">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="accca-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="accca-111">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="accca-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="accca-112">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="accca-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="accca-113">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="accca-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
