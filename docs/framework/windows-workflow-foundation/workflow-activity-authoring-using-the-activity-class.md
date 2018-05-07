---
title: Crear actividades de flujo de trabajo mediante la clase Activity
ms.date: 03/30/2017
ms.assetid: 7b7b1c66-f093-43c3-b4d1-7173b46516da
ms.openlocfilehash: 040fe777e332efdfb296e6fb6565935f466ded71
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
---
# <a name="workflow-activity-authoring-using-the-activity-class"></a>Crear actividades de flujo de trabajo mediante la clase Activity
La manera más sencilla de crear una actividad utilizando Windows Workflow Foundation (WF) en [!INCLUDE[netfx_current_long](../../../includes/netfx-current-long-md.md)] consiste en crear una clase que hereda de <xref:System.Activities.Activity> que crea la funcionalidad ensamblando personalizado actividades o actividades de la [integrada Biblioteca de actividades](../../../docs/framework/windows-workflow-foundation/net-framework-4-5-built-in-activity-library.md). En este tema se muestra cómo crear una actividad que escribe dos mensajes en la consola.  
  
### <a name="to-create-a-custom-activity-using-the-activity-designer"></a>Para crear una actividad personalizada mediante el diseñador de actividad  
  
1.  Abra [!INCLUDE[vs_current_long](../../../includes/vs-current-long-md.md)].  
  
2.  Seleccione Archivo, Nuevo, Proyecto. Seleccione **Workflow 4.0** en **Visual C#** en el **tipos de proyecto** ventana y seleccione el **v2010** nodo. Seleccione **biblioteca de actividades** en el **plantillas** ventana. Dé al nuevo proyecto el nombre "HelloActivity".  
  
3.  Abra la nueva actividad.  Arrastre una actividad <xref:System.Activities.Statements.Sequence> desde el cuadro de herramientas a la superficie del diseñador.  
  
4.  Arrastre una actividad <xref:System.Activities.Statements.WriteLine> a la actividad <xref:System.Activities.Statements.Sequence>. Escriba `"Hello World"` (con comillas) en el **texto** campo.  
  
5.  Arrastre una segunda actividad <xref:System.Activities.Statements.WriteLine> a la actividad <xref:System.Activities.Statements.Sequence>, debajo de la primera. Escriba `"Goodbye"` (con comillas) en el **texto** campo.
