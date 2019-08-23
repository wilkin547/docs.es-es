---
title: Representar un control de formularios Windows Forms
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
ms.openlocfilehash: b24fbefac0dcfb666e25ad1d1726ef2cf8a5d84e
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "69968273"
---
# <a name="rendering-a-windows-forms-control"></a>Representar un control de formularios Windows Forms
La representación hace referencia al proceso de creación de una representación visual en la pantalla de un usuario. Windows Forms usa GDI (la nueva biblioteca de gráficos de Windows) para la representación. Las clases administradas que proporcionan acceso a GDI se encuentran <xref:System.Drawing?displayProperty=nameWithType> en el espacio de nombres y sus subespacios de nombres.  
  
 Los elementos siguientes están implicados en la representación de controles:  
  
- Funcionalidad de dibujo proporcionada por la clase <xref:System.Windows.Forms.Control?displayProperty=nameWithType>base.  
  
- Elementos esenciales de la biblioteca de gráficos GDI.  
  
- Geometría de la región de dibujo.  
  
- El procedimiento para liberar recursos de gráficos.  
  
## <a name="drawing-functionality-provided-by-control"></a>Funcionalidad de dibujo proporcionada por el control  
 La clase <xref:System.Windows.Forms.Control> base proporciona la funcionalidad de dibujo <xref:System.Windows.Forms.Control.Paint> a través de su evento. Un control genera el <xref:System.Windows.Forms.Control.Paint> evento cada vez que necesita actualizar su presentación. Para obtener más información acerca de los eventos en el .NET Framework, consulte [controlar y provocar eventos](../../../standard/events/index.md).  
  
 La clase de datos de evento <xref:System.Windows.Forms.Control.Paint> para el <xref:System.Windows.Forms.PaintEventArgs>evento,, contiene los datos necesarios para dibujar un control, un identificador de un objeto de gráficos y un objeto de rectángulo que representa la región en la que se va a dibujar. Estos objetos se muestran en negrita en el fragmento de código siguiente.  
  
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
  
 <xref:System.Drawing.Graphics>es una clase administrada que encapsula la funcionalidad de dibujo, como se describe en la descripción de GDI más adelante en este tema. Es una instancia de la <xref:System.Drawing.Rectangle> estructura y define el área disponible en la que puede dibujarse un control. <xref:System.Windows.Forms.PaintEventArgs.ClipRectangle%2A> Un desarrollador de controles puede calcular <xref:System.Windows.Forms.PaintEventArgs.ClipRectangle%2A> mediante la <xref:System.Windows.Forms.PaintEventArgs.ClipRectangle%2A> propiedad de un control, tal y como se describe en la descripción de Geometry más adelante en este tema.  
  
 Un control debe proporcionar la lógica de representación invalidando <xref:System.Windows.Forms.Control.OnPaint%2A> el método del <xref:System.Windows.Forms.Control>que hereda. <xref:System.Windows.Forms.Control.OnPaint%2A>obtiene acceso a un objeto gráfico y un rectángulo para dibujar a través de <xref:System.Drawing.Design.PaintValueEventArgs.Graphics%2A> las <xref:System.Windows.Forms.PaintEventArgs.ClipRectangle%2A> propiedades y de la <xref:System.Windows.Forms.PaintEventArgs> instancia de que se le ha pasado.  
  
```vb  
Protected Overridable Sub OnPaint(pe As PaintEventArgs)  
```  
  
```csharp  
protected virtual void OnPaint(PaintEventArgs pe);  
```  
  
 El <xref:System.Windows.Forms.Control.OnPaint%2A> método de la clase <xref:System.Windows.Forms.Control> base no implementa ninguna funcionalidad de dibujo, sino que simplemente invoca los delegados de eventos que <xref:System.Windows.Forms.Control.Paint> se registran con el evento. Al invalidar <xref:System.Windows.Forms.Control.OnPaint%2A>, normalmente debe invocar el <xref:System.Windows.Forms.Control.OnPaint%2A> método de la clase base para que los delegados <xref:System.Windows.Forms.Control.Paint> registrados reciban el evento. Sin embargo, los controles que pintan toda la superficie no deben invocar <xref:System.Windows.Forms.Control.OnPaint%2A>la clase base, ya que esto presenta el parpadeo. Para obtener un ejemplo de cómo invalidar el <xref:System.Windows.Forms.Control.OnPaint%2A> evento, consulte el [procedimiento: Cree un control de Windows Forms que muestre](how-to-create-a-windows-forms-control-that-shows-progress.md)el progreso.  
  
