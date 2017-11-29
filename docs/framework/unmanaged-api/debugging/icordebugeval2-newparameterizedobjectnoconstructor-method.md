---
title: "ICorDebugEval2::NewParameterizedObjectNoConstructor (Método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugEval2.NewParameterizedObjectNoConstructor
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugEval2::NewParameterizedObjectNoConstructor
helpviewer_keywords:
- NewParameterizedObjectNoConstructor method [.NET Framework debugging]
- ICorDebugEval2::NewParameterizedObjectNoConstructor method [.NET Framework debugging]
ms.assetid: f15b5b78-94f4-4eb9-b3b3-a621272f357c
topic_type: apiref
caps.latest.revision: "12"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 94cf9e0596e8e5cbd59da319247ced6780d0accb
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="icordebugeval2newparameterizedobjectnoconstructor-method"></a><span data-ttu-id="df967-102">ICorDebugEval2::NewParameterizedObjectNoConstructor (Método)</span><span class="sxs-lookup"><span data-stu-id="df967-102">ICorDebugEval2::NewParameterizedObjectNoConstructor Method</span></span>
<span data-ttu-id="df967-103">Crea un nuevo objeto de tipo parametrizado de la clase especificada sin intentar llamar a un método de constructor.</span><span class="sxs-lookup"><span data-stu-id="df967-103">Instantiates a new parameterized type object of the specified class without attempting to call a constructor method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="df967-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="df967-104">Syntax</span></span>  
  
```  
HRESULT NewParameterizedObjectNoConstructor (  
    [in] ICorDebugClass        *pClass,  
    [in] ULONG32               nTypeArgs,  
    [in, size_is(nTypeArgs)] ICorDebugType *ppTypeArgs[]  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="df967-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="df967-105">Parameters</span></span>  
 `pClass`  
 <span data-ttu-id="df967-106">[in] Un puntero a un objeto ICorDebugClass que representa la clase del objeto que se pueden crear instancias.</span><span class="sxs-lookup"><span data-stu-id="df967-106">[in] A pointer to an ICorDebugClass object that represents the class of the object to be instantiated.</span></span>  
  
 `nTypeArgs`  
 <span data-ttu-id="df967-107">[in] El número de argumentos de tipo pasados.</span><span class="sxs-lookup"><span data-stu-id="df967-107">[in] The number of type arguments passed.</span></span>  
  
 `ppTypeArgs`  
 <span data-ttu-id="df967-108">[in] Una matriz de punteros, cada uno de los cuales señala a un objeto ICorDebugType que representa un argumento de tipo para el objeto que se crea una instancia.</span><span class="sxs-lookup"><span data-stu-id="df967-108">[in] An array of pointers, each of which points to an ICorDebugType object that represents a type argument for the object that is being instantiated.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="df967-109">Comentarios</span><span class="sxs-lookup"><span data-stu-id="df967-109">Remarks</span></span>  
 <span data-ttu-id="df967-110">El `NewParameterizedObjectNoConstructor` método se producirá un error si un número incorrecto de argumentos de tipo o si se pasan los tipos de argumentos de tipo incorrectos.</span><span class="sxs-lookup"><span data-stu-id="df967-110">The `NewParameterizedObjectNoConstructor` method will fail if an incorrect number of type arguments or the wrong types of type arguments are passed.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="df967-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="df967-111">Requirements</span></span>  
 <span data-ttu-id="df967-112">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="df967-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="df967-113">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="df967-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="df967-114">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="df967-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="df967-115">**Versiones de .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="df967-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
