---
title: "ICorDebugAppDomain2::GetFunctionPointerType (Método)"
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
- ICorDebugAppDomain2.GetFunctionPointerType
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugAppDomain2::GetFunctionPointerType
helpviewer_keywords:
- ICorDebugAppDomain2::GetFunctionPointerType method [.NET Framework debugging]
- GetFunctionPointerType method [.NET Framework debugging]
ms.assetid: 0aba6096-5b38-435c-a72a-86d35db4daef
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 12cb3e62454aacacc69207ce3675448ea8c2ffee
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugappdomain2getfunctionpointertype-method"></a><span data-ttu-id="51fe1-102">ICorDebugAppDomain2::GetFunctionPointerType (Método)</span><span class="sxs-lookup"><span data-stu-id="51fe1-102">ICorDebugAppDomain2::GetFunctionPointerType Method</span></span>
<span data-ttu-id="51fe1-103">Obtiene un puntero a una función que tiene una firma dada.</span><span class="sxs-lookup"><span data-stu-id="51fe1-103">Gets a pointer to a function that has a given signature.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="51fe1-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="51fe1-104">Syntax</span></span>  
  
```  
HRESULT GetFunctionPointerType (  
    [in] ULONG32                             nTypeArgs,  
    [in, size_is(nTypeArgs)] ICorDebugType   *ppTypeArgs[],  
    [out] ICorDebugType                      **ppType  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="51fe1-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="51fe1-105">Parameters</span></span>  
 `nTypeArgs`  
 <span data-ttu-id="51fe1-106">[in] El número de argumentos de tipo para la función.</span><span class="sxs-lookup"><span data-stu-id="51fe1-106">[in] The number of type arguments for the function.</span></span>  
  
 `ppTypeArgs`  
 <span data-ttu-id="51fe1-107">[in] Una matriz de punteros, cada uno de los cuales señala a un objeto ICorDebugType que representa un argumento de tipo de la función.</span><span class="sxs-lookup"><span data-stu-id="51fe1-107">[in] An array of pointers, each of which points to an ICorDebugType object that represents a type argument of the function.</span></span> <span data-ttu-id="51fe1-108">El primer elemento es el tipo de valor devuelto; cada uno de los demás elementos es un tipo de parámetro.</span><span class="sxs-lookup"><span data-stu-id="51fe1-108">The first element is the return type; each of the other elements is a parameter type.</span></span>  
  
 `ppType`  
 <span data-ttu-id="51fe1-109">[out] Un puntero a la dirección de un `ICorDebugType` objeto que representa el puntero a la función.</span><span class="sxs-lookup"><span data-stu-id="51fe1-109">[out] A pointer to the address of an `ICorDebugType` object that represents the pointer to the function.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="51fe1-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="51fe1-110">Requirements</span></span>  
 <span data-ttu-id="51fe1-111">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="51fe1-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="51fe1-112">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="51fe1-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="51fe1-113">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="51fe1-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="51fe1-114">**Versiones de .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="51fe1-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
