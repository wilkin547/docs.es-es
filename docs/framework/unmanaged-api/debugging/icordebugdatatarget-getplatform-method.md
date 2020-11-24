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
ms.openlocfilehash: e8612b23cbfa506fddb2fad712848b285b9ac28e
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95679798"
---
# <a name="icordebugdatatargetgetplatform-method"></a>ICorDebugDataTarget::GetPlatform (Método)

Proporciona información sobre la plataforma, incluida la arquitectura del procesador y el sistema operativo, en la que se ejecuta el proceso de destino.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT GetPlatform([out] CorDebugPlatform * pTargetPlatform);  
```  
  
## <a name="parameters"></a>Parámetros  

 `pTargetPlatform`  
 enuncia Puntero a una enumeración [CorDebugPlatformEnum (](cordebugplatform-enumeration.md) que describe la plataforma de destino.  
  
## <a name="remarks"></a>Comentarios  

 La `CorDebugPlatformEnum` interfaz [ICorDebug](icordebug-interface.md) usa el valor devuelto de la enumeración para determinar los detalles del proceso de destino, como su tamaño de puntero, el diseño del espacio de direcciones, el conjunto de registros, el formato de instrucciones, el diseño del contexto y las convenciones de llamada.  
  
 El `pTargetPlatform` valor puede hacer referencia a una plataforma que se está emulando para el destino en lugar de especificar el hardware real en uso. Por ejemplo, un proceso que se ejecuta en el entorno de Windows en Windows (WOW) en una edición de 64 bits del sistema operativo Windows debe usar el `CORDB_PLATFORM_WINDOWS_X86` valor de la enumeración [CorDebugPlatformEnum (](cordebugplatform-enumeration.md) .  
  
 Este método debe realizarse correctamente. Si se produce un error, la plataforma de destino no se puede usar. El método puede producir un error por las razones siguientes:  
  
- La plataforma que se está emulando para el destino no se puede usar.  
  
- El hardware real de la plataforma de destino no se puede usar.  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Consulte también

- [ICorDebugDataTarget (Interfaz)](icordebugdatatarget-interface.md)
- [Interfaces para depuración](debugging-interfaces.md)
- [Depuración](index.md)
