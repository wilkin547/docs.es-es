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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 5574b457925506f3178af7c636a834fad4fdd15e
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54502461"
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
  
#### <a name="parameters"></a>Parámetros  
 `flags`  
 [in] Un [ILCodeKind](../../../../docs/framework/unmanaged-api/debugging/ilcodekind-enumeration.md) miembro de enumeración que especifica si el lenguaje intermedio (IL) definido por solicitud de ReJIT del generador de perfiles se incluye en el marco.  
  
 `ppCode`  
 [out] Un puntero a la dirección de un objeto "ICorDebugCode" que representa el código que se está ejecutando este marco de pila.  
  
## <a name="remarks"></a>Comentarios  
 Este método es similar a la [ICorDebugFrame](../../../../docs/framework/unmanaged-api/debugging/icordebugframe-getcode-method.md) método, excepto que accede opcionalmente a código definido por la solicitud de ReJIT del generador de perfiles. Llamar a este método con un `flags` valor `ILCODE_ORIGINAL_IL` equivale a llamar a [GetCode](../../../../docs/framework/unmanaged-api/debugging/icordebugframe-getcode-method.md); si el método está instrumentado, su IL no será accesible. `ILCODE_REJIT_IL` permite al depurador acceder al IL definido por la solicitud ReJIT del generador de perfiles+. Si el IL no se ha instrumentado, `ppCode` es **null**, y el método devuelve `S_OK`.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado**: CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]  
  
## <a name="see-also"></a>Vea también
- [ICorDebugILFrame4 (interfaz)](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe4-interface.md)
- [Interfaces de depuración](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [ReJIT: Una guía de procedimientos](https://blogs.msdn.com/b/davbr/archive/2011/10/12/rejit-a-how-to-guide.aspx)
