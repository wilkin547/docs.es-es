---
title: ICorDebugILFrame4::GetLocalVariableEx (Método)
ms.date: 03/30/2017
dev_langs:
- cpp
api_name:
- ICorDebugILFrame4.GetCodeEx
api_location:
- mscordbi.dll
api_type:
- COM
ms.assetid: 0c8676f8-ca0d-4998-b64d-fefac7e38912
topic_type:
- apiref
ms.openlocfilehash: 89a8aa1f789ad71b04bc5fed8885f55ee25c4609
ms.sourcegitcommit: 7e2128d4a4c45b4274bea3b8e5760d4694569ca1
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/14/2020
ms.locfileid: "75937668"
---
# <a name="icordebugilframe4getlocalvariableex-method"></a>ICorDebugILFrame4::GetLocalVariableEx (Método)
[Compatible con .NET Framework 4.5.2 y versiones posteriores]  
  
 Obtiene el valor de la variable local especificada en este marco de pila de lenguaje intermedio (IL) y, opcionalmente, accede a una variable agregada en la instrumentación ReJIT del generador de perfiles.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp
HRESULT GetLocalVariableEx(  
   [in] ILCodeKind flags,   
   [in] DWORD dwIndex,   
   [out] ICorDebugValue **ppValue  
);  
```  
  
## <a name="parameters"></a>Parameters  
 `flags`  
 de Miembro de la enumeración [ILCodeKind](../../../../docs/framework/unmanaged-api/debugging/ilcodekind-enumeration.md) que especifica si en el marco se incluye una variable agregada en la instrumentación ReJIT del generador de perfiles.  
  
 `dwIndex`  
 [in] Índice de la variable local en el marco de pila de IL.  
  
 `ppValue`  
 enuncia Puntero a la dirección de un objeto "ICorDebugValue" que representa el valor recuperado.  
  
## <a name="remarks"></a>Notas  
 Este método es similar al método [getlocalvariable (](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe-getlocalvariable-method.md) , salvo que, de manera opcional, tiene acceso a una variable agregada en la instrumentación ReJIT del generador de perfiles. Llamar a este método con un valor `flags` de `ILCODE_ORIGINAL_IL` es equivalente a llamar a [getlocalvariable (](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe-getlocalvariable-method.md); Si el método está instrumentado con variables locales adicionales, no se puede tener acceso a esas variables. `ILCODE_REJIT_IL` permite al depurador acceder a las variables locales agregadas en la instrumentación ReJIT del generador de perfiles. Si el IL no se ha instrumentado, el método devuelve `E_INVALIDARG`.  
  
## <a name="requirements"></a>Requisitos de  
 **Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **.NET Framework versiones:** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [ICorDebugILFrame4 (interfaz)](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe4-interface.md)
- [Interfaces de depuración](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [ReJIT: Guía de procedimientos](https://docs.microsoft.com/archive/blogs/davbr/rejit-a-how-to-guide)
