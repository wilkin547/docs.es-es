---
title: ICorDebugDataTarget::GetPlatform (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugDataTarget.GetPlatform Method
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugDataTarget::GetPlatform
helpviewer_keywords:
- GetPlatform method [.NET Framework debugging]
- ICorDebugDataTarget::GetPlatform method [.NET Framework debugging]
ms.assetid: 9ee96c9d-7a3d-4129-a6cc-7675c7f2dda4
topic_type:
- apiref
ms.openlocfilehash: 3654c94975d16e35d5c3d8e762730d17509a2c6d
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/28/2020
ms.locfileid: "76788879"
---
# <a name="icordebugdatatargetgetplatform-method"></a>ICorDebugDataTarget::GetPlatform (Método)
Proporciona información sobre la plataforma, incluida la arquitectura del procesador y el sistema operativo, en la que se ejecuta el proceso de destino.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT GetPlatform([out] CorDebugPlatform * pTargetPlatform);  
```  
  
## <a name="parameters"></a>Parameters  
 `pTargetPlatform`  
 enuncia Puntero a una enumeración [CorDebugPlatformEnum (](cordebugplatform-enumeration.md) que describe la plataforma de destino.  
  
## <a name="remarks"></a>Notas  
 La interfaz [ICorDebug](icordebug-interface.md) usa el valor devuelto `CorDebugPlatformEnum` enumeración para determinar los detalles del proceso de destino, como su tamaño de puntero, el diseño del espacio de direcciones, el conjunto de registros, el formato de la instrucción, el diseño del contexto y las convenciones de llamada.  
  
 El valor `pTargetPlatform` puede hacer referencia a una plataforma que se está emulando para el destino en lugar de especificar el hardware real en uso. Por ejemplo, un proceso que se ejecuta en el entorno de Windows en Windows (WOW) en una edición de 64 bits del sistema operativo Windows debe utilizar el valor `CORDB_PLATFORM_WINDOWS_X86` de la enumeración [CorDebugPlatformEnum (](cordebugplatform-enumeration.md) .  
  
 Este método debe realizarse correctamente. Si se produce un error, la plataforma de destino no se puede usar. El método puede producir un error por las razones siguientes:  
  
- La plataforma que se está emulando para el destino no se puede usar.  
  
- El hardware real de la plataforma de destino no se puede usar.  
  
## <a name="requirements"></a>Requisitos de  
 **Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **.NET Framework versiones:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [ICorDebugDataTarget (interfaz)](icordebugdatatarget-interface.md)
- [Interfaces de depuración](debugging-interfaces.md)
- [Depuración](index.md)
