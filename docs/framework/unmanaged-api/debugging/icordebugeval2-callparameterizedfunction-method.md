---
title: ICorDebugEval2::CallParameterizedFunction (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugEval2.CallParameterizedFunction
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugEval2::CallParameterizedFunction
helpviewer_keywords:
- ICorDebugEval2::CallParameterizedFunction method [.NET Framework debugging]
- CallParameterizedFunction method [.NET Framework debugging]
ms.assetid: 72f54a45-dbe6-4bb4-8c99-e879a27368e5
topic_type:
- apiref
ms.openlocfilehash: c36dec80b6885b0ee56670b94dbd0b155a9710b4
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95729712"
---
# <a name="icordebugeval2callparameterizedfunction-method"></a><span data-ttu-id="8dde8-102">ICorDebugEval2::CallParameterizedFunction (Método)</span><span class="sxs-lookup"><span data-stu-id="8dde8-102">ICorDebugEval2::CallParameterizedFunction Method</span></span>

<span data-ttu-id="8dde8-103">Configura una llamada a la ICorDebugFunction especificada, que se puede anidar dentro de una clase cuyo constructor toma <xref:System.Type> parámetros, o bien puede tomar <xref:System.Type> parámetros.</span><span class="sxs-lookup"><span data-stu-id="8dde8-103">Sets up a call to the specified ICorDebugFunction, which can be nested inside a class whose constructor takes <xref:System.Type> parameters, or can itself take <xref:System.Type> parameters.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8dde8-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="8dde8-104">Syntax</span></span>  
  
```cpp  
HRESULT CallParameterizedFunction (  
    [in] ICorDebugFunction     *pFunction,  
    [in] ULONG32               nTypeArgs,  
    [in, size_is(nTypeArgs)] ICorDebugType *ppTypeArgs[],  
    [in] ULONG32               nArgs,  
    [in, size_is(nArgs)] ICorDebugValue *ppArgs[]  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="8dde8-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="8dde8-105">Parameters</span></span>  

 `pFunction`  
 <span data-ttu-id="8dde8-106">de Un puntero a un `ICorDebugFunction` objeto que representa la función a la que se va a llamar.</span><span class="sxs-lookup"><span data-stu-id="8dde8-106">[in] A pointer to an `ICorDebugFunction` object that represents the function to be called.</span></span>  
  
 `nTypeArgs`  
 <span data-ttu-id="8dde8-107">de El número de argumentos que toma la función.</span><span class="sxs-lookup"><span data-stu-id="8dde8-107">[in] The number of arguments that the function takes.</span></span>  
  
 `ppTypeArgs`  
 <span data-ttu-id="8dde8-108">de Matriz de punteros, cada uno de los cuales señala a un objeto ICorDebugType que representa un argumento de función.</span><span class="sxs-lookup"><span data-stu-id="8dde8-108">[in] An array of pointers, each of which points to an ICorDebugType object that represents a function argument.</span></span>  
  
 `nArgs`  
 <span data-ttu-id="8dde8-109">de Número de valores pasados en la función.</span><span class="sxs-lookup"><span data-stu-id="8dde8-109">[in] The number of values passed in the function.</span></span>  
  
 `ppArgs`  
 <span data-ttu-id="8dde8-110">de Matriz de punteros, cada uno de los cuales señala a un objeto ICorDebugValue que representa un valor pasado en un argumento de función.</span><span class="sxs-lookup"><span data-stu-id="8dde8-110">[in] An array of pointers, each of which points to an ICorDebugValue object that represents a value passed in a function argument.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="8dde8-111">Comentarios</span><span class="sxs-lookup"><span data-stu-id="8dde8-111">Remarks</span></span>  

 <span data-ttu-id="8dde8-112">`CallParameterizedFunction` es como [ICorDebugEval:: CallFunction](icordebugeval-callfunction-method.md) , salvo que la función puede estar dentro de una clase con parámetros de tipo, puede tomar parámetros de tipo o ambos.</span><span class="sxs-lookup"><span data-stu-id="8dde8-112">`CallParameterizedFunction` is like [ICorDebugEval::CallFunction](icordebugeval-callfunction-method.md) except that the function may be inside a class with type parameters, may itself take type parameters, or both.</span></span> <span data-ttu-id="8dde8-113">Los argumentos de tipo deben proporcionarse primero para la clase y, a continuación, para la función.</span><span class="sxs-lookup"><span data-stu-id="8dde8-113">The type arguments should be given first for the class, and then for the function.</span></span>  
  
 <span data-ttu-id="8dde8-114">Si la función está en un dominio de aplicación diferente, se producirá una transición.</span><span class="sxs-lookup"><span data-stu-id="8dde8-114">If the function is in a different application domain, a transition will occur.</span></span> <span data-ttu-id="8dde8-115">Sin embargo, todos los argumentos de tipo y valor deben estar en el dominio de aplicación de destino.</span><span class="sxs-lookup"><span data-stu-id="8dde8-115">However, all type and value arguments must be in the target application domain.</span></span>  
  
 <span data-ttu-id="8dde8-116">La evaluación de funciones solo se puede realizar en escenarios limitados.</span><span class="sxs-lookup"><span data-stu-id="8dde8-116">Function evaluation can be performed only in limited scenarios.</span></span> <span data-ttu-id="8dde8-117">Si `CallParameterizedFunction` o `ICorDebugEval::CallFunction` produce un error, el HRESULT devuelto indicará el motivo más general posible del error.</span><span class="sxs-lookup"><span data-stu-id="8dde8-117">If `CallParameterizedFunction` or `ICorDebugEval::CallFunction` fails, the returned HRESULT will indicate the most general possible reason for failure.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8dde8-118">Requisitos</span><span class="sxs-lookup"><span data-stu-id="8dde8-118">Requirements</span></span>  

 <span data-ttu-id="8dde8-119">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8dde8-119">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8dde8-120">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="8dde8-120">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="8dde8-121">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="8dde8-121">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="8dde8-122">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8dde8-122">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
