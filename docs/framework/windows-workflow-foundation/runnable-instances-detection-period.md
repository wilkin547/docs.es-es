---
title: Período de detección de instancias ejecutables
ms.date: 03/30/2017
ms.assetid: 4ea5c787-b638-47fd-bfc8-ede8c2898ce6
ms.openlocfilehash: 9652dd811f64e5324219b8aa0700ab8219edeeb0
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/09/2019
ms.locfileid: "57709713"
---
# <a name="runnable-instances-detection-period"></a>Período de detección de instancias ejecutables
El almacén de instancias de flujo de trabajo de SQL ejecuta una tarea interna que se inicia periódicamente y que detecta instancias de flujo de trabajo ejecutables o activables en la base de datos de persistencia. El **período de detección de instancias ejecutables** propiedad del Store de instancia de flujo de trabajo de SQL especifica el período de tiempo después del cual el Store de instancia de flujo de trabajo de SQL ejecuta una tarea de detección para detectar cualquier flujo de trabajo ejecutable o activable instancias de la base de datos de persistencia después del ciclo de detección anterior.  
  
 Al establecer un intervalo más corto para esta propiedad, se reduce el tiempo entre la expiración de un temporizador asociado a una instancia de flujo de trabajo y la señal del evento y la posterior carga de la instancia. Sin embargo, también aumenta la carga de procesamiento en un host y puede no ser aconsejable en escenarios donde los temporizadores de larga duración o los errores del host son escasos. El tipo de la propiedad es TimeSpan y su valor sigue el formato: hh:mm:ss. El valor mínimo de esta propiedad es 00:00:01. El valor predeterminado de la propiedad es 00:00:05.  
  
 Para obtener más información, detectar y activar instancias de flujo de trabajo ejecutables y activables, vea [activación de instancias](instance-activation.md).
