---
title: Período de detección de instancias ejecutables
ms.date: 03/30/2017
ms.assetid: 4ea5c787-b638-47fd-bfc8-ede8c2898ce6
ms.openlocfilehash: aefde2726bb2ccc15f9e68009e5e141602b13b10
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96245775"
---
# <a name="runnable-instances-detection-period"></a>Período de detección de instancias ejecutables

El almacén de instancias de flujo de trabajo de SQL ejecuta una tarea interna que se inicia periódicamente y que detecta instancias de flujo de trabajo ejecutables o activables en la base de datos de persistencia. La propiedad **período de detección de instancias ejecutables** del almacén de instancias de flujo de trabajo de SQL especifica el período de tiempo después del cual el almacén de instancias de flujo de trabajo de SQL ejecuta una tarea de detección para detectar las instancias de flujo de trabajo ejecutables o activables en la base de datos de persistencia después del ciclo  
  
 Al establecer un intervalo más corto para esta propiedad, se reduce el tiempo entre la expiración de un temporizador asociado a una instancia de flujo de trabajo y la señal del evento y la posterior carga de la instancia. Sin embargo, también aumenta la carga de procesamiento en un host y puede no ser aconsejable en escenarios donde los temporizadores de larga duración o los errores del host son escasos. El tipo de la propiedad es TimeSpan y su valor sigue el formato: hh:mm:ss. El valor mínimo de esta propiedad es 00:00:01. El valor predeterminado de la propiedad es 00:00:05.  
  
 Para obtener más información sobre la detección y activación de instancias de flujo de trabajo ejecutables y activables, vea [activación de instancias](instance-activation.md).
