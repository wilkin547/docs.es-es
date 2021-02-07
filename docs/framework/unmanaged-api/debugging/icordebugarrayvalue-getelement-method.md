---
description: 'Más información acerca de: ICorDebugArrayValue:: GetElement (método)'
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
ms.openlocfilehash: dfae074b78735934d1e71b13ce01c24741a5f2ed
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99723067"
---
# <a name="icordebugarrayvaluegetelement-method"></a><span data-ttu-id="75c3c-103">ICorDebugArrayValue::GetElement (Método)</span><span class="sxs-lookup"><span data-stu-id="75c3c-103">ICorDebugArrayValue::GetElement Method</span></span>

<span data-ttu-id="75c3c-104">Obtiene el valor del elemento de la matriz especificado.</span><span class="sxs-lookup"><span data-stu-id="75c3c-104">Gets the value of the given array element.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="75c3c-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="75c3c-105">Syntax</span></span>  
  
```cpp  
HRESULT GetElement (  
    [in]  ULONG32          cdim,  
    [in, size_is(cdim), length_is(cdim)]
         ULONG32           indices[],  
    [out] ICorDebugValue   **ppValue  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="75c3c-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="75c3c-106">Parameters</span></span>  

 `cdim`  
 <span data-ttu-id="75c3c-107">de Número de dimensiones de este `ICorDebugArrayValue` objeto.</span><span class="sxs-lookup"><span data-stu-id="75c3c-107">[in] The number of dimensions of this `ICorDebugArrayValue` object.</span></span>  
  
 <span data-ttu-id="75c3c-108">Este valor también es el tamaño de la `indices` matriz porque su tamaño es igual al número de dimensiones del `ICorDebugArrayValue` objeto.</span><span class="sxs-lookup"><span data-stu-id="75c3c-108">This value is also the size of the `indices` array because its size is equal to the number of dimensions of the `ICorDebugArrayValue` object.</span></span>  
  
 `indices`  
 <span data-ttu-id="75c3c-109">de Matriz de valores de índice, cada uno de los cuales especifica una posición dentro de una dimensión del `ICorDebugArrayValue` objeto.</span><span class="sxs-lookup"><span data-stu-id="75c3c-109">[in] An array of index values, each of which specifies a position within a dimension of the `ICorDebugArrayValue` object.</span></span>  
  
 <span data-ttu-id="75c3c-110">Este valor no debe ser NULL.</span><span class="sxs-lookup"><span data-stu-id="75c3c-110">This value must not be null.</span></span>  
  
 `ppValue`  
 <span data-ttu-id="75c3c-111">enuncia Puntero a la dirección de un objeto ICorDebugValue que representa el valor del elemento especificado.</span><span class="sxs-lookup"><span data-stu-id="75c3c-111">[out] A pointer to the address of an ICorDebugValue object that represents the value of the specified element.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="75c3c-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="75c3c-112">Requirements</span></span>  

 <span data-ttu-id="75c3c-113">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="75c3c-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="75c3c-114">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="75c3c-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="75c3c-115">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="75c3c-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="75c3c-116">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="75c3c-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
