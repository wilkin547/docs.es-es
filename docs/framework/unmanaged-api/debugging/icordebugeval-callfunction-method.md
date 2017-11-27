---
title: "ICorDebugEval::CallFunction (Método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugEval.CallFunction
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugEval::CallFunction
helpviewer_keywords:
- ICorDebugEval::CallFunction method [.NET Framework debugging]
- CallFunction method [.NET Framework debugging]
ms.assetid: 7f470c5c-e1c0-4d8d-aad8-830f113ae751
topic_type: apiref
caps.latest.revision: "16"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 72713d81931b53e8d61fb39cee146fd30a59bfcc
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="icordebugevalcallfunction-method"></a><span data-ttu-id="1bb11-102">ICorDebugEval::CallFunction (Método)</span><span class="sxs-lookup"><span data-stu-id="1bb11-102">ICorDebugEval::CallFunction Method</span></span>
<span data-ttu-id="1bb11-103">Configura una llamada a la función especificada.</span><span class="sxs-lookup"><span data-stu-id="1bb11-103">Sets up a call to the specified function.</span></span>  
  
 <span data-ttu-id="1bb11-104">Este método está obsoleto en la versión 2.0 de .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="1bb11-104">This method is obsolete in the .NET Framework version 2.0.</span></span> <span data-ttu-id="1bb11-105">Use [ICorDebugEval2:: CallParameterizedFunction](../../../../docs/framework/unmanaged-api/debugging/icordebugeval2-callparameterizedfunction-method.md) en su lugar.</span><span class="sxs-lookup"><span data-stu-id="1bb11-105">Use [ICorDebugEval2::CallParameterizedFunction](../../../../docs/framework/unmanaged-api/debugging/icordebugeval2-callparameterizedfunction-method.md) instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1bb11-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="1bb11-106">Syntax</span></span>  
  
```  
HRESULT CallFunction (  
    [in] ICorDebugFunction  *pFunction,  
    [in] ULONG32            nArgs,  
    [in, size_is(nArgs)] ICorDebugValue *ppArgs[]  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="1bb11-107">Parámetros</span><span class="sxs-lookup"><span data-stu-id="1bb11-107">Parameters</span></span>  
 `pFunction`  
 <span data-ttu-id="1bb11-108">[in] Puntero a un objeto ICorDebugFunction que especifica la función que se llamará.</span><span class="sxs-lookup"><span data-stu-id="1bb11-108">[in] Pointer to an ICorDebugFunction object that specifies the function to be called.</span></span>  
  
 `nArgs`  
 <span data-ttu-id="1bb11-109">[in] El número de argumentos de la función.</span><span class="sxs-lookup"><span data-stu-id="1bb11-109">[in] The number of arguments for the function.</span></span>  
  
 `ppArgs`  
 <span data-ttu-id="1bb11-110">[in] Matriz de punteros, cada uno de los cuales señala a un objeto ICorDebugValue que especifica un argumento que se pasan a la función.</span><span class="sxs-lookup"><span data-stu-id="1bb11-110">[in] An array of pointers, each of which points to an ICorDebugValue object that specifies an argument to be passed to the function.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="1bb11-111">Comentarios</span><span class="sxs-lookup"><span data-stu-id="1bb11-111">Remarks</span></span>  
 <span data-ttu-id="1bb11-112">Si la función es virtual, `CallFunction` realizará el envío virtual.</span><span class="sxs-lookup"><span data-stu-id="1bb11-112">If the function is virtual, `CallFunction` will perform virtual dispatch.</span></span> <span data-ttu-id="1bb11-113">Si la función está en un dominio de aplicación diferente, se producirá una transición siempre que todos los argumentos se encuentran también en ese dominio de aplicación.</span><span class="sxs-lookup"><span data-stu-id="1bb11-113">If the function is in a different application domain, a transition will occur as long as all arguments are also in that application domain.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1bb11-114">Requisitos</span><span class="sxs-lookup"><span data-stu-id="1bb11-114">Requirements</span></span>  
 <span data-ttu-id="1bb11-115">**Plataformas:** WindowSee [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1bb11-115">**Platforms:** WindowSee [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1bb11-116">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="1bb11-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="1bb11-117">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="1bb11-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="1bb11-118">**Versiones de .NET framework:** 1.1, 1.0</span><span class="sxs-lookup"><span data-stu-id="1bb11-118">**.NET Framework Versions:** 1.1, 1.0</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1bb11-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="1bb11-119">See Also</span></span>  
 [<span data-ttu-id="1bb11-120">CallParameterizedFunction (método)</span><span class="sxs-lookup"><span data-stu-id="1bb11-120">CallParameterizedFunction Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugeval2-callparameterizedfunction-method.md)
