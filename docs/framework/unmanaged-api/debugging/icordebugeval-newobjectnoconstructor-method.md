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
ms.openlocfilehash: 45efa1939813a319e996a72fef62ada167b877c2
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/28/2020
ms.locfileid: "76788693"
---
# <a name="icordebugevalnewobjectnoconstructor-method"></a><span data-ttu-id="791e2-102">ICorDebugEval::NewObjectNoConstructor (Método)</span><span class="sxs-lookup"><span data-stu-id="791e2-102">ICorDebugEval::NewObjectNoConstructor Method</span></span>
<span data-ttu-id="791e2-103">Asigna una nueva instancia de objeto del tipo especificado, sin intentar llamar a un método de constructor.</span><span class="sxs-lookup"><span data-stu-id="791e2-103">Allocates a new object instance of the specified type, without attempting to call a constructor method.</span></span>  
  
 <span data-ttu-id="791e2-104">Este método está obsoleto en la .NET Framework versión 2,0.</span><span class="sxs-lookup"><span data-stu-id="791e2-104">This method is obsolete in the .NET Framework version 2.0.</span></span> <span data-ttu-id="791e2-105">Use [ICorDebugEval2:: newparameterizedobjectnoconstructor (](icordebugeval2-newparameterizedobjectnoconstructor-method.md) en su lugar.</span><span class="sxs-lookup"><span data-stu-id="791e2-105">Use [ICorDebugEval2::NewParameterizedObjectNoConstructor](icordebugeval2-newparameterizedobjectnoconstructor-method.md) instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="791e2-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="791e2-106">Syntax</span></span>  
  
```cpp  
HRESULT NewObjectNoConstructor (  
    [in] ICorDebugClass     *pClass  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="791e2-107">Parameters</span><span class="sxs-lookup"><span data-stu-id="791e2-107">Parameters</span></span>  
 `pClass`  
 <span data-ttu-id="791e2-108">de Puntero a un objeto ICorDebugClass que representa el tipo de objeto del que se va a crear una instancia.</span><span class="sxs-lookup"><span data-stu-id="791e2-108">[in] Pointer to an ICorDebugClass object that represents the type of object to be instantiated.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="791e2-109">Requisitos de</span><span class="sxs-lookup"><span data-stu-id="791e2-109">Requirements</span></span>  
 <span data-ttu-id="791e2-110">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="791e2-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="791e2-111">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="791e2-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="791e2-112">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="791e2-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="791e2-113">**.NET Framework versiones:** 1,1, 1,0</span><span class="sxs-lookup"><span data-stu-id="791e2-113">**.NET Framework Versions:** 1.1, 1.0</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="791e2-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="791e2-114">See also</span></span>

- [<span data-ttu-id="791e2-115">NewParameterizedObjectNoConstructor (método)</span><span class="sxs-lookup"><span data-stu-id="791e2-115">NewParameterizedObjectNoConstructor Method</span></span>](icordebugeval2-newparameterizedobjectnoconstructor-method.md)
