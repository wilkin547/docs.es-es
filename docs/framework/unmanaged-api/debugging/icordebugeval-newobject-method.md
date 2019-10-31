---
title: ICorDebugEval::NewObject (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugEval.NewObject
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugEval::NewObject
helpviewer_keywords:
- NewObject method [.NET Framework debugging]
- ICorDebugEval::NewObject method [.NET Framework debugging]
ms.assetid: ce3025e8-defa-4c5e-8298-f49d71fa5736
topic_type:
- apiref
ms.openlocfilehash: 68a7e911c2bd1798ea8f34f6a6e24299fe68775d
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73137622"
---
# <a name="icordebugevalnewobject-method"></a><span data-ttu-id="1c782-102">ICorDebugEval::NewObject (Método)</span><span class="sxs-lookup"><span data-stu-id="1c782-102">ICorDebugEval::NewObject Method</span></span>
<span data-ttu-id="1c782-103">Asigna una nueva instancia de objeto y llama al método de constructor especificado.</span><span class="sxs-lookup"><span data-stu-id="1c782-103">Allocates a new object instance and calls the specified constructor method.</span></span>  
  
 <span data-ttu-id="1c782-104">Este método está obsoleto en la .NET Framework versión 2,0.</span><span class="sxs-lookup"><span data-stu-id="1c782-104">This method is obsolete in the .NET Framework version 2.0.</span></span> <span data-ttu-id="1c782-105">Use [ICorDebugEval2:: NewParameterizedObject (](../../../../docs/framework/unmanaged-api/debugging/icordebugeval2-newparameterizedobject-method.md) en su lugar.</span><span class="sxs-lookup"><span data-stu-id="1c782-105">Use [ICorDebugEval2::NewParameterizedObject](../../../../docs/framework/unmanaged-api/debugging/icordebugeval2-newparameterizedobject-method.md) instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1c782-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="1c782-106">Syntax</span></span>  
  
```cpp  
HRESULT NewObject (  
    [in] ICorDebugFunction  *pConstructor,  
    [in] ULONG32            nArgs,  
    [in, size_is(nArgs)] ICorDebugValue *ppArgs[]  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="1c782-107">Parámetros</span><span class="sxs-lookup"><span data-stu-id="1c782-107">Parameters</span></span>  
 `pConstructor`  
 <span data-ttu-id="1c782-108">de Constructor al que se va a llamar.</span><span class="sxs-lookup"><span data-stu-id="1c782-108">[in] The constructor to be called.</span></span>  
  
 `nArgs`  
 <span data-ttu-id="1c782-109">[in] Tamaño de la matriz `ppArgs`.</span><span class="sxs-lookup"><span data-stu-id="1c782-109">[in] The size of the `ppArgs` array.</span></span>  
  
 `ppArgs`  
 <span data-ttu-id="1c782-110">de Una matriz de objetos ICorDebugValue, cada uno de los cuales representa un argumento que se va a pasar al constructor.</span><span class="sxs-lookup"><span data-stu-id="1c782-110">[in] An array of ICorDebugValue objects, each of which represents an argument to be passed to the constructor.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1c782-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="1c782-111">Requirements</span></span>  
 <span data-ttu-id="1c782-112">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1c782-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1c782-113">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="1c782-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="1c782-114">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="1c782-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="1c782-115">**.NET Framework versiones:** 1,1, 1,0</span><span class="sxs-lookup"><span data-stu-id="1c782-115">**.NET Framework Versions:** 1.1, 1.0</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1c782-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="1c782-116">See also</span></span>

- [<span data-ttu-id="1c782-117">NewParameterizedObject (método)</span><span class="sxs-lookup"><span data-stu-id="1c782-117">NewParameterizedObject Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugeval2-newparameterizedobject-method.md)
