---
title: Representar un control
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- custom controls [Windows Forms], rendering
- OnPaintBackground method [Windows Forms], invoking in Windows Forms custom controls
- custom controls [Windows Forms], graphics resources
- custom controls [Windows Forms], invalidation and painting
ms.assetid: aae8e1e6-4786-432b-a15e-f4c44760d302
ms.openlocfilehash: 0e1a7ca5dc0414d518c081b1db2dca5477d4f743
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/24/2020
ms.locfileid: "76742384"
---
# <a name="rendering-a-windows-forms-control"></a>Representar un control de formularios Windows Forms
La representación hace referencia al proceso de creación de una representación visual en la pantalla de un usuario. Windows Forms usa GDI (la nueva biblioteca de gráficos de Windows) para la representación. Las clases administradas que proporcionan acceso a GDI se encuentran en el espacio de nombres <xref:System.Drawing?displayProperty=nameWithType> y sus subespacios de nombres.  
  
 Los elementos siguientes están implicados en la representación de controles:  
  
- La funcionalidad de dibujo proporcionada por la clase base <xref:System.Windows.Forms.Control?displayProperty=nameWithType>.  
  
- Elementos esenciales de la biblioteca de gráficos GDI.  
  
- Geometría de la región de dibujo.  
  
- El procedimiento para liberar recursos de gráficos.  
  
## <a name="drawing-functionality-provided-by-control"></a>Funcionalidad de dibujo proporcionada por el control  
 La clase base <xref:System.Windows.Forms.Control> proporciona la funcionalidad de dibujo a través de su evento <xref:System.Windows.Forms.Control.Paint>. Un control genera el evento <xref:System.Windows.Forms.Control.Paint> cada vez que necesita actualizar su presentación. Para obtener más información acerca de los eventos en el .NET Framework, consulte [controlar y provocar eventos](../../../standard/events/index.md).  
  
 La clase de datos de evento para el evento de <xref:System.Windows.Forms.Control.Paint>, <xref:System.Windows.Forms.PaintEventArgs>, contiene los datos necesarios para dibujar un control, un identificador de un objeto de gráficos y un objeto de rectángulo que representa la región en la que se va a dibujar. Estos objetos se muestran en negrita en el fragmento de código siguiente.  
  
```vb  
Public Class PaintEventArgs  
   Inherits EventArgs  
   Implements IDisposable  
  
   Public ReadOnly Property ClipRectangle() As System.Drawing.Rectangle  
      ...  
   End Property  
  
   Public ReadOnly Property Graphics() As System.Drawing.Graphics  
      ...  
   End Property  
   ' Other properties and methods.  
   ...  
End Class  
```  
  
```csharp  
public class PaintEventArgs : EventArgs, IDisposable {  
public System.Drawing.Rectangle ClipRectangle {get;}  
public System.Drawing.Graphics Graphics {get;}  
// Other properties and methods.  
...  
}  
```  
  
 <xref:System.Drawing.Graphics> es una clase administrada que encapsula la funcionalidad de dibujo, como se describe en la descripción de GDI más adelante en este tema. El <xref:System.Windows.Forms.PaintEventArgs.ClipRectangle%2A> es una instancia de la estructura de <xref:System.Drawing.Rectangle> y define el área disponible en la que puede dibujarse un control. Un desarrollador de controles puede calcular el <xref:System.Windows.Forms.PaintEventArgs.ClipRectangle%2A> mediante la propiedad <xref:System.Windows.Forms.PaintEventArgs.ClipRectangle%2A> de un control, tal y como se describe en la descripción de Geometry más adelante en este tema.  
  
 Un control debe proporcionar la lógica de representación invalidando el método de <xref:System.Windows.Forms.Control.OnPaint%2A> que hereda de <xref:System.Windows.Forms.Control>. <xref:System.Windows.Forms.Control.OnPaint%2A> obtiene acceso a un objeto gráfico y a un rectángulo para dibujar a través del <xref:System.Drawing.Design.PaintValueEventArgs.Graphics%2A> y las propiedades <xref:System.Windows.Forms.PaintEventArgs.ClipRectangle%2A> de la instancia de <xref:System.Windows.Forms.PaintEventArgs> que se le ha pasado.  
  
```vb  
Protected Overridable Sub OnPaint(pe As PaintEventArgs)  
```  
  
