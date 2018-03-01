---
title: "ICorDebugEval2::NewParameterizedObjectNoConstructor (Método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- ICorDebugEval2.NewParameterizedObjectNoConstructor
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugEval2::NewParameterizedObjectNoConstructor
helpviewer_keywords:
- NewParameterizedObjectNoConstructor method [.NET Framework debugging]
- ICorDebugEval2::NewParameterizedObjectNoConstructor method [.NET Framework debugging]
ms.assetid: f15b5b78-94f4-4eb9-b3b3-a621272f357c
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 27e4693b39f9ce27ac18eb2fa542b5a0196f21cb
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugeval2newparameterizedobjectnoconstructor-method"></a><span data-ttu-id="f1ed0-102">ICorDebugEval2::NewParameterizedObjectNoConstructor (Método)</span><span class="sxs-lookup"><span data-stu-id="f1ed0-102">ICorDebugEval2::NewParameterizedObjectNoConstructor Method</span></span>
<span data-ttu-id="f1ed0-103">Crea un nuevo objeto de tipo parametrizado de la clase especificada sin intentar llamar a un método de constructor.</span><span class="sxs-lookup"><span data-stu-id="f1ed0-103">Instantiates a new parameterized type object of the specified class without attempting to call a constructor method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f1ed0-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="f1ed0-104">Syntax</span></span>  
  
```  
HRESULT NewParameterizedObjectNoConstructor (  
    [in] ICorDebugClass        *pClass,  
    [in] ULONG32               nTypeArgs,  
    [in, size_is(nTypeArgs)] ICorDebugType *ppTypeArgs[]  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="f1ed0-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="f1ed0-105">Parameters</span></span>  
 `pClass`  
 <span data-ttu-id="f1ed0-106">[in] Un puntero a un objeto ICorDebugClass que representa la clase del objeto que se pueden crear instancias.</span><span class="sxs-lookup"><span data-stu-id="f1ed0-106">[in] A pointer to an ICorDebugClass object that represents the class of the object to be instantiated.</span></span>  
  
 `nTypeArgs`  
 <span data-ttu-id="f1ed0-107">[in] El número de argumentos de tipo pasados.</span><span class="sxs-lookup"><span data-stu-id="f1ed0-107">[in] The number of type arguments passed.</span></span>  
  
 `ppTypeArgs`  
 <span data-ttu-id="f1ed0-108">[in] Una matriz de punteros, cada uno de los cuales señala a un objeto ICorDebugType que representa un argumento de tipo para el objeto que se crea una instancia.</span><span class="sxs-lookup"><span data-stu-id="f1ed0-108">[in] An array of pointers, each of which points to an ICorDebugType object that represents a type argument for the object that is being instantiated.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f1ed0-109">Comentarios</span><span class="sxs-lookup"><span data-stu-id="f1ed0-109">Remarks</span></span>  
 <span data-ttu-id="f1ed0-110">El `NewParameterizedObjectNoConstructor` método se producirá un error si un número incorrecto de argumentos de tipo o si se pasan los tipos de argumentos de tipo incorrectos.</span><span class="sxs-lookup"><span data-stu-id="f1ed0-110">The `NewParameterizedObjectNoConstructor` method will fail if an incorrect number of type arguments or the wrong types of type arguments are passed.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f1ed0-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="f1ed0-111">Requirements</span></span>  
 <span data-ttu-id="f1ed0-112">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f1ed0-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f1ed0-113">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="f1ed0-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="f1ed0-114">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f1ed0-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f1ed0-115">**Versiones de .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f1ed0-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
