---
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
ms.openlocfilehash: c347346c9157fea843527c662e26ffcfba22ace4
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/28/2020
ms.locfileid: "76790952"
---
# <a name="icordebugvariablehome-interface"></a><span data-ttu-id="903f1-102">Interfaz ICorDebugVariableHome</span><span class="sxs-lookup"><span data-stu-id="903f1-102">ICorDebugVariableHome Interface</span></span>
<span data-ttu-id="903f1-103">Representa una variable local o un argumento de una función.</span><span class="sxs-lookup"><span data-stu-id="903f1-103">Represents a local variable or argument of a function.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="903f1-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="903f1-104">Methods</span></span>  
  
|<span data-ttu-id="903f1-105">Método</span><span class="sxs-lookup"><span data-stu-id="903f1-105">Method</span></span>|<span data-ttu-id="903f1-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="903f1-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="903f1-107">GetArgumentIndex (método)</span><span class="sxs-lookup"><span data-stu-id="903f1-107">GetArgumentIndex Method</span></span>](icordebugvariablehome-getargumentindex-method.md)|<span data-ttu-id="903f1-108">Obtiene el índice de un argumento de función.</span><span class="sxs-lookup"><span data-stu-id="903f1-108">Gets the index of a function argument.</span></span>|  
|[<span data-ttu-id="903f1-109">GetCode (método)</span><span class="sxs-lookup"><span data-stu-id="903f1-109">GetCode Method</span></span>](icordebugvariablehome-getcode-method.md)|<span data-ttu-id="903f1-110">Obtiene la instancia de "ICorDebugCode" que contiene este objeto `ICorDebugVariableHome`.</span><span class="sxs-lookup"><span data-stu-id="903f1-110">Gets the "ICorDebugCode" instance that contains this `ICorDebugVariableHome` object.</span></span>|  
|[<span data-ttu-id="903f1-111">GetLiveRange (método)</span><span class="sxs-lookup"><span data-stu-id="903f1-111">GetLiveRange Method</span></span>](icordebugvariablehome-getliverange-method.md)|<span data-ttu-id="903f1-112">Obtiene el intervalo nativo en el que esta variable está activa.</span><span class="sxs-lookup"><span data-stu-id="903f1-112">Gets the native range over which this variable is live.</span></span>|  
|[<span data-ttu-id="903f1-113">GetLocationType (método)</span><span class="sxs-lookup"><span data-stu-id="903f1-113">GetLocationType Method</span></span>](icordebugvariablehome-getlocationtype-method.md)|<span data-ttu-id="903f1-114">Obtiene el tipo de la ubicación nativa de la variable.</span><span class="sxs-lookup"><span data-stu-id="903f1-114">Gets the type of the variable's native location.</span></span>|  
|[<span data-ttu-id="903f1-115">GetOffset (método)</span><span class="sxs-lookup"><span data-stu-id="903f1-115">GetOffset Method</span></span>](icordebugvariablehome-getoffset-method.md)|<span data-ttu-id="903f1-116">Obtiene el desplazamiento del registro base para una variable.</span><span class="sxs-lookup"><span data-stu-id="903f1-116">Gets the offset from the base register for a variable.</span></span>|  
|[<span data-ttu-id="903f1-117">GetRegister (método)</span><span class="sxs-lookup"><span data-stu-id="903f1-117">GetRegister Method</span></span>](icordebugvariablehome-getregister-method.md)|<span data-ttu-id="903f1-118">Obtiene el registro que contiene una variable con un tipo de ubicación de `VLT_REGISTER`y el registro base de una variable con un tipo de ubicación de `VLT_REGISTER_RELATIVE`.</span><span class="sxs-lookup"><span data-stu-id="903f1-118">Gets the register that contains a variable with a location type of `VLT_REGISTER`, and the base register for a variable with a location type of `VLT_REGISTER_RELATIVE`.</span></span>|  
|[<span data-ttu-id="903f1-119">GetSlotIndex (método)</span><span class="sxs-lookup"><span data-stu-id="903f1-119">GetSlotIndex Method</span></span>](icordebugvariablehome-getslotindex-method.md)|<span data-ttu-id="903f1-120">Obtiene el índice de ranura administrado de una variable local.</span><span class="sxs-lookup"><span data-stu-id="903f1-120">Gets the managed slot-index of a local variable.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="903f1-121">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="903f1-121">Example</span></span>  
 <span data-ttu-id="903f1-122">En el siguiente fragmento de código se usa el objeto [interfaces icordebugcode4](icordebugcode4-interface.md) denominado `pCode4`.</span><span class="sxs-lookup"><span data-stu-id="903f1-122">The following code fragment uses the [ICorDebugCode4](icordebugcode4-interface.md) object named `pCode4`.</span></span>  
  
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
  
## <a name="requirements"></a><span data-ttu-id="903f1-123">Requisitos de</span><span class="sxs-lookup"><span data-stu-id="903f1-123">Requirements</span></span>  
 <span data-ttu-id="903f1-124">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="903f1-124">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="903f1-125">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="903f1-125">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="903f1-126">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="903f1-126">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="903f1-127">**.NET Framework versiones:** [!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="903f1-127">**.NET Framework Versions:** [!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="903f1-128">Vea también</span><span class="sxs-lookup"><span data-stu-id="903f1-128">See also</span></span>

- [<span data-ttu-id="903f1-129">Interfaces de depuración</span><span class="sxs-lookup"><span data-stu-id="903f1-129">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="903f1-130">ICorDebugVariableHomeEnum (interfaz)</span><span class="sxs-lookup"><span data-stu-id="903f1-130">ICorDebugVariableHomeEnum Interface</span></span>](icordebugvariablehomeenum-interface.md)