```csharp  
protected virtual void OnPaint(PaintEventArgs pe);  
```  
  
 El método <xref:System.Windows.Forms.Control.OnPaint%2A> de la clase base <xref:System.Windows.Forms.Control> no implementa ninguna funcionalidad de dibujo, sino que simplemente invoca los delegados de eventos que se registran con el evento <xref:System.Windows.Forms.Control.Paint>. Cuando invalide <xref:System.Windows.Forms.Control.OnPaint%2A>, normalmente debe invocar el método <xref:System.Windows.Forms.Control.OnPaint%2A> de la clase base para que los delegados registrados reciban el evento <xref:System.Windows.Forms.Control.Paint>. Sin embargo, los controles que pintan toda la superficie no deben invocar la <xref:System.Windows.Forms.Control.OnPaint%2A>de la clase base, ya que esto presenta el parpadeo. Para obtener un ejemplo de cómo invalidar el evento <xref:System.Windows.Forms.Control.OnPaint%2A>, consulte la información [sobre cómo crear un Control Windows Forms que muestre el progreso](how-to-create-a-windows-forms-control-that-shows-progress.md).  
  
> [!NOTE]
> No invoque <xref:System.Windows.Forms.Control.OnPaint%2A> directamente desde el control; en su lugar, invoque el método <xref:System.Windows.Forms.Control.Invalidate%2A> (heredado de <xref:System.Windows.Forms.Control>) o algún otro método que invoque <xref:System.Windows.Forms.Control.Invalidate%2A>. A su vez, el método <xref:System.Windows.Forms.Control.Invalidate%2A> invoca <xref:System.Windows.Forms.Control.OnPaint%2A>. El método <xref:System.Windows.Forms.Control.Invalidate%2A> está sobrecargado y, dependiendo de los argumentos proporcionados para <xref:System.Windows.Forms.Control.Invalidate%2A> `e`, un control vuelve a dibujar parte o todo el área de la pantalla.  
  
 La clase <xref:System.Windows.Forms.Control> base define otro método que es útil para dibujar: el método <xref:System.Windows.Forms.Control.OnPaintBackground%2A>.  
  
```vb  
Protected Overridable Sub OnPaintBackground(pevent As PaintEventArgs)  
```  
  
```csharp  
protected virtual void OnPaintBackground(PaintEventArgs pevent);  
```  
  
 <xref:System.Windows.Forms.Control.OnPaintBackground%2A> pinta el fondo (y, por tanto, la forma) de la ventana y se garantiza que es rápido, mientras <xref:System.Windows.Forms.Control.OnPaint%2A> pinta los detalles y podría ser más lento, ya que las solicitudes de dibujo individuales se combinan en un evento de <xref:System.Windows.Forms.Control.Paint> que cubre todas las áreas que deben volver a dibujarse. Es posible que desee invocar el <xref:System.Windows.Forms.Control.OnPaintBackground%2A> si, por ejemplo, desea dibujar un fondo de color degradado para el control.  
  
 Aunque <xref:System.Windows.Forms.Control.OnPaintBackground%2A> tiene una nomenclatura similar a un evento y toma el mismo argumento que el método `OnPaint`, <xref:System.Windows.Forms.Control.OnPaintBackground%2A> no es un método de evento true. No hay ningún evento de `PaintBackground` y <xref:System.Windows.Forms.Control.OnPaintBackground%2A> no invoca los delegados de eventos. Al reemplazar el método <xref:System.Windows.Forms.Control.OnPaintBackground%2A>, no es necesario que una clase derivada invoque el método <xref:System.Windows.Forms.Control.OnPaintBackground%2A> de su clase base.  
  
## <a name="gdi-basics"></a>Aspectos básicos de GDI+  
 La clase <xref:System.Drawing.Graphics> proporciona métodos para dibujar diversas formas, como círculos, triángulos, arcos y elipses, así como métodos para mostrar texto. El espacio de nombres <xref:System.Drawing?displayProperty=nameWithType> y sus subespacios de nombres contienen clases que encapsulan elementos gráficos como formas (círculos, rectángulos, arcos y otros), colores, fuentes, pinceles, etc. Para obtener más información acerca de GDI, vea [usar clases de gráficos administrados](../advanced/using-managed-graphics-classes.md). Los aspectos básicos de GDI también se describen en el [Windows Forms cómo: crear un control de que muestra el progreso](how-to-create-a-windows-forms-control-that-shows-progress.md).  
  
