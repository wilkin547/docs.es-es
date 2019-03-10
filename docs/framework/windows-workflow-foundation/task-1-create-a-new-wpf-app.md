---
title: 'Tarea 1: Crear una nueva aplicación de Windows Presentation Foundation'
ms.date: 03/30/2017
ms.assetid: 270eaeba-9492-4532-af9f-403ce5c9935b
ms.openlocfilehash: 533b4a1030ab5f47eb96ca62dc2805eae7933b9b
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/09/2019
ms.locfileid: "57711903"
---
# <a name="task-1-create-a-new-windows-presentation-foundation-application"></a>Tarea 1: Crear una nueva aplicación de Windows Presentation Foundation
En esta tarea, creará una aplicación vacía de Windows Presentation Foundation (WPF) mediante la plantilla de aplicaciones de WPF de Visual Studio y agregue referencias a adecuado [!INCLUDE[netfx_current_short](../../../includes/netfx-current-short-md.md)] ensamblados de flujo de trabajo.  
  
### <a name="to-create-the-wpf-application-project"></a>Para crear el proyecto de aplicación WPF  
  
1.  Abra Visual Studio y en el **archivo** menú, elija **New**y, a continuación, haga clic en **proyecto**.  
  
2.  En el **nuevo proyecto** cuadro de diálogo, seleccione **Visual C#**  o **Visual Basic** desde el **plantillas instaladas** panel de la izquierda lado del cuadro. Si el idioma que prefiera no aparece, mire en **otros lenguajes**.  
  
3.  Seleccione **Windows** en el **plantillas instaladas** panel.  
  
4.  En el panel superior, confirme que (el valor predeterminado) **.NET Framework 4** se ha seleccionado en el cuadro de lista desplegable y, a continuación, seleccione **aplicación WPF**.  
  
5.  Establezca el nombre del proyecto a **HostingApplication** en la parte inferior de la ventana.  
  
6.  Establece el nombre de la solución en **"rehostingthedesigner"**.  
  
7.  Haga clic en **Aceptar** para crear el proyecto de aplicación. Visual Studio crea una UI WPF básica para la aplicación e incluye el XAML adecuado y los archivos de código subyacente.  
  
8.  Agregue referencias a **WorkflowModel** ensamblados. Para ello, en **el Explorador de soluciones**, haga clic en el **HostingApplication** del proyecto y seleccione **Agregar referencia**.  
  
9. En el **Agregar referencia** cuadro de diálogo, haga clic en el **.NET** , mantenga presionada la tecla CTRL, seleccione los ensamblados siguientes y, a continuación, haga clic en **Aceptar**:  
  
    -   System.Activities  
  
    -   System.Activities.Presentation  
  
    -   System.Activities.Core.Presentation  
  
10. Haga clic en **Aceptar**.  
  
11. Consulte [tarea 2: Hospedar el Diseñador de flujo de trabajo](task-2-host-the-workflow-designer.md) para aprender a hospedar el lienzo de diseño del Diseñador de flujo de trabajo.  
  
## <a name="see-also"></a>Vea también
- [Rehospedaje del Diseñador de flujo de trabajo](rehosting-the-workflow-designer.md)
- [Tarea 2: Hospedar el Diseñador de flujo de trabajo](task-2-host-the-workflow-designer.md)
