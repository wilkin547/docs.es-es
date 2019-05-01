---
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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 8c639204fa207774b0e362f1ba8fe71937494ae2
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61989002"
---
# <a name="icordebugeval2newparameterizedarray-method"></a><span data-ttu-id="a7ec6-102">ICorDebugEval2::NewParameterizedArray (Método)</span><span class="sxs-lookup"><span data-stu-id="a7ec6-102">ICorDebugEval2::NewParameterizedArray Method</span></span>
<span data-ttu-id="a7ec6-103">Asigna una nueva matriz del tipo de elemento especificado y las dimensiones.</span><span class="sxs-lookup"><span data-stu-id="a7ec6-103">Allocates a new array of the specified element type and dimensions.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a7ec6-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="a7ec6-104">Syntax</span></span>  
  
```  
HRESULT NewParameterizedArray(  
    [in] ICorDebugType          *pElementType,  
    [in] ULONG32                rank,  
    [in, size_is(rank)] ULONG32 dims[],  
    [in, size_is(rank)] ULONG32 lowBounds[]  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a7ec6-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="a7ec6-105">Parameters</span></span>  
 `pElementType`  
 <span data-ttu-id="a7ec6-106">[in] Un puntero a un objeto ICorDebugType que representa el tipo de elemento almacenado en la matriz.</span><span class="sxs-lookup"><span data-stu-id="a7ec6-106">[in] A pointer to an ICorDebugType object that represents the type of element stored in the array.</span></span>  
  
 `rank`  
 <span data-ttu-id="a7ec6-107">[in] El número de dimensiones de la matriz.</span><span class="sxs-lookup"><span data-stu-id="a7ec6-107">[in] The number of dimensions of the array.</span></span> <span data-ttu-id="a7ec6-108">En la versión 2.0 de .NET Framework, este valor debe ser 1.</span><span class="sxs-lookup"><span data-stu-id="a7ec6-108">In the .NET Framework version 2.0, this value must be 1.</span></span>  
  
 `dims`  
 <span data-ttu-id="a7ec6-109">[in] El tamaño, en bytes, de cada dimensión de la matriz.</span><span class="sxs-lookup"><span data-stu-id="a7ec6-109">[in] The size, in bytes, of each dimension of the array.</span></span>  
  
 `lowBounds`  
 <span data-ttu-id="a7ec6-110">[in] Opcional.</span><span class="sxs-lookup"><span data-stu-id="a7ec6-110">[in] Optional.</span></span> <span data-ttu-id="a7ec6-111">El límite inferior de cada dimensión de la matriz.</span><span class="sxs-lookup"><span data-stu-id="a7ec6-111">The lower bound of each dimension of the array.</span></span> <span data-ttu-id="a7ec6-112">Si este valor se omite, se asume un límite inferior de cero para cada dimensión.</span><span class="sxs-lookup"><span data-stu-id="a7ec6-112">If this value is omitted, a lower bound of zero is assumed for each dimension.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a7ec6-113">Comentarios</span><span class="sxs-lookup"><span data-stu-id="a7ec6-113">Remarks</span></span>  
 <span data-ttu-id="a7ec6-114">Los elementos de la matriz pueden ser instancias de un tipo genérico.</span><span class="sxs-lookup"><span data-stu-id="a7ec6-114">The elements of the array may be instances of a generic type.</span></span> <span data-ttu-id="a7ec6-115">La matriz siempre se crea en el dominio de aplicación en el que se está ejecutando el subproceso.</span><span class="sxs-lookup"><span data-stu-id="a7ec6-115">The array is always created in the application domain in which the thread is currently running.</span></span> <span data-ttu-id="a7ec6-116">En .NET Framework 2.0, el valor de `rank` debe ser 1.</span><span class="sxs-lookup"><span data-stu-id="a7ec6-116">In the .NET Framework 2.0, the value of `rank` must be 1.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a7ec6-117">Requisitos</span><span class="sxs-lookup"><span data-stu-id="a7ec6-117">Requirements</span></span>  
 <span data-ttu-id="a7ec6-118">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a7ec6-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a7ec6-119">**Encabezado**: CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="a7ec6-119">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="a7ec6-120">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a7ec6-120">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a7ec6-121">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a7ec6-121">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
