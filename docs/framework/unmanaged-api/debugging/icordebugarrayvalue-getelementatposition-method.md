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
ms.openlocfilehash: a6e5ecee9a89da98a73dfb20935c5ec594d5958f
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95732936"
---
# <a name="icordebugarrayvaluegetelementatposition-method"></a><span data-ttu-id="b994a-102">ICorDebugArrayValue::GetElementAtPosition (Método)</span><span class="sxs-lookup"><span data-stu-id="b994a-102">ICorDebugArrayValue::GetElementAtPosition Method</span></span>

<span data-ttu-id="b994a-103">Obtiene el elemento en la posición especificada y trata la matriz como una matriz unidimensional de base cero.</span><span class="sxs-lookup"><span data-stu-id="b994a-103">Gets the element at the given position, treating the array as a zero-based, single-dimensional array.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b994a-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="b994a-104">Syntax</span></span>  
  
```cpp  
HRESULT GetElementAtPosition (  
    [in]  ULONG32          nPosition,  
    [out] ICorDebugValue   **ppValue  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b994a-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="b994a-105">Parameters</span></span>  

 `nPosition`  
 <span data-ttu-id="b994a-106">de Posición del elemento que se va a recuperar.</span><span class="sxs-lookup"><span data-stu-id="b994a-106">[in] The position of the element to be retrieved.</span></span>  
  
 `ppValue`  
 <span data-ttu-id="b994a-107">enuncia Puntero a la dirección de un objeto ICorDebugValue que representa el valor del elemento.</span><span class="sxs-lookup"><span data-stu-id="b994a-107">[out] A pointer to the address of an ICorDebugValue object that represents the value of the element.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b994a-108">Comentarios</span><span class="sxs-lookup"><span data-stu-id="b994a-108">Remarks</span></span>  

 <span data-ttu-id="b994a-109">El diseño de una matriz de varias dimensiones sigue el estilo de C++ del diseño de la matriz.</span><span class="sxs-lookup"><span data-stu-id="b994a-109">The layout of a multi-dimension array follows the C++ style of array layout.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b994a-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="b994a-110">Requirements</span></span>  

 <span data-ttu-id="b994a-111">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b994a-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b994a-112">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="b994a-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="b994a-113">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b994a-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b994a-114">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b994a-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
