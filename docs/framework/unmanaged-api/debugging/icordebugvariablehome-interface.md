---
description: 'Más información acerca de: interfaz ICorDebugVariableHome'
title: Interfaz ICorDebugVariableHome
ms.date: 03/30/2017
dev_langs:
- cpp
api_name:
- ICorDebugVariableHome
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugVariableHome
helpviewer_keywords:
- ICorDebugVariableHome interface [.NET Framework debugging]
ms.assetid: 76f2bf3b-759f-4eed-bce7-119415b25915
topic_type:
- apiref
ms.openlocfilehash: a1dcc959ba9aeffc0e511dcd2f5bb15f58445139
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99790638"
---
# <a name="icordebugvariablehome-interface"></a><span data-ttu-id="e7eb3-103">Interfaz ICorDebugVariableHome</span><span class="sxs-lookup"><span data-stu-id="e7eb3-103">ICorDebugVariableHome Interface</span></span>

<span data-ttu-id="e7eb3-104">Representa una variable local o un argumento de una función.</span><span class="sxs-lookup"><span data-stu-id="e7eb3-104">Represents a local variable or argument of a function.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="e7eb3-105">Métodos</span><span class="sxs-lookup"><span data-stu-id="e7eb3-105">Methods</span></span>  
  
|<span data-ttu-id="e7eb3-106">Método</span><span class="sxs-lookup"><span data-stu-id="e7eb3-106">Method</span></span>|<span data-ttu-id="e7eb3-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="e7eb3-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="e7eb3-108">Método GetArgumentIndex</span><span class="sxs-lookup"><span data-stu-id="e7eb3-108">GetArgumentIndex Method</span></span>](icordebugvariablehome-getargumentindex-method.md)|<span data-ttu-id="e7eb3-109">Obtiene el índice de un argumento de función.</span><span class="sxs-lookup"><span data-stu-id="e7eb3-109">Gets the index of a function argument.</span></span>|  
|[<span data-ttu-id="e7eb3-110">Método GetCode</span><span class="sxs-lookup"><span data-stu-id="e7eb3-110">GetCode Method</span></span>](icordebugvariablehome-getcode-method.md)|<span data-ttu-id="e7eb3-111">Obtiene la instancia de "ICorDebugCode" que contiene este `ICorDebugVariableHome` objeto.</span><span class="sxs-lookup"><span data-stu-id="e7eb3-111">Gets the "ICorDebugCode" instance that contains this `ICorDebugVariableHome` object.</span></span>|  
|[<span data-ttu-id="e7eb3-112">Método GetLiveRange</span><span class="sxs-lookup"><span data-stu-id="e7eb3-112">GetLiveRange Method</span></span>](icordebugvariablehome-getliverange-method.md)|<span data-ttu-id="e7eb3-113">Obtiene el intervalo nativo en el que esta variable está activa.</span><span class="sxs-lookup"><span data-stu-id="e7eb3-113">Gets the native range over which this variable is live.</span></span>|  
|[<span data-ttu-id="e7eb3-114">Método GetLocationType</span><span class="sxs-lookup"><span data-stu-id="e7eb3-114">GetLocationType Method</span></span>](icordebugvariablehome-getlocationtype-method.md)|<span data-ttu-id="e7eb3-115">Obtiene el tipo de la ubicación nativa de la variable.</span><span class="sxs-lookup"><span data-stu-id="e7eb3-115">Gets the type of the variable's native location.</span></span>|  
|[<span data-ttu-id="e7eb3-116">Método GetOffset</span><span class="sxs-lookup"><span data-stu-id="e7eb3-116">GetOffset Method</span></span>](icordebugvariablehome-getoffset-method.md)|<span data-ttu-id="e7eb3-117">Obtiene el desplazamiento del registro base para una variable.</span><span class="sxs-lookup"><span data-stu-id="e7eb3-117">Gets the offset from the base register for a variable.</span></span>|  
|[<span data-ttu-id="e7eb3-118">Método GetRegister</span><span class="sxs-lookup"><span data-stu-id="e7eb3-118">GetRegister Method</span></span>](icordebugvariablehome-getregister-method.md)|<span data-ttu-id="e7eb3-119">Obtiene el registro que contiene una variable con un tipo de ubicación de `VLT_REGISTER` y el registro base de una variable con un tipo de ubicación de `VLT_REGISTER_RELATIVE` .</span><span class="sxs-lookup"><span data-stu-id="e7eb3-119">Gets the register that contains a variable with a location type of `VLT_REGISTER`, and the base register for a variable with a location type of `VLT_REGISTER_RELATIVE`.</span></span>|  
|[<span data-ttu-id="e7eb3-120">Método GetSlotIndex</span><span class="sxs-lookup"><span data-stu-id="e7eb3-120">GetSlotIndex Method</span></span>](icordebugvariablehome-getslotindex-method.md)|<span data-ttu-id="e7eb3-121">Obtiene el índice de ranura administrado de una variable local.</span><span class="sxs-lookup"><span data-stu-id="e7eb3-121">Gets the managed slot-index of a local variable.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="e7eb3-122">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="e7eb3-122">Example</span></span>  

 <span data-ttu-id="e7eb3-123">En el fragmento de código siguiente se usa el objeto [interfaces icordebugcode4](icordebugcode4-interface.md) denominado `pCode4` .</span><span class="sxs-lookup"><span data-stu-id="e7eb3-123">The following code fragment uses the [ICorDebugCode4](icordebugcode4-interface.md) object named `pCode4`.</span></span>  
  
