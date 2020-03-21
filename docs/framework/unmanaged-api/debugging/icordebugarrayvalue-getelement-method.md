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
ms.openlocfilehash: adcb7b5a27f3b8c63dbbb660a23b5c891f84ac46
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79179009"
---
# <a name="icordebugarrayvaluegetelement-method"></a><span data-ttu-id="90e7b-102">ICorDebugArrayValue::GetElement (Método)</span><span class="sxs-lookup"><span data-stu-id="90e7b-102">ICorDebugArrayValue::GetElement Method</span></span>
<span data-ttu-id="90e7b-103">Obtiene el valor del elemento de matriz especificado.</span><span class="sxs-lookup"><span data-stu-id="90e7b-103">Gets the value of the given array element.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="90e7b-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="90e7b-104">Syntax</span></span>  
  
```cpp  
HRESULT GetElement (  
    [in]  ULONG32          cdim,  
    [in, size_is(cdim), length_is(cdim)]
         ULONG32           indices[],  
    [out] ICorDebugValue   **ppValue  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="90e7b-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="90e7b-105">Parameters</span></span>  
 `cdim`  
 <span data-ttu-id="90e7b-106">[en] El número de `ICorDebugArrayValue` dimensiones de este objeto.</span><span class="sxs-lookup"><span data-stu-id="90e7b-106">[in] The number of dimensions of this `ICorDebugArrayValue` object.</span></span>  
  
 <span data-ttu-id="90e7b-107">Este valor también es `indices` el tamaño de la matriz porque su `ICorDebugArrayValue` tamaño es igual al número de dimensiones del objeto.</span><span class="sxs-lookup"><span data-stu-id="90e7b-107">This value is also the size of the `indices` array because its size is equal to the number of dimensions of the `ICorDebugArrayValue` object.</span></span>  
  
 `indices`  
 <span data-ttu-id="90e7b-108">[en] Matriz de valores de índice, cada uno de los `ICorDebugArrayValue` cuales especifica una posición dentro de una dimensión del objeto.</span><span class="sxs-lookup"><span data-stu-id="90e7b-108">[in] An array of index values, each of which specifies a position within a dimension of the `ICorDebugArrayValue` object.</span></span>  
  
 <span data-ttu-id="90e7b-109">Este valor no debe ser null.</span><span class="sxs-lookup"><span data-stu-id="90e7b-109">This value must not be null.</span></span>  
  
 `ppValue`  
 <span data-ttu-id="90e7b-110">[fuera] Puntero a la dirección de un ICorDebugValue objeto que representa el valor del elemento especificado.</span><span class="sxs-lookup"><span data-stu-id="90e7b-110">[out] A pointer to the address of an ICorDebugValue object that represents the value of the specified element.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="90e7b-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="90e7b-111">Requirements</span></span>  
 <span data-ttu-id="90e7b-112">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="90e7b-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="90e7b-113">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="90e7b-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="90e7b-114">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="90e7b-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="90e7b-115">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="90e7b-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
