---
title: "Actividades de control de errores en WF | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 24b68bd3-cef5-4413-ab82-2e2625f209aa
caps.latest.revision: 7
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 7
---
# Actividades de control de errores en WF
[!INCLUDE[netfx_current_long](../../../includes/netfx-current-long-md.md)] proporciona varias actividades proporcionadas por el sistema para implementar el control y la recuperación de errores.  [!INCLUDE[crdefault](../../../includes/crdefault-md.md)][Excepciones](../../../docs/framework/windows-workflow-foundation//exceptions.md).  
  
## Actividades de control de errores  
  
|||  
|-|-|  
|<xref:System.Activities.Statements.Rethrow>|Vuelve a iniciar la última excepción que se produjo desde una actividad `TryCatch`.|  
|<xref:System.Activities.Statements.Throw>|Inicia una excepción.|  
|<xref:System.Activities.Statements.TryCatch>|Implementa el control de excepciones.|