```cpp  
ICorDebugCode4 *pCode4 = NULL;  
pCode->QueryInterface(IID_ICorDebugCode4, &pCode4);  
  
ICorDebugVariableEnum *pVarLocEnum = NULL;  
pCode4->EnumerateVariableHomes(&pVarLocEnum);  
  
// retrieve local variables and arguments  
ULONG celt = 0;  
pVarLocEnum->GetCount(&celt);  
ICorDebugVariableHome **homes = new ICorDebugVariableHome *[celt];  
ULONG celtFetched = 0;  
pVarLocEnum->Next(celt, homes, &celtFetched);  
  
for (int i = 0; i < celtFetched; i++)  
{  
    VariableLocationType locType = VLT_INVALID;  
    homes[i].GetLocationType(&locType);  
    switch (locType)  
    {  
    case VLT_REGISTER:  
        CorDebugRegister register = 0;  
        locals[i].GetRegister(&register);  
        // now we know which register it is in  
        break;  
    case VLT_REGISTER_RELATIVE:  
        CorDebugRegister baseRegister = 0;  
        LONG offset = 0;  
        locals[i].GetRegister(&register);  
        locals[i].GetOffset(&offset);  
        // now we know the register-relative offset  
        break;  
    case VLT_INVALID:  
        // handle case where we can't access the location  
        break;  
    }  
}  
```  
  
## <a name="requirements"></a><span data-ttu-id="e7eb3-124">Requisitos</span><span class="sxs-lookup"><span data-stu-id="e7eb3-124">Requirements</span></span>  

 <span data-ttu-id="e7eb3-125">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e7eb3-125">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e7eb3-126">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="e7eb3-126">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="e7eb3-127">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e7eb3-127">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e7eb3-128">**.NET Framework versiones:**[!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e7eb3-128">**.NET Framework Versions:** [!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e7eb3-129">Vea también</span><span class="sxs-lookup"><span data-stu-id="e7eb3-129">See also</span></span>

- [<span data-ttu-id="e7eb3-130">Interfaces para depuración</span><span class="sxs-lookup"><span data-stu-id="e7eb3-130">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="e7eb3-131">Interfaz ICorDebugVariableHomeEnum</span><span class="sxs-lookup"><span data-stu-id="e7eb3-131">ICorDebugVariableHomeEnum Interface</span></span>](icordebugvariablehomeenum-interface.md)
