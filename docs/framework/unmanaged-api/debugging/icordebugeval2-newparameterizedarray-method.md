---
description: 'Más información sobre: ICorDebugEval2:: NewParameterizedArray ((método)'
title: ICorDebugEval2::NewParameterizedArray (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugEval2.NewParameterizedArray
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugEval2::NewParameterizedArray
helpviewer_keywords:
- ICorDebugEval2::NewParameterizedArray method [.NET Framework debugging]
- NewParameterizedArray method [.NET Framework debugging]
ms.assetid: 45efb8ba-c4de-4109-945f-e734d376b43c
topic_type:
- apiref
ms.openlocfilehash: 0ce8582328013ad02357361f05efb55ade8780e5
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99693751"
---
# <a name="icordebugeval2newparameterizedarray-method"></a><span data-ttu-id="2fed4-103">ICorDebugEval2::NewParameterizedArray (Método)</span><span class="sxs-lookup"><span data-stu-id="2fed4-103">ICorDebugEval2::NewParameterizedArray Method</span></span>

<span data-ttu-id="2fed4-104">Asigna una nueva matriz del tipo de elemento y las dimensiones especificadas.</span><span class="sxs-lookup"><span data-stu-id="2fed4-104">Allocates a new array of the specified element type and dimensions.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2fed4-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="2fed4-105">Syntax</span></span>  
  
```cpp  
HRESULT NewParameterizedArray(  
    [in] ICorDebugType          *pElementType,  
    [in] ULONG32                rank,  
    [in, size_is(rank)] ULONG32 dims[],  
    [in, size_is(rank)] ULONG32 lowBounds[]  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="2fed4-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="2fed4-106">Parameters</span></span>  

 `pElementType`  
 <span data-ttu-id="2fed4-107">de Un puntero a un objeto ICorDebugType que representa el tipo de elemento almacenado en la matriz.</span><span class="sxs-lookup"><span data-stu-id="2fed4-107">[in] A pointer to an ICorDebugType object that represents the type of element stored in the array.</span></span>  
  
 `rank`  
 <span data-ttu-id="2fed4-108">de Número de dimensiones de la matriz.</span><span class="sxs-lookup"><span data-stu-id="2fed4-108">[in] The number of dimensions of the array.</span></span> <span data-ttu-id="2fed4-109">En la .NET Framework versión 2,0, este valor debe ser 1.</span><span class="sxs-lookup"><span data-stu-id="2fed4-109">In the .NET Framework version 2.0, this value must be 1.</span></span>  
  
 `dims`  
 <span data-ttu-id="2fed4-110">de Tamaño, en bytes, de cada dimensión de la matriz.</span><span class="sxs-lookup"><span data-stu-id="2fed4-110">[in] The size, in bytes, of each dimension of the array.</span></span>  
  
 `lowBounds`  
 <span data-ttu-id="2fed4-111">[in] Opcional.</span><span class="sxs-lookup"><span data-stu-id="2fed4-111">[in] Optional.</span></span> <span data-ttu-id="2fed4-112">Límite inferior de cada dimensión de la matriz.</span><span class="sxs-lookup"><span data-stu-id="2fed4-112">The lower bound of each dimension of the array.</span></span> <span data-ttu-id="2fed4-113">Si se omite este valor, se supone un límite inferior de cero para cada dimensión.</span><span class="sxs-lookup"><span data-stu-id="2fed4-113">If this value is omitted, a lower bound of zero is assumed for each dimension.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="2fed4-114">Observaciones</span><span class="sxs-lookup"><span data-stu-id="2fed4-114">Remarks</span></span>  

 <span data-ttu-id="2fed4-115">Los elementos de la matriz pueden ser instancias de un tipo genérico.</span><span class="sxs-lookup"><span data-stu-id="2fed4-115">The elements of the array may be instances of a generic type.</span></span> <span data-ttu-id="2fed4-116">La matriz siempre se crea en el dominio de aplicación en el que el subproceso se está ejecutando actualmente.</span><span class="sxs-lookup"><span data-stu-id="2fed4-116">The array is always created in the application domain in which the thread is currently running.</span></span> <span data-ttu-id="2fed4-117">En el .NET Framework 2,0, el valor de `rank` debe ser 1.</span><span class="sxs-lookup"><span data-stu-id="2fed4-117">In the .NET Framework 2.0, the value of `rank` must be 1.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2fed4-118">Requisitos</span><span class="sxs-lookup"><span data-stu-id="2fed4-118">Requirements</span></span>  

 <span data-ttu-id="2fed4-119">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2fed4-119">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2fed4-120">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="2fed4-120">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="2fed4-121">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="2fed4-121">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="2fed4-122">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2fed4-122">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
