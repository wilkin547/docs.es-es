---
title: "C&#243;mo: Disponer objetos en capas en formularios Windows Forms | Microsoft Docs"
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
  - "controles [Windows Forms], disponer en capas"
  - "controles [Windows Forms], colocar"
  - "controles de Windows Forms, disponer en capas"
  - "orden z"
  - "orden z"
ms.assetid: 1acc4281-2976-4715-86f4-bda68134baaf
caps.latest.revision: 14
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 14
---
# C&#243;mo: Disponer objetos en capas en formularios Windows Forms
Cuando se crea una interfaz de usuario compleja o se trabaja con un formulario de interfaz de múltiples documentos \(MDI\), suele resultar conveniente disponer en capas los controles y los formularios secundarios para crear interfaces de usuario más complejas.  Para mover y hacer un seguimiento de los controles y las ventanas dentro del contexto de un grupo, deberá manipular su orden z.  El *orden z* es la disposición visual en capas de los controles en un formulario a lo largo del eje z del formulario \(profundidad\).  La ventana que se encuentra en la parte superior del orden z se superpone a todas las demás ventanas.  Todas las demás ventanas se superponen a la ventana que se encuentra en la parte inferior del orden z.  
  
> [!NOTE]
>  Los cuadros de diálogo y comandos de menú que se ven pueden diferir de los descritos en la Ayuda, en función de los valores de configuración o de edición activos.  Para cambiar la configuración, elija **Importar y exportar configuraciones** en el menú **Herramientas**.  Para obtener más información, vea [Customizing Development Settings in Visual Studio](http://msdn.microsoft.com/es-es/22c4debb-4e31-47a8-8f19-16f328d7dcd3).  
  
### Para disponer en capas los controles en tiempo de diseño  
  
1.  Seleccione el control que desee disponer en capas.  
  
2.  En el menú **Formato**, seleccione **Ordenar** y, a continuación, haga clic en **Traer al frente** o **Enviar al fondo**.  
  
### Para disponer en capas los controles mediante programación  
  
-   Use los métodos <xref:System.Windows.Forms.Control.BringToFront%2A> y <xref:System.Windows.Forms.Control.SendToBack%2A> para manipular el orden z de los controles.  
  
     Por ejemplo, si un control <xref:System.Windows.Forms.TextBox>, `txtFirstName`, se encuentra debajo de otro control y se desea colocarlo encima, utilice el código siguiente:  
  
    ```vb  
    txtFirstName.BringToFront()  
  
    ```  
  
    ```csharp  
    txtFirstName.BringToFront();  
  
    ```  
  
    ```cpp  
    txtFirstName->BringToFront();  
    ```  
  
> [!NOTE]
>  Los formularios Windows Forms admiten la *contención de controles*.  La contención de controles significa la colocación de diferentes controles dentro de un control contenedor como, por ejemplo, varios controles <xref:System.Windows.Forms.RadioButton> dentro de un control <xref:System.Windows.Forms.GroupBox>.  Entonces, es posible disponer los controles en capas dentro del control contenedor.  Al mover el cuadro de grupo, se mueven también los controles, puesto que están contenidos dentro de él.  
  
## Vea también  
 [Controles de Windows Forms](../../../../docs/framework/winforms/controls/index.md)   
 [Organizar controles en formularios Windows Forms](../../../../docs/framework/winforms/controls/arranging-controls-on-windows-forms.md)   
 [Asignar etiquetas a controles individuales de formularios Windows Forms y proporcionar accesos directos a los mismos](../../../../docs/framework/winforms/controls/labeling-individual-windows-forms-controls-and-providing-shortcuts-to-them.md)   
 [Controles que se utilizan en formularios Windows Forms](../../../../docs/framework/winforms/controls/controls-to-use-on-windows-forms.md)   
 [Controles de formularios Windows Forms por función](../../../../docs/framework/winforms/controls/windows-forms-controls-by-function.md)