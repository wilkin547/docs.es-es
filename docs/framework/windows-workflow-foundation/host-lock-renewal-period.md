---
description: 'Más información acerca de: período de renovación del bloqueo de host'
title: Período de renovación del bloqueo de host
ms.date: 03/30/2017
ms.assetid: f8ba94fc-27e0-4d8e-8f85-50a6d2a3cd43
ms.openlocfilehash: 88348c4cebd7ac42657c4ba68238a3b58a8f0d1a
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99742218"
---
# <a name="host-lock-renewal-period"></a>Período de renovación del bloqueo de host

La propiedad **período de renovación del bloqueo de host** del almacén de instancias de flujo de trabajo de SQL le permite especificar el período de tiempo en el que el host renueva su bloqueo en una instancia de flujo de trabajo. El bloqueo sigue siendo válido durante el período de renovación del bloqueo de host más un período de 30 segundos adicional. Si se produce un error cuando el host renueva el bloqueo (en otras palabras, amplía la concesión) dentro de este período de tiempo, el bloqueo expira y el proveedor de persistencia desbloquea la instancia. El valor de esta propiedad es de tipo TimeSpan con el formato "HH: mm: SS". El valor mínimo permitido es "00:00:01" (1 segundo). El valor predeterminado de esta propiedad es "00:00:30" (30 segundos).  
  
 Esta propiedad es significativa en escenarios donde se produce un error en un host de servicio de flujo de trabajo antes de que pueda desbloquear una instancia de servicio de flujo de trabajo que posee. En este escenario, el proveedor de persistencia quita el bloqueo en la instancia de servicio de flujo de trabajo en la base de datos de persistencia después de que el bloqueo expire. De este modo, otro host de servicio de flujo de trabajo en el mismo equipo o en otro en una granja de servidores puede adquirir el bloqueo y cargar la instancia de servicio de flujo de trabajo en la memoria para reanudar su ejecución a partir de su último estado persistente.  
  
 Establecer un valor superior para este propiedad provoca el bloqueo de las instancias de servicio de flujo de trabajo en la base de datos de persistencia para un período más largo y, por tanto, se retrasa la recuperación de la instancia desde el último punto de persistencia. Establecer un intervalo corto para esta propiedad provoca que la nueva instancia del host de servicio de flujo de trabajo recoja la instancia fallida de servicio de flujo de trabajo rápidamente aunque causa un aumento en la carga de trabajo del host de servicio de flujo de trabajo y la base de datos SQL Server.  
  
 El almacén de instancias de flujo de trabajo de SQL ejecuta una tarea interna que periódicamente se activa y detecta las instancias con bloqueos expirados en ellos. Cuando encuentra instancias con bloqueos expirados, coloca las instancias en la tabla RunnableInstances para que un host de flujo de trabajo pueda escoger y ejecutar estas instancias.
