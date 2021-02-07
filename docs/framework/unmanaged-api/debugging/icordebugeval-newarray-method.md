---
description: 'Más información acerca de: ICorDebugEval:: NewArray (método)'
title: ICorDebugEval::NewArray (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugEval.NewArray
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugEval::NewArray
helpviewer_keywords:
- NewArray method [.NET Framework debugging]
- ICorDebugEval::NewArray method [.NET Framework debugging]
ms.assetid: cc79a67d-5368-434d-a943-209db90491b9
topic_type:
- apiref
ms.openlocfilehash: 1344a99450974369533b1c54b641c036fc64e3ea
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99693985"
---
# <a name="icordebugevalnewarray-method"></a><span data-ttu-id="328aa-103">ICorDebugEval::NewArray (Método)</span><span class="sxs-lookup"><span data-stu-id="328aa-103">ICorDebugEval::NewArray Method</span></span>

<span data-ttu-id="328aa-104">Asigna una nueva matriz del tipo de elemento y las dimensiones especificadas.</span><span class="sxs-lookup"><span data-stu-id="328aa-104">Allocates a new array of the specified element type and dimensions.</span></span>  
  
 <span data-ttu-id="328aa-105">Este método está obsoleto en la .NET Framework versión 2,0.</span><span class="sxs-lookup"><span data-stu-id="328aa-105">This method is obsolete in the .NET Framework version 2.0.</span></span> <span data-ttu-id="328aa-106">Use [ICorDebugEval2:: NewParameterizedArray (](icordebugeval2-newparameterizedarray-method.md) en su lugar.</span><span class="sxs-lookup"><span data-stu-id="328aa-106">Use [ICorDebugEval2::NewParameterizedArray](icordebugeval2-newparameterizedarray-method.md) instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="328aa-107">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="328aa-107">Syntax</span></span>  
  
```cpp  
HRESULT NewArray (  
    [in] CorElementType     elementType,  
    [in] ICorDebugClass     *pElementClass,  
    [in] ULONG32            rank,  
    [in, size_is(rank)] ULONG32 dims[],  
    [in, size_is(rank)] ULONG32 lowBounds[]  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="328aa-108">Parámetros</span><span class="sxs-lookup"><span data-stu-id="328aa-108">Parameters</span></span>  

 `elementType`  
 <span data-ttu-id="328aa-109">de Un valor de la enumeración CorElementType que especifica el tipo de elemento de la matriz.</span><span class="sxs-lookup"><span data-stu-id="328aa-109">[in] A value of the CorElementType enumeration that specifies the element type of the array.</span></span>  
  
 `pElementClass`  
 <span data-ttu-id="328aa-110">de Un puntero a un objeto ICorDebugClass que especifica la clase del elemento.</span><span class="sxs-lookup"><span data-stu-id="328aa-110">[in] A pointer to a ICorDebugClass object that specifies the class of the element.</span></span> <span data-ttu-id="328aa-111">Este valor puede ser null si el tipo de elemento es un tipo primitivo.</span><span class="sxs-lookup"><span data-stu-id="328aa-111">This value may be null if the element type is a primitive type.</span></span>  
  
 `rank`  
 <span data-ttu-id="328aa-112">de Número de dimensiones de la matriz.</span><span class="sxs-lookup"><span data-stu-id="328aa-112">[in] The number of dimensions of the array.</span></span> <span data-ttu-id="328aa-113">En el .NET Framework 2,0, este valor debe ser 1.</span><span class="sxs-lookup"><span data-stu-id="328aa-113">In the .NET Framework 2.0, this value must be 1.</span></span>  
  
 `dims`  
 <span data-ttu-id="328aa-114">de Tamaño, en bytes, de cada dimensión de la matriz.</span><span class="sxs-lookup"><span data-stu-id="328aa-114">[in] The size, in bytes, of each dimension of the array.</span></span>  
  
 `lowBounds`  
 <span data-ttu-id="328aa-115">[in] Opcional.</span><span class="sxs-lookup"><span data-stu-id="328aa-115">[in] Optional.</span></span> <span data-ttu-id="328aa-116">Límite inferior de cada dimensión de la matriz.</span><span class="sxs-lookup"><span data-stu-id="328aa-116">The lower bound of each dimension of the array.</span></span> <span data-ttu-id="328aa-117">Si se omite este valor, se supone un límite inferior de cero para cada dimensión.</span><span class="sxs-lookup"><span data-stu-id="328aa-117">If this value is omitted, a lower bound of zero is assumed for each dimension.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="328aa-118">Observaciones</span><span class="sxs-lookup"><span data-stu-id="328aa-118">Remarks</span></span>  

 <span data-ttu-id="328aa-119">La matriz siempre se crea en el dominio de aplicación en el que se está ejecutando el subproceso.</span><span class="sxs-lookup"><span data-stu-id="328aa-119">The array is always created in the application domain in which the thread is currently executing.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="328aa-120">Requisitos</span><span class="sxs-lookup"><span data-stu-id="328aa-120">Requirements</span></span>  

 <span data-ttu-id="328aa-121">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="328aa-121">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="328aa-122">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="328aa-122">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="328aa-123">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="328aa-123">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="328aa-124">**.NET Framework versiones:** 1,1, 1,0</span><span class="sxs-lookup"><span data-stu-id="328aa-124">**.NET Framework Versions:** 1.1, 1.0</span></span>
