---
description: 'Más información acerca de: ICorDebugEval:: Newobjectnoconstructor ((método)'
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
ms.openlocfilehash: 4bc8f95da1a554091052dc7e7f49aef4f494578d
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99693816"
---
# <a name="icordebugevalnewobjectnoconstructor-method"></a><span data-ttu-id="07e04-103">ICorDebugEval::NewObjectNoConstructor (Método)</span><span class="sxs-lookup"><span data-stu-id="07e04-103">ICorDebugEval::NewObjectNoConstructor Method</span></span>

<span data-ttu-id="07e04-104">Asigna una nueva instancia de objeto del tipo especificado, sin intentar llamar a un método de constructor.</span><span class="sxs-lookup"><span data-stu-id="07e04-104">Allocates a new object instance of the specified type, without attempting to call a constructor method.</span></span>  
  
 <span data-ttu-id="07e04-105">Este método está obsoleto en la .NET Framework versión 2,0.</span><span class="sxs-lookup"><span data-stu-id="07e04-105">This method is obsolete in the .NET Framework version 2.0.</span></span> <span data-ttu-id="07e04-106">Use [ICorDebugEval2:: newparameterizedobjectnoconstructor (](icordebugeval2-newparameterizedobjectnoconstructor-method.md) en su lugar.</span><span class="sxs-lookup"><span data-stu-id="07e04-106">Use [ICorDebugEval2::NewParameterizedObjectNoConstructor](icordebugeval2-newparameterizedobjectnoconstructor-method.md) instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="07e04-107">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="07e04-107">Syntax</span></span>  
  
```cpp  
HRESULT NewObjectNoConstructor (  
    [in] ICorDebugClass     *pClass  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="07e04-108">Parámetros</span><span class="sxs-lookup"><span data-stu-id="07e04-108">Parameters</span></span>  

 `pClass`  
 <span data-ttu-id="07e04-109">de Puntero a un objeto ICorDebugClass que representa el tipo de objeto del que se va a crear una instancia.</span><span class="sxs-lookup"><span data-stu-id="07e04-109">[in] Pointer to an ICorDebugClass object that represents the type of object to be instantiated.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="07e04-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="07e04-110">Requirements</span></span>  

 <span data-ttu-id="07e04-111">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="07e04-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="07e04-112">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="07e04-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="07e04-113">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="07e04-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="07e04-114">**.NET Framework versiones:** 1,1, 1,0</span><span class="sxs-lookup"><span data-stu-id="07e04-114">**.NET Framework Versions:** 1.1, 1.0</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="07e04-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="07e04-115">See also</span></span>

- [<span data-ttu-id="07e04-116">Método NewParameterizedObjectNoConstructor</span><span class="sxs-lookup"><span data-stu-id="07e04-116">NewParameterizedObjectNoConstructor Method</span></span>](icordebugeval2-newparameterizedobjectnoconstructor-method.md)
