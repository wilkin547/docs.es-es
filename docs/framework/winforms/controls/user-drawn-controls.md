---
title: "Controles dibujados por el usuario | Microsoft Docs"
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
  - "controles personalizados [Windows Forms], dibujados por el usuario"
  - "OnPaint (método) [Windows Forms]"
  - "controles dibujados por el usuario [Windows Forms]"
ms.assetid: 034af4b5-457f-4160-a937-22891817faa8
caps.latest.revision: 14
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 14
---
# Controles dibujados por el usuario
Gracias a .NET Framework podrá programar fácilmente controles propios.  Puede crear un control de usuario, que es un conjunto de controles estándar enlazados mediante código, o bien diseñar un control propio desde el principio.  Es posible, incluso, utilizar la herencia para crear un control que herede de un control existente y hacer adiciones a su funcionalidad inherente.  Independientemente del método que se utilice, .NET Framework proporciona la funcionalidad necesaria para dibujar una interfaz gráfica personalizada para cualquier control que se cree.  
  
 La representación de un control se realiza mediante la ejecución del código del método <xref:System.Windows.Forms.Control.OnPaint%2A> del control.  El único argumento del método <xref:System.Windows.Forms.Control.OnPaint%2A> es un objeto <xref:System.Windows.Forms.PaintEventArgs> que proporciona toda la información y la funcionalidad necesarias para representar el control.  El objeto <xref:System.Windows.Forms.PaintEventArgs> proporciona, en forma de propiedades, dos objetos principales que se utilizarán para la representación del control:  
  
-   Objeto <xref:System.Windows.Forms.PaintEventArgs.ClipRectangle%2A>: rectángulo que representa la parte del control que se dibujará.  Puede ser el control entero o parte del mismo, dependiendo de cómo se dibuje el control.  
  
-   Objeto <xref:System.Drawing.Graphics>: encapsula varios objetos y métodos orientados a gráficos que proporcionan la funcionalidad necesaria para dibujar el control.  
  
 Para obtener más información acerca del objeto <xref:System.Drawing.Graphics> y cómo utilizarlo, vea [Cómo: Crear objetos Graphics para dibujar](../../../../docs/framework/winforms/advanced/how-to-create-graphics-objects-for-drawing.md).  
  
 El evento <xref:System.Windows.Forms.Control.OnPaint%2A> se inicia cada vez que se dibuja o se actualiza el control en la pantalla, y el objeto <xref:System.Windows.Forms.PaintEventArgs.ClipRectangle%2A> representa el rectángulo en el que tendrá lugar el proceso de dibujo.  Si es necesario actualizar todo el control, <xref:System.Windows.Forms.PaintEventArgs.ClipRectangle%2A> representará el tamaño del control entero.  En cambio, si sólo es necesario actualizar parte del control, el objeto <xref:System.Windows.Forms.PaintEventArgs.ClipRectangle%2A> representará únicamente la región que se debe dibujar de nuevo.  Un ejemplo sería cuando un control se ve oscurecido parcialmente por otro control o formulario en la interfaz de usuario.  
  
 Cuando herede de la clase <xref:System.Windows.Forms.Control>, deberá reemplazar el método <xref:System.Windows.Forms.Control.OnPaint%2A> y proporcionar en él código de representación gráfica.  Si desea proporcionar una interfaz gráfica personalizada para un control de usuario o un control heredado, reemplace el método <xref:System.Windows.Forms.Control.OnPaint%2A>.  A continuación se muestra un ejemplo:  
  
```vb  
Protected Overrides Sub OnPaint(ByVal pe As PaintEventArgs)  
   ' Call the OnPaint method of the base class.  
   MyBase.OnPaint(pe)  
  
   ' Declare and instantiate a drawing pen.  
   Dim myPen As System.Drawing.Pen = New System.Drawing.Pen(Color.Aqua)  
  
   ' Draw an aqua rectangle in the rectangle represented by the control.  
   pe.Graphics.DrawRectangle(myPen, New Rectangle(Me.Location, Me.Size))  
End Sub  
  
```  
  
```csharp  
protected override void OnPaint(PaintEventArgs pe)  
{  
   // Call the OnPaint method of the base class.  
   base.OnPaint(pe);  
  
   // Declare and instantiate a new pen.  
   System.Drawing.Pen myPen = new System.Drawing.Pen(Color.Aqua);  
  
   // Draw an aqua rectangle in the rectangle represented by the control.  
   pe.Graphics.DrawRectangle(myPen, new Rectangle(this.Location,   
      this.Size));  
}  
  
```  
  
 El ejemplo anterior muestra cómo dibujar un control con una representación gráfica muy sencilla.  Llama al método <xref:System.Windows.Forms.Control.OnPaint%2A> de la clase base, crea un objeto <xref:System.Drawing.Pen> para dibujar y, finalmente, dibuja una elipse en el rectángulo determinada por los parámetros <xref:System.Windows.Forms.Control.Location%2A> y <xref:System.Windows.Forms.Control.Size%2A> del control.  Aunque la mayor parte del código de representación será significativamente más complicada que éste, este ejemplo muestra el uso del objeto <xref:System.Drawing.Graphics> contenido en el objeto <xref:System.Windows.Forms.PaintEventArgs>.  Observe que, si está heredando de una clase que ya tiene una representación gráfica, como, por ejemplo, <xref:System.Windows.Forms.UserControl> o <xref:System.Windows.Forms.Button> y no desea incorporar esa representación en la propia, no deberá llamar al método <xref:System.Windows.Forms.Control.OnPaint%2A> de la clase base.  
  
 El código del método <xref:System.Windows.Forms.Control.OnPaint%2A> del control se ejecutará cuando el control se dibuje por primera vez y siempre que se actualice.  Para asegurarse de que el control se dibuje de nuevo cada vez que cambie de tamaño, agregue la línea siguiente al constructor del control:  
  
```vb  
SetStyle(ControlStyles.ResizeRedraw, True)  
  
```  
  
```csharp  
SetStyle(ControlStyles.ResizeRedraw, true);  
  
```  
  
> [!NOTE]
>  Utilice la propiedad <xref:System.Windows.Forms.Control.Region%2A?displayProperty=fullName> para implementar un control no rectangular.  
  
## Vea también  
 <xref:System.Windows.Forms.Control.Region%2A>   
 <xref:System.Windows.Forms.ControlStyles>   
 <xref:System.Drawing.Graphics>   
 <xref:System.Windows.Forms.Control.OnPaint%2A>   
 <xref:System.Windows.Forms.PaintEventArgs>   
 [Cómo: Crear objetos Graphics para dibujar](../../../../docs/framework/winforms/advanced/how-to-create-graphics-objects-for-drawing.md)   
 [Controles constituyentes](../../../../docs/framework/winforms/controls/constituent-controls.md)   
 [Variedades de controles personalizados](../../../../docs/framework/winforms/controls/varieties-of-custom-controls.md)