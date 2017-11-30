---
title: "Tarea 1: Crear una nueva aplicación de Windows Presentation Foundation"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 270eaeba-9492-4532-af9f-403ce5c9935b
caps.latest.revision: "14"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: bfebf11d66ded668d7c0892d11adde76e0a42c01
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="task-1-create-a-new-windows-presentation-foundation-application"></a>Tarea 1: Crear una nueva aplicación de Windows Presentation Foundation
En esta tarea, creará una aplicación [!INCLUDE[avalon1](../../../includes/avalon1-md.md)] vacía usando para ello la plantilla de Visual Studio de aplicación WPF y agregará referencias a los ensamblados de flujo de trabajo de [!INCLUDE[netfx_current_short](../../../includes/netfx-current-short-md.md)] adecuados.  
  
### <a name="to-create-the-wpf-application-project"></a>Para crear el proyecto de aplicación WPF  
  
1.  Abra [!INCLUDE[vs_current_short](../../../includes/vs-current-short-md.md)] y en el **archivo** menú, elija **New**y, a continuación, haga clic en **proyecto**.  
  
2.  En el **nuevo proyecto** cuadro de diálogo, seleccione **Visual C#** o **Visual Basic** desde el **plantillas instaladas** panel en el lado izquierdo del el cuadro. Si no aparece el idioma de su elección, mire debajo **otros lenguajes**.  
  
3.  Seleccione **Windows** en el **plantillas instaladas** panel.  
  
4.  En el panel superior, confirme que (el valor predeterminado) **.NET Framework 4** se ha seleccionado en el cuadro de lista desplegable y, a continuación, seleccione **aplicación WPF**.  
  
5.  Establecer el nombre del proyecto para **HostingApplication** en la parte inferior de la ventana.  
  
6.  Establece el nombre de la solución en **RehostingTheDesigner**.  
  
7.  Haga clic en **Aceptar** para crear el proyecto de aplicación. [!INCLUDE[vs_current_short](../../../includes/vs-current-short-md.md)] crea una interfaz de usuario básica de WPF para su aplicación e incluye el XAML y los archivos de código subyacente adecuados.  
  
8.  Agregue referencias a **WorkflowModel** ensamblados. Para ello, en **el Explorador de soluciones**, haga clic en el **HostingApplication** de proyecto y seleccione **Agregar referencia**.  
  
9. En el **Agregar referencia** cuadro de diálogo, haga clic en el **.NET** ficha, mantenga presionada la tecla CTRL, seleccione los ensamblados siguientes y, a continuación, haga clic en **Aceptar**:  
  
    -   System.Activities  
  
    -   System.Activities.Presentation  
  
    -   System.Activities.Core.Presentation  
  
10. Haga clic en **Aceptar**.  
  
11. Vea [tarea 2: hospedaje del Diseñador de flujo de trabajo](../../../docs/framework/windows-workflow-foundation/task-2-host-the-workflow-designer.md) para obtener información sobre cómo hospedar el lienzo de diseño del Diseñador de flujo de trabajo.  
  
## <a name="see-also"></a>Vea también  
 [Rehospedaje del Diseñador de flujo de trabajo](../../../docs/framework/windows-workflow-foundation/rehosting-the-workflow-designer.md)  
 [Tarea 2: Hospedaje del Diseñador de flujo de trabajo](../../../docs/framework/windows-workflow-foundation/task-2-host-the-workflow-designer.md)
