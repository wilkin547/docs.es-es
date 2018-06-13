---
title: Actividades de tiempo de ejecución en WF
ms.date: 03/30/2017
ms.assetid: e5ae8c31-19bc-4655-88b3-6b75cd6a1bd5
ms.openlocfilehash: 7981d3f75c8fd2d0ddd2ae0233f425c2907c270c
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33513040"
---
# <a name="runtime-activities-in-wf"></a>Actividades de tiempo de ejecución en WF
[!INCLUDE[netfx_current_short](../../../includes/netfx-current-short-md.md)] ofrece varias actividades proporcionadas por el sistema para tener acceso a las características del tiempo de ejecución del flujo de trabajo, como persistencia y terminación.  
  
|Actividad|Descripción|  
|--------------|-----------------|  
|<xref:System.Activities.Statements.Persist>|Solicita de manera explícita que el flujo de trabajo conserve su estado.|  
|<xref:System.Activities.Statements.TerminateWorkflow>|Finaliza la instancia de flujo de trabajo en ejecución.|  
|<xref:System.Activities.Statements.NoPersistScope>|Una actividad de contenedor que evita que las actividades secundarias se conserven.|
