---
title: Depuración en Silverlight
ms.date: 03/30/2017
helpviewer_keywords:
- debugging API [Silverlight]
- Silverlight, debugging
ms.assetid: 5e903e04-17d0-4014-ac9a-a43330ec8b1c
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 80cee666a05432099a380a5ac547a5ca28698c31
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33436038"
---
# <a name="silverlight-debugging"></a>Depuración en Silverlight
En los temas de esta sección describen el entorno y las interfaces que Common Language Runtime (CLR) proporciona para admitir la depuración de aplicaciones basadas en Silverlight que se ejecutan en el sistema operativo Windows, o en la plataforma Macintosh.  
  
## <a name="in-this-section"></a>En esta sección  
 [EnumerateCLRs (función)](../../../../docs/framework/unmanaged-api/debugging/enumerateclrs-function.md)  
 Proporciona un mecanismo para enumerar los CLR de un proceso.  
  
 [CloseCLREnumeration (Función)](../../../../docs/framework/unmanaged-api/debugging/closeclrenumeration-function.md)  
 Cierra los eventos de inicio continuo de CLR válidos ubicados en una matriz de identificadores devuelta por la [EnumerateCLRs (función)](../../../../docs/framework/unmanaged-api/debugging/enumerateclrs-function.md)y libera la memoria para las matrices de rutas de cadenas y los identificadores.  
  
 [CreateCoreClrDebugTarget (Función)](../../../../docs/framework/unmanaged-api/debugging/createcoreclrdebugtarget-function.md)  
 Crea una conexión a un destino remoto para la enumeración de procesos y tiempos de ejecución.  
  
 [CreateCordbObject (Función)](../../../../docs/framework/unmanaged-api/debugging/createcordbobject-function.md)  
 Crea una interfaz de depurador que proporciona la funcionalidad para crear instancias de una sesión de depuración administrada en un proceso remoto.  
  
 [CreateVersionStringFromModule (Función)](../../../../docs/framework/unmanaged-api/debugging/createversionstringfrommodule-function.md)  
 Crea una cadena de versión a partir de una ruta de acceso de CLR en un proceso de destino.  
  
 [CreateDebuggingInterfaceFromVersion (Función)](../../../../docs/framework/unmanaged-api/debugging/createdebugginginterfacefromversion-function-for-silverlight.md)  
 Acepta una cadena de versión CLR que se devuelve desde [CreateVersionStringFromModule (función)](../../../../docs/framework/unmanaged-api/debugging/createversionstringfrommodule-function.md)función y devuelve una interfaz de depurador correspondiente.  
  
 [CoreClrDebugProcInfo (estructura)](../../../../docs/framework/unmanaged-api/debugging/coreclrdebugprocinfo-structure.md)  
 Representa un proceso que se ejecuta en un equipo remoto.  
  
 [CoreClrDebugRuntimeInfo (estructura)](../../../../docs/framework/unmanaged-api/debugging/coreclrdebugruntimeinfo-structure.md)  
 Representa una instancia de CLR que se carga en un proceso en un equipo remoto.  
  
 [GetStartupNotificationEvent (Función)](../../../../docs/framework/unmanaged-api/debugging/getstartupnotificationevent-function.md)  
 Crea o abre un identificador de evento al que señalará cualquier Common Language Runtime (CLR) que se cargue en el proceso de destino especificado.  
  
 [ICoreClrDebugTarget (interfaz)](../../../../docs/framework/unmanaged-api/debugging/icoreclrdebugtarget-interface.md)  
 Crea una conexión a un destino remoto para la enumeración de procesos y tiempos de ejecución.  
  
 [InitDbgTransportManager (Función)](../../../../docs/framework/unmanaged-api/debugging/initdbgtransportmanager-function.md)  
 Inicializa el administrador de transporte para conectarse a un destino remoto para la enumeración de proceso y tiempo de ejecución.  
  
 [ShutdownDbgTransportManager (Función)](../../../../docs/framework/unmanaged-api/debugging/shutdowndbgtransportmanager-function.md)  
 Cierra el administrador de transporte para una conexión a un equipo de destino remoto.  
  
## <a name="see-also"></a>Vea también  
 [Coclases para la depuración](../../../../docs/framework/unmanaged-api/debugging/debugging-coclasses.md)  
 [Interfaces de depuración](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)  
 [Funciones estáticas globales de depuración](../../../../docs/framework/unmanaged-api/debugging/debugging-global-static-functions.md)  
 [Enumeraciones de depuración](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)  
 [Estructuras de depuración](../../../../docs/framework/unmanaged-api/debugging/debugging-structures.md)
