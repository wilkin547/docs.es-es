---
title: "Tarea 1: Crear una nueva aplicaci&#243;n de Windows Presentation Foundation | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 270eaeba-9492-4532-af9f-403ce5c9935b
caps.latest.revision: 14
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 14
---
# Tarea 1: Crear una nueva aplicaci&#243;n de Windows Presentation Foundation
En esta tarea, creará una aplicación [!INCLUDE[avalon1](../../../includes/avalon1-md.md)] vacía usando para ello la plantilla de Visual Studio de aplicación WPF y agregará referencias a los ensamblados de flujo de trabajo de [!INCLUDE[netfx_current_short](../../../includes/netfx-current-short-md.md)] adecuados.  
  
### Para crear el proyecto de aplicación WPF  
  
1.  Abra [!INCLUDE[vs_current_short](../../../includes/vs-current-short-md.md)] y, en el menú **Archivo**, elija **Nuevo** y, a continuación, haga clic en **Proyecto**.  
  
2.  En el cuadro de diálogo **Nuevo proyecto**, seleccione **Visual C\#** o **Visual Basic** en el panel **Plantillas instaladas** del lado izquierdo del cuadro.Si el lenguaje que desea no aparece, mire debajo de **Otros lenguajes**.  
  
3.  Seleccione **Windows** en el panel **Plantillas instaladas**.  
  
4.  En el panel superior, confirme que se ha seleccionado **.NET Framework 4** \(el valor predeterminado\) en el cuadro de lista desplegable y, a continuación, seleccione **Aplicación WPF**.  
  
5.  Establezca el nombre del proyecto en **HostingApplication** en la parte inferior de la ventana.  
  
6.  Dé a la solución el nombre **RehostingTheDesigner**.  
  
7.  Haga clic en **Aceptar** para crear el proyecto de aplicación.[!INCLUDE[vs_current_short](../../../includes/vs-current-short-md.md)] crea una interfaz de usuario básica de WPF para su aplicación e incluye el XAML y los archivos de código subyacente adecuados.  
  
8.  Agregue referencias a los ensamblados de **WorkflowModel**.Para ello, en el **Explorador de soluciones**, haga clic con el botón de secundario en el proyecto **HostingApplication** y seleccione **Agregar referencia**.  
  
9. En el cuadro de diálogo **Agregar referencia**, haga clic en la pestaña **.NET**, mantenga presionada la CTRL, seleccione los siguientes ensamblados y, a continuación, haga clic en **Aceptar**:  
  
    -   System.Activities  
  
    -   System.Activities.Presentation  
  
    -   System.Activities.Core.Presentation  
  
10. Haga clic en **Aceptar**.  
  
11. Vea [Tarea 2: Hospedaje del Diseñador de flujo de trabajo](../../../docs/framework/windows-workflow-foundation//task-2-host-the-workflow-designer.md) para obtener más información sobre cómo hospedar el lienzo de diseño del Diseñador de flujo de trabajo.  
  
## Vea también  
 [Rehospedar el Diseñador de flujo de trabajo](../../../docs/framework/windows-workflow-foundation//rehosting-the-workflow-designer.md)   
 [Tarea 2: Hospedaje del Diseñador de flujo de trabajo](../../../docs/framework/windows-workflow-foundation//task-2-host-the-workflow-designer.md)