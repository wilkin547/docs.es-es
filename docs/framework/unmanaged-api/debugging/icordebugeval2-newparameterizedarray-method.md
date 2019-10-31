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
ms.openlocfilehash: 9476bcc9706e89fd3d7e0abc14031f70a0aa0ad0
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73084833"
---
# <a name="icordebugeval2newparameterizedarray-method"></a><span data-ttu-id="ab1b2-102">ICorDebugEval2::NewParameterizedArray (Método)</span><span class="sxs-lookup"><span data-stu-id="ab1b2-102">ICorDebugEval2::NewParameterizedArray Method</span></span>
<span data-ttu-id="ab1b2-103">Asigna una nueva matriz del tipo de elemento y las dimensiones especificadas.</span><span class="sxs-lookup"><span data-stu-id="ab1b2-103">Allocates a new array of the specified element type and dimensions.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ab1b2-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="ab1b2-104">Syntax</span></span>  
  
```cpp  
HRESULT NewParameterizedArray(  
    [in] ICorDebugType          *pElementType,  
    [in] ULONG32                rank,  
    [in, size_is(rank)] ULONG32 dims[],  
    [in, size_is(rank)] ULONG32 lowBounds[]  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ab1b2-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="ab1b2-105">Parameters</span></span>  
 `pElementType`  
 <span data-ttu-id="ab1b2-106">de Un puntero a un objeto ICorDebugType que representa el tipo de elemento almacenado en la matriz.</span><span class="sxs-lookup"><span data-stu-id="ab1b2-106">[in] A pointer to an ICorDebugType object that represents the type of element stored in the array.</span></span>  
  
 `rank`  
 <span data-ttu-id="ab1b2-107">de Número de dimensiones de la matriz.</span><span class="sxs-lookup"><span data-stu-id="ab1b2-107">[in] The number of dimensions of the array.</span></span> <span data-ttu-id="ab1b2-108">En la .NET Framework versión 2,0, este valor debe ser 1.</span><span class="sxs-lookup"><span data-stu-id="ab1b2-108">In the .NET Framework version 2.0, this value must be 1.</span></span>  
  
 `dims`  
 <span data-ttu-id="ab1b2-109">de Tamaño, en bytes, de cada dimensión de la matriz.</span><span class="sxs-lookup"><span data-stu-id="ab1b2-109">[in] The size, in bytes, of each dimension of the array.</span></span>  
  
 `lowBounds`  
 <span data-ttu-id="ab1b2-110">[in] Opcional.</span><span class="sxs-lookup"><span data-stu-id="ab1b2-110">[in] Optional.</span></span> <span data-ttu-id="ab1b2-111">Límite inferior de cada dimensión de la matriz.</span><span class="sxs-lookup"><span data-stu-id="ab1b2-111">The lower bound of each dimension of the array.</span></span> <span data-ttu-id="ab1b2-112">Si se omite este valor, se supone un límite inferior de cero para cada dimensión.</span><span class="sxs-lookup"><span data-stu-id="ab1b2-112">If this value is omitted, a lower bound of zero is assumed for each dimension.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ab1b2-113">Comentarios</span><span class="sxs-lookup"><span data-stu-id="ab1b2-113">Remarks</span></span>  
 <span data-ttu-id="ab1b2-114">Los elementos de la matriz pueden ser instancias de un tipo genérico.</span><span class="sxs-lookup"><span data-stu-id="ab1b2-114">The elements of the array may be instances of a generic type.</span></span> <span data-ttu-id="ab1b2-115">La matriz siempre se crea en el dominio de aplicación en el que el subproceso se está ejecutando actualmente.</span><span class="sxs-lookup"><span data-stu-id="ab1b2-115">The array is always created in the application domain in which the thread is currently running.</span></span> <span data-ttu-id="ab1b2-116">En el .NET Framework 2,0, el valor de `rank` debe ser 1.</span><span class="sxs-lookup"><span data-stu-id="ab1b2-116">In the .NET Framework 2.0, the value of `rank` must be 1.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ab1b2-117">Requisitos</span><span class="sxs-lookup"><span data-stu-id="ab1b2-117">Requirements</span></span>  
 <span data-ttu-id="ab1b2-118">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ab1b2-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ab1b2-119">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="ab1b2-119">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="ab1b2-120">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ab1b2-120">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ab1b2-121">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ab1b2-121">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
