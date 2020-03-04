---
title: Eventos ETW de grupo de subprocesos
ms.date: 03/30/2017
helpviewer_keywords:
- thread pool events [.NET Framework]
- ETW, thread pool events (CLR)
ms.assetid: f2a21e3a-3b6c-4433-97f3-47ff16855ecc
ms.openlocfilehash: 249d0607ddd280bcb4e9cf3ef34b28ff8ada3b04
ms.sourcegitcommit: 43d10ef65f0f1fd6c3b515e363bde11a3fcd8d6d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/03/2020
ms.locfileid: "78240498"
---
# <a name="thread-pool-etw-events"></a>Eventos ETW de grupo de subprocesos
Estos eventos recopilan información sobre los subprocesos de E/S y de trabajo.  
  
 Hay dos grupos de eventos de grupo de subprocesos:  
  
- [Eventos de grupo de subprocesos de trabajo](#worker-thread-pool-events), que proporcionan información sobre cómo una aplicación usa el grupo de subprocesos y el efecto de las cargas de trabajo en el control de simultaneidad.  
  
- [Eventos de grupo de subprocesos de E/S](#io-thread-events), que proporcionan información sobre los subprocesos de E/S que se crean, se retiran, se anula su retirada o finalizan en el grupo de subprocesos.  

## <a name="worker-thread-pool-events"></a>Eventos de grupo de subprocesos de trabajo
 Estos eventos se relacionan con el grupo de subprocesos de trabajo de runtime y proporcionan notificaciones de eventos de subproceso (por ejemplo, cuando se crea o se detiene un subproceso). El grupo de subprocesos de trabajo usa un algoritmo adaptable para el control de simultaneidad, en el que el número de subprocesos se calcula en función del rendimiento medido. Los eventos de grupo de subprocesos de trabajo pueden usarse para saber cómo una aplicación utiliza el grupo de subprocesos y el efecto que ciertas cargas de trabajo pueden tener en el control de simultaneidad.  
  
### <a name="threadpoolworkerthreadstart-and-threadpoolworkerthreadstop"></a>ThreadPoolWorkerThreadStart y ThreadPoolWorkerThreadStop  
 En la tabla siguiente se muestra la palabra clave y el nivel correspondientes a estos eventos. (Para obtener más información, vea [CLR ETW Keywords and Levels](clr-etw-keywords-and-levels.md)).  
  
|Palabra clave para generar el evento|Nivel|  
|-----------------------------------|-----------|  
|`ThreadingKeyword` (0x10000)|Informativo (4)|  
  
 En la siguiente tabla se muestra la información del evento.  
  
|evento|Id. de evento|Se genera cuando|  
|-|-|-|  
|`ThreadPoolWorkerThreadStart`|50|Se crea un subproceso de trabajo.|  
|`ThreadPoolWorkerThreadStop`|51|Se detiene un subproceso de trabajo.|  
|`ThreadPoolWorkerThreadRetirementStart`|52|Se retira un subproceso de trabajo.|  
|`ThreadPoolWorkerThreadRetirementStop`|53|Un subproceso de trabajo retirado se vuelve activo.|  
  
 En la siguiente tabla se muestran los datos del evento.  
  
|Nombre de campo|Tipo de datos|Description|  
|----------------|---------------|-----------------|  
|ActiveWorkerThreadCount|win:UInt32|Número de subprocesos de trabajo disponibles para procesar trabajo, incluidos los que ya están procesando trabajo.|  
|RetiredWorkerThreadCount|win:UInt32|Número de subprocesos de trabajo que no están disponibles para procesar trabajo, pero que se mantienen en reserva en caso de que posteriormente se necesiten más subprocesos.|  
|ClrInstanceID|Win:UInt16|Identificador único para la instancia de CLR o CoreCLR.|  
  
### <a name="threadpoolworkerthreadadjustment"></a>ThreadPoolWorkerThreadAdjustment  
 Estos eventos de grupo de subprocesos proporcionan información para entender y depurar el comportamiento del algoritmo de inserción de subprocesos (control de simultaneidad). El grupo de subprocesos de trabajo usa la información internamente.  
  
#### <a name="threadpoolworkerthreadadjustmentsample"></a>ThreadPoolWorkerThreadAdjustmentSample  
 En la tabla siguiente se muestra la palabra clave y el nivel.  
  
|Palabra clave para generar el evento|Nivel|  
|-----------------------------------|-----------|  
|`ThreadingKeyword` (0x10000)|Informativo (4)|  
  
 En la siguiente tabla se muestra la información del evento.  
  
|evento|Id. de evento|Description|  
|-----------|--------------|-----------------|  
|`ThreadPoolWorkerThreadAdjustmentSample`|54|Se refiere a la recopilación de información para un ejemplo; es decir, una medición del rendimiento con un determinado nivel de simultaneidad en un instante de tiempo.|  
  
 En la siguiente tabla se muestran los datos del evento.  
  
|Nombre de campo|Tipo de datos|Description|  
|----------------|---------------|-----------------|  
|Rendimiento|win:Double|Número de finalizaciones por unidad de tiempo.|  
|ClrInstanceID|Win:UInt16|Identificador único para la instancia de CLR o CoreCLR.|  
  
#### <a name="threadpoolworkerthreadadjustmentadjustment"></a>ThreadPoolWorkerThreadAdjustmentAdjustment  
 En la tabla siguiente se muestra la palabra clave y el nivel.  
  
|Palabra clave para generar el evento|Nivel|  
|-----------------------------------|-----------|  
|`ThreadingKeyword` (0x10000)|Informativo (4)|  
  
 En la siguiente tabla se muestra la información del evento.  
  
|evento|Id. de evento|Description|  
|-----------|--------------|-----------------|  
|`ThreadPoolWorkerThreadAdjustmentAdjustment`|55|Registra un cambio en el control, cuando el algoritmo de inserción de subproceso (hill-climbing) determina que tiene lugar un cambio en el nivel de simultaneidad.|  
  
 En la siguiente tabla se muestran los datos del evento.  
  
|Nombre de campo|Tipo de datos|Description|  
|----------------|---------------|-----------------|  
|AverageThroughput|win:Double|Rendimiento medio de un ejemplo de mediciones.|  
|NewWorkerThreadCount|win:UInt32|Nuevo número de subprocesos de trabajo activos.|  
|Motivo|win:UInt32|Razón para el ajuste.<br /><br /> 0x00: preparación.<br /><br /> 0x01: inicializando.<br /><br /> 0x02: movimiento aleatorio.<br /><br /> 0x03: movimiento escalada.<br /><br /> 0x04: cambiar punto.<br /><br /> 0x05: estabilización.<br /><br /> 0x06: colapso.<br /><br /> 0x07: tiempo de espera de subproceso agotado.|  
|ClrInstanceID|Win:UInt16|Identificador único para la instancia de CLR o CoreCLR.|  
  
#### <a name="threadpoolworkerthreadadjustmentstats"></a>ThreadPoolWorkerThreadAdjustmentStats  
 En la tabla siguiente se muestra la palabra clave y el nivel.  
  
|Palabra clave para generar el evento|Nivel|  
|-----------------------------------|-----------|  
|`ThreadingKeyword` (0x10000)|Informativo (4)|  
  
 En la siguiente tabla se muestra la información del evento.  
  
|evento|Id. de evento|Description|  
|-----------|--------------|-----------------|  
|`ThreadPoolWorkerThreadAdjustmentStats`|56|Recopila datos en el grupo de subprocesos.|  
  
 En la siguiente tabla se muestran los datos del evento.  
  
|Nombre de campo|Tipo de datos|Description|  
|----------------|---------------|-----------------|  
|Duración|win:Double|Cantidad de tiempo, en segundos, durante el que se recopilaron estas estadísticas.|  
|Rendimiento|win:Double|Promedio de finalizaciones por segundo durante este intervalo.|  
|ThreadWave|win:Double|Reservado para uso interno.|  
|ThroughputWave|win:Double|Reservado para uso interno.|  
|ThroughputErrorEstimate|win:Double|Reservado para uso interno.|  
|AverageThroughputErrorEstimate|win:Double|Reservado para uso interno.|  
|ThroughputRatio|win:Double|Mejora relativa en el rendimiento producida por variaciones en el número de subprocesos de trabajo activos durante este intervalo.|  
|Confidence|win:Double|Medida de la validez del campo ThroughputRatio.|  
|NewcontrolSetting|win:Double|El número de subprocesos de trabajo activos que servirá de línea de base para las variaciones futuras en el recuento de subprocesos activos.|  
|NewThreadWaveMagnitude|Win:UInt16|La magnitud de variaciones futuras en el recuento de subprocesos activos.|  
|ClrInstanceID|Win:UInt16|Identificador único para la instancia de CLR o CoreCLR.|  

## <a name="io-thread-events"></a>Eventos de subprocesos de E/S  
 Estos eventos de grupo de subprocesos se producen para los subprocesos del grupo de subprocesos de E/S (puertos de finalización), que es asincrónico.  
  
### <a name="iothreadcreate_v1"></a>IOThreadCreate_V1  
 En la tabla siguiente se muestra la palabra clave y el nivel.  
  
|Palabra clave para generar el evento|Nivel|  
|-----------------------------------|-----------|  
|`ThreadingKeyword` (0x10000)|Informativo (4)|  
  
 En la siguiente tabla se muestra la información del evento.  
  
|evento|Id. de evento|Se genera cuando|  
|-|-|-|  
|`IOThreadCreate_V1`|44|Se crea un subproceso de E/S en el grupo de subprocesos.|  
  
 En la siguiente tabla se muestran los datos del evento.  
  
|Nombre de campo|Tipo de datos|Description|  
|----------------|---------------|-----------------|  
|Recuento|win:UInt64|Número de subprocesos de E/S, incluido el subproceso recién creado.|  
|NumRetired|win:UInt64|Número de subprocesos de trabajo retirados.|  
|ClrInstanceID|Win:UInt16|Identificador único para la instancia de CLR o CoreCLR.|  
  
### <a name="iothreadretire_v1"></a>IOThreadRetire_V1  
 En la tabla siguiente se muestra la palabra clave y el nivel.  
  
|Palabra clave para generar el evento|Nivel|  
|-----------------------------------|-----------|  
|`ThreadingKeyword` (0x10000)|Informativo (4)|  
  
 En la siguiente tabla se muestra la información del evento.  
  
|evento|Id. de evento|Se genera cuando|  
|-----------|--------------|-----------------|  
|`IOThreadRetire_V1`|46|Un subproceso de E/S se convierte en un candidato para la retirada.|  
  
 En la siguiente tabla se muestran los datos del evento.  
  
|Nombre de campo|Tipo de datos|Description|  
|----------------|---------------|-----------------|  
|Recuento|win:UInt64|Número de subprocesos de E/S restantes en el grupo de subprocesos.|  
|NumRetired|win:UInt64|Número de subprocesos de E/S retirados.|  
|ClrInstanceID|Win:UInt16|Identificador único para la instancia de CLR o CoreCLR.|  
  
### <a name="iothreadunretire_v1"></a>IOThreadUnretire_V1  
 En la tabla siguiente se muestra la palabra clave y el nivel.  
  
|Palabra clave para generar el evento|Nivel|  
|-----------------------------------|-----------|  
|`ThreadingKeyword` (0x10000)|Informativo (4)|  
  
 En la siguiente tabla se muestra la información del evento.  
  
|evento|Id. de evento|Se genera cuando|  
|-----------|--------------|-----------------|  
|`IOThreadUnretire_V1`|47|La retirada de un subproceso de E/S se anula debido a que llega una E/S dentro de un período de espera y después de que el subproceso se convierte en un candidato para la retirada.|  
  
 En la siguiente tabla se muestran los datos del evento.  
  
|Nombre de campo|Tipo de datos|Description|  
|----------------|---------------|-----------------|  
|Recuento|win:UInt64|Número de subprocesos de E/S en el grupo de subprocesos, incluido este.|  
|NumRetired|win:UInt64|Número de subprocesos de E/S retirados.|  
|ClrInstanceID|Win:UInt16|Identificador único para la instancia de CLR o CoreCLR.|  
  
### <a name="iothreadterminate"></a>IOThreadTerminate  
 En la tabla siguiente se muestra la palabra clave y el nivel.  
  
|Palabra clave para generar el evento|Nivel|  
|-----------------------------------|-----------|  
|`ThreadingKeyword` (0x10000)|Informativo (4)|  
  
 En la siguiente tabla se muestra la información del evento.  
  
|evento|Id. de evento|Se genera cuando|  
|-----------|--------------|-----------------|  
|`IOThreadTerminate`|45|Se termina un subproceso de e/s en el grupo de subprocesos.|  
  
 En la siguiente tabla se muestran los datos del evento.  
  
|Nombre de campo|Tipo de datos|Description|  
|----------------|---------------|-----------------|  
|Recuento|win:UInt64|Número de subprocesos de E/S restantes en el grupo de subprocesos.|  
|NumRetired|win:UInt64|Número de subprocesos de E/S retirados.|  
|ClrInstanceID|Win:UInt16|Identificador único para la instancia de CLR o CoreCLR.|  
  
## <a name="see-also"></a>Vea también

- [Eventos ETW de CLR](clr-etw-events.md)
