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
ms.openlocfilehash: a2d7a02e725e3f8065b80a6b30ea21158be43ea8
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
---
# <a name="rendering-a-windows-forms-control"></a>Representar un control de formularios Windows Forms
Representación se refiere al proceso de creación de una representación visual en la pantalla del usuario. Windows Forms usa [!INCLUDE[ndptecgdi](../../../../includes/ndptecgdi-md.md)] (la nueva biblioteca gráfica de Windows) para la representación. Las clases administradas que proporcionan acceso a [!INCLUDE[ndptecgdi](../../../../includes/ndptecgdi-md.md)] están en el <xref:System.Drawing?displayProperty=nameWithType> espacio de nombres y sus subespacios de nombres.  
  
 Los siguientes elementos implicados en la representación del control:  
  
-   La funcionalidad de dibujo proporcionada por la clase base <xref:System.Windows.Forms.Control?displayProperty=nameWithType>.  
  
-   Los elementos básicos de la [!INCLUDE[ndptecgdi](../../../../includes/ndptecgdi-md.md)] biblioteca de gráficos.  
  
-   La geometría de la región de dibujo.  
  
-   El procedimiento para liberar recursos gráficos.  
  
## <a name="drawing-functionality-provided-by-control"></a>Funcionalidad proporcionada por el Control de dibujo  
 La clase base <xref:System.Windows.Forms.Control> proporciona funcionalidad de dibujo a través de su <xref:System.Windows.Forms.Control.Paint> eventos. Un control provoca la <xref:System.Windows.Forms.Control.Paint> evento cada vez que necesita actualizar su apariencia. Para obtener más información sobre los eventos de .NET Framework, vea [controlar y provocar eventos](../../../../docs/standard/events/index.md).  
  
 Clase de los datos del evento para el <xref:System.Windows.Forms.Control.Paint> eventos, <xref:System.Windows.Forms.PaintEventArgs>, contiene los datos necesarios para dibujar un control, un identificador de un objeto graphics y un objeto de rectángulo que representa la región para dibujar. Estos objetos se muestran en negrita en el siguiente fragmento de código.  
  
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
  
 <xref:System.Drawing.Graphics> es una clase administrada que encapsula la funcionalidad de dibujo, como se describe en la explicación de [!INCLUDE[ndptecgdi](../../../../includes/ndptecgdi-md.md)] más adelante en este tema. El <xref:System.Windows.Forms.PaintEventArgs.ClipRectangle%2A> es una instancia de la <xref:System.Drawing.Rectangle> permite organizar y define el área disponible en la que puede dibujar un control. Un desarrollador del control se puede calcular el <xref:System.Windows.Forms.PaintEventArgs.ClipRectangle%2A> mediante el <xref:System.Windows.Forms.PaintEventArgs.ClipRectangle%2A> propiedad de un control, como se describe en la descripción de geometría más adelante en este tema.  
  
 Un control debe proporcionar lógica de procesamiento reemplazando el <xref:System.Windows.Forms.Control.OnPaint%2A> método que hereda de <xref:System.Windows.Forms.Control>. <xref:System.Windows.Forms.Control.OnPaint%2A> Obtiene acceso a un objeto graphics y un rectángulo para dibujar a través de la <xref:System.Drawing.Design.PaintValueEventArgs.Graphics%2A> y <xref:System.Windows.Forms.PaintEventArgs.ClipRectangle%2A> propiedades de la <xref:System.Windows.Forms.PaintEventArgs> instancia pasa a él.  
  
```vb  
Protected Overridable Sub OnPaint(pe As PaintEventArgs)  
```  
  
```csharp  
protected virtual void OnPaint(PaintEventArgs pe);  
```  
  
 El <xref:System.Windows.Forms.Control.OnPaint%2A> método de la base de <xref:System.Windows.Forms.Control> clase no implementa ninguna funcionalidad de dibujo, pero limita a invocar los delegados de eventos que están registrados con el <xref:System.Windows.Forms.Control.Paint> eventos. Cuando se reemplaza <xref:System.Windows.Forms.Control.OnPaint%2A>, normalmente debe invocar el <xref:System.Windows.Forms.Control.OnPaint%2A> método de la clase base para que los delegados registrados reciban el <xref:System.Windows.Forms.Control.Paint> eventos. Sin embargo, los controles que dibujan toda su superficie no deben invocar la clase base <xref:System.Windows.Forms.Control.OnPaint%2A>, ya que esto causa parpadeos. Para obtener un ejemplo de cómo reemplazar el <xref:System.Windows.Forms.Control.OnPaint%2A> eventos, vea el [Cómo: crear un Windows Forms Control That Shows Progress](../../../../docs/framework/winforms/controls/how-to-create-a-windows-forms-control-that-shows-progress.md).  
  
