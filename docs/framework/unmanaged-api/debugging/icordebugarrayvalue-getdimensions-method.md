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
ms.openlocfilehash: c5199794098e4d83588728eeb165aee5f81fe4c4
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73088508"
---
# <a name="icordebugarrayvaluegetdimensions-method"></a><span data-ttu-id="1fe7b-102">ICorDebugArrayValue::GetDimensions (Método)</span><span class="sxs-lookup"><span data-stu-id="1fe7b-102">ICorDebugArrayValue::GetDimensions Method</span></span>
<span data-ttu-id="1fe7b-103">Obtiene el número de elementos de cada dimensión de esta matriz.</span><span class="sxs-lookup"><span data-stu-id="1fe7b-103">Gets the number of elements in each dimension of this array.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1fe7b-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="1fe7b-104">Syntax</span></span>  
  
```cpp  
HRESULT GetDimensions (  
    [in] ULONG32         cdim,  
    [out, size_is(cdim), length_is(cdim)]   
        ULONG32          dims[]  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="1fe7b-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="1fe7b-105">Parameters</span></span>  
 `cdim`  
 <span data-ttu-id="1fe7b-106">de Número de dimensiones de este objeto ICorDebugArrayValue.</span><span class="sxs-lookup"><span data-stu-id="1fe7b-106">[in] The number of dimensions of this ICorDebugArrayValue object.</span></span>  
  
 <span data-ttu-id="1fe7b-107">Este valor también es el tamaño de la matriz de `dims` porque su tamaño es igual al número de dimensiones del objeto `ICorDebugArrayValue`.</span><span class="sxs-lookup"><span data-stu-id="1fe7b-107">This value is also the size of the `dims` array because its size is equal to the number of dimensions of the `ICorDebugArrayValue` object.</span></span>  
  
 `dims`  
 <span data-ttu-id="1fe7b-108">enuncia Matriz de enteros, cada uno de los cuales especifica el número de elementos de una dimensión en este objeto `ICorDebugArrayValue`.</span><span class="sxs-lookup"><span data-stu-id="1fe7b-108">[out] An array of integers, each of which specifies the number of elements in a dimension in this `ICorDebugArrayValue` object.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1fe7b-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="1fe7b-109">Requirements</span></span>  
 <span data-ttu-id="1fe7b-110">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1fe7b-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1fe7b-111">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="1fe7b-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="1fe7b-112">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="1fe7b-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="1fe7b-113">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1fe7b-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
