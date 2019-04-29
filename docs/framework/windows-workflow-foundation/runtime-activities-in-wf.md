---
title: Actividades de tiempo de ejecución en WF
ms.date: 03/30/2017
ms.assetid: e5ae8c31-19bc-4655-88b3-6b75cd6a1bd5
ms.openlocfilehash: 7981d3f75c8fd2d0ddd2ae0233f425c2907c270c
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61938104"
---
# <a name="runtime-activities-in-wf"></a>Actividades de tiempo de ejecución en WF
[!INCLUDE[netfx_current_short](../../../includes/netfx-current-short-md.md)] ofrece varias actividades proporcionadas por el sistema para tener acceso a las características del tiempo de ejecución del flujo de trabajo, como persistencia y terminación.  
  
|Actividad|Descripción|  
|--------------|-----------------|  
|<xref:System.Activities.Statements.Persist>|Solicita de manera explícita que el flujo de trabajo conserve su estado.|  
|<xref:System.Activities.Statements.TerminateWorkflow>|Finaliza la instancia de flujo de trabajo en ejecución.|  
|<xref:System.Activities.Statements.NoPersistScope>|Una actividad de contenedor que evita que las actividades secundarias se conserven.|
