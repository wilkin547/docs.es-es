---
title: ICorDebugEval2::CreateValueForType (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugEval2.CreateValueForType
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugEval2::CreateValueForType
helpviewer_keywords:
- CreateValueForType method [.NET Framework debugging]
- ICorDebugEval2::CreateValueForType method [.NET Framework debugging]
ms.assetid: ea38ae20-7e0a-427a-be77-d78fae719d82
topic_type:
- apiref
ms.openlocfilehash: 8632799b68ae8f92835d1774472bc1432d886f3b
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/28/2020
ms.locfileid: "76793482"
---
# <a name="icordebugeval2createvaluefortype-method"></a><span data-ttu-id="779a2-102">ICorDebugEval2::CreateValueForType (Método)</span><span class="sxs-lookup"><span data-stu-id="779a2-102">ICorDebugEval2::CreateValueForType Method</span></span>
<span data-ttu-id="779a2-103">Obtiene un puntero a una nueva ICorDebugValue del tipo especificado, con un valor inicial de cero o null.</span><span class="sxs-lookup"><span data-stu-id="779a2-103">Gets a pointer to a new ICorDebugValue of the specified type, with an initial value of zero or null.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="779a2-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="779a2-104">Syntax</span></span>  
  
```cpp  
HRESULT CreateValueForType (  
    [in] ICorDebugType         *pType,  
    [out] ICorDebugValue       **ppValue  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="779a2-105">Parameters</span><span class="sxs-lookup"><span data-stu-id="779a2-105">Parameters</span></span>  
 `pType`  
 <span data-ttu-id="779a2-106">de Puntero a un objeto ICorDebugType que representa el tipo.</span><span class="sxs-lookup"><span data-stu-id="779a2-106">[in] Pointer to an ICorDebugType object that represents the type.</span></span>  
  
 `ppValue`  
 <span data-ttu-id="779a2-107">enuncia Puntero a la dirección de un objeto `ICorDebugValue` que representa el valor.</span><span class="sxs-lookup"><span data-stu-id="779a2-107">[out] Pointer to the address of an `ICorDebugValue` object that represents the value.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="779a2-108">Notas</span><span class="sxs-lookup"><span data-stu-id="779a2-108">Remarks</span></span>  
 <span data-ttu-id="779a2-109">`CreateValueForType` generaliza a [ICorDebugEval:: CreateValue (](icordebugeval-createvalue-method.md) permitiéndole especificar un tipo de objeto arbitrario, incluidos los tipos construidos como `List<int>`.</span><span class="sxs-lookup"><span data-stu-id="779a2-109">`CreateValueForType` generalizes [ICorDebugEval::CreateValue](icordebugeval-createvalue-method.md) by allowing you to specify an arbitrary object type, including constructed types such as `List<int>`.</span></span> <span data-ttu-id="779a2-110">El único propósito de este método es generar un valor que se pueda pasar a una evaluación de función.</span><span class="sxs-lookup"><span data-stu-id="779a2-110">The only purpose of this method is to generate a value that can be passed to a function evaluation.</span></span>  
  
 <span data-ttu-id="779a2-111">El tipo debe ser una clase o un tipo de valor.</span><span class="sxs-lookup"><span data-stu-id="779a2-111">The type must be a class or a value type.</span></span> <span data-ttu-id="779a2-112">No se puede usar este método para crear valores de matriz o valores de cadena.</span><span class="sxs-lookup"><span data-stu-id="779a2-112">You cannot use this method to create array values or string values.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="779a2-113">Requisitos de</span><span class="sxs-lookup"><span data-stu-id="779a2-113">Requirements</span></span>  
 <span data-ttu-id="779a2-114">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="779a2-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="779a2-115">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="779a2-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="779a2-116">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="779a2-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="779a2-117">**.NET Framework versiones:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="779a2-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
