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
ms.openlocfilehash: 74c5036bdc8a4a75e5711c6dc1d34d8f2c21128f
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33408676"
---
# <a name="icordebug-interface"></a>ICorDebug (Interfaz)
Proporciona métodos que permiten a los desarrolladores depurar aplicaciones en el entorno de common language runtime (CLR).  
  
> [!NOTE]
>  No se admite la depuración en modo mixto (código administrado y nativo) en Windows 95, Windows 98 o Windows ME, ni en plataformas de x86 no (por ejemplo, IA64 y AMD64).  
  
## <a name="methods"></a>Métodos  
  
|Método|Descripción|  
|------------|-----------------|  
|[CanLaunchOrAttach (método)](../../../../docs/framework/unmanaged-api/debugging/icordebug-canlaunchorattach-method.md)|Determina si es posible en el contexto de la configuración actual de la máquina y en tiempo de ejecución iniciar un nuevo proceso o asociarse al proceso especificado.|  
|[CreateProcess (método)](../../../../docs/framework/unmanaged-api/debugging/icordebug-createprocess-method.md)|Inicia un proceso y su subproceso principal bajo el control del depurador.|  
|[DebugActiveProcess (método)](../../../../docs/framework/unmanaged-api/debugging/icordebug-debugactiveprocess-method.md)|Asocia al depurador a un proceso existente.|  
|[EnumerateProcesses (método)](../../../../docs/framework/unmanaged-api/debugging/icordebug-enumerateprocesses-method.md)|Obtiene un enumerador para los procesos que se están depurando.|  
|[GetProcess (método)](../../../../docs/framework/unmanaged-api/debugging/icordebug-getprocess-method.md)|Devuelve el objeto "ICorDebugProcess" con el identificador de proceso especificado.|  
|[Initialize (método)](../../../../docs/framework/unmanaged-api/debugging/icordebug-initialize-method.md)|Inicializa el `ICorDebug` objeto.|  
|[SetManagedHandler (método)](../../../../docs/framework/unmanaged-api/debugging/icordebug-setmanagedhandler-method.md)|Especifica el objeto de controlador de eventos para los eventos administrados.|  
|[SetUnmanagedHandler (método)](../../../../docs/framework/unmanaged-api/debugging/icordebug-setunmanagedhandler-method.md)|Especifica el objeto de controlador de eventos para eventos no administrados.|  
|[Terminate (método)](../../../../docs/framework/unmanaged-api/debugging/icordebug-terminate-method.md)|Finaliza el `ICorDebug` objeto.|  
  
## <a name="remarks"></a>Comentarios  
 `ICorDebug` Representa un bucle de procesamiento de eventos para un proceso de depuración. El depurador debe esperar a que el [ICorDebugManagedCallback:: ExitProcess](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-exitprocess-method.md) devolución de llamada de todos los procesos que se están depurando antes de liberar esta interfaz.  
  
 La `ICorDebug` objeto es el objeto inicial para controlar la depuración administrada todo posterior. En las versiones 1.0 y 1.1 de .NET Framework, este objeto era un `CoClass` objeto creado a partir de COM. En la versión 2.0 de .NET Framework, este objeto ya no es un `CoClass` objeto. Debe crearse mediante el [CreateDebuggingInterfaceFromVersion](../../../../docs/framework/unmanaged-api/hosting/createdebugginginterfacefromversion-function.md) función, que es más con identificación de versión. Esta nueva función de creación permite a los clientes obtener una implementación específica de `ICorDebug`, que también emula una versión concreta de la API de depuración.  
  
> [!NOTE]
>  Esta interfaz no admite que se la llame de forma remota, ya sea entre procesos o entre equipos.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **Versiones de .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vea también  
 [Interfaces de depuración](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