> [!NOTE]
> No invoque <xref:System.Windows.Forms.Control.OnPaint%2A> directamente desde el control; en su lugar, invoque el <xref:System.Windows.Forms.Control.Invalidate%2A> método ( <xref:System.Windows.Forms.Control>heredado de <xref:System.Windows.Forms.Control.Invalidate%2A>) o algún otro método que invoque. A <xref:System.Windows.Forms.Control.Invalidate%2A> su vez, el método <xref:System.Windows.Forms.Control.OnPaint%2A>invoca a. El <xref:System.Windows.Forms.Control.Invalidate%2A> método está sobrecargado y, dependiendo de los argumentos proporcionados a, <xref:System.Windows.Forms.Control.Invalidate%2A> un control vuelve a `e`dibujar parte o todo el área de la pantalla.  
  
 La clase <xref:System.Windows.Forms.Control> base define otro método que es útil para dibujar, el <xref:System.Windows.Forms.Control.OnPaintBackground%2A> método.  
  
```vb  
Protected Overridable Sub OnPaintBackground(pevent As PaintEventArgs)  
```  
  
```csharp  
protected virtual void OnPaintBackground(PaintEventArgs pevent);  
```  
  
 <xref:System.Windows.Forms.Control.OnPaintBackground%2A>pinta el fondo (y, por tanto, la forma) de la ventana y se garantiza que es <xref:System.Windows.Forms.Control.OnPaint%2A> rápido, mientras pinta los detalles y puede ser más lento, ya que las <xref:System.Windows.Forms.Control.Paint> solicitudes de dibujo individuales se combinan en un evento que cubre todas las áreas que deben vuelve a dibujarse. Es posible que desee invocar <xref:System.Windows.Forms.Control.OnPaintBackground%2A> si, por ejemplo, desea dibujar un fondo de color degradado para el control.  
  
 Aunque <xref:System.Windows.Forms.Control.OnPaintBackground%2A> tiene una nomenclatura similar a un evento y toma el mismo argumento que `OnPaint` el método <xref:System.Windows.Forms.Control.OnPaintBackground%2A> , no es un método de evento true. No hay ningún `PaintBackground` evento y <xref:System.Windows.Forms.Control.OnPaintBackground%2A> no invoca los delegados de eventos. Al reemplazar el <xref:System.Windows.Forms.Control.OnPaintBackground%2A> método, no es necesario que una clase derivada invoque el <xref:System.Windows.Forms.Control.OnPaintBackground%2A> método de su clase base.  
  
## <a name="gdi-basics"></a>Aspectos básicos de GDI+  
 La <xref:System.Drawing.Graphics> clase proporciona métodos para dibujar varias formas, como círculos, triángulos, arcos y elipses, así como métodos para mostrar texto. El <xref:System.Drawing?displayProperty=nameWithType> espacio de nombres y sus subespacios de nombres contienen clases que encapsulan elementos gráficos como formas (círculos, rectángulos, arcos y otros), colores, fuentes, pinceles, etc. Para obtener más información acerca de GDI, vea [usar clases de gráficos administrados](../advanced/using-managed-graphics-classes.md). Los aspectos básicos de GDI también se describen en el [ Cree un control de Windows Forms que muestre](how-to-create-a-windows-forms-control-that-shows-progress.md)el progreso.  
  
