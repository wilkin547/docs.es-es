---
description: 'Más información acerca de: ICorDebugEval:: CallFunction (método)'
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
ms.openlocfilehash: c0978ab3bdffc83e3eb5e3a6553e7f374ab6d5da
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99694193"
---
# <a name="icordebugevalcallfunction-method"></a><span data-ttu-id="9e65f-103">ICorDebugEval::CallFunction (Método)</span><span class="sxs-lookup"><span data-stu-id="9e65f-103">ICorDebugEval::CallFunction Method</span></span>

<span data-ttu-id="9e65f-104">Configura una llamada a la función especificada.</span><span class="sxs-lookup"><span data-stu-id="9e65f-104">Sets up a call to the specified function.</span></span>

<span data-ttu-id="9e65f-105">Este método está obsoleto en la .NET Framework versión 2,0.</span><span class="sxs-lookup"><span data-stu-id="9e65f-105">This method is obsolete in the .NET Framework version 2.0.</span></span> <span data-ttu-id="9e65f-106">Use [ICorDebugEval2:: CallParameterizedFunction (](icordebugeval2-callparameterizedfunction-method.md) en su lugar.</span><span class="sxs-lookup"><span data-stu-id="9e65f-106">Use [ICorDebugEval2::CallParameterizedFunction](icordebugeval2-callparameterizedfunction-method.md) instead.</span></span>

## <a name="syntax"></a><span data-ttu-id="9e65f-107">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="9e65f-107">Syntax</span></span>

```cpp
HRESULT CallFunction (
    [in] ICorDebugFunction  *pFunction,
    [in] ULONG32            nArgs,
    [in, size_is(nArgs)] ICorDebugValue *ppArgs[]
);
```

## <a name="parameters"></a><span data-ttu-id="9e65f-108">Parámetros</span><span class="sxs-lookup"><span data-stu-id="9e65f-108">Parameters</span></span>

`pFunction`\
<span data-ttu-id="9e65f-109">de Puntero a un objeto ICorDebugFunction que especifica la función a la que se va a llamar.</span><span class="sxs-lookup"><span data-stu-id="9e65f-109">[in] Pointer to an ICorDebugFunction object that specifies the function to be called.</span></span>

`nArgs`\
<span data-ttu-id="9e65f-110">de El número de argumentos de la función.</span><span class="sxs-lookup"><span data-stu-id="9e65f-110">[in] The number of arguments for the function.</span></span>

`ppArgs`\
<span data-ttu-id="9e65f-111">de Matriz de punteros, cada uno de los cuales señala a un objeto ICorDebugValue que especifica un argumento que se va a pasar a la función.</span><span class="sxs-lookup"><span data-stu-id="9e65f-111">[in] An array of pointers, each of which points to an ICorDebugValue object that specifies an argument to be passed to the function.</span></span>

## <a name="remarks"></a><span data-ttu-id="9e65f-112">Observaciones</span><span class="sxs-lookup"><span data-stu-id="9e65f-112">Remarks</span></span>

<span data-ttu-id="9e65f-113">Si la función es virtual, `CallFunction` realizará el envío virtual.</span><span class="sxs-lookup"><span data-stu-id="9e65f-113">If the function is virtual, `CallFunction` will perform virtual dispatch.</span></span> <span data-ttu-id="9e65f-114">Si la función está en un dominio de aplicación diferente, se producirá una transición siempre y cuando todos los argumentos estén también en ese dominio de aplicación.</span><span class="sxs-lookup"><span data-stu-id="9e65f-114">If the function is in a different application domain, a transition will occur as long as all arguments are also in that application domain.</span></span>

## <a name="requirements"></a><span data-ttu-id="9e65f-115">Requisitos</span><span class="sxs-lookup"><span data-stu-id="9e65f-115">Requirements</span></span>

<span data-ttu-id="9e65f-116">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9e65f-116">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>

<span data-ttu-id="9e65f-117">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="9e65f-117">**Header:** CorDebug.idl, CorDebug.h</span></span>

<span data-ttu-id="9e65f-118">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="9e65f-118">**Library:** CorGuids.lib</span></span>

<span data-ttu-id="9e65f-119">**.NET Framework versiones:** 1,1, 1,0</span><span class="sxs-lookup"><span data-stu-id="9e65f-119">**.NET Framework Versions:** 1.1, 1.0</span></span>

## <a name="see-also"></a><span data-ttu-id="9e65f-120">Vea también</span><span class="sxs-lookup"><span data-stu-id="9e65f-120">See also</span></span>

- [<span data-ttu-id="9e65f-121">Método CallParameterizedFunction</span><span class="sxs-lookup"><span data-stu-id="9e65f-121">CallParameterizedFunction Method</span></span>](icordebugeval2-callparameterizedfunction-method.md)
