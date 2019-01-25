---
title: ICorDebugEval::CallFunction (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugEval.CallFunction
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugEval::CallFunction
helpviewer_keywords:
- ICorDebugEval::CallFunction method [.NET Framework debugging]
- CallFunction method [.NET Framework debugging]
ms.assetid: 7f470c5c-e1c0-4d8d-aad8-830f113ae751
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 493b4850436b3724287210878992d1d8ce8fe168
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54589404"
---
# <a name="icordebugevalcallfunction-method"></a><span data-ttu-id="1e761-102">ICorDebugEval::CallFunction (Método)</span><span class="sxs-lookup"><span data-stu-id="1e761-102">ICorDebugEval::CallFunction Method</span></span>
<span data-ttu-id="1e761-103">Configura una llamada a la función especificada.</span><span class="sxs-lookup"><span data-stu-id="1e761-103">Sets up a call to the specified function.</span></span>  
  
 <span data-ttu-id="1e761-104">Este método está obsoleto en .NET Framework versión 2.0.</span><span class="sxs-lookup"><span data-stu-id="1e761-104">This method is obsolete in the .NET Framework version 2.0.</span></span> <span data-ttu-id="1e761-105">Use [ICorDebugEval2:: CallParameterizedFunction](../../../../docs/framework/unmanaged-api/debugging/icordebugeval2-callparameterizedfunction-method.md) en su lugar.</span><span class="sxs-lookup"><span data-stu-id="1e761-105">Use [ICorDebugEval2::CallParameterizedFunction](../../../../docs/framework/unmanaged-api/debugging/icordebugeval2-callparameterizedfunction-method.md) instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1e761-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="1e761-106">Syntax</span></span>  
  
```  
HRESULT CallFunction (  
    [in] ICorDebugFunction  *pFunction,  
    [in] ULONG32            nArgs,  
    [in, size_is(nArgs)] ICorDebugValue *ppArgs[]  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="1e761-107">Parámetros</span><span class="sxs-lookup"><span data-stu-id="1e761-107">Parameters</span></span>  
 `pFunction`  
 <span data-ttu-id="1e761-108">[in] Puntero a un objeto ICorDebugFunction que especifica la función debe llamarse.</span><span class="sxs-lookup"><span data-stu-id="1e761-108">[in] Pointer to an ICorDebugFunction object that specifies the function to be called.</span></span>  
  
 `nArgs`  
 <span data-ttu-id="1e761-109">[in] El número de argumentos de la función.</span><span class="sxs-lookup"><span data-stu-id="1e761-109">[in] The number of arguments for the function.</span></span>  
  
 `ppArgs`  
 <span data-ttu-id="1e761-110">[in] Una matriz de punteros, cada uno de los cuales señala a un objeto ICorDebugValue que especifica un argumento que se pasará a la función.</span><span class="sxs-lookup"><span data-stu-id="1e761-110">[in] An array of pointers, each of which points to an ICorDebugValue object that specifies an argument to be passed to the function.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="1e761-111">Comentarios</span><span class="sxs-lookup"><span data-stu-id="1e761-111">Remarks</span></span>  
 <span data-ttu-id="1e761-112">Si la función es virtual, `CallFunction` llevará a cabo distribución virtual.</span><span class="sxs-lookup"><span data-stu-id="1e761-112">If the function is virtual, `CallFunction` will perform virtual dispatch.</span></span> <span data-ttu-id="1e761-113">Si la función está en un dominio de aplicación diferente, se producirá una transición siempre y cuando todos los argumentos son también en ese dominio de aplicación.</span><span class="sxs-lookup"><span data-stu-id="1e761-113">If the function is in a different application domain, a transition will occur as long as all arguments are also in that application domain.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1e761-114">Requisitos</span><span class="sxs-lookup"><span data-stu-id="1e761-114">Requirements</span></span>  
 <span data-ttu-id="1e761-115">**Plataformas:** WindowSee [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1e761-115">**Platforms:** WindowSee [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1e761-116">**Encabezado**: CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="1e761-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="1e761-117">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="1e761-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="1e761-118">**Versiones de .NET framework:** 1.1, 1.0</span><span class="sxs-lookup"><span data-stu-id="1e761-118">**.NET Framework Versions:** 1.1, 1.0</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1e761-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="1e761-119">See also</span></span>
- [<span data-ttu-id="1e761-120">CallParameterizedFunction (método)</span><span class="sxs-lookup"><span data-stu-id="1e761-120">CallParameterizedFunction Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugeval2-callparameterizedfunction-method.md)
