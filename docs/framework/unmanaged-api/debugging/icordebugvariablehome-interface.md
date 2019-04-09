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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 339a0f502b7e47f7bee82a0da92185481d909e64
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59202916"
---
# <a name="icordebugvariablehome-interface"></a><span data-ttu-id="6324d-102">Interfaz ICorDebugVariableHome</span><span class="sxs-lookup"><span data-stu-id="6324d-102">ICorDebugVariableHome Interface</span></span>
<span data-ttu-id="6324d-103">Representa una variable local o argumento de una función.</span><span class="sxs-lookup"><span data-stu-id="6324d-103">Represents a local variable or argument of a function.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="6324d-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="6324d-104">Methods</span></span>  
  
|<span data-ttu-id="6324d-105">Método</span><span class="sxs-lookup"><span data-stu-id="6324d-105">Method</span></span>|<span data-ttu-id="6324d-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="6324d-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="6324d-107">Método GetArgumentIndex</span><span class="sxs-lookup"><span data-stu-id="6324d-107">GetArgumentIndex Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-getargumentindex-method.md)|<span data-ttu-id="6324d-108">Obtiene el índice de un argumento de función.</span><span class="sxs-lookup"><span data-stu-id="6324d-108">Gets the index of a function argument.</span></span>|  
|[<span data-ttu-id="6324d-109">Método GetCode</span><span class="sxs-lookup"><span data-stu-id="6324d-109">GetCode Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-getcode-method.md)|<span data-ttu-id="6324d-110">Obtiene la instancia de "ICorDebugCode" que contiene este `ICorDebugVariableHome` objeto.</span><span class="sxs-lookup"><span data-stu-id="6324d-110">Gets the "ICorDebugCode" instance that contains this `ICorDebugVariableHome` object.</span></span>|  
|[<span data-ttu-id="6324d-111">Método GetLiveRange</span><span class="sxs-lookup"><span data-stu-id="6324d-111">GetLiveRange Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-getliverange-method.md)|<span data-ttu-id="6324d-112">Obtiene el intervalo nativo a través de la que esta variable está activa.</span><span class="sxs-lookup"><span data-stu-id="6324d-112">Gets the native range over which this variable is live.</span></span>|  
|[<span data-ttu-id="6324d-113">Método GetLocationType</span><span class="sxs-lookup"><span data-stu-id="6324d-113">GetLocationType Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-getlocationtype-method.md)|<span data-ttu-id="6324d-114">Obtiene el tipo de ubicación de la variable nativa.</span><span class="sxs-lookup"><span data-stu-id="6324d-114">Gets the type of the variable's native location.</span></span>|  
|[<span data-ttu-id="6324d-115">Método GetOffset</span><span class="sxs-lookup"><span data-stu-id="6324d-115">GetOffset Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-getoffset-method.md)|<span data-ttu-id="6324d-116">Obtiene el desplazamiento desde el registro de base de una variable.</span><span class="sxs-lookup"><span data-stu-id="6324d-116">Gets the offset from the base register for a variable.</span></span>|  
|[<span data-ttu-id="6324d-117">Método GetRegister</span><span class="sxs-lookup"><span data-stu-id="6324d-117">GetRegister Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-getregister-method.md)|<span data-ttu-id="6324d-118">Obtiene el registro que contiene una variable con un tipo de ubicación de `VLT_REGISTER`y el registro de base de una variable con un tipo de ubicación de `VLT_REGISTER_RELATIVE`.</span><span class="sxs-lookup"><span data-stu-id="6324d-118">Gets the register that contains a variable with a location type of `VLT_REGISTER`, and the base register for a variable with a location type of `VLT_REGISTER_RELATIVE`.</span></span>|  
|[<span data-ttu-id="6324d-119">Método GetSlotIndex</span><span class="sxs-lookup"><span data-stu-id="6324d-119">GetSlotIndex Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-getslotindex-method.md)|<span data-ttu-id="6324d-120">Obtiene el índice de ranura administrado de una variable local.</span><span class="sxs-lookup"><span data-stu-id="6324d-120">Gets the managed slot-index of a local variable.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="6324d-121">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="6324d-121">Example</span></span>  
 <span data-ttu-id="6324d-122">El siguiente fragmento de código utiliza el [ICorDebugCode4](../../../../docs/framework/unmanaged-api/debugging/icordebugcode4-interface.md) objeto denominado `pCode4`.</span><span class="sxs-lookup"><span data-stu-id="6324d-122">The following code fragment uses the [ICorDebugCode4](../../../../docs/framework/unmanaged-api/debugging/icordebugcode4-interface.md) object named `pCode4`.</span></span>  
  
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
  
## <a name="requirements"></a><span data-ttu-id="6324d-123">Requisitos</span><span class="sxs-lookup"><span data-stu-id="6324d-123">Requirements</span></span>  
 <span data-ttu-id="6324d-124">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6324d-124">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6324d-125">**Encabezado**: CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="6324d-125">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="6324d-126">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="6324d-126">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="6324d-127">Versiones de .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="6324d-127">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="6324d-128">Vea también</span><span class="sxs-lookup"><span data-stu-id="6324d-128">See also</span></span>

- [<span data-ttu-id="6324d-129">Interfaces para depuración</span><span class="sxs-lookup"><span data-stu-id="6324d-129">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [<span data-ttu-id="6324d-130">Interfaz ICorDebugVariableHomeEnum</span><span class="sxs-lookup"><span data-stu-id="6324d-130">ICorDebugVariableHomeEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehomeenum-interface.md)