> [!NOTE]
>  No invocan <xref:System.Windows.Forms.Control.OnPaint%2A> directamente desde el control; en su lugar, invoque la <xref:System.Windows.Forms.Control.Invalidate%2A> (método) (se hereda de <xref:System.Windows.Forms.Control>) o algún otro método que invoca <xref:System.Windows.Forms.Control.Invalidate%2A>. El <xref:System.Windows.Forms.Control.Invalidate%2A> a su vez invoca el método <xref:System.Windows.Forms.Control.OnPaint%2A>. El <xref:System.Windows.Forms.Control.Invalidate%2A> método está sobrecargado y, dependiendo de los argumentos proporcionados a <xref:System.Windows.Forms.Control.Invalidate%2A> `e`, un control vuelve a dibujarse algunos o todos de su área de la pantalla.  
  
 La base de <xref:System.Windows.Forms.Control> clase define otro método que resulta útil para dibujar: el <xref:System.Windows.Forms.Control.OnPaintBackground%2A> método.  
  
```vb  
Protected Overridable Sub OnPaintBackground(pevent As PaintEventArgs)  
```  
  
```csharp  
protected virtual void OnPaintBackground(PaintEventArgs pevent);  
```  
  
 <xref:System.Windows.Forms.Control.OnPaintBackground%2A> pinta el fondo (y, por tanto, la forma) de la ventana y se garantiza que sea rápido, al <xref:System.Windows.Forms.Control.OnPaint%2A> dibuja los detalles y podría ser más lento debido a solicitudes de dibujo individuales se combinan en una sola <xref:System.Windows.Forms.Control.Paint> evento que abarca todas las áreas que deben estar vuelve a dibujar. Puede invocar la <xref:System.Windows.Forms.Control.OnPaintBackground%2A> si, por ejemplo, va a dibujar un fondo de color degradado para el control.  
  
 Mientras <xref:System.Windows.Forms.Control.OnPaintBackground%2A> tiene una nomenclatura similar a eventos y los mismos argumentos que el `OnPaint` método <xref:System.Windows.Forms.Control.OnPaintBackground%2A> no es un método de evento auténtico. No hay ningún `PaintBackground` eventos y <xref:System.Windows.Forms.Control.OnPaintBackground%2A> no invoca delegados de eventos. Al reemplazar el <xref:System.Windows.Forms.Control.OnPaintBackground%2A> método, una clase derivada no es necesaria para invocar la <xref:System.Windows.Forms.Control.OnPaintBackground%2A> método de su clase base.  
  
## <a name="gdi-basics"></a>Conceptos básicos de GDI +  
 La <xref:System.Drawing.Graphics> clase proporciona métodos para dibujar varias formas como círculos, triángulos, arcos y elipses, así como métodos para mostrar texto. El <xref:System.Drawing?displayProperty=nameWithType> espacio de nombres y sus subespacios de nombres contienen clases que encapsulan elementos gráficos, como formas (círculos, rectángulos, arcos y otras), colores, fuentes, pinceles y así sucesivamente. Para obtener más información acerca de [!INCLUDE[ndptecgdi](../../../../includes/ndptecgdi-md.md)], consulte [utilizar clases gráficas administradas](../../../../docs/framework/winforms/advanced/using-managed-graphics-classes.md). Las operaciones básicas de [!INCLUDE[ndptecgdi](../../../../includes/ndptecgdi-md.md)] también se describen en la [Cómo: crear un Windows Forms Control That Shows Progress](../../../../docs/framework/winforms/controls/how-to-create-a-windows-forms-control-that-shows-progress.md).  
  
