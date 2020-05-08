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
ms.openlocfilehash: 9aadbe7c6f18c6b15350267d1f9ecaa3a23cdd20
ms.sourcegitcommit: 957c49696eaf048c284ef8f9f8ffeb562357ad95
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/07/2020
ms.locfileid: "82895068"
---
# <a name="icordebugarrayvaluegetbaseindicies-method"></a><span data-ttu-id="c6054-102">ICorDebugArrayValue::GetBaseIndicies (Método)</span><span class="sxs-lookup"><span data-stu-id="c6054-102">ICorDebugArrayValue::GetBaseIndicies Method</span></span>
<span data-ttu-id="c6054-103">Obtiene el índice base de cada dimensión de la matriz.</span><span class="sxs-lookup"><span data-stu-id="c6054-103">Gets the base index of each dimension in the array.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c6054-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="c6054-104">Syntax</span></span>  
  
```cpp  
HRESULT GetBaseIndicies (  
    [in] ULONG32          cdim,  
    [out, size_is(cdim), length_is(cdim)]
        ULONG32           indicies[]  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c6054-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="c6054-105">Parameters</span></span>  
 `cdim`  
 <span data-ttu-id="c6054-106">de Número de dimensiones de este `ICorDebugArrayValue` objeto.</span><span class="sxs-lookup"><span data-stu-id="c6054-106">[in] The number of dimensions of this `ICorDebugArrayValue` object.</span></span> <span data-ttu-id="c6054-107">Este valor también es el tamaño de la `indicies` matriz porque su tamaño es igual al número de dimensiones del `ICorDebugArrayValue` objeto.</span><span class="sxs-lookup"><span data-stu-id="c6054-107">This value is also the size of the `indicies` array because its size is equal to the number of dimensions of the `ICorDebugArrayValue` object.</span></span>  
  
 `indicies`  
 <span data-ttu-id="c6054-108">enuncia Matriz de enteros, cada uno de los cuales es el índice base (es decir, el índice inicial) de una dimensión de este `ICorDebugArrayValue` objeto.</span><span class="sxs-lookup"><span data-stu-id="c6054-108">[out] An array of integers, each of which is the base index (that is, the starting index) of a dimension of this `ICorDebugArrayValue` object.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c6054-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="c6054-109">Requirements</span></span>  
 <span data-ttu-id="c6054-110">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c6054-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c6054-111">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="c6054-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="c6054-112">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c6054-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c6054-113">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c6054-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
