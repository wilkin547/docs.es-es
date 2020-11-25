---
title: ICorDebugArrayValue::GetElement (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugArrayValue.GetElement
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugArrayValue::GetElement
helpviewer_keywords:
- GetElement method [.NET Framework debugging]
- ICorDebugArrayValue::GetElement method [.NET Framework debugging]
ms.assetid: 7ac3cba5-c282-402e-b7ef-b46634f5176b
topic_type:
- apiref
ms.openlocfilehash: 0b6b6f46c7fff8f1d4c2ad555c93423f9ca8ac09
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95698158"
---
# <a name="icordebugarrayvaluegetelement-method"></a><span data-ttu-id="81146-102">ICorDebugArrayValue::GetElement (Método)</span><span class="sxs-lookup"><span data-stu-id="81146-102">ICorDebugArrayValue::GetElement Method</span></span>

<span data-ttu-id="81146-103">Obtiene el valor del elemento de la matriz especificado.</span><span class="sxs-lookup"><span data-stu-id="81146-103">Gets the value of the given array element.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="81146-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="81146-104">Syntax</span></span>  
  
```cpp  
HRESULT GetElement (  
    [in]  ULONG32          cdim,  
    [in, size_is(cdim), length_is(cdim)]
         ULONG32           indices[],  
    [out] ICorDebugValue   **ppValue  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="81146-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="81146-105">Parameters</span></span>  

 `cdim`  
 <span data-ttu-id="81146-106">de Número de dimensiones de este `ICorDebugArrayValue` objeto.</span><span class="sxs-lookup"><span data-stu-id="81146-106">[in] The number of dimensions of this `ICorDebugArrayValue` object.</span></span>  
  
 <span data-ttu-id="81146-107">Este valor también es el tamaño de la `indices` matriz porque su tamaño es igual al número de dimensiones del `ICorDebugArrayValue` objeto.</span><span class="sxs-lookup"><span data-stu-id="81146-107">This value is also the size of the `indices` array because its size is equal to the number of dimensions of the `ICorDebugArrayValue` object.</span></span>  
  
 `indices`  
 <span data-ttu-id="81146-108">de Matriz de valores de índice, cada uno de los cuales especifica una posición dentro de una dimensión del `ICorDebugArrayValue` objeto.</span><span class="sxs-lookup"><span data-stu-id="81146-108">[in] An array of index values, each of which specifies a position within a dimension of the `ICorDebugArrayValue` object.</span></span>  
  
 <span data-ttu-id="81146-109">Este valor no debe ser NULL.</span><span class="sxs-lookup"><span data-stu-id="81146-109">This value must not be null.</span></span>  
  
 `ppValue`  
 <span data-ttu-id="81146-110">enuncia Puntero a la dirección de un objeto ICorDebugValue que representa el valor del elemento especificado.</span><span class="sxs-lookup"><span data-stu-id="81146-110">[out] A pointer to the address of an ICorDebugValue object that represents the value of the specified element.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="81146-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="81146-111">Requirements</span></span>  

 <span data-ttu-id="81146-112">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="81146-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="81146-113">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="81146-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="81146-114">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="81146-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="81146-115">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="81146-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
