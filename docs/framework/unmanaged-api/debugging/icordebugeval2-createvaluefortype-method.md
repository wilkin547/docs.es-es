---
description: 'Más información sobre: ICorDebugEval2:: Createvaluefortype ((método)'
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
ms.openlocfilehash: 2a8cd129d6194a4870817eb64b79606c395cb055
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99693920"
---
# <a name="icordebugeval2createvaluefortype-method"></a><span data-ttu-id="dff48-103">ICorDebugEval2::CreateValueForType (Método)</span><span class="sxs-lookup"><span data-stu-id="dff48-103">ICorDebugEval2::CreateValueForType Method</span></span>

<span data-ttu-id="dff48-104">Obtiene un puntero a una nueva ICorDebugValue del tipo especificado, con un valor inicial de cero o null.</span><span class="sxs-lookup"><span data-stu-id="dff48-104">Gets a pointer to a new ICorDebugValue of the specified type, with an initial value of zero or null.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="dff48-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="dff48-105">Syntax</span></span>  
  
```cpp  
HRESULT CreateValueForType (  
    [in] ICorDebugType         *pType,  
    [out] ICorDebugValue       **ppValue  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="dff48-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="dff48-106">Parameters</span></span>  

 `pType`  
 <span data-ttu-id="dff48-107">de Puntero a un objeto ICorDebugType que representa el tipo.</span><span class="sxs-lookup"><span data-stu-id="dff48-107">[in] Pointer to an ICorDebugType object that represents the type.</span></span>  
  
 `ppValue`  
 <span data-ttu-id="dff48-108">enuncia Puntero a la dirección de un `ICorDebugValue` objeto que representa el valor.</span><span class="sxs-lookup"><span data-stu-id="dff48-108">[out] Pointer to the address of an `ICorDebugValue` object that represents the value.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="dff48-109">Observaciones</span><span class="sxs-lookup"><span data-stu-id="dff48-109">Remarks</span></span>  

 <span data-ttu-id="dff48-110">`CreateValueForType` generaliza [ICorDebugEval:: CreateValue (](icordebugeval-createvalue-method.md) permitiéndole especificar un tipo de objeto arbitrario, incluidos los tipos construidos como `List<int>` .</span><span class="sxs-lookup"><span data-stu-id="dff48-110">`CreateValueForType` generalizes [ICorDebugEval::CreateValue](icordebugeval-createvalue-method.md) by allowing you to specify an arbitrary object type, including constructed types such as `List<int>`.</span></span> <span data-ttu-id="dff48-111">El único propósito de este método es generar un valor que se pueda pasar a una evaluación de función.</span><span class="sxs-lookup"><span data-stu-id="dff48-111">The only purpose of this method is to generate a value that can be passed to a function evaluation.</span></span>  
  
 <span data-ttu-id="dff48-112">El tipo debe ser una clase o un tipo de valor.</span><span class="sxs-lookup"><span data-stu-id="dff48-112">The type must be a class or a value type.</span></span> <span data-ttu-id="dff48-113">No se puede usar este método para crear valores de matriz o valores de cadena.</span><span class="sxs-lookup"><span data-stu-id="dff48-113">You cannot use this method to create array values or string values.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="dff48-114">Requisitos</span><span class="sxs-lookup"><span data-stu-id="dff48-114">Requirements</span></span>  

 <span data-ttu-id="dff48-115">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="dff48-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="dff48-116">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="dff48-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="dff48-117">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="dff48-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="dff48-118">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="dff48-118">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
