---
title: "C&#243;mo: Colocar los controles en formularios Windows Forms | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-winforms"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "Location"
  - "Location.Y"
  - "Location.X"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "controles [Windows Forms]"
  - "controles [Windows Forms], mover"
  - "controles [Windows Forms], colocar"
  - "líneas de ajuste"
ms.assetid: 4693977e-34a4-4f19-8221-68c3120c2b2b
caps.latest.revision: 18
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 18
---
# C&#243;mo: Colocar los controles en formularios Windows Forms
Para colocar controles, utilice el Diseñador de Windows Forms o especifique la propiedad <xref:System.Windows.Forms.Control.Location%2A>.  
  
> [!NOTE]
>  Los cuadros de diálogo y comandos de menú que se ven pueden diferir de los descritos en la Ayuda, en función de los valores de configuración o de edición activos.  Para cambiar la configuración, elija **Importar y exportar configuraciones** en el menú **Herramientas**.  Para obtener más información, vea [Customizing Development Settings in Visual Studio](http://msdn.microsoft.com/es-es/22c4debb-4e31-47a8-8f19-16f328d7dcd3).  
  
### Para colocar un control en la superficie de diseño del Diseñador de Windows Forms  
  
-   Arrastre el control a la ubicación adecuada con el mouse.  
  
    > [!NOTE]
    >  Seleccione el control y muévalo con las teclas de dirección para colocarlo con más precisión.  Además, las *líneas de ajuste* le ayudan a colocar los controles con precisión en el formulario.  Para obtener más información, vea [Tutorial: Organizar controles en formularios Windows Forms mediante líneas de ajuste](../../../../docs/framework/winforms/controls/walkthrough-arranging-controls-on-windows-forms-using-snaplines.md).  
  
### Para colocar un control mediante la ventana Propiedades  
  
1.  Haga clic en el control que desee colocar.  
  
2.  En la ventana **Propiedades**, escriba valores para la propiedad <xref:System.Windows.Forms.Control.Location%2A>, separados por comas, para colocar el control dentro de su contenedor.  
  
     El primer número \(X\) es la distancia desde el borde izquierdo del contenedor; el segundo número \(Y\) es la distancia desde el borde superior del área contenedora, medido en píxeles.  
  
    > [!NOTE]
    >  Puede expandir la propiedad <xref:System.Windows.Forms.Control.Location%2A> para escribir individualmente los valores **X** e **Y**.  
  
### Para colocar un control mediante programación  
  
1.  Establezca la propiedad <xref:System.Windows.Forms.Control.Location%2A> del control en <xref:System.Drawing.Point>:  
  
    ```vb  
    Button1.Location = New Point(100, 100)  
    ```  
  
    ```csharp  
    button1.Location = new Point(100, 100);  
    ```  
  
    ```cpp  
    button1->Location = Point(100, 100);  
    ```  
  
2.  Cambie la coordenada X de la ubicación del control mediante la subpropiedad <xref:System.Windows.Forms.Control.Left%2A>.  
  
    ```vb  
    Button1.Left = 300  
    ```  
  
    ```csharp  
    button1.Left = 300;  
    ```  
  
    ```cpp  
    button1->Left = 300;  
    ```  
  
### Para incrementar la ubicación de un control mediante programación  
  
1.  Establezca la subpropiedad <xref:System.Windows.Forms.Control.Left%2A> para incrementar la coordenada X del control.  
  
    ```vb  
    Button1.Left += 200  
    ```  
  
    ```csharp  
    button1.Left += 200;  
    ```  
  
    ```cpp  
    button1->Left += 200;  
    ```  
  
    > [!NOTE]
    >  Utilice la propiedad <xref:System.Windows.Forms.Control.Location%2A> para establecer simultáneamente los valores X e Y de un control.  Para establecer una posición individualmente, utilice la subpropiedad <xref:System.Windows.Forms.Control.Left%2A> \(**X**\) o <xref:System.Windows.Forms.Control.Top%2A> \(**Y**\) del control.  No intente establecer implícitamente las coordenadas X e Y de la estructura <xref:System.Drawing.Point> que representa la ubicación del botón, porque esta estructura contiene una copia de las coordenadas del botón.  
  
## Vea también  
 [Controles de Windows Forms](../../../../docs/framework/winforms/controls/index.md)   
 [Tutorial: Organizar controles en formularios Windows Forms mediante líneas de ajuste](../../../../docs/framework/winforms/controls/walkthrough-arranging-controls-on-windows-forms-using-snaplines.md)   
 [Tutorial: Organizar controles en formularios Windows Forms mediante TableLayoutPanel](../../../../docs/framework/winforms/controls/walkthrough-arranging-controls-on-windows-forms-using-a-tablelayoutpanel.md)   
 [Tutorial: Organizar controles en Windows Forms mediante FlowLayoutPanel](../../../../docs/framework/winforms/controls/walkthrough-arranging-controls-on-windows-forms-using-a-flowlayoutpanel.md)   
 [Organizar controles en formularios Windows Forms](../../../../docs/framework/winforms/controls/arranging-controls-on-windows-forms.md)   
 [Asignar etiquetas a controles individuales de formularios Windows Forms y proporcionar accesos directos a los mismos](../../../../docs/framework/winforms/controls/labeling-individual-windows-forms-controls-and-providing-shortcuts-to-them.md)   
 [Controles que se utilizan en formularios Windows Forms](../../../../docs/framework/winforms/controls/controls-to-use-on-windows-forms.md)   
 [Controles de formularios Windows Forms por función](../../../../docs/framework/winforms/controls/windows-forms-controls-by-function.md)   
 [How to: Set the Screen Location of Windows Forms](http://msdn.microsoft.com/es-es/cb023ab7-dea7-4284-9aa6-8c03c59b60c6)