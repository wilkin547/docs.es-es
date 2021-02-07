---
description: 'Más información acerca de: tarea 1: creación de una nueva aplicación de Windows Presentation Foundation'
title: 'Tarea 1: Crear una aplicación de Windows Presentation Foundation'
ms.date: 03/30/2017
ms.assetid: 270eaeba-9492-4532-af9f-403ce5c9935b
ms.openlocfilehash: 7bbb49e3d663d1878b2b3e150a24f775eeca0135
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99755244"
---
# <a name="task-1-create-a-new-windows-presentation-foundation-application"></a>Tarea 1: Crear una aplicación de Windows Presentation Foundation

En esta tarea, creará una aplicación de Windows Presentation Foundation (WPF) vacía mediante la plantilla de Visual Studio de aplicación WPF y agregará referencias a los [!INCLUDE[netfx_current_short](../../../includes/netfx-current-short-md.md)] ensamblados de flujo de trabajo adecuados.  
  
## <a name="to-create-the-wpf-application-project"></a>Para crear el proyecto de aplicación WPF

1. Abra Visual Studio y, en el menú **archivo** , seleccione **nuevo** y, a continuación, haga clic en **proyecto**.

2. En el cuadro de diálogo **nuevo proyecto** , seleccione **Visual C#** o **Visual Basic** en el panel **plantillas instaladas** en el lado izquierdo del cuadro. Si el idioma de su elección no aparece, mire debajo de **otros idiomas**.

3. Seleccione **Windows** en el panel **plantillas instaladas** .

4. En el panel superior, confirme que se ha seleccionado (el valor predeterminado) **.NET Framework 4** en el cuadro de lista desplegable y, a continuación, seleccione **aplicación WPF**.

5. Establezca el nombre del proyecto en **HostingApplication** en la parte inferior de la ventana.

6. Establezca el nombre de la solución en **RehostingTheDesigner**.

7. Haga clic en **Aceptar** para crear el proyecto de aplicación. Visual Studio crea una interfaz de usuario de WPF básica para su aplicación e incluye los archivos XAML y de código subyacente adecuados.

8. Agregue referencias a los ensamblados de **WorkflowModel** . Para ello, en **Explorador de soluciones**, haga clic con el botón derecho en el proyecto **HostingApplication** y seleccione **Agregar referencia**.

9. En el cuadro de diálogo **Agregar referencia** , haga clic en la pestaña **.net** , mantenga presionada la tecla Ctrl, seleccione los siguientes ensamblados y, a continuación, haga clic en **Aceptar**:

    - System.Activities
    - System.Activities.Presentation
    - System.Activities.Core.Presentation

10. Vea [tarea 2: hospedar el diseñador de flujo de trabajo](task-2-host-the-workflow-designer.md) para obtener información sobre cómo hospedar el lienzo de diseño del diseñador de flujo de trabajo.

## <a name="see-also"></a>Vea también

- [Rehospedar el Diseñador de flujo de trabajo](rehosting-the-workflow-designer.md)
- [Tarea 2: Hospedar el diseñador de flujo de trabajo](task-2-host-the-workflow-designer.md)
