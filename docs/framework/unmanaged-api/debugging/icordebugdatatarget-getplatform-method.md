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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 309c31dacd801f1c46a2d37932124638bc157cd6
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59214032"
---
# <a name="icordebugdatatargetgetplatform-method"></a>ICorDebugDataTarget::GetPlatform (Método)
Proporciona información acerca de la plataforma, incluida la arquitectura de procesador y del sistema operativo, en el que se está ejecutando el proceso de destino.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
HRESULT GetPlatform([out] CorDebugPlatform * pTargetPlatform);  
```  
  
## <a name="parameters"></a>Parámetros  
 `pTargetPlatform`  
 [out] Un puntero a un [CorDebugPlatformEnum](../../../../docs/framework/unmanaged-api/debugging/cordebugplatform-enumeration.md) enumeración que describe la plataforma de destino.  
  
## <a name="remarks"></a>Comentarios  
 El `CorDebugPlatformEnum` se usa el valor de enumeración devuelto por la [ICorDebug](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md) interfaz para determinar los detalles del proceso de destino, como su tamaño de puntero, el diseño del espacio de direcciones, conjunto de registros, formato de instrucción, el diseño de contexto, y convenciones de llamada.  
  
 El `pTargetPlatform` valor puede hacer referencia a una plataforma que se está emulando para el destino en lugar de especificar el hardware real en uso. Por ejemplo, debe usar un proceso que se ejecuta en el Windows en el entorno de Windows (WOW) en una edición de 64 bits del sistema operativo Windows la `CORDB_PLATFORM_WINDOWS_X86` valor de la [CorDebugPlatformEnum](../../../../docs/framework/unmanaged-api/debugging/cordebugplatform-enumeration.md) enumeración.  
  
 Este método debe ejecutarse correctamente. Si se produce un error, la plataforma de destino es inutilizable. El método puede producir un error por las razones siguientes:  
  
-   La plataforma que se está emulando para el destino es inutilizable.  
  
-   El hardware real de la plataforma de destino es inutilizable.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado**: CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [ICorDebugDataTarget (Interfaz)](../../../../docs/framework/unmanaged-api/debugging/icordebugdatatarget-interface.md)
- [Interfaces para depuración](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [Depuración](../../../../docs/framework/unmanaged-api/debugging/index.md)
