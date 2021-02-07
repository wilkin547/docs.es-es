---
description: 'Más información acerca de: ICorDebugArrayValue:: Getelementatposition ((método)'
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
ms.openlocfilehash: ef8e4a39f5fe4088b1883803aee037c51f410241
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99723041"
---
# <a name="icordebugarrayvaluegetelementatposition-method"></a><span data-ttu-id="512a8-103">ICorDebugArrayValue::GetElementAtPosition (Método)</span><span class="sxs-lookup"><span data-stu-id="512a8-103">ICorDebugArrayValue::GetElementAtPosition Method</span></span>

<span data-ttu-id="512a8-104">Obtiene el elemento en la posición especificada y trata la matriz como una matriz unidimensional de base cero.</span><span class="sxs-lookup"><span data-stu-id="512a8-104">Gets the element at the given position, treating the array as a zero-based, single-dimensional array.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="512a8-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="512a8-105">Syntax</span></span>  
  
```cpp  
HRESULT GetElementAtPosition (  
    [in]  ULONG32          nPosition,  
    [out] ICorDebugValue   **ppValue  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="512a8-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="512a8-106">Parameters</span></span>  

 `nPosition`  
 <span data-ttu-id="512a8-107">de Posición del elemento que se va a recuperar.</span><span class="sxs-lookup"><span data-stu-id="512a8-107">[in] The position of the element to be retrieved.</span></span>  
  
 `ppValue`  
 <span data-ttu-id="512a8-108">enuncia Puntero a la dirección de un objeto ICorDebugValue que representa el valor del elemento.</span><span class="sxs-lookup"><span data-stu-id="512a8-108">[out] A pointer to the address of an ICorDebugValue object that represents the value of the element.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="512a8-109">Observaciones</span><span class="sxs-lookup"><span data-stu-id="512a8-109">Remarks</span></span>  

 <span data-ttu-id="512a8-110">El diseño de una matriz de varias dimensiones sigue el estilo de C++ del diseño de la matriz.</span><span class="sxs-lookup"><span data-stu-id="512a8-110">The layout of a multi-dimension array follows the C++ style of array layout.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="512a8-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="512a8-111">Requirements</span></span>  

 <span data-ttu-id="512a8-112">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="512a8-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="512a8-113">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="512a8-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="512a8-114">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="512a8-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="512a8-115">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="512a8-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
