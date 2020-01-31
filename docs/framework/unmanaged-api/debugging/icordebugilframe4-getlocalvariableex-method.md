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
ms.openlocfilehash: 017c14e9170087f3c3c9de64f50d165fc91aa297
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/28/2020
ms.locfileid: "76782414"
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
 de Miembro de la enumeración [ILCodeKind](ilcodekind-enumeration.md) que especifica si en el marco se incluye una variable agregada en la instrumentación ReJIT del generador de perfiles.  
  
 `dwIndex`  
 [in] Índice de la variable local en el marco de pila de IL.  
  
 `ppValue`  
 enuncia Puntero a la dirección de un objeto "ICorDebugValue" que representa el valor recuperado.  
  
## <a name="remarks"></a>Notas  
 Este método es similar al método [getlocalvariable (](icordebugilframe-getlocalvariable-method.md) , salvo que, de manera opcional, tiene acceso a una variable agregada en la instrumentación ReJIT del generador de perfiles. Llamar a este método con un valor `flags` de `ILCODE_ORIGINAL_IL` es equivalente a llamar a [getlocalvariable (](icordebugilframe-getlocalvariable-method.md); Si el método está instrumentado con variables locales adicionales, no se puede tener acceso a esas variables. `ILCODE_REJIT_IL` permite al depurador acceder a las variables locales agregadas en la instrumentación ReJIT del generador de perfiles. Si el IL no se ha instrumentado, el método devuelve `E_INVALIDARG`.  
  
## <a name="requirements"></a>Requisitos de  
 **Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **.NET Framework versiones:** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [ICorDebugILFrame4 (interfaz)](icordebugilframe4-interface.md)
- [Interfaces de depuración](debugging-interfaces.md)
- [ReJIT: Guía de procedimientos](https://docs.microsoft.com/archive/blogs/davbr/rejit-a-how-to-guide)
