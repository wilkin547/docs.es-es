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
ms.openlocfilehash: ee263e8c49cd6da7278bd2299557336629720d2f
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79178778"
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
  
## <a name="parameters"></a>Parámetros  
 `flags`  
 [en] Un [ILCodeKind](ilcodekind-enumeration.md) miembro de enumeración que especifica si una variable agregada en la instrumentación ReJIT del generador de perfiles se incluye en el marco.  
  
 `dwIndex`  
 [in] Índice de la variable local en el marco de pila de IL.  
  
 `ppValue`  
 [fuera] Puntero a la dirección de un objeto "ICorDebugValue" que representa el valor recuperado.  
  
## <a name="remarks"></a>Observaciones  
 Este método es similar al método [GetLocalVariable,](icordebugilframe-getlocalvariable-method.md) excepto que, opcionalmente, tiene acceso a una variable agregada en la instrumentación ReJIT del generador de perfiles. Llamar a este `flags` método `ILCODE_ORIGINAL_IL` con un valor de es equivalente a llamar a [GetLocalVariable](icordebugilframe-getlocalvariable-method.md); si el método se instrumenta con variables locales adicionales, no se puede acceder a esas variables. `ILCODE_REJIT_IL` permite al depurador acceder a las variables locales agregadas en la instrumentación ReJIT del generador de perfiles. Si el IL no se ha instrumentado, el método devuelve `E_INVALIDARG`.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]  
  
## <a name="see-also"></a>Consulte también

- [ICorDebugILFrame4 (interfaz)](icordebugilframe4-interface.md)
- [Interfaces de depuración](debugging-interfaces.md)
- [ReJIT: Una guía de cómo hacerlo](https://docs.microsoft.com/archive/blogs/davbr/rejit-a-how-to-guide)
