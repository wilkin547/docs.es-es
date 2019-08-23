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
ms.openlocfilehash: 50036f5bef323368b4970a080ca7a70cf94252d6
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "69966484"
---
# <a name="user-drawn-controls"></a>Controles dibujados por el usuario
El .NET Framework le proporciona la capacidad de desarrollar fácilmente sus propios controles. Puede crear un control de usuario, que es un conjunto de controles estándar enlazados por código, o puede diseñar su propio control desde el principio. Incluso puede usar la herencia para crear un control que herede de un control existente y agregue a su funcionalidad inherente. Sea cual sea el enfoque que use, el .NET Framework proporciona la funcionalidad para dibujar una interfaz gráfica personalizada para cualquier control que cree.  
  
 La representación de un control se realiza mediante la ejecución de código en el método <xref:System.Windows.Forms.Control.OnPaint%2A> del control. El único argumento del <xref:System.Windows.Forms.Control.OnPaint%2A> método es un <xref:System.Windows.Forms.PaintEventArgs> objeto que proporciona toda la información y funcionalidad necesaria para representar el control. <xref:System.Windows.Forms.PaintEventArgs> Proporciona como propiedades dos objetos principales que se utilizarán en la representación del control:  
  
- <xref:System.Windows.Forms.PaintEventArgs.ClipRectangle%2A>objeto: el rectángulo que representa la parte del control que se va a dibujar. Puede ser todo el control o parte del control, en función de cómo se dibuje el control.  
  
- <xref:System.Drawing.Graphics>objeto: encapsula varios objetos y métodos orientados a gráficos que proporcionan la funcionalidad necesaria para dibujar el control.  
  
 Para obtener más información sobre <xref:System.Drawing.Graphics> el objeto y cómo usarlo, consulte [cómo: Crear objetos gráficos para dibujar](../advanced/how-to-create-graphics-objects-for-drawing.md).  
  
 El <xref:System.Windows.Forms.Control.OnPaint%2A> evento se desencadena cuando el control se dibuja o se actualiza en la pantalla, y el <xref:System.Windows.Forms.PaintEventArgs.ClipRectangle%2A> objeto representa el rectángulo en el que tendrá lugar el dibujo. Si es necesario actualizar todo el control, el <xref:System.Windows.Forms.PaintEventArgs.ClipRectangle%2A> representará el tamaño de todo el control. Sin embargo, si solo se necesita actualizar parte del control, el <xref:System.Windows.Forms.PaintEventArgs.ClipRectangle%2A> objeto representará solo la región que debe volver a dibujarse. Un ejemplo de este caso sería cuando un control estaba oscurecida parcialmente por otro control o formulario en la interfaz de usuario.  
  
 Al heredar de la <xref:System.Windows.Forms.Control> clase, debe invalidar el <xref:System.Windows.Forms.Control.OnPaint%2A> método y proporcionar código de representación de gráficos dentro de. Si desea proporcionar una interfaz gráfica personalizada a un control de usuario o un control heredado, también puede hacerlo invalidando el <xref:System.Windows.Forms.Control.OnPaint%2A> método. A continuación se muestra un ejemplo:  
  
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
  
 En el ejemplo anterior se muestra cómo representar un control con una representación gráfica muy simple. Llama al <xref:System.Windows.Forms.Control.OnPaint%2A> método de la clase base, crea un <xref:System.Drawing.Pen> objeto con el que se va a dibujar y, por último, dibuja una elipse en el <xref:System.Windows.Forms.Control.Location%2A> rectángulo <xref:System.Windows.Forms.Control.Size%2A> determinada por la y del control. Aunque la mayor parte del código de representación será significativamente más complicada que esto, en este ejemplo se muestra <xref:System.Drawing.Graphics> el uso del objeto <xref:System.Windows.Forms.PaintEventArgs> incluido en el objeto. Tenga en cuenta que si hereda de una clase que ya tiene una representación gráfica, como <xref:System.Windows.Forms.UserControl> o <xref:System.Windows.Forms.Button>, y no desea incorporar esa representación en la representación, no debe llamar al método de <xref:System.Windows.Forms.Control.OnPaint%2A> la clase base. forma.  
  
 El código <xref:System.Windows.Forms.Control.OnPaint%2A> del método del control se ejecutará cuando se dibuje el control por primera vez y siempre que se actualice. Para asegurarse de que el control se vuelve a dibujar cada vez que se cambia el tamaño, agregue la siguiente línea al constructor del control:  
  
```vb  
SetStyle(ControlStyles.ResizeRedraw, True)  
```  
  
```csharp  
SetStyle(ControlStyles.ResizeRedraw, true);  
```  
  
> [!NOTE]
> Use la <xref:System.Windows.Forms.Control.Region%2A?displayProperty=nameWithType> propiedad para implementar un control no rectangular.  
  
## <a name="see-also"></a>Vea también

- <xref:System.Windows.Forms.Control.Region%2A>
- <xref:System.Windows.Forms.ControlStyles>
- <xref:System.Drawing.Graphics>
- <xref:System.Windows.Forms.Control.OnPaint%2A>
- <xref:System.Windows.Forms.PaintEventArgs>
- [Cómo: Crear objetos Graphics para dibujar](../advanced/how-to-create-graphics-objects-for-drawing.md)
- [Controles constituyentes](constituent-controls.md)
- [Variedades de controles personalizados](varieties-of-custom-controls.md)
