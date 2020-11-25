---
title: ICorDebugEval2::NewParameterizedObjectNoConstructor (Método)
ms.date: 03/30/2017
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
ms.openlocfilehash: 796c6aa4c42a037fe612b4b1ee5267a678cf5224
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95729647"
---
# <a name="icordebugeval2newparameterizedobjectnoconstructor-method"></a><span data-ttu-id="8a66a-102">ICorDebugEval2::NewParameterizedObjectNoConstructor (Método)</span><span class="sxs-lookup"><span data-stu-id="8a66a-102">ICorDebugEval2::NewParameterizedObjectNoConstructor Method</span></span>

<span data-ttu-id="8a66a-103">Crea una instancia de un nuevo objeto de tipo parametrizado de la clase especificada sin intentar llamar a un método de constructor.</span><span class="sxs-lookup"><span data-stu-id="8a66a-103">Instantiates a new parameterized type object of the specified class without attempting to call a constructor method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8a66a-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="8a66a-104">Syntax</span></span>  
  
```cpp  
HRESULT NewParameterizedObjectNoConstructor (  
    [in] ICorDebugClass        *pClass,  
    [in] ULONG32               nTypeArgs,  
    [in, size_is(nTypeArgs)] ICorDebugType *ppTypeArgs[]  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="8a66a-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="8a66a-105">Parameters</span></span>  

 `pClass`  
 <span data-ttu-id="8a66a-106">de Un puntero a un objeto ICorDebugClass que representa la clase del objeto del que se va a crear una instancia.</span><span class="sxs-lookup"><span data-stu-id="8a66a-106">[in] A pointer to an ICorDebugClass object that represents the class of the object to be instantiated.</span></span>  
  
 `nTypeArgs`  
 <span data-ttu-id="8a66a-107">de El número de argumentos de tipo pasados.</span><span class="sxs-lookup"><span data-stu-id="8a66a-107">[in] The number of type arguments passed.</span></span>  
  
 `ppTypeArgs`  
 <span data-ttu-id="8a66a-108">de Matriz de punteros, cada uno de los cuales señala a un objeto ICorDebugType que representa un argumento de tipo para el objeto del que se crea una instancia.</span><span class="sxs-lookup"><span data-stu-id="8a66a-108">[in] An array of pointers, each of which points to an ICorDebugType object that represents a type argument for the object that is being instantiated.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="8a66a-109">Comentarios</span><span class="sxs-lookup"><span data-stu-id="8a66a-109">Remarks</span></span>  

 <span data-ttu-id="8a66a-110">El `NewParameterizedObjectNoConstructor` método producirá un error si se pasa un número incorrecto de argumentos de tipo o los tipos de argumentos de tipo incorrectos.</span><span class="sxs-lookup"><span data-stu-id="8a66a-110">The `NewParameterizedObjectNoConstructor` method will fail if an incorrect number of type arguments or the wrong types of type arguments are passed.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8a66a-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="8a66a-111">Requirements</span></span>  

 <span data-ttu-id="8a66a-112">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8a66a-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8a66a-113">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="8a66a-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="8a66a-114">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="8a66a-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="8a66a-115">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8a66a-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
