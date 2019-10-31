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
ms.openlocfilehash: 9a74fd64e046ab3a8943e9a975e4de808c662677
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73090958"
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
 de Un miembro de enumeración [ILCodeKind](../../../../docs/framework/unmanaged-api/debugging/ilcodekind-enumeration.md) que especifica si el lenguaje intermedio (IL) definido por la solicitud ReJIT del generador de perfiles está incluido en el marco.  
  
 `ppCode`  
 enuncia Puntero a la dirección de un objeto "ICorDebugCode" que representa el código que está ejecutando este marco de pila.  
  
## <a name="remarks"></a>Comentarios  
 Este método es similar al método [ICorDebugFrame:: getCode](../../../../docs/framework/unmanaged-api/debugging/icordebugframe-getcode-method.md) , salvo que, de manera opcional, tiene acceso al código definido por la solicitud ReJIT del generador de perfiles. Llamar a este método con un valor `flags` de `ILCODE_ORIGINAL_IL` es equivalente a llamar a [getCode](../../../../docs/framework/unmanaged-api/debugging/icordebugframe-getcode-method.md); Si el método está instrumentado, no se podrá obtener acceso a su IL. `ILCODE_REJIT_IL` permite al depurador acceder al IL definido por la solicitud ReJIT del generador de perfiles+. Si no se instrumenta IL, `ppCode` es **null**y el método devuelve `S_OK`.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [ICorDebugILFrame4 (interfaz)](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe4-interface.md)
- [Interfaces de depuración](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [ReJIT: Guía de procedimientos](https://blogs.msdn.microsoft.com/davbr/2011/10/12/rejit-a-how-to-guide/)
