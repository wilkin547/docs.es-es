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
ms.openlocfilehash: 93fff7ec315edec8b20b4149650b27e7792fb2f1
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/06/2019
ms.locfileid: "57475052"
---
# <a name="icordebugevalnewobjectnoconstructor-method"></a><span data-ttu-id="79a63-102">ICorDebugEval::NewObjectNoConstructor (Método)</span><span class="sxs-lookup"><span data-stu-id="79a63-102">ICorDebugEval::NewObjectNoConstructor Method</span></span>
<span data-ttu-id="79a63-103">Asigna una nueva instancia de objeto del tipo especificado, sin intentar llamar a un método de constructor.</span><span class="sxs-lookup"><span data-stu-id="79a63-103">Allocates a new object instance of the specified type, without attempting to call a constructor method.</span></span>  
  
 <span data-ttu-id="79a63-104">Este método está obsoleto en .NET Framework versión 2.0.</span><span class="sxs-lookup"><span data-stu-id="79a63-104">This method is obsolete in the .NET Framework version 2.0.</span></span> <span data-ttu-id="79a63-105">Use [ICorDebugEval2:: NewParameterizedObjectNoConstructor](../../../../docs/framework/unmanaged-api/debugging/icordebugeval2-newparameterizedobjectnoconstructor-method.md) en su lugar.</span><span class="sxs-lookup"><span data-stu-id="79a63-105">Use [ICorDebugEval2::NewParameterizedObjectNoConstructor](../../../../docs/framework/unmanaged-api/debugging/icordebugeval2-newparameterizedobjectnoconstructor-method.md) instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="79a63-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="79a63-106">Syntax</span></span>  
  
```  
HRESULT NewObjectNoConstructor (  
    [in] ICorDebugClass     *pClass  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="79a63-107">Parámetros</span><span class="sxs-lookup"><span data-stu-id="79a63-107">Parameters</span></span>  
 `pClass`  
 <span data-ttu-id="79a63-108">[in] Puntero a un objeto ICorDebugClass que representa el tipo de objeto que se creará una instancia.</span><span class="sxs-lookup"><span data-stu-id="79a63-108">[in] Pointer to an ICorDebugClass object that represents the type of object to be instantiated.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="79a63-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="79a63-109">Requirements</span></span>  
 <span data-ttu-id="79a63-110">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="79a63-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="79a63-111">**Encabezado**: CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="79a63-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="79a63-112">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="79a63-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="79a63-113">**Versiones de .NET framework:** 1.1, 1.0</span><span class="sxs-lookup"><span data-stu-id="79a63-113">**.NET Framework Versions:** 1.1, 1.0</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="79a63-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="79a63-114">See also</span></span>
- [<span data-ttu-id="79a63-115">NewParameterizedObjectNoConstructor (método)</span><span class="sxs-lookup"><span data-stu-id="79a63-115">NewParameterizedObjectNoConstructor Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugeval2-newparameterizedobjectnoconstructor-method.md)
