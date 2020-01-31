---
title: Depuración en Silverlight
ms.date: 03/30/2017
helpviewer_keywords:
- debugging API [Silverlight]
- Silverlight, debugging
ms.assetid: 5e903e04-17d0-4014-ac9a-a43330ec8b1c
ms.openlocfilehash: 91f311818b615ea8f166bb3362ec52d39fcd0297
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/28/2020
ms.locfileid: "76790326"
---
# <a name="silverlight-debugging"></a>Depuración en Silverlight
En los temas de esta sección describen el entorno y las interfaces que Common Language Runtime (CLR) proporciona para admitir la depuración de aplicaciones basadas en Silverlight que se ejecutan en el sistema operativo Windows, o en la plataforma Macintosh.  
  
## <a name="in-this-section"></a>Esta sección  
 [EnumerateCLRs (función)](enumerateclrs-function.md)  
 Proporciona un mecanismo para enumerar los CLR de un proceso.  
  
 [CloseCLREnumeration (Función)](closeclrenumeration-function.md)  
 Cierra los eventos válidos continue-startup de CLR que se encuentran en una matriz de identificadores devueltos por la [función enumerateclrs (](enumerateclrs-function.md)y libera la memoria para las matrices de rutas de acceso de identificador y de cadena.  
  
 [CreateCoreClrDebugTarget (Función)](createcoreclrdebugtarget-function.md)  
 Crea una conexión a un destino remoto para la enumeración de procesos y tiempos de ejecución.  
  
 [CreateCordbObject (Función)](createcordbobject-function.md)  
 Crea una interfaz de depurador que proporciona la funcionalidad para crear instancias de una sesión de depuración administrada en un proceso remoto.  
  
 [CreateVersionStringFromModule (Función)](createversionstringfrommodule-function.md)  
 Crea una cadena de versión a partir de una ruta de acceso de CLR en un proceso de destino.  
  
 [CreateDebuggingInterfaceFromVersion (Función)](createdebugginginterfacefromversion-function-for-silverlight.md)  
 Acepta una cadena de versión de CLR devuelta por la función de [función createversionstringfrommodule (](createversionstringfrommodule-function.md)y devuelve una interfaz de depurador correspondiente.  
  
 [CoreClrDebugProcInfo (estructura)](coreclrdebugprocinfo-structure.md)  
 Representa un proceso que se ejecuta en un equipo remoto.  
  
 [CoreClrDebugRuntimeInfo (estructura)](coreclrdebugruntimeinfo-structure.md)  
 Representa una instancia de CLR que se carga en un proceso en un equipo remoto.  
  
 [GetStartupNotificationEvent (Función)](getstartupnotificationevent-function.md)  
 Crea o abre un identificador de evento al que apuntará cualquier Common Language Runtime (CLR) que se cargue en el proceso de destino especificado.  
  
 [ICoreClrDebugTarget (interfaz)](icoreclrdebugtarget-interface.md)  
 Crea una conexión a un destino remoto para la enumeración de procesos y tiempos de ejecución.  
  
 [InitDbgTransportManager (Función)](initdbgtransportmanager-function.md)  
 Inicializa el administrador de transporte para conectarse a un destino remoto para la enumeración de procesos y tiempos de ejecución.  
  
 [ShutdownDbgTransportManager (Función)](shutdowndbgtransportmanager-function.md)  
 Cierra el administrador de transporte para una conexión a un equipo de destino remoto.  
  
## <a name="see-also"></a>Vea también

- [Coclases para la depuración](debugging-coclasses.md)
- [Interfaces de depuración](debugging-interfaces.md)
- [Funciones estáticas globales de depuración](debugging-global-static-functions.md)
- [Enumeraciones de depuración](debugging-enumerations.md)
- [Estructuras de depuración](debugging-structures.md)
