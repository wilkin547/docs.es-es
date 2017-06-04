---
title: "C&#243;mo: Definir el comportamiento de cambio de tama&#241;o y colocaci&#243;n de una ventana dividida | Microsoft Docs"
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
  - "ventanas divisoras, cambiar el tamaño"
  - "SplitContainer (control) [Windows Forms], cambiar el tamaño"
  - "ventanas divisoras, cambiar el tamaño"
ms.assetid: 9bf73f36-ed2d-4a02-b15a-0770eff4fdfa
caps.latest.revision: 13
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 13
---
# C&#243;mo: Definir el comportamiento de cambio de tama&#241;o y colocaci&#243;n de una ventana dividida
Los paneles del control <xref:System.Windows.Forms.SplitContainer> son susceptibles de ser manipulados por los usuarios y resulta sencillo modificar su tamaño.  Sin embargo, en ocasiones es conveniente controlar el divisor mediante programación \(dónde colocarlo y en qué medida se puede mover\).  
  
 La propiedad <xref:System.Windows.Forms.SplitContainer.SplitterIncrement%2A> y las demás propiedades del control <xref:System.Windows.Forms.SplitContainer> permiten controlar con precisión el comportamiento de la interfaz de usuario para que se adapte a sus necesidades.  Estas propiedades se enumeran en la tabla siguiente.  
  
|Name|Descripción|  
|----------|-----------------|  
|Propiedad <xref:System.Windows.Forms.SplitContainer.IsSplitterFixed%2A>|Determina si el divisor se podrá mover desde el teclado o el mouse.|  
|Propiedad <xref:System.Windows.Forms.SplitContainer.SplitterDistance%2A>|Determina la distancia en píxeles, contando desde el borde izquierdo o superior, hasta la barra de división movible.|  
|Propiedad <xref:System.Windows.Forms.SplitContainer.SplitterIncrement%2A>|Determina la distancia mínima, en píxeles, que el usuario puede trasladar el divisor.|  
  
 El ejemplo siguiente modifica la propiedad <xref:System.Windows.Forms.SplitContainer.SplitterIncrement%2A> para crear un efecto de "divisor con ajuste"; cuando el usuario arrastra el divisor, avanza en bloques de 10 píxeles en lugar de hacerlo de 1 en 1, que es el valor predeterminado.  
  
### Para definir el comportamiento de cambio de tamaño de SplitContainer  
  
1.  En un procedimiento, establezca la propiedad <xref:System.Windows.Forms.SplitContainer.SplitterIncrement%2A> en el tamaño deseado, para lograr el comportamiento de 'ajuste' del divisor.  
  
     En el ejemplo de código siguiente, contenido en el evento <xref:System.Windows.Forms.Form.Load> del formulario, se establece el divisor incluido  en el control <xref:System.Windows.Forms.SplitContainer> de modo que salte 10 píxeles cuando se arrastra.  
  
    ```vb  
    Private Sub Form1_Load(ByVal sender As System.Object, _  
        ByVal e As System.EventArgs) Handles MyBase.Load  
        Dim splitSnapper as new SplitContainer()  
        splitSnapper.SplitterIncrement = 10  
        splitSnapper.Dock = DockStyle.Fill  
        splitSnapper.Parent = me  
    End Sub  
  
    ```  
  
    ```csharp  
    private void Form1_Load(System.Object sender, System.EventArgs e)  
    {  
        SplitContainer splitSnapper = new SplitContainer();  
        splitSnapper.SplitterIncrement = 10;  
        splitSnapper.Dock = DockStyle.Fill;  
        splitSnapper.Parent = this;  
    }  
    ```  
  
     \([!INCLUDE[csprcs](../../../../includes/csprcs-md.md)]\) Coloque el código siguiente en el constructor del formulario para registrar el controlador de eventos.  
  
    ```csharp  
    this.Load += new System.EventHandler(this.Form1_Load);  
    ```  
  
     Al mover el divisor ligeramente a la izquierda o la derecha no se producirá ningún efecto visible; sin embargo, cuando el puntero del mouse se desplace 10 píxeles en cualquier dirección, el divisor se ajustará a la nueva posición.  
  
## Vea también  
 <xref:System.Windows.Forms.SplitContainer>   
 <xref:System.Windows.Forms.SplitContainer.SplitterIncrement%2A>