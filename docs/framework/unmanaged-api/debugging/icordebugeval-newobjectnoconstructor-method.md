---
title: ICorDebugEval::NewObjectNoConstructor (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugEval.NewObjectNoConstructor
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugEval::NewObjectNoConstructor
helpviewer_keywords:
- NewObjectNoConstructor method [.NET Framework debugging]
- ICorDebugEval::NewObjectNoConstructor method [.NET Framework debugging]
ms.assetid: 80d509ca-b5e3-4c46-9c14-800db73d9bf7
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 6846b866fd47674ca6b5fd187b580fd28e080fd0
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59162311"
---
# <a name="icordebugevalnewobjectnoconstructor-method"></a><span data-ttu-id="ffacb-102">ICorDebugEval::NewObjectNoConstructor (Método)</span><span class="sxs-lookup"><span data-stu-id="ffacb-102">ICorDebugEval::NewObjectNoConstructor Method</span></span>
<span data-ttu-id="ffacb-103">Asigna una nueva instancia de objeto del tipo especificado, sin intentar llamar a un método de constructor.</span><span class="sxs-lookup"><span data-stu-id="ffacb-103">Allocates a new object instance of the specified type, without attempting to call a constructor method.</span></span>  
  
 <span data-ttu-id="ffacb-104">Este método está obsoleto en .NET Framework versión 2.0.</span><span class="sxs-lookup"><span data-stu-id="ffacb-104">This method is obsolete in the .NET Framework version 2.0.</span></span> <span data-ttu-id="ffacb-105">Use [ICorDebugEval2:: NewParameterizedObjectNoConstructor](../../../../docs/framework/unmanaged-api/debugging/icordebugeval2-newparameterizedobjectnoconstructor-method.md) en su lugar.</span><span class="sxs-lookup"><span data-stu-id="ffacb-105">Use [ICorDebugEval2::NewParameterizedObjectNoConstructor](../../../../docs/framework/unmanaged-api/debugging/icordebugeval2-newparameterizedobjectnoconstructor-method.md) instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ffacb-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="ffacb-106">Syntax</span></span>  
  
```  
HRESULT NewObjectNoConstructor (  
    [in] ICorDebugClass     *pClass  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ffacb-107">Parámetros</span><span class="sxs-lookup"><span data-stu-id="ffacb-107">Parameters</span></span>  
 `pClass`  
 <span data-ttu-id="ffacb-108">[in] Puntero a un objeto ICorDebugClass que representa el tipo de objeto que se creará una instancia.</span><span class="sxs-lookup"><span data-stu-id="ffacb-108">[in] Pointer to an ICorDebugClass object that represents the type of object to be instantiated.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ffacb-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="ffacb-109">Requirements</span></span>  
 <span data-ttu-id="ffacb-110">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ffacb-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ffacb-111">**Encabezado**: CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="ffacb-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="ffacb-112">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ffacb-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ffacb-113">**Versiones de .NET framework:** 1.1, 1.0</span><span class="sxs-lookup"><span data-stu-id="ffacb-113">**.NET Framework Versions:** 1.1, 1.0</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ffacb-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="ffacb-114">See also</span></span>

- [<span data-ttu-id="ffacb-115">Método NewParameterizedObjectNoConstructor</span><span class="sxs-lookup"><span data-stu-id="ffacb-115">NewParameterizedObjectNoConstructor Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugeval2-newparameterizedobjectnoconstructor-method.md)
