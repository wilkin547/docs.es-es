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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 9c2d6a66eca080b480b508afea36c33b3e0aeec0
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59178235"
---
# <a name="icordebugevalnewobject-method"></a><span data-ttu-id="a9603-102">ICorDebugEval::NewObject (Método)</span><span class="sxs-lookup"><span data-stu-id="a9603-102">ICorDebugEval::NewObject Method</span></span>
<span data-ttu-id="a9603-103">Asigna una nueva instancia de objeto y llama al método de constructor especificado.</span><span class="sxs-lookup"><span data-stu-id="a9603-103">Allocates a new object instance and calls the specified constructor method.</span></span>  
  
 <span data-ttu-id="a9603-104">Este método está obsoleto en .NET Framework versión 2.0.</span><span class="sxs-lookup"><span data-stu-id="a9603-104">This method is obsolete in the .NET Framework version 2.0.</span></span> <span data-ttu-id="a9603-105">Use [ICorDebugEval2:: NewParameterizedObject](../../../../docs/framework/unmanaged-api/debugging/icordebugeval2-newparameterizedobject-method.md) en su lugar.</span><span class="sxs-lookup"><span data-stu-id="a9603-105">Use [ICorDebugEval2::NewParameterizedObject](../../../../docs/framework/unmanaged-api/debugging/icordebugeval2-newparameterizedobject-method.md) instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a9603-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="a9603-106">Syntax</span></span>  
  
```  
HRESULT NewObject (  
    [in] ICorDebugFunction  *pConstructor,  
    [in] ULONG32            nArgs,  
    [in, size_is(nArgs)] ICorDebugValue *ppArgs[]  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a9603-107">Parámetros</span><span class="sxs-lookup"><span data-stu-id="a9603-107">Parameters</span></span>  
 `pConstructor`  
 <span data-ttu-id="a9603-108">[in] El constructor para llamarlo.</span><span class="sxs-lookup"><span data-stu-id="a9603-108">[in] The constructor to be called.</span></span>  
  
 `nArgs`  
 <span data-ttu-id="a9603-109">[in] Tamaño de la matriz `ppArgs`.</span><span class="sxs-lookup"><span data-stu-id="a9603-109">[in] The size of the `ppArgs` array.</span></span>  
  
 `ppArgs`  
 <span data-ttu-id="a9603-110">[in] Una matriz de objetos ICorDebugValue, cada uno de los cuales representa un argumento que se pasa al constructor.</span><span class="sxs-lookup"><span data-stu-id="a9603-110">[in] An array of ICorDebugValue objects, each of which represents an argument to be passed to the constructor.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a9603-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="a9603-111">Requirements</span></span>  
 <span data-ttu-id="a9603-112">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a9603-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a9603-113">**Encabezado**: CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="a9603-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="a9603-114">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a9603-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a9603-115">**Versiones de .NET framework:** 1.1, 1.0</span><span class="sxs-lookup"><span data-stu-id="a9603-115">**.NET Framework Versions:** 1.1, 1.0</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a9603-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="a9603-116">See also</span></span>

- [<span data-ttu-id="a9603-117">NewParameterizedObject (método)</span><span class="sxs-lookup"><span data-stu-id="a9603-117">NewParameterizedObject Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugeval2-newparameterizedobject-method.md)
