---
title: "ICorDebugEval2::NewParameterizedObject (Método)"
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
- ICorDebugEval2.NewParameterizedObject
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugEval2::NewParameterizedObject
helpviewer_keywords:
- NewParameterizedObject method [.NET Framework debugging]
- ICorDebugEval2::NewParameterizedObject method [.NET Framework debugging]
ms.assetid: 3d705463-e640-4249-8036-4e8206d03cfe
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 39b69a82f25ab6df5f2bd2f6dc70caf1bf13a0f9
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugeval2newparameterizedobject-method"></a><span data-ttu-id="6caf2-102">ICorDebugEval2::NewParameterizedObject (Método)</span><span class="sxs-lookup"><span data-stu-id="6caf2-102">ICorDebugEval2::NewParameterizedObject Method</span></span>
<span data-ttu-id="6caf2-103">Crea un nuevo objeto de tipo parametrizado y llama al método del objeto constructor.</span><span class="sxs-lookup"><span data-stu-id="6caf2-103">Instantiates a new parameterized type object and calls the object's constructor method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6caf2-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="6caf2-104">Syntax</span></span>  
  
```  
HRESULT NewParameterizedObject (  
    [in] ICorDebugFunction     *pConstructor,  
    [in] ULONG32               nTypeArgs,  
    [in, size_is(nTypeArgs)] ICorDebugType *ppTypeArgs[],  
    [in] ULONG32               nArgs,  
    [in, size_is(nArgs)] ICorDebugValue *ppArgs[]  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="6caf2-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="6caf2-105">Parameters</span></span>  
 `pConstructor`  
 <span data-ttu-id="6caf2-106">[in] Un puntero a un objeto ICorDebugFunction que representa el constructor del objeto que se pueden crear instancias.</span><span class="sxs-lookup"><span data-stu-id="6caf2-106">[in] A pointer to an ICorDebugFunction object that represents the constructor of the object to be instantiated.</span></span>  
  
 `nTypeArgs`  
 <span data-ttu-id="6caf2-107">[in] El número de argumentos de tipo pasados.</span><span class="sxs-lookup"><span data-stu-id="6caf2-107">[in] The number of type arguments passed.</span></span>  
  
 `ppTypeArgs`  
 <span data-ttu-id="6caf2-108">[in] Una matriz de punteros, cada uno de los cuales señala a un objeto ICorDebugType que representa un argumento de tipo para el objeto que se crea una instancia.</span><span class="sxs-lookup"><span data-stu-id="6caf2-108">[in] An array of pointers, each of which points to an ICorDebugType object that represents a type argument for the object that is being instantiated.</span></span>  
  
 `nArgs`  
 <span data-ttu-id="6caf2-109">[in] El número de argumentos pasados al constructor.</span><span class="sxs-lookup"><span data-stu-id="6caf2-109">[in] The number of arguments passed to the constructor.</span></span>  
  
 `ppArgs`  
 <span data-ttu-id="6caf2-110">[in] Una matriz de punteros, cada uno de los cuales señala a un objeto ICorDebugValue que representa un valor de argumento que se pasa al constructor.</span><span class="sxs-lookup"><span data-stu-id="6caf2-110">[in] An array of pointers, each of which points to an ICorDebugValue object that represents an argument value that is passed to the constructor.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="6caf2-111">Comentarios</span><span class="sxs-lookup"><span data-stu-id="6caf2-111">Remarks</span></span>  
 <span data-ttu-id="6caf2-112">El constructor del objeto puede tardar <xref:System.Type> parámetros.</span><span class="sxs-lookup"><span data-stu-id="6caf2-112">The object's constructor may take <xref:System.Type> parameters.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6caf2-113">Requisitos</span><span class="sxs-lookup"><span data-stu-id="6caf2-113">Requirements</span></span>  
 <span data-ttu-id="6caf2-114">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6caf2-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6caf2-115">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="6caf2-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="6caf2-116">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="6caf2-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="6caf2-117">**Versiones de .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6caf2-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
