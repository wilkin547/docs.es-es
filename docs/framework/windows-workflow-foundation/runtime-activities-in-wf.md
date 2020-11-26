---
title: Actividades de tiempo de ejecución en WF
ms.date: 03/30/2017
ms.assetid: e5ae8c31-19bc-4655-88b3-6b75cd6a1bd5
ms.openlocfilehash: b0472c669d69d9397843a004bee1bb2c15e139c4
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96245712"
---
# <a name="runtime-activities-in-wf"></a>Actividades de tiempo de ejecución en WF

[!INCLUDE[netfx_current_short](../../../includes/netfx-current-short-md.md)] ofrece varias actividades proporcionadas por el sistema para tener acceso a las características del tiempo de ejecución del flujo de trabajo, como persistencia y terminación.  
  
|Actividad|Descripción|  
|--------------|-----------------|  
|<xref:System.Activities.Statements.Persist>|Solicita de manera explícita que el flujo de trabajo conserve su estado.|  
|<xref:System.Activities.Statements.TerminateWorkflow>|Finaliza la instancia de flujo de trabajo en ejecución.|  
|<xref:System.Activities.Statements.NoPersistScope>|Una actividad de contenedor que evita que las actividades secundarias se conserven.|
