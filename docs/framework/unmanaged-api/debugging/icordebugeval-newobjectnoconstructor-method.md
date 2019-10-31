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
ms.openlocfilehash: 255d88dcdd880c73a7535cddcad410dcfdcf1d70
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73132661"
---
# <a name="icordebugevalnewobjectnoconstructor-method"></a><span data-ttu-id="7655a-102">ICorDebugEval::NewObjectNoConstructor (Método)</span><span class="sxs-lookup"><span data-stu-id="7655a-102">ICorDebugEval::NewObjectNoConstructor Method</span></span>
<span data-ttu-id="7655a-103">Asigna una nueva instancia de objeto del tipo especificado, sin intentar llamar a un método de constructor.</span><span class="sxs-lookup"><span data-stu-id="7655a-103">Allocates a new object instance of the specified type, without attempting to call a constructor method.</span></span>  
  
 <span data-ttu-id="7655a-104">Este método está obsoleto en la .NET Framework versión 2,0.</span><span class="sxs-lookup"><span data-stu-id="7655a-104">This method is obsolete in the .NET Framework version 2.0.</span></span> <span data-ttu-id="7655a-105">Use [ICorDebugEval2:: newparameterizedobjectnoconstructor (](../../../../docs/framework/unmanaged-api/debugging/icordebugeval2-newparameterizedobjectnoconstructor-method.md) en su lugar.</span><span class="sxs-lookup"><span data-stu-id="7655a-105">Use [ICorDebugEval2::NewParameterizedObjectNoConstructor](../../../../docs/framework/unmanaged-api/debugging/icordebugeval2-newparameterizedobjectnoconstructor-method.md) instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7655a-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="7655a-106">Syntax</span></span>  
  
```cpp  
HRESULT NewObjectNoConstructor (  
    [in] ICorDebugClass     *pClass  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="7655a-107">Parámetros</span><span class="sxs-lookup"><span data-stu-id="7655a-107">Parameters</span></span>  
 `pClass`  
 <span data-ttu-id="7655a-108">de Puntero a un objeto ICorDebugClass que representa el tipo de objeto del que se va a crear una instancia.</span><span class="sxs-lookup"><span data-stu-id="7655a-108">[in] Pointer to an ICorDebugClass object that represents the type of object to be instantiated.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7655a-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="7655a-109">Requirements</span></span>  
 <span data-ttu-id="7655a-110">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7655a-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7655a-111">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="7655a-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="7655a-112">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="7655a-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="7655a-113">**.NET Framework versiones:** 1,1, 1,0</span><span class="sxs-lookup"><span data-stu-id="7655a-113">**.NET Framework Versions:** 1.1, 1.0</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7655a-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="7655a-114">See also</span></span>

- [<span data-ttu-id="7655a-115">NewParameterizedObjectNoConstructor (método)</span><span class="sxs-lookup"><span data-stu-id="7655a-115">NewParameterizedObjectNoConstructor Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugeval2-newparameterizedobjectnoconstructor-method.md)
