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
ms.openlocfilehash: 10584442d7e0bd61e6decaf2b494dfe39f339d6d
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73088414"
---
# <a name="icordebugarrayvaluegetelementatposition-method"></a><span data-ttu-id="371fa-102">ICorDebugArrayValue::GetElementAtPosition (Método)</span><span class="sxs-lookup"><span data-stu-id="371fa-102">ICorDebugArrayValue::GetElementAtPosition Method</span></span>
<span data-ttu-id="371fa-103">Obtiene el elemento en la posición especificada y trata la matriz como una matriz unidimensional de base cero.</span><span class="sxs-lookup"><span data-stu-id="371fa-103">Gets the element at the given position, treating the array as a zero-based, single-dimensional array.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="371fa-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="371fa-104">Syntax</span></span>  
  
```cpp  
HRESULT GetElementAtPosition (  
    [in]  ULONG32          nPosition,  
    [out] ICorDebugValue   **ppValue  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="371fa-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="371fa-105">Parameters</span></span>  
 `nPosition`  
 <span data-ttu-id="371fa-106">de Posición del elemento que se va a recuperar.</span><span class="sxs-lookup"><span data-stu-id="371fa-106">[in] The position of the element to be retrieved.</span></span>  
  
 `ppValue`  
 <span data-ttu-id="371fa-107">enuncia Puntero a la dirección de un objeto ICorDebugValue que representa el valor del elemento.</span><span class="sxs-lookup"><span data-stu-id="371fa-107">[out] A pointer to the address of an ICorDebugValue object that represents the value of the element.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="371fa-108">Comentarios</span><span class="sxs-lookup"><span data-stu-id="371fa-108">Remarks</span></span>  
 <span data-ttu-id="371fa-109">El diseño de una matriz de varias dimensiones sigue el C++ estilo del diseño de la matriz.</span><span class="sxs-lookup"><span data-stu-id="371fa-109">The layout of a multi-dimension array follows the C++ style of array layout.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="371fa-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="371fa-110">Requirements</span></span>  
 <span data-ttu-id="371fa-111">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="371fa-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="371fa-112">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="371fa-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="371fa-113">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="371fa-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="371fa-114">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="371fa-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
