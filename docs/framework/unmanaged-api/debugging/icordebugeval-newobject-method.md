---
description: 'Más información acerca de: ICorDebugEval:: NewObject (método)'
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
ms.openlocfilehash: 0f7feb53d061e5dbc453015772b97f2a5a59bbb3
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99693959"
---
# <a name="icordebugevalnewobject-method"></a><span data-ttu-id="975e9-103">ICorDebugEval::NewObject (Método)</span><span class="sxs-lookup"><span data-stu-id="975e9-103">ICorDebugEval::NewObject Method</span></span>

<span data-ttu-id="975e9-104">Asigna una nueva instancia de objeto y llama al método de constructor especificado.</span><span class="sxs-lookup"><span data-stu-id="975e9-104">Allocates a new object instance and calls the specified constructor method.</span></span>  
  
 <span data-ttu-id="975e9-105">Este método está obsoleto en la .NET Framework versión 2,0.</span><span class="sxs-lookup"><span data-stu-id="975e9-105">This method is obsolete in the .NET Framework version 2.0.</span></span> <span data-ttu-id="975e9-106">Use [ICorDebugEval2:: NewParameterizedObject (](icordebugeval2-newparameterizedobject-method.md) en su lugar.</span><span class="sxs-lookup"><span data-stu-id="975e9-106">Use [ICorDebugEval2::NewParameterizedObject](icordebugeval2-newparameterizedobject-method.md) instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="975e9-107">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="975e9-107">Syntax</span></span>  
  
```cpp  
HRESULT NewObject (  
    [in] ICorDebugFunction  *pConstructor,  
    [in] ULONG32            nArgs,  
    [in, size_is(nArgs)] ICorDebugValue *ppArgs[]  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="975e9-108">Parámetros</span><span class="sxs-lookup"><span data-stu-id="975e9-108">Parameters</span></span>  

 `pConstructor`  
 <span data-ttu-id="975e9-109">de Constructor al que se va a llamar.</span><span class="sxs-lookup"><span data-stu-id="975e9-109">[in] The constructor to be called.</span></span>  
  
 `nArgs`  
 <span data-ttu-id="975e9-110">[in] Tamaño de la matriz `ppArgs`.</span><span class="sxs-lookup"><span data-stu-id="975e9-110">[in] The size of the `ppArgs` array.</span></span>  
  
 `ppArgs`  
 <span data-ttu-id="975e9-111">de Una matriz de objetos ICorDebugValue, cada uno de los cuales representa un argumento que se va a pasar al constructor.</span><span class="sxs-lookup"><span data-stu-id="975e9-111">[in] An array of ICorDebugValue objects, each of which represents an argument to be passed to the constructor.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="975e9-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="975e9-112">Requirements</span></span>  

 <span data-ttu-id="975e9-113">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="975e9-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="975e9-114">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="975e9-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="975e9-115">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="975e9-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="975e9-116">**.NET Framework versiones:** 1,1, 1,0</span><span class="sxs-lookup"><span data-stu-id="975e9-116">**.NET Framework Versions:** 1.1, 1.0</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="975e9-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="975e9-117">See also</span></span>

- [<span data-ttu-id="975e9-118">Método NewParameterizedObject</span><span class="sxs-lookup"><span data-stu-id="975e9-118">NewParameterizedObject Method</span></span>](icordebugeval2-newparameterizedobject-method.md)
