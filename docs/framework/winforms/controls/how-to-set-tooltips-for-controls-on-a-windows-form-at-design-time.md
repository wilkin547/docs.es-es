---
title: "C&#243;mo: Establecer informaci&#243;n sobre herramientas en controles de Windows Forms en tiempo de dise&#241;o | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-winforms"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "ejemplos [Windows Forms], información sobre herramientas"
  - "información sobre herramientas [Windows Forms], para controles"
ms.assetid: c4b60637-4c0a-44c2-a103-f66dff887936
caps.latest.revision: 18
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 18
---
# C&#243;mo: Establecer informaci&#243;n sobre herramientas en controles de Windows Forms en tiempo de dise&#241;o
Puede establecer una cadena <xref:System.Windows.Forms.ToolTip> en el código o en el Diseñador de Windows Forms.  Para obtener más información sobre el componente <xref:System.Windows.Forms.ToolTip>, vea [Información general sobre el componente ToolTip](../../../../docs/framework/winforms/controls/tooltip-component-overview-windows-forms.md).  
  
> [!NOTE]
>  Los cuadros de diálogo y comandos de menú que se ven pueden diferir de los descritos en la Ayuda, en función de los valores de configuración o de edición activos.  Para cambiar la configuración, elija **Importar y exportar configuraciones** en el menú **Herramientas**.  Para obtener más información, vea [Customizing Development Settings in Visual Studio](http://msdn.microsoft.com/es-es/22c4debb-4e31-47a8-8f19-16f328d7dcd3).  
  
### Para establecer información sobre herramientas mediante programación  
  
1.  Agregue el control que va a mostrar la información sobre herramientas.  
  
2.  Utilice el método <xref:System.Windows.Forms.ToolTip.SetToolTip%2A> del componente <xref:System.Windows.Forms.ToolTip>.  
  
    ```vb  
    ' In this example, Button1 is the control to display the ToolTip.  
    ToolTip1.SetToolTip(Button1, "Save changes")  
  
    ```  
  
    ```csharp  
    // In this example, button1 is the control to display the ToolTip.  
    toolTip1.SetToolTip(button1, "Save changes");  
  
    ```  
  
    ```cpp  
    // In this example, button1 is the control to display the ToolTip.  
    toolTip1->SetToolTip(button1, "Save changes");  
    ```  
  
### Para establecer una información sobre herramientas en el diseñador  
  
1.  Agregue un componente <xref:System.Windows.Forms.ToolTip> al formulario.  
  
2.  Seleccione el control que va a mostrar la información sobre herramientas o agréguelo al formulario.  
  
3.  En la ventana **Propiedades**, establezca una cadena de texto adecuada como valor de **Información sobre herramientas en ToolTip1**.  
  
## Vea también  
 [Información general sobre el componente ToolTip](../../../../docs/framework/winforms/controls/tooltip-component-overview-windows-forms.md)   
 [Cómo: Cambiar el retardo del componente ToolTip de formularios Windows Forms](../../../../docs/framework/winforms/controls/how-to-change-the-delay-of-the-windows-forms-tooltip-component.md)   
 [ToolTip](../../../../docs/framework/winforms/controls/tooltip-component-windows-forms.md)