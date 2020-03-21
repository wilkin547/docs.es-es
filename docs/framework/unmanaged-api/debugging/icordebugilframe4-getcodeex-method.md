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
ms.openlocfilehash: ef2e4bc0caddd6b13c8dbe8edb59e0673519421b
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79178794"
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
 [en] Un [ilCodeKind](ilcodekind-enumeration.md) miembro de enumeración que especifica si el lenguaje intermedio (IL) definido por la solicitud ReJIT del generador de perfiles se incluye en el marco.  
  
 `ppCode`  
 [fuera] Puntero a la dirección de un objeto "ICorDebugCode" que representa el código que se está ejecutando este marco de pila.  
  
## <a name="remarks"></a>Observaciones  
 Este método es similar a la [ICorDebugFrame::GetCode](icordebugframe-getcode-method.md) método, excepto que opcionalmente tiene acceso al código definido por la solicitud ReJIT del generador de perfiles. Llamar a este `flags` método `ILCODE_ORIGINAL_IL` con un valor de es equivalente a llamar a [GetCode](icordebugframe-getcode-method.md); si se instrumenta el método, su IL no será accesible. `ILCODE_REJIT_IL` permite al depurador acceder al IL definido por la solicitud ReJIT del generador de perfiles+. Si la IL no `ppCode` está instrumentada, es `S_OK` **null**y el método devuelve .  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]  
  
## <a name="see-also"></a>Consulte también

- [ICorDebugILFrame4 (interfaz)](icordebugilframe4-interface.md)
- [Interfaces de depuración](debugging-interfaces.md)
- [ReJIT: Una guía de cómo hacerlo](https://docs.microsoft.com/archive/blogs/davbr/rejit-a-how-to-guide)
