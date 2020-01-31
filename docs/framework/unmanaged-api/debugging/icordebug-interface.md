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
ms.openlocfilehash: 0ca66f001d04bc86b64e0fe2d1cd37559e4fc633
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/28/2020
ms.locfileid: "76785118"
---
# <a name="icordebug-interface"></a>ICorDebug (Interfaz)
Proporciona métodos que permiten a los desarrolladores depurar aplicaciones en el entorno de Common Language Runtime (CLR).  
  
> [!NOTE]
> La depuración en modo mixto (código administrado y nativo) no se admite en Windows 95, Windows 98 ni Windows ME, ni en plataformas que no son x86 (como IA64 y AMD64).  
  
## <a name="methods"></a>Métodos  
  
|Método|Descripción|  
|------------|-----------------|  
|[CanLaunchOrAttach (método)](icordebug-canlaunchorattach-method.md)|Determina si el inicio de un nuevo proceso o la asociación al proceso dado es posible en el contexto del equipo actual y de la configuración en tiempo de ejecución.|  
|[CreateProcess (método)](icordebug-createprocess-method.md)|Inicia un proceso y su subproceso primario bajo el control del depurador.|  
|[DebugActiveProcess (método)](icordebug-debugactiveprocess-method.md)|Asocia el depurador a un proceso existente.|  
|[EnumerateProcesses (método)](icordebug-enumerateprocesses-method.md)|Obtiene un enumerador para los procesos que se están depurando.|  
|[GetProcess (método)](icordebug-getprocess-method.md)|Devuelve el objeto "ICorDebugProcess" con el identificador de proceso especificado.|  
|[Initialize (método)](icordebug-initialize-method.md)|Inicializa el objeto `ICorDebug`.|  
|[SetManagedHandler (método)](icordebug-setmanagedhandler-method.md)|Especifica el objeto de controlador de eventos para los eventos administrados.|  
|[SetUnmanagedHandler (método)](icordebug-setunmanagedhandler-method.md)|Especifica el objeto de controlador de eventos para los eventos no administrados.|  
|[Terminate (método)](icordebug-terminate-method.md)|Finaliza el objeto `ICorDebug`.|  
  
## <a name="remarks"></a>Notas  
 `ICorDebug` representa un bucle de procesamiento de eventos para un proceso del depurador. El depurador debe esperar a la devolución de llamada [ICorDebugManagedCallback:: ExitProcess](icordebugmanagedcallback-exitprocess-method.md) de todos los procesos que se están depurando antes de liberar esta interfaz.  
  
 El objeto `ICorDebug` es el objeto inicial para controlar toda la depuración administrada. En las versiones 1,0 y 1,1 de .NET Framework, este objeto era un objeto `CoClass` creado a partir de COM. En la versión .NET Framework 2,0, este objeto ya no es un objeto `CoClass`. Debe crearse mediante la función [CreateDebuggingInterfaceFromVersion (](../../../../docs/framework/unmanaged-api/hosting/createdebugginginterfacefromversion-function.md) , que es más compatible con la versión. Esta nueva función de creación permite a los clientes obtener una implementación específica de `ICorDebug`, que también emula una versión específica de la API de depuración.  
  
> [!NOTE]
> Esta interfaz no admite que se la llame de forma remota, ya sea entre procesos o entre equipos.  
  
## <a name="requirements"></a>Requisitos de  
 **Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **.NET Framework versiones:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [Interfaces de depuración](debugging-interfaces.md)