## <a name="geometry-of-the-drawing-region"></a>Geometría de la región de dibujo  
 La propiedad <xref:System.Windows.Forms.Control.ClientRectangle%2A> de un control especifica la región rectangular disponible para el control en la pantalla del usuario, mientras que la propiedad <xref:System.Windows.Forms.PaintEventArgs.ClipRectangle%2A> de <xref:System.Windows.Forms.PaintEventArgs> especifica el área que se dibuja realmente. (Recuerde que el dibujo se realiza en el método de evento <xref:System.Windows.Forms.Control.Paint> que toma una instancia <xref:System.Windows.Forms.PaintEventArgs> como argumento). Es posible que un control solo tenga que pintar una parte de su área disponible, como es el caso cuando se cambia una pequeña sección de la pantalla del control. En esas situaciones, un desarrollador de control debe calcular el rectángulo real para dibujar en y pasarlo a <xref:System.Windows.Forms.Control.Invalidate%2A>. Las versiones sobrecargadas de <xref:System.Windows.Forms.Control.Invalidate%2A> que toman un <xref:System.Drawing.Rectangle> o <xref:System.Drawing.Region> como argumento usan ese argumento para generar la propiedad <xref:System.Windows.Forms.PaintEventArgs.ClipRectangle%2A> de <xref:System.Windows.Forms.PaintEventArgs>.  
  
 En el fragmento de código siguiente se muestra cómo el control personalizado `FlashTrackBar` calcula el área rectangular en la que se va a dibujar. La variable `client` denota la propiedad <xref:System.Windows.Forms.PaintEventArgs.ClipRectangle%2A>. Para obtener un ejemplo completo, vea [Cómo: crear un control de Windows Forms que muestre el progreso](how-to-create-a-windows-forms-control-that-shows-progress.md).  
  
 [!code-csharp[System.Windows.Forms.FlashTrackBar#6](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.FlashTrackBar/CS/FlashTrackBar.cs#6)]
 [!code-vb[System.Windows.Forms.FlashTrackBar#6](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.FlashTrackBar/VB/FlashTrackBar.vb#6)]  
  
## <a name="freeing-graphics-resources"></a>Liberar recursos de gráficos  
 Los objetos gráficos son caros porque usan recursos del sistema. Estos objetos incluyen instancias de la clase <xref:System.Drawing.Graphics?displayProperty=nameWithType>, así como instancias de <xref:System.Drawing.Brush?displayProperty=nameWithType>, <xref:System.Drawing.Pen?displayProperty=nameWithType>y otras clases de gráficos. Es importante que cree un recurso de gráficos solo cuando lo necesite y lo libere en cuanto termine de usarlo. Si crea un tipo que implementa la interfaz <xref:System.IDisposable>, llame a su método de <xref:System.IDisposable.Dispose%2A> cuando termine de utilizarlo para liberar recursos.  
  
 En el fragmento de código siguiente se muestra cómo el control personalizado `FlashTrackBar` crea y libera un recurso <xref:System.Drawing.Brush>. Para obtener el código fuente completo, vea [Cómo: crear un control de Windows Forms que muestre el progreso](how-to-create-a-windows-forms-control-that-shows-progress.md).  
  
 [!code-csharp[System.Windows.Forms.FlashTrackBar#5](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.FlashTrackBar/CS/FlashTrackBar.cs#5)]
 [!code-vb[System.Windows.Forms.FlashTrackBar#5](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.FlashTrackBar/VB/FlashTrackBar.vb#5)]  
  
 [!code-csharp[System.Windows.Forms.FlashTrackBar#4](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.FlashTrackBar/CS/FlashTrackBar.cs#4)]
 [!code-vb[System.Windows.Forms.FlashTrackBar#4](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.FlashTrackBar/VB/FlashTrackBar.vb#4)]  
  
 [!code-csharp[System.Windows.Forms.FlashTrackBar#3](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.FlashTrackBar/CS/FlashTrackBar.cs#3)]
 [!code-vb[System.Windows.Forms.FlashTrackBar#3](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.FlashTrackBar/VB/FlashTrackBar.vb#3)]  
  
## <a name="see-also"></a>Vea también

- [Crear un control de formularios Windows Forms que muestre el progreso](how-to-create-a-windows-forms-control-that-shows-progress.md)
