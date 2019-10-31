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
ms.openlocfilehash: 306a07450b8ae6d29875ca0cc4679390472e4d1d
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73121040"
---
# <a name="icordebugvariablehome-interface"></a>Interfaz ICorDebugVariableHome
Representa una variable local o un argumento de una función.  
  
## <a name="methods"></a>Métodos  
  
|Método|Descripción|  
|------------|-----------------|  
|[GetArgumentIndex (método)](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-getargumentindex-method.md)|Obtiene el índice de un argumento de función.|  
|[GetCode (método)](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-getcode-method.md)|Obtiene la instancia de "ICorDebugCode" que contiene este objeto `ICorDebugVariableHome`.|  
|[GetLiveRange (método)](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-getliverange-method.md)|Obtiene el intervalo nativo en el que esta variable está activa.|  
|[GetLocationType (método)](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-getlocationtype-method.md)|Obtiene el tipo de la ubicación nativa de la variable.|  
|[GetOffset (método)](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-getoffset-method.md)|Obtiene el desplazamiento del registro base para una variable.|  
|[GetRegister (método)](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-getregister-method.md)|Obtiene el registro que contiene una variable con un tipo de ubicación de `VLT_REGISTER`y el registro base de una variable con un tipo de ubicación de `VLT_REGISTER_RELATIVE`.|  
|[GetSlotIndex (método)](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-getslotindex-method.md)|Obtiene el índice de ranura administrado de una variable local.|  
  
## <a name="example"></a>Ejemplo  
 En el siguiente fragmento de código se usa el objeto [interfaces icordebugcode4](../../../../docs/framework/unmanaged-api/debugging/icordebugcode4-interface.md) denominado `pCode4`.  
  
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
 **Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [Interfaces de depuración](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [ICorDebugVariableHomeEnum (interfaz)](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehomeenum-interface.md)
