---
title: ICorDebug (Interfaz)
ms.date: 03/30/2017
api_name:
- ICorDebug
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebug
helpviewer_keywords:
- ICorDebug interface [.NET Framework debugging]
ms.assetid: 33f431d7-ab1a-494d-8af2-20ab15aba194
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 193232ce1006a9cf209db9330343386404948440
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59168290"
---
# <a name="icordebug-interface"></a>ICorDebug (Interfaz)
Proporciona métodos que permiten a los desarrolladores depurar aplicaciones en el entorno de common language runtime (CLR).  
  
> [!NOTE]
>  No se admite la depuración en modo mixto (código administrado y nativo) en Windows 95, Windows 98 o Windows Millennium Edition o en plataformas que no sean x86 (por ejemplo, IA64 y AMD64).  
  
## <a name="methods"></a>Métodos  
  
|Método|Descripción|  
|------------|-----------------|  
|[CanLaunchOrAttach (método)](../../../../docs/framework/unmanaged-api/debugging/icordebug-canlaunchorattach-method.md)|Determina si inicia un proceso nuevo o asociar al proceso especificado es posible dentro del contexto de la configuración actual de la máquina y en tiempo de ejecución.|  
|[CreateProcess (método)](../../../../docs/framework/unmanaged-api/debugging/icordebug-createprocess-method.md)|Inicia un proceso y su subproceso principal bajo el control del depurador.|  
|[DebugActiveProcess (método)](../../../../docs/framework/unmanaged-api/debugging/icordebug-debugactiveprocess-method.md)|Asocia al depurador a un proceso existente.|  
|[EnumerateProcesses (método)](../../../../docs/framework/unmanaged-api/debugging/icordebug-enumerateprocesses-method.md)|Obtiene un enumerador para los procesos que se están depurando.|  
|[GetProcess (método)](../../../../docs/framework/unmanaged-api/debugging/icordebug-getprocess-method.md)|Devuelve el objeto "ICorDebugProcess" con el identificador de proceso determinado.|  
|[Initialize (método)](../../../../docs/framework/unmanaged-api/debugging/icordebug-initialize-method.md)|Inicializa el objeto `ICorDebug`.|  
|[SetManagedHandler (método)](../../../../docs/framework/unmanaged-api/debugging/icordebug-setmanagedhandler-method.md)|Especifica el objeto de controlador de eventos para eventos administrados.|  
|[SetUnmanagedHandler (método)](../../../../docs/framework/unmanaged-api/debugging/icordebug-setunmanagedhandler-method.md)|Especifica el objeto de controlador de eventos para eventos no administrados.|  
|[Terminate (método)](../../../../docs/framework/unmanaged-api/debugging/icordebug-terminate-method.md)|Finaliza el `ICorDebug` objeto.|  
  
## <a name="remarks"></a>Comentarios  
 `ICorDebug` Representa un bucle de procesamiento de eventos para un proceso de depuración. El depurador debe esperar el [ICorDebugManagedCallback](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-exitprocess-method.md) de todos los procesos que se está depurando antes de liberar esta interfaz de devolución de llamada.  
  
 La `ICorDebug` objeto es el objeto inicial para controlar la depuración administrada todo aún más. En las versiones 1.0 y 1.1 de .NET Framework, este objeto era un `CoClass` objeto creado desde COM. En la versión 2.0 de .NET Framework, este objeto ya no es un `CoClass` objeto. Debe crearse mediante el [CreateDebuggingInterfaceFromVersion](../../../../docs/framework/unmanaged-api/hosting/createdebugginginterfacefromversion-function.md) función, que es más consciente de versión. Esta nueva función de creación permite a los clientes obtener una implementación específica de `ICorDebug`, que también emula una versión específica de la API de depuración.  
  
> [!NOTE]
>  Esta interfaz no admite que se la llame de forma remota, ya sea entre procesos o entre equipos.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado**: CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [Interfaces de depuración](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
