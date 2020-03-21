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
ms.openlocfilehash: c68c8c88376cfe7295962264c466030115f2f3db
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79182011"
---
# <a name="user-drawn-controls"></a>Controles dibujados por el usuario
.NET Framework proporciona la capacidad de desarrollar fácilmente sus propios controles. Puede crear un control de usuario, que es un conjunto de controles estándar enlazados entre sí por código, o puede diseñar su propio control desde cero. Incluso puede usar la herencia para crear un control que hereda de un control existente y agregar a su funcionalidad inherente. Sea cual sea el enfoque que use, .NET Framework proporciona la funcionalidad para dibujar una interfaz gráfica personalizada para cualquier control que cree.  
  
 La pintura de un control se realiza mediante <xref:System.Windows.Forms.Control.OnPaint%2A> la ejecución de código en el método del control. El único argumento <xref:System.Windows.Forms.Control.OnPaint%2A> del <xref:System.Windows.Forms.PaintEventArgs> método es un objeto que proporciona toda la información y funcionalidad necesaria para representar el control. Proporciona <xref:System.Windows.Forms.PaintEventArgs> como propiedades dos objetos principales que se usarán en la representación del control:  
  
- <xref:System.Windows.Forms.PaintEventArgs.ClipRectangle%2A>object - el rectángulo que representa la parte del control que se dibujará. Esto puede ser todo el control, o parte del control dependiendo de cómo se dibuja el control.  
  
- <xref:System.Drawing.Graphics>object: encapsula varios objetos y métodos orientados a gráficos que proporcionan la funcionalidad necesaria para dibujar el control.  
  
 Para obtener más <xref:System.Drawing.Graphics> información sobre el objeto y cómo utilizarlo, consulte [Cómo: Crear objetos gráficos para dibujo](../advanced/how-to-create-graphics-objects-for-drawing.md).  
  
 El <xref:System.Windows.Forms.Control.OnPaint%2A> evento se desencadena siempre que el control se <xref:System.Windows.Forms.PaintEventArgs.ClipRectangle%2A> dibuja o actualiza en la pantalla y el objeto representa el rectángulo en el que tendrá lugar la pintura. Si es necesario actualizar todo el <xref:System.Windows.Forms.PaintEventArgs.ClipRectangle%2A> control, el representará el tamaño de todo el control. Sin embargo, si solo es necesario actualizar <xref:System.Windows.Forms.PaintEventArgs.ClipRectangle%2A> una parte del control, el objeto solo representará la región que se debe volver a dibujar. Un ejemplo de este tipo sería cuando un control estaba parcialmente oscurecido por otro control o formulario en la interfaz de usuario.  
  
 Al heredar <xref:System.Windows.Forms.Control> de la clase, <xref:System.Windows.Forms.Control.OnPaint%2A> debe invalidar el método y proporcionar código de representación de gráficos dentro. Si desea proporcionar una interfaz gráfica personalizada a un control de usuario o <xref:System.Windows.Forms.Control.OnPaint%2A> un control heredado, también puede hacerlo reemplazando el método. A continuación se muestra un ejemplo:  
  
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
  
 En el ejemplo anterior se muestra cómo representar un control con una representación gráfica muy simple. Llama al <xref:System.Windows.Forms.Control.OnPaint%2A> método de la clase <xref:System.Drawing.Pen> base, crea un objeto con el que dibujar y, finalmente, dibuja una elipse en el rectángulo determinado por el <xref:System.Windows.Forms.Control.Location%2A> y <xref:System.Windows.Forms.Control.Size%2A> del control. Aunque la mayoría del código de representación será significativamente más <xref:System.Drawing.Graphics> complicado que <xref:System.Windows.Forms.PaintEventArgs> este, en este ejemplo se muestra el uso del objeto contenido en el objeto. Tenga en cuenta que si está heredando de una <xref:System.Windows.Forms.UserControl> clase <xref:System.Windows.Forms.Button>que ya tiene una representación gráfica, como o , y <xref:System.Windows.Forms.Control.OnPaint%2A> no desea incorporar esa representación en la representación, no debe llamar al método de la clase base.  
  
 El código <xref:System.Windows.Forms.Control.OnPaint%2A> del método del control se ejecutará cuando se dibuje el control por primera vez y siempre que se actualice. Para asegurarse de que el control se redibuja cada vez que se cambia el tamaño, agregue la siguiente línea al constructor del control:  
  
```vb  
SetStyle(ControlStyles.ResizeRedraw, True)  
```  
  
```csharp  
SetStyle(ControlStyles.ResizeRedraw, true);  
```  
  
> [!NOTE]
> Utilice <xref:System.Windows.Forms.Control.Region%2A?displayProperty=nameWithType> la propiedad para implementar un control no rectangular.  
  
## <a name="see-also"></a>Consulte también

- <xref:System.Windows.Forms.Control.Region%2A>
- <xref:System.Windows.Forms.ControlStyles>
- <xref:System.Drawing.Graphics>
- <xref:System.Windows.Forms.Control.OnPaint%2A>
- <xref:System.Windows.Forms.PaintEventArgs>
- [Cómo: Crear objetos Graphics para dibujar](../advanced/how-to-create-graphics-objects-for-drawing.md)
- [Controles constituyentes](constituent-controls.md)
- [Variedades de controles personalizados](varieties-of-custom-controls.md)
