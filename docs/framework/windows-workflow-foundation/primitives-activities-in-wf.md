---
title: "Actividades primitivas en WF | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 8e9009d1-236e-4d8e-86fc-e43132bf6dfc
caps.latest.revision: 6
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 6
---
# Actividades primitivas en WF
[!INCLUDE[netfx_current_short](../../../includes/netfx-current-short-md.md)] proporciona varias actividades proporcionadas por el sistema que proporcionan un mecanismo conveniente para realizar tareas comunes.  
  
|Actividad|Descripción|  
|---------------|-----------------|  
|<xref:System.Activities.Statements.Assign>|Asigna un valor a una variable en el ámbito actual.|  
|<xref:System.Activities.Statements.Delay>|Coloca una ruta de acceso de ejecución en estado inactivo, lo que permite que, posiblemente, se descargue el flujo de trabajo.|  
|<xref:System.Activities.Statements.InvokeDelegate>|Ejecuta un delegado que deriva de <xref:System.Activities.ActivityDelegate> y se expone como una propiedad.|  
|<xref:System.Activities.Statements.InvokeMethod>|Ejecuta un método público de un objeto CLR.|  
|<xref:System.Activities.Statements.WriteLine>|Escribe una cadena especificada en la consola o en un objeto <xref:System.IO.TextWriter> concreto.|