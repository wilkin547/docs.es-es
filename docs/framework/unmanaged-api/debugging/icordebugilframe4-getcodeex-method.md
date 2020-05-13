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
ms.openlocfilehash: 582e28c18f36b253425b1e0a2034cdd262fddd57
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/12/2020
ms.locfileid: "83213743"
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
  
## <a name="parameters"></a>Parámetros  
 `flags`  
 de Un miembro de enumeración [ILCodeKind](ilcodekind-enumeration.md) que especifica si el lenguaje intermedio (IL) definido por la solicitud ReJIT del generador de perfiles está incluido en el marco.  
  
 `ppCode`  
 enuncia Puntero a la dirección de un objeto "ICorDebugCode" que representa el código que está ejecutando este marco de pila.  
  
## <a name="remarks"></a>Observaciones  
 Este método es similar al método [ICorDebugFrame:: getCode](icordebugframe-getcode-method.md) , salvo que, de manera opcional, tiene acceso al código definido por la solicitud ReJIT del generador de perfiles. Llamar a este método con un `flags` valor de `ILCODE_ORIGINAL_IL` es equivalente a llamar a [getCode](icordebugframe-getcode-method.md); si el método está instrumentado, no se podrá acceder a su Il. `ILCODE_REJIT_IL` permite al depurador acceder al IL definido por la solicitud ReJIT del generador de perfiles+. Si el IL no está instrumentado, `ppCode` es **null**y el método devuelve `S_OK` .  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]  
  
## <a name="see-also"></a>Consulte también

- [ICorDebugILFrame4 (Interfaz)](icordebugilframe4-interface.md)
- [Interfaces para depuración](debugging-interfaces.md)
- [ReJIT: Guía de procedimientos](https://docs.microsoft.com/archive/blogs/davbr/rejit-a-how-to-guide)
