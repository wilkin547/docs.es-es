---
title: "Crear actividades de flujo de trabajo mediante la clase Activity | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 7b7b1c66-f093-43c3-b4d1-7173b46516da
caps.latest.revision: 7
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 7
---
# Crear actividades de flujo de trabajo mediante la clase Activity
La manera más básica de crear una actividad con [!INCLUDE[wf](../../../includes/wf-md.md)] en [!INCLUDE[netfx_current_long](../../../includes/netfx-current-long-md.md)] es crear una clase que herede de <xref:System.Activities.Activity> y que cree funciones ensamblando actividades personalizadas o de la [Biblioteca de actividades integrada](../../../docs/framework/windows-workflow-foundation//net-framework-4-5-built-in-activity-library.md).En este tema se muestra cómo crear una actividad que escribe dos mensajes en la consola.  
  
### Para crear una actividad personalizada mediante el diseñador de actividad  
  
1.  Abra [!INCLUDE[vs_current_long](../../../includes/vs-current-long-md.md)].  
  
2.  Seleccione Archivo, Nuevo, Proyecto.Seleccione **Workflow 4.0** debajo de **Visual C\#** en la ventana **Tipos de proyecto** y seleccione el nodo **v2010**.Seleccione **Biblioteca de actividad** en la ventana **Plantillas**.Dé al nuevo proyecto el nombre "HelloActivity".  
  
3.  Abra la nueva actividad.Arrastre una actividad <xref:System.Activities.Statements.Sequence> desde el cuadro de herramientas a la superficie del diseñador.  
  
4.  Arrastre una actividad <xref:System.Activities.Statements.WriteLine> a la actividad <xref:System.Activities.Statements.Sequence>.Escriba `“Hello World”` \(con comillas\) en el campo **Texto**.  
  
5.  Arrastre una segunda actividad <xref:System.Activities.Statements.WriteLine> a la actividad <xref:System.Activities.Statements.Sequence>, debajo de la primera.Escriba `“Goodbye”` \(con comillas\) en el campo **Texto**.