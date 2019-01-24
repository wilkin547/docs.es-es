---
title: Controles dibujados por el usuario
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- custom controls [Windows Forms], user-drawn
- OnPaint method [Windows Forms]
- user-drawn controls [Windows Forms]
ms.assetid: 034af4b5-457f-4160-a937-22891817faa8
ms.openlocfilehash: e9eab78695db128c0538914c5364aaa54c135403
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54509966"
---
# <a name="user-drawn-controls"></a>Controles dibujados por el usuario
.NET Framework proporciona la capacidad de desarrollar fácilmente sus propios controles. Puede crear un control de usuario, que es un conjunto de controles estándares unidos mediante código, o puede diseñar su propio control desde el principio de seguridad. Incluso puede usar la herencia para crear un control que hereda de un control existente y agregar a su funcionalidad inherente. El método que utilice, .NET Framework proporciona la funcionalidad para dibujar una interfaz gráfica personalizada para cualquier control que cree.  
  
 Representación de un control se realiza mediante la ejecución de código en el control <xref:System.Windows.Forms.Control.OnPaint%2A> método. El único argumento de la <xref:System.Windows.Forms.Control.OnPaint%2A> método es un <xref:System.Windows.Forms.PaintEventArgs> objeto que proporciona toda la información y funcionalidad necesarias para representar el control. El <xref:System.Windows.Forms.PaintEventArgs> proporciona como propiedades de dos objetos principales que se usará en la representación del control:  
  
-   <xref:System.Windows.Forms.PaintEventArgs.ClipRectangle%2A> objeto: el rectángulo que representa la parte del control que se va a dibujar. Puede tratarse de todo el control, o parte del control en función de cómo se dibuja el control.  
  
-   <xref:System.Drawing.Graphics> objeto: encapsula varios objetos orientados a gráficos y los métodos que proporcionan la funcionalidad necesaria para dibujar el control.  
  
 Para obtener más información sobre la <xref:System.Drawing.Graphics> objeto y cómo usarlo, vea [Cómo: Crear objetos Graphics para dibujar](../../../../docs/framework/winforms/advanced/how-to-create-graphics-objects-for-drawing.md).  
  
 El <xref:System.Windows.Forms.Control.OnPaint%2A> evento se desencadena cada vez que se dibuja el control o se actualiza en la pantalla y el <xref:System.Windows.Forms.PaintEventArgs.ClipRectangle%2A> objeto representa el rectángulo en el que llevará a cabo pintura. Si el control completo debe actualizarse, la <xref:System.Windows.Forms.PaintEventArgs.ClipRectangle%2A> representará el tamaño de todo el control. Si solo parte del control debe actualizarse, sin embargo, la <xref:System.Windows.Forms.PaintEventArgs.ClipRectangle%2A> objeto representará únicamente la región que se debe volver a dibujar. Un ejemplo de este caso sería cuando un control se parcialmente tapado por otro control o formulario en la interfaz de usuario.  
  
 Al heredar de la <xref:System.Windows.Forms.Control> (clase), debe invalidar el <xref:System.Windows.Forms.Control.OnPaint%2A> método y proporcionar código de representación de gráficos. Si desea proporcionar una interfaz gráfica personalizada a un control de usuario o un control heredado, puede hacerlo mediante la invalidación de la <xref:System.Windows.Forms.Control.OnPaint%2A> método. A continuación se muestra un ejemplo:  
  
```vb  
Protected Overrides Sub OnPaint(ByVal e As PaintEventArgs)  
   ' Call the OnPaint method of the base class.  
   MyBase.OnPaint(e)  
  
   ' Declare and instantiate a drawing pen.  
   Using myPen As System.Drawing.Pen = New System.Drawing.Pen(Color.Aqua)  
      ' Draw an aqua rectangle in the rectangle represented by the control.  
      e.Graphics.DrawRectangle(myPen, New Rectangle(Me.Location, Me.Size))  
   End Using
End Sub  
```  
  
```csharp  
protected override void OnPaint(PaintEventArgs e)  
{  
   // Call the OnPaint method of the base class.  
   base.OnPaint(e);  
  
   // Declare and instantiate a new pen.  
   using (System.Drawing.Pen myPen = new System.Drawing.Pen(Color.Aqua))  
   {
      // Draw an aqua rectangle in the rectangle represented by the control.  
      e.Graphics.DrawRectangle(myPen, new Rectangle(this.Location,   
         this.Size));  
   }
}  
```  
  
 El ejemplo anterior muestra cómo representar un control con una representación gráfica muy sencilla. Lo llama el <xref:System.Windows.Forms.Control.OnPaint%2A> método de la clase base, crea un <xref:System.Drawing.Pen> objeto con el que se va a dibujar y, por último, dibuja una elipse en el rectángulo determinado por la <xref:System.Windows.Forms.Control.Location%2A> y <xref:System.Windows.Forms.Control.Size%2A> del control. Aunque la mayoría del código representación será mucho más complicada de esto, en este ejemplo muestra el uso de la <xref:System.Drawing.Graphics> objeto dentro de la <xref:System.Windows.Forms.PaintEventArgs> objeto. Tenga en cuenta que si se hereda de una clase que ya tiene una representación gráfica, como <xref:System.Windows.Forms.UserControl> o <xref:System.Windows.Forms.Button>y no desea incorporar esa representación a la representación, no debe llamar a la clase base <xref:System.Windows.Forms.Control.OnPaint%2A> método.  
  
 El código en el <xref:System.Windows.Forms.Control.OnPaint%2A> método del control se ejecutará cuando el control se dibuja primero, y siempre que se actualice. Para asegurarse de que se vuelve a dibujar el control cada vez que se cambia el tamaño, agregue la línea siguiente al constructor del control:  
  
```vb  
SetStyle(ControlStyles.ResizeRedraw, True)  
```  
  
```csharp  
SetStyle(ControlStyles.ResizeRedraw, true);  
```  
  
> [!NOTE]
>  Use el <xref:System.Windows.Forms.Control.Region%2A?displayProperty=nameWithType> propiedad para implementar un control no rectangulares.  
  
## <a name="see-also"></a>Vea también
- <xref:System.Windows.Forms.Control.Region%2A>
- <xref:System.Windows.Forms.ControlStyles>
- <xref:System.Drawing.Graphics>
- <xref:System.Windows.Forms.Control.OnPaint%2A>
- <xref:System.Windows.Forms.PaintEventArgs>
- [Cómo: Crear objetos Graphics para dibujar](../../../../docs/framework/winforms/advanced/how-to-create-graphics-objects-for-drawing.md)
- [Controles constituyentes](../../../../docs/framework/winforms/controls/constituent-controls.md)
- [Variedades de controles personalizados](../../../../docs/framework/winforms/controls/varieties-of-custom-controls.md)
