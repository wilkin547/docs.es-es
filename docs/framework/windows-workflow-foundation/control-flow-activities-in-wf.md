---
title: Actividades de flujo de control en WF
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 6892885b-f7c5-4aea-8f5e-28863fb4ae75
caps.latest.revision: "16"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 1e8520e34cf9bd9d31e9b877849e7c9611d6d989
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="control-flow-activities-in-wf"></a>Actividades de flujo de control en WF
[!INCLUDE[netfx_current_long](../../../includes/netfx-current-long-md.md)] proporciona varias actividades para controlar el flujo de ejecución dentro de un flujo de trabajo. Algunas de estas actividades (como `Switch` y `If`) implementan estructuras de control de flujo similares a las que se encuentran en los entornos de programación, como [!INCLUDE[csprcs](../../../includes/csprcs-md.md)], mientras que otras modelan nuevas estructuras de programación (como `Pick`.)  
  
 Tenga en cuenta que mientras las actividades `Parallel` y `ParallelForEach` programan varias actividades secundarias para su ejecución simultánea, solo se usa un subproceso para un flujo de trabajo. Cada actividad secundaria de estas actividades se ejecuta secuencialmente mientras que las actividades sucesivas no se ejecutan hasta que las anteriores se completen o pasen a estar inactivas. Como resultado, estas actividades son muy útiles para las aplicaciones en las que se deben ejecutar de un modo intercalado varias actividades de bloqueo. Si ninguna de las actividades secundarias de estas actividades se está bloqueando o está inactiva, una actividad `Parallel` se ejecuta simplemente como una actividad `Sequence` y una actividad `ParallelForEach` se ejecuta como una actividad `ForEach`. Sin embargo, si se usan actividades asincrónicas (como actividades que derivan de <xref:System.Activities.AsyncCodeActivity>) o actividades de mensajería, el control pasará a la bifurcación siguiente mientras la actividad secundaria espera que se reciba su mensaje o se complete su trabajo asincrónico.  
  
## <a name="flow-control-activities"></a>Actividades de control de flujo  
  
|Actividad|Descripción|  
|--------------|-----------------|  
|<xref:System.Activities.Statements.DoWhile>|Ejecuta las actividades contenidas una vez y continúa haciéndolo mientras que haya una condición con el valor `true`.|  
|<xref:System.Activities.Statements.ForEach%601>|Ejecuta una instrucción incrustada en secuencia para cada elemento de una colección. <xref:System.Activities.Statements.ForEach%601> es similar a la palabra clave `foreach`, pero se implementa como una actividad en lugar de como una instrucción de lenguaje.|  
|<xref:System.Activities.Statements.If>|Ejecuta las actividades contenidas si una condición es `true`. Puede ejecutar actividades contenidas en la propiedad <xref:System.Activities.Statements.If.Else%2A> si la condición es `false`.|  
|<xref:System.Activities.Statements.Parallel>|Ejecuta las actividades contenidas en paralelo.|  
|<xref:System.Activities.Statements.ParallelForEach%601>|Ejecuta una instrucción incrustada en paralelo para cada elemento de una colección.|  
|<xref:System.Activities.Statements.Pick>|Proporciona el modelado del flujo de control basado en eventos.|  
|<xref:System.Activities.Statements.PickBranch>|Representa una ruta de acceso de ejecución potencial en una actividad <xref:System.Activities.Statements.Pick>.|  
|<xref:System.Activities.Statements.Sequence>|Ejecuta las actividades contenidas en secuencia.|  
|<xref:System.Activities.Statements.Switch%601>|Selecciona una opción de varias actividades que ejecutar, según el valor de una expresión determinada.|  
|<xref:System.Activities.Statements.While>|Ejecuta las actividades contenidas mientras una condición sea `true`.|
