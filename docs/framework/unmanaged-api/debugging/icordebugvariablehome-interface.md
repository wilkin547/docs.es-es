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
# <a name="icordebugvariablehome-interface"></a>Interfaz ICorDebugVariableHome
Representa una variable local o argumento de una función.  
  
## <a name="methods"></a>Métodos  
  
|Método|Descripción|  
|------------|-----------------|  
|[Método GetArgumentIndex](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-getargumentindex-method.md)|Obtiene el índice de un argumento de función.|  
|[Método GetCode](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-getcode-method.md)|Obtiene la instancia de "ICorDebugCode" que contiene este `ICorDebugVariableHome` objeto.|  
|[Método GetLiveRange](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-getliverange-method.md)|Obtiene el intervalo nativo a través de la que esta variable está activa.|  
|[Método GetLocationType](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-getlocationtype-method.md)|Obtiene el tipo de ubicación de la variable nativa.|  
|[Método GetOffset](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-getoffset-method.md)|Obtiene el desplazamiento desde el registro de base de una variable.|  
|[Método GetRegister](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-getregister-method.md)|Obtiene el registro que contiene una variable con un tipo de ubicación de `VLT_REGISTER`y el registro de base de una variable con un tipo de ubicación de `VLT_REGISTER_RELATIVE`.|  
|[Método GetSlotIndex](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-getslotindex-method.md)|Obtiene el índice de ranura administrado de una variable local.|  
  
## <a name="example"></a>Ejemplo  
 El siguiente fragmento de código utiliza el [ICorDebugCode4](../../../../docs/framework/unmanaged-api/debugging/icordebugcode4-interface.md) objeto denominado `pCode4`.  
  
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
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado**: CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [Interfaces para depuración](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [Interfaz ICorDebugVariableHomeEnum](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehomeenum-interface.md)
