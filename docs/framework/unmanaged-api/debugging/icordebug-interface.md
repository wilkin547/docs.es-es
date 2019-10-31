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
ms.openlocfilehash: ee6bcbc9f3377735ed289d52afddb6efa755b16d
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73134075"
---
# <a name="icordebug-interface"></a>ICorDebug (Interfaz)
Proporciona métodos que permiten a los desarrolladores depurar aplicaciones en el entorno de Common Language Runtime (CLR).  
  
> [!NOTE]
> La depuración en modo mixto (código administrado y nativo) no se admite en Windows 95, Windows 98 ni Windows ME, ni en plataformas que no son x86 (como IA64 y AMD64).  
  
## <a name="methods"></a>Métodos  
  
|Método|Descripción|  
|------------|-----------------|  
|[CanLaunchOrAttach (método)](../../../../docs/framework/unmanaged-api/debugging/icordebug-canlaunchorattach-method.md)|Determina si el inicio de un nuevo proceso o la asociación al proceso dado es posible en el contexto del equipo actual y de la configuración en tiempo de ejecución.|  
|[CreateProcess (método)](../../../../docs/framework/unmanaged-api/debugging/icordebug-createprocess-method.md)|Inicia un proceso y su subproceso primario bajo el control del depurador.|  
|[DebugActiveProcess (método)](../../../../docs/framework/unmanaged-api/debugging/icordebug-debugactiveprocess-method.md)|Asocia el depurador a un proceso existente.|  
|[EnumerateProcesses (método)](../../../../docs/framework/unmanaged-api/debugging/icordebug-enumerateprocesses-method.md)|Obtiene un enumerador para los procesos que se están depurando.|  
|[GetProcess (método)](../../../../docs/framework/unmanaged-api/debugging/icordebug-getprocess-method.md)|Devuelve el objeto "ICorDebugProcess" con el identificador de proceso especificado.|  
|[Initialize (método)](../../../../docs/framework/unmanaged-api/debugging/icordebug-initialize-method.md)|Inicializa el objeto `ICorDebug`.|  
|[SetManagedHandler (método)](../../../../docs/framework/unmanaged-api/debugging/icordebug-setmanagedhandler-method.md)|Especifica el objeto de controlador de eventos para los eventos administrados.|  
|[SetUnmanagedHandler (método)](../../../../docs/framework/unmanaged-api/debugging/icordebug-setunmanagedhandler-method.md)|Especifica el objeto de controlador de eventos para los eventos no administrados.|  
|[Terminate (método)](../../../../docs/framework/unmanaged-api/debugging/icordebug-terminate-method.md)|Finaliza el objeto `ICorDebug`.|  
  
## <a name="remarks"></a>Comentarios  
 `ICorDebug` representa un bucle de procesamiento de eventos para un proceso del depurador. El depurador debe esperar a la devolución de llamada [ICorDebugManagedCallback:: ExitProcess](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-exitprocess-method.md) de todos los procesos que se están depurando antes de liberar esta interfaz.  
  
 El objeto `ICorDebug` es el objeto inicial para controlar toda la depuración administrada. En las versiones 1,0 y 1,1 de .NET Framework, este objeto era un objeto `CoClass` creado a partir de COM. En la versión .NET Framework 2,0, este objeto ya no es un objeto `CoClass`. Debe crearse mediante la función [CreateDebuggingInterfaceFromVersion (](../../../../docs/framework/unmanaged-api/hosting/createdebugginginterfacefromversion-function.md) , que es más compatible con la versión. Esta nueva función de creación permite a los clientes obtener una implementación específica de `ICorDebug`, que también emula una versión específica de la API de depuración.  
  
> [!NOTE]
> Esta interfaz no admite que se la llame de forma remota, ya sea entre procesos o entre equipos.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [Interfaces de depuración](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
