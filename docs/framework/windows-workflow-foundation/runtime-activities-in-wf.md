---
title: "Actividades de tiempo de ejecución en WF"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: e5ae8c31-19bc-4655-88b3-6b75cd6a1bd5
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 022f12448d697ba179fb3705f18962e6b0c44239
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/02/2017
---
# <a name="runtime-activities-in-wf"></a>Actividades de tiempo de ejecución en WF
[!INCLUDE[netfx_current_short](../../../includes/netfx-current-short-md.md)] ofrece varias actividades proporcionadas por el sistema para tener acceso a las características del tiempo de ejecución del flujo de trabajo, como persistencia y terminación.  
  
|Actividad|Descripción|  
|--------------|-----------------|  
|<xref:System.Activities.Statements.Persist>|Solicita de manera explícita que el flujo de trabajo conserve su estado.|  
|<xref:System.Activities.Statements.TerminateWorkflow>|Finaliza la instancia de flujo de trabajo en ejecución.|  
|<xref:System.Activities.Statements.NoPersistScope>|Una actividad de contenedor que evita que las actividades secundarias se conserven.|