## <a name="geometry-of-the-drawing-region"></a>Geometría de la región de dibujo  
 La <xref:System.Windows.Forms.Control.ClientRectangle%2A> propiedad de un control especifica la región rectangular disponible para el control en la pantalla del usuario, mientras que <xref:System.Windows.Forms.PaintEventArgs.ClipRectangle%2A> la propiedad <xref:System.Windows.Forms.PaintEventArgs> de especifica el área que se dibuja realmente. (Recuerde que el dibujo se realiza en <xref:System.Windows.Forms.Control.Paint> el método de evento que <xref:System.Windows.Forms.PaintEventArgs> toma una instancia como su argumento). Es posible que un control solo tenga que pintar una parte de su área disponible, como es el caso cuando se cambia una pequeña sección de la pantalla del control. En esas situaciones, un desarrollador de control debe calcular el rectángulo real para dibujar en y pasarlo a <xref:System.Windows.Forms.Control.Invalidate%2A>. Las versiones sobrecargadas de <xref:System.Windows.Forms.Control.Invalidate%2A> que <xref:System.Drawing.Rectangle> toman o <xref:System.Drawing.Region> como argumento usan ese argumento para generar la <xref:System.Windows.Forms.PaintEventArgs.ClipRectangle%2A> propiedad de <xref:System.Windows.Forms.PaintEventArgs>.  
  
 En el fragmento de código siguiente se `FlashTrackBar` muestra cómo el control personalizado calcula el área rectangular en la que se va a dibujar. La `client` variable denota la <xref:System.Windows.Forms.PaintEventArgs.ClipRectangle%2A> propiedad. Para obtener un ejemplo completo, [consulte Cómo: Cree un control de Windows Forms que muestre](how-to-create-a-windows-forms-control-that-shows-progress.md)el progreso.  
  
 [!code-csharp[System.Windows.Forms.FlashTrackBar#6](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.FlashTrackBar/CS/FlashTrackBar.cs#6)]
 [!code-vb[System.Windows.Forms.FlashTrackBar#6](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.FlashTrackBar/VB/FlashTrackBar.vb#6)]  
  
## <a name="freeing-graphics-resources"></a>Liberar recursos de gráficos  
 Los objetos gráficos son caros porque usan recursos del sistema. Estos objetos incluyen instancias de la <xref:System.Drawing.Graphics?displayProperty=nameWithType> clase, así como instancias de <xref:System.Drawing.Brush?displayProperty=nameWithType>, <xref:System.Drawing.Pen?displayProperty=nameWithType>y otras clases de gráficos. Es importante que cree un recurso de gráficos solo cuando lo necesite y lo libere en cuanto termine de usarlo. Si crea un tipo que implementa la <xref:System.IDisposable> interfaz, llame a su <xref:System.IDisposable.Dispose%2A> método cuando termine de utilizarlo para liberar recursos.  
  
 En el fragmento de código siguiente se `FlashTrackBar` muestra cómo el control personalizado crea <xref:System.Drawing.Brush> y libera un recurso. Para obtener el código fuente completo, [consulte Cómo: Cree un control de Windows Forms que muestre](how-to-create-a-windows-forms-control-that-shows-progress.md)el progreso.  
  
 [!code-csharp[System.Windows.Forms.FlashTrackBar#5](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.FlashTrackBar/CS/FlashTrackBar.cs#5)]
 [!code-vb[System.Windows.Forms.FlashTrackBar#5](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.FlashTrackBar/VB/FlashTrackBar.vb#5)]  
  
 [!code-csharp[System.Windows.Forms.FlashTrackBar#4](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.FlashTrackBar/CS/FlashTrackBar.cs#4)]
 [!code-vb[System.Windows.Forms.FlashTrackBar#4](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.FlashTrackBar/VB/FlashTrackBar.vb#4)]  
  
 [!code-csharp[System.Windows.Forms.FlashTrackBar#3](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.FlashTrackBar/CS/FlashTrackBar.cs#3)]
 [!code-vb[System.Windows.Forms.FlashTrackBar#3](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.FlashTrackBar/VB/FlashTrackBar.vb#3)]  
  
## <a name="see-also"></a>Vea también

- [Procedimientos: Crear un control de Windows Forms que muestre el progreso](how-to-create-a-windows-forms-control-that-shows-progress.md)
