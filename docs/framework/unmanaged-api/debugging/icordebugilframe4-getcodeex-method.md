---
title: ICorDebugILFrame4::GetCodeEx (Método)
ms.date: 03/30/2017
dev_langs:
- cpp
api_name:
- ICorDebugILFrame4.GetLocalVariableEx
api_location:
- mscordbi.dll
api_type:
- COM
ms.assetid: aeda0e42-29ee-4ca8-9f21-ac4641677a62
topic_type:
- apiref
ms.openlocfilehash: e77344a99189ec8e234129262d45698c794dc249
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/28/2020
ms.locfileid: "76788514"
---
# <a name="icordebugilframe4getcodeex-method"></a>ICorDebugILFrame4::GetCodeEx (Método)
[Compatible con .NET Framework 4.5.2 y versiones posteriores]  
  
 Obtiene un puntero al código que este marco de pila está ejecutando.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp
HRESULT GetCodeEx(  
   [in] ILCodeKind flags,   
   [out] ICorDebugCode **ppCode  
);  
```  
  
## <a name="parameters"></a>Parameters  
 `flags`  
 de Un miembro de enumeración [ILCodeKind](ilcodekind-enumeration.md) que especifica si el lenguaje intermedio (IL) definido por la solicitud ReJIT del generador de perfiles está incluido en el marco.  
  
 `ppCode`  
 enuncia Puntero a la dirección de un objeto "ICorDebugCode" que representa el código que está ejecutando este marco de pila.  
  
## <a name="remarks"></a>Notas  
 Este método es similar al método [ICorDebugFrame:: getCode](icordebugframe-getcode-method.md) , salvo que, de manera opcional, tiene acceso al código definido por la solicitud ReJIT del generador de perfiles. Llamar a este método con un valor `flags` de `ILCODE_ORIGINAL_IL` es equivalente a llamar a [getCode](icordebugframe-getcode-method.md); Si el método está instrumentado, no se podrá obtener acceso a su IL. `ILCODE_REJIT_IL` permite al depurador acceder al IL definido por la solicitud ReJIT del generador de perfiles+. Si no se instrumenta IL, `ppCode` es **null**y el método devuelve `S_OK`.  
  
## <a name="requirements"></a>Requisitos de  
 **Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **.NET Framework versiones:** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [ICorDebugILFrame4 (interfaz)](icordebugilframe4-interface.md)
- [Interfaces de depuración](debugging-interfaces.md)
- [ReJIT: Guía de procedimientos](https://docs.microsoft.com/archive/blogs/davbr/rejit-a-how-to-guide)