## <a name="geometry-of-the-drawing-region"></a>Geometría de la región de dibujo  
 El <xref:System.Windows.Forms.Control.ClientRectangle%2A> propiedad de un control especifica la región rectangular que disponibles para el control en la pantalla del usuario, mientras que la <xref:System.Windows.Forms.PaintEventArgs.ClipRectangle%2A> propiedad de <xref:System.Windows.Forms.PaintEventArgs> especifica el área que realmente se está pintando. (Recuerde que el dibujo se realiza el <xref:System.Windows.Forms.Control.Paint> método eventos que tome un <xref:System.Windows.Forms.PaintEventArgs> instancia como su argumento). Un control que tenga que pintar solo una parte de su área disponible, como sucede cuando una pequeña parte de los cambios de pantalla del control. En estos casos, un desarrollador del control debe calcular el rectángulo real para dibujar en y pasar a <xref:System.Windows.Forms.Control.Invalidate%2A>. Las versiones sobrecargadas de <xref:System.Windows.Forms.Control.Invalidate%2A> que toman un <xref:System.Drawing.Rectangle> o <xref:System.Drawing.Region> como argumento, utilizan dicho argumento para generar la <xref:System.Windows.Forms.PaintEventArgs.ClipRectangle%2A> propiedad de <xref:System.Windows.Forms.PaintEventArgs>.  
  
 El siguiente fragmento de código se muestra cómo el `FlashTrackBar` control personalizado calcula el área rectangular para dibujar. El `client` variable denota el <xref:System.Windows.Forms.PaintEventArgs.ClipRectangle%2A> propiedad. Para obtener un ejemplo completo, vea [Cómo: crear un Windows Forms Control That Shows Progress](../../../../docs/framework/winforms/controls/how-to-create-a-windows-forms-control-that-shows-progress.md).  
  
 [!code-csharp[System.Windows.Forms.FlashTrackBar#6](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.FlashTrackBar/CS/FlashTrackBar.cs#6)]
 [!code-vb[System.Windows.Forms.FlashTrackBar#6](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.FlashTrackBar/VB/FlashTrackBar.vb#6)]  
  
## <a name="freeing-graphics-resources"></a>Liberar recursos gráficos  
 Objetos gráficos son costosos ya que utilizan recursos del sistema. Estos objetos incluyen instancias de la <xref:System.Drawing.Graphics?displayProperty=nameWithType> , así como instancias de la clase <xref:System.Drawing.Brush?displayProperty=nameWithType>, <xref:System.Drawing.Pen?displayProperty=nameWithType>y otras clases de gráficos. Es importante que cree un recurso de gráficos solo cuando lo necesite y liberarla pronto, ya que haya terminado de usarlo. Si crea un tipo que implementa el <xref:System.IDisposable> interfaz, llame a su <xref:System.IDisposable.Dispose%2A> método cuando haya terminado de usarla para liberar recursos.  
  
 El siguiente fragmento de código se muestra cómo el `FlashTrackBar` control personalizado crea y libera un <xref:System.Drawing.Brush> recursos. Para el código fuente completo, vea [Cómo: crear un Windows Forms Control That Shows Progress](../../../../docs/framework/winforms/controls/how-to-create-a-windows-forms-control-that-shows-progress.md).  
  
 [!code-csharp[System.Windows.Forms.FlashTrackBar#5](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.FlashTrackBar/CS/FlashTrackBar.cs#5)]
 [!code-vb[System.Windows.Forms.FlashTrackBar#5](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.FlashTrackBar/VB/FlashTrackBar.vb#5)]  
  
 [!code-csharp[System.Windows.Forms.FlashTrackBar#4](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.FlashTrackBar/CS/FlashTrackBar.cs#4)]
 [!code-vb[System.Windows.Forms.FlashTrackBar#4](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.FlashTrackBar/VB/FlashTrackBar.vb#4)]  
  
 [!code-csharp[System.Windows.Forms.FlashTrackBar#3](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.FlashTrackBar/CS/FlashTrackBar.cs#3)]
 [!code-vb[System.Windows.Forms.FlashTrackBar#3](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.FlashTrackBar/VB/FlashTrackBar.vb#3)]  
  
## <a name="see-also"></a>Vea también  
 [Crear un control de formularios Windows Forms que muestre el progreso](../../../../docs/framework/winforms/controls/how-to-create-a-windows-forms-control-that-shows-progress.md)
