---
title: "ICorDebugArrayValue::GetElementAtPosition (Método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugArrayValue.GetElementAtPosition
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugArrayValue::GetElementAtPosition
helpviewer_keywords:
- GetElementAtPosition method [.NET Framework debugging]
- ICorDebugArrayValue::GetElementAtPosition method [.NET Framework debugging]
ms.assetid: 6fd5eaa4-1997-4910-82f5-3887480db764
topic_type: apiref
caps.latest.revision: "12"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 20af0afa395dd69dc8967aa9f39a8bf99eacf530
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="icordebugarrayvaluegetelementatposition-method"></a><span data-ttu-id="8ff5b-102">ICorDebugArrayValue::GetElementAtPosition (Método)</span><span class="sxs-lookup"><span data-stu-id="8ff5b-102">ICorDebugArrayValue::GetElementAtPosition Method</span></span>
<span data-ttu-id="8ff5b-103">Obtiene el elemento en la posición determinada, tratando la matriz como una matriz unidimensional de base cero.</span><span class="sxs-lookup"><span data-stu-id="8ff5b-103">Gets the element at the given position, treating the array as a zero-based, single-dimensional array.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8ff5b-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="8ff5b-104">Syntax</span></span>  
  
```  
HRESULT GetElementAtPosition (  
    [in]  ULONG32          nPosition,  
    [out] ICorDebugValue   **ppValue  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="8ff5b-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="8ff5b-105">Parameters</span></span>  
 `nPosition`  
 <span data-ttu-id="8ff5b-106">[in] La posición del elemento que se va a recuperar.</span><span class="sxs-lookup"><span data-stu-id="8ff5b-106">[in] The position of the element to be retrieved.</span></span>  
  
 `ppValue`  
 <span data-ttu-id="8ff5b-107">[out] Un puntero a la dirección de un objeto ICorDebugValue que representa el valor del elemento.</span><span class="sxs-lookup"><span data-stu-id="8ff5b-107">[out] A pointer to the address of an ICorDebugValue object that represents the value of the element.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="8ff5b-108">Comentarios</span><span class="sxs-lookup"><span data-stu-id="8ff5b-108">Remarks</span></span>  
 <span data-ttu-id="8ff5b-109">El diseño de una matriz multidimensional sigue el estilo de C++ de diseño de matriz.</span><span class="sxs-lookup"><span data-stu-id="8ff5b-109">The layout of a multi-dimension array follows the C++ style of array layout.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8ff5b-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="8ff5b-110">Requirements</span></span>  
 <span data-ttu-id="8ff5b-111">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8ff5b-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8ff5b-112">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="8ff5b-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="8ff5b-113">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="8ff5b-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="8ff5b-114">**Versiones de .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8ff5b-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
