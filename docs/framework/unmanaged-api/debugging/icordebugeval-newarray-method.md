---
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
ms.openlocfilehash: 496a6a7e01dec8aa90ba4e849c431ccd499ef53d
ms.sourcegitcommit: fff146ba3fd1762c8c432d95c8b877825ae536fc
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/08/2020
ms.locfileid: "82976205"
---
# <a name="icordebugevalnewarray-method"></a><span data-ttu-id="e2b07-102">ICorDebugEval::NewArray (Método)</span><span class="sxs-lookup"><span data-stu-id="e2b07-102">ICorDebugEval::NewArray Method</span></span>
<span data-ttu-id="e2b07-103">Asigna una nueva matriz del tipo de elemento y las dimensiones especificadas.</span><span class="sxs-lookup"><span data-stu-id="e2b07-103">Allocates a new array of the specified element type and dimensions.</span></span>  
  
 <span data-ttu-id="e2b07-104">Este método está obsoleto en la .NET Framework versión 2,0.</span><span class="sxs-lookup"><span data-stu-id="e2b07-104">This method is obsolete in the .NET Framework version 2.0.</span></span> <span data-ttu-id="e2b07-105">Use [ICorDebugEval2:: NewParameterizedArray (](icordebugeval2-newparameterizedarray-method.md) en su lugar.</span><span class="sxs-lookup"><span data-stu-id="e2b07-105">Use [ICorDebugEval2::NewParameterizedArray](icordebugeval2-newparameterizedarray-method.md) instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e2b07-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="e2b07-106">Syntax</span></span>  
  
```cpp  
HRESULT NewArray (  
    [in] CorElementType     elementType,  
    [in] ICorDebugClass     *pElementClass,  
    [in] ULONG32            rank,  
    [in, size_is(rank)] ULONG32 dims[],  
    [in, size_is(rank)] ULONG32 lowBounds[]  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e2b07-107">Parámetros</span><span class="sxs-lookup"><span data-stu-id="e2b07-107">Parameters</span></span>  
 `elementType`  
 <span data-ttu-id="e2b07-108">de Un valor de la enumeración CorElementType que especifica el tipo de elemento de la matriz.</span><span class="sxs-lookup"><span data-stu-id="e2b07-108">[in] A value of the CorElementType enumeration that specifies the element type of the array.</span></span>  
  
 `pElementClass`  
 <span data-ttu-id="e2b07-109">de Un puntero a un objeto ICorDebugClass que especifica la clase del elemento.</span><span class="sxs-lookup"><span data-stu-id="e2b07-109">[in] A pointer to a ICorDebugClass object that specifies the class of the element.</span></span> <span data-ttu-id="e2b07-110">Este valor puede ser null si el tipo de elemento es un tipo primitivo.</span><span class="sxs-lookup"><span data-stu-id="e2b07-110">This value may be null if the element type is a primitive type.</span></span>  
  
 `rank`  
 <span data-ttu-id="e2b07-111">de Número de dimensiones de la matriz.</span><span class="sxs-lookup"><span data-stu-id="e2b07-111">[in] The number of dimensions of the array.</span></span> <span data-ttu-id="e2b07-112">En el .NET Framework 2,0, este valor debe ser 1.</span><span class="sxs-lookup"><span data-stu-id="e2b07-112">In the .NET Framework 2.0, this value must be 1.</span></span>  
  
 `dims`  
 <span data-ttu-id="e2b07-113">de Tamaño, en bytes, de cada dimensión de la matriz.</span><span class="sxs-lookup"><span data-stu-id="e2b07-113">[in] The size, in bytes, of each dimension of the array.</span></span>  
  
 `lowBounds`  
 <span data-ttu-id="e2b07-114">[in] Opcional.</span><span class="sxs-lookup"><span data-stu-id="e2b07-114">[in] Optional.</span></span> <span data-ttu-id="e2b07-115">Límite inferior de cada dimensión de la matriz.</span><span class="sxs-lookup"><span data-stu-id="e2b07-115">The lower bound of each dimension of the array.</span></span> <span data-ttu-id="e2b07-116">Si se omite este valor, se supone un límite inferior de cero para cada dimensión.</span><span class="sxs-lookup"><span data-stu-id="e2b07-116">If this value is omitted, a lower bound of zero is assumed for each dimension.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e2b07-117">Observaciones</span><span class="sxs-lookup"><span data-stu-id="e2b07-117">Remarks</span></span>  
 <span data-ttu-id="e2b07-118">La matriz siempre se crea en el dominio de aplicación en el que se está ejecutando el subproceso.</span><span class="sxs-lookup"><span data-stu-id="e2b07-118">The array is always created in the application domain in which the thread is currently executing.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e2b07-119">Requisitos</span><span class="sxs-lookup"><span data-stu-id="e2b07-119">Requirements</span></span>  
 <span data-ttu-id="e2b07-120">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e2b07-120">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e2b07-121">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="e2b07-121">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="e2b07-122">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e2b07-122">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e2b07-123">**.NET Framework versiones:** 1,1, 1,0</span><span class="sxs-lookup"><span data-stu-id="e2b07-123">**.NET Framework Versions:** 1.1, 1.0</span></span>
