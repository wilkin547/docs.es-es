---
description: 'Más información acerca de: depuración de Silverlight'
title: Depuración en Silverlight
ms.date: 03/30/2017
helpviewer_keywords:
- debugging API [Silverlight]
- Silverlight, debugging
ms.assetid: 5e903e04-17d0-4014-ac9a-a43330ec8b1c
ms.openlocfilehash: 54a3f7f4b2de867509ff94dafa25c067a78b3ee6
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99800544"
---
# <a name="silverlight-debugging"></a>Depuración en Silverlight

En los temas de esta sección describen el entorno y las interfaces que Common Language Runtime (CLR) proporciona para admitir la depuración de aplicaciones basadas en Silverlight que se ejecutan en el sistema operativo Windows, o en la plataforma Macintosh.  
  
## <a name="in-this-section"></a>En esta sección  

 [EnumerateCLRs (Función)](enumerateclrs-function.md)  
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
  
 [CoreClrDebugProcInfo (Estructura)](coreclrdebugprocinfo-structure.md)  
 Representa un proceso que se ejecuta en un equipo remoto.  
  
 [CoreClrDebugRuntimeInfo (Estructura)](coreclrdebugruntimeinfo-structure.md)  
 Representa una instancia de CLR que se carga en un proceso en un equipo remoto.  
  
 [GetStartupNotificationEvent (Función)](getstartupnotificationevent-function.md)  
 Crea o abre un identificador de evento al que apuntará cualquier Common Language Runtime (CLR) que se cargue en el proceso de destino especificado.  
  
 [ICoreClrDebugTarget (Interfaz)](icoreclrdebugtarget-interface.md)  
 Crea una conexión a un destino remoto para la enumeración de procesos y tiempos de ejecución.  
  
 [InitDbgTransportManager (Función)](initdbgtransportmanager-function.md)  
 Inicializa el administrador de transporte para conectarse a un destino remoto para la enumeración de procesos y tiempos de ejecución.  
  
 [ShutdownDbgTransportManager (Función)](shutdowndbgtransportmanager-function.md)  
 Cierra el administrador de transporte para una conexión a un equipo de destino remoto.  
  
## <a name="see-also"></a>Vea también

- [Coclases para la depuración](debugging-coclasses.md)
- [Interfaces para depuración](debugging-interfaces.md)
- [Funciones estáticas globales para la depuración](debugging-global-static-functions.md)
- [Enumeraciones de depuración](debugging-enumerations.md)
- [Estructuras de depuración](debugging-structures.md)
