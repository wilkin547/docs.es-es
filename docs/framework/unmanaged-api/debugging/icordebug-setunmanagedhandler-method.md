---
title: ICorDebug::SetUnmanagedHandler (Método)
ms.date: 03/30/2017
api_name:
- ICorDebug.SetUnmanagedHandler
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebug::SetUnmanagerHandler
helpviewer_keywords:
- SetUnmanagedHandler method [.NET Framework debugging]
- ICorDebug::SetUnmanagedHandler method [.NET Framework debugging]
ms.assetid: 6b546be4-f86d-4536-8cfc-1d08e5066eb6
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: c234b3953130f53d7e6b583cd92670149a70689b
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59168875"
---
# <a name="icordebugsetunmanagedhandler-method"></a>ICorDebug::SetUnmanagedHandler (Método)
Especifica el objeto de controlador de eventos para eventos no administrados.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
HRESULT SetUnmanagedHandler (  
    [in] ICorDebugUnmanagedCallback  *pCallback  
);  
```  
  
## <a name="parameters"></a>Parámetros  
 `pCallback`  
 [in] Un puntero a un [ICorDebugUnmanagedCallback](../../../../docs/framework/unmanaged-api/debugging/icordebugunmanagedcallback-interface.md) objeto que representa el controlador de eventos para eventos no administrados.  
  
## <a name="remarks"></a>Comentarios  
 El controlador de eventos de objeto para no administrada de eventos deben establecerse después de llamar a [ICorDebug](../../../../docs/framework/unmanaged-api/debugging/icordebug-initialize-method.md) y antes de llamar a [ICorDebug:: CreateProcess](../../../../docs/framework/unmanaged-api/debugging/icordebug-createprocess-method.md) o [DebugActiveProcess ](../../../../docs/framework/unmanaged-api/debugging/icordebug-debugactiveprocess-method.md). Sin embargo, para fines de herencia, no debe establecer el objeto de controlador de eventos para los eventos no administrados hasta que se produce el primer evento de depuración nativo. En concreto, si `ICorDebug::CreateProcess` ha establecido la marca CREATE_SUSPENDED, no se pueden enviar los eventos hasta que se reanude el subproceso principal de depuración nativo.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado**: CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [ICorDebug (Interfaz)](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md)
