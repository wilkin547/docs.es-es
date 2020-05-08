---
title: ICorDebugArrayValue::GetElementAtPosition (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugArrayValue.GetElementAtPosition
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugArrayValue::GetElementAtPosition
helpviewer_keywords:
- GetElementAtPosition method [.NET Framework debugging]
- ICorDebugArrayValue::GetElementAtPosition method [.NET Framework debugging]
ms.assetid: 6fd5eaa4-1997-4910-82f5-3887480db764
topic_type:
- apiref
ms.openlocfilehash: 5644c20ec5df2606c7258131573691997f424e50
ms.sourcegitcommit: 957c49696eaf048c284ef8f9f8ffeb562357ad95
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/07/2020
ms.locfileid: "82895016"
---
# <a name="icordebugarrayvaluegetelementatposition-method"></a><span data-ttu-id="de34e-102">ICorDebugArrayValue::GetElementAtPosition (Método)</span><span class="sxs-lookup"><span data-stu-id="de34e-102">ICorDebugArrayValue::GetElementAtPosition Method</span></span>
<span data-ttu-id="de34e-103">Obtiene el elemento en la posición especificada y trata la matriz como una matriz unidimensional de base cero.</span><span class="sxs-lookup"><span data-stu-id="de34e-103">Gets the element at the given position, treating the array as a zero-based, single-dimensional array.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="de34e-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="de34e-104">Syntax</span></span>  
  
```cpp  
HRESULT GetElementAtPosition (  
    [in]  ULONG32          nPosition,  
    [out] ICorDebugValue   **ppValue  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="de34e-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="de34e-105">Parameters</span></span>  
 `nPosition`  
 <span data-ttu-id="de34e-106">de Posición del elemento que se va a recuperar.</span><span class="sxs-lookup"><span data-stu-id="de34e-106">[in] The position of the element to be retrieved.</span></span>  
  
 `ppValue`  
 <span data-ttu-id="de34e-107">enuncia Puntero a la dirección de un objeto ICorDebugValue que representa el valor del elemento.</span><span class="sxs-lookup"><span data-stu-id="de34e-107">[out] A pointer to the address of an ICorDebugValue object that represents the value of the element.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="de34e-108">Observaciones</span><span class="sxs-lookup"><span data-stu-id="de34e-108">Remarks</span></span>  
 <span data-ttu-id="de34e-109">El diseño de una matriz de varias dimensiones sigue el estilo de C++ del diseño de la matriz.</span><span class="sxs-lookup"><span data-stu-id="de34e-109">The layout of a multi-dimension array follows the C++ style of array layout.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="de34e-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="de34e-110">Requirements</span></span>  
 <span data-ttu-id="de34e-111">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="de34e-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="de34e-112">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="de34e-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="de34e-113">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="de34e-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="de34e-114">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="de34e-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
