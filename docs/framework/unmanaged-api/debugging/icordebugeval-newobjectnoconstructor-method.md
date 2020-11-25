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
ms.openlocfilehash: bb27ec755fb83dc71af7dd48b5ed6e7699436335
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95729734"
---
# <a name="icordebugevalnewobjectnoconstructor-method"></a><span data-ttu-id="7f913-102">ICorDebugEval::NewObjectNoConstructor (Método)</span><span class="sxs-lookup"><span data-stu-id="7f913-102">ICorDebugEval::NewObjectNoConstructor Method</span></span>

<span data-ttu-id="7f913-103">Asigna una nueva instancia de objeto del tipo especificado, sin intentar llamar a un método de constructor.</span><span class="sxs-lookup"><span data-stu-id="7f913-103">Allocates a new object instance of the specified type, without attempting to call a constructor method.</span></span>  
  
 <span data-ttu-id="7f913-104">Este método está obsoleto en la .NET Framework versión 2,0.</span><span class="sxs-lookup"><span data-stu-id="7f913-104">This method is obsolete in the .NET Framework version 2.0.</span></span> <span data-ttu-id="7f913-105">Use [ICorDebugEval2:: newparameterizedobjectnoconstructor (](icordebugeval2-newparameterizedobjectnoconstructor-method.md) en su lugar.</span><span class="sxs-lookup"><span data-stu-id="7f913-105">Use [ICorDebugEval2::NewParameterizedObjectNoConstructor](icordebugeval2-newparameterizedobjectnoconstructor-method.md) instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7f913-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="7f913-106">Syntax</span></span>  
  
```cpp  
HRESULT NewObjectNoConstructor (  
    [in] ICorDebugClass     *pClass  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="7f913-107">Parámetros</span><span class="sxs-lookup"><span data-stu-id="7f913-107">Parameters</span></span>  

 `pClass`  
 <span data-ttu-id="7f913-108">de Puntero a un objeto ICorDebugClass que representa el tipo de objeto del que se va a crear una instancia.</span><span class="sxs-lookup"><span data-stu-id="7f913-108">[in] Pointer to an ICorDebugClass object that represents the type of object to be instantiated.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7f913-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="7f913-109">Requirements</span></span>  

 <span data-ttu-id="7f913-110">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7f913-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7f913-111">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="7f913-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="7f913-112">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="7f913-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="7f913-113">**.NET Framework versiones:** 1,1, 1,0</span><span class="sxs-lookup"><span data-stu-id="7f913-113">**.NET Framework Versions:** 1.1, 1.0</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7f913-114">Consulte también</span><span class="sxs-lookup"><span data-stu-id="7f913-114">See also</span></span>

- [<span data-ttu-id="7f913-115">Método NewParameterizedObjectNoConstructor</span><span class="sxs-lookup"><span data-stu-id="7f913-115">NewParameterizedObjectNoConstructor Method</span></span>](icordebugeval2-newparameterizedobjectnoconstructor-method.md)
