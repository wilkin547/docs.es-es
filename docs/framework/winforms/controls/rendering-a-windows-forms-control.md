---
title: "Representar un control de formularios Windows Forms | Microsoft Docs"
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
  - "controles personalizados [Windows Forms], recursos gráficos"
  - "controles personalizados [Windows Forms], invalidación y dibujo"
  - "controles personalizados [Windows Forms], representar"
  - "OnPaintBackground (método), invocar en controles personalizados de Windows Forms"
ms.assetid: aae8e1e6-4786-432b-a15e-f4c44760d302
caps.latest.revision: 12
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 12
---
# Representar un control de formularios Windows Forms
Por representar se entiende la creación de una representación visual en la pantalla de un usuario.  Los formularios Windows Forms utilizan [!INCLUDE[ndptecgdi](../../../../includes/ndptecgdi-md.md)] \(la nueva biblioteca gráfica de Windows\) para realizar la representación.  Las clases administradas que proporcionan acceso a [!INCLUDE[ndptecgdi](../../../../includes/ndptecgdi-md.md)] se encuentran en el espacio de nombres <xref:System.Drawing?displayProperty=fullName> y sus subespacios de nombres.  
  
 Los siguientes elementos intervienen en la representación de los controles:  
  
-   La funcionalidad de dibujo proporcionada por la clase base <xref:System.Windows.Forms.Control?displayProperty=fullName>.  
  
-   Los elementos básicos de la biblioteca gráfica [!INCLUDE[ndptecgdi](../../../../includes/ndptecgdi-md.md)].  
  
-   La geometría de la zona de dibujo.  
  
-   El procedimiento para liberar recursos gráficos.  
  
## Funcionalidad de dibujo proporcionada por un control  
 La clase base <xref:System.Windows.Forms.Control> proporciona funcionalidad de dibujo a través del evento <xref:System.Windows.Forms.Control.Paint>.  Un control provoca el evento <xref:System.Windows.Forms.Control.Paint> cada vez que necesita actualizar su apariencia.  Para obtener más información acerca de los eventos de .NET Framework, vea [Controlar y provocar eventos](../../../../docs/standard/events/index.md).  
  
 La clase de datos del evento <xref:System.Windows.Forms.Control.Paint>, <xref:System.Windows.Forms.PaintEventArgs>, guarda los datos necesarios para dibujar un control; un identificador de un objeto Graphics y un objeto Rectangle que representa la zona en la que se va a dibujar.  Estos objetos se muestran en negrita en el siguiente fragmento de código.  
  
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
  
 <xref:System.Drawing.Graphics> es una clase administrada que encapsula la funcionalidad de dibujo, como se indica en la descripción de [!INCLUDE[ndptecgdi](../../../../includes/ndptecgdi-md.md)] más adelante en este mismo tema.  <xref:System.Windows.Forms.PaintEventArgs.ClipRectangle%2A> es una instancia de la estructura <xref:System.Drawing.Rectangle> y define el área disponible en la que puede dibujar un control.  Los desarrolladores de controles pueden calcular la propiedad <xref:System.Windows.Forms.PaintEventArgs.ClipRectangle%2A> utilizando la propiedad <xref:System.Windows.Forms.PaintEventArgs.ClipRectangle%2A> de un control, como se explica en la descripción de geometría más adelante en este mismo tema.  
  
 Un control debe proporcionar lógica de representación al reemplazar el método <xref:System.Windows.Forms.Control.OnPaint%2A> que hereda de <xref:System.Windows.Forms.Control>.  El método <xref:System.Windows.Forms.Control.OnPaint%2A> obtiene el acceso al objeto gráfico y a un rectángulo donde se va a dibujar mediante las propiedades <xref:System.Windows.Forms.PaintEventArgs.ClipRectangle%2A> y <xref:System.Drawing.Design.PaintValueEventArgs.Graphics%2A> de la instancia <xref:System.Windows.Forms.PaintEventArgs> que se le ha pasado.  
  
```vb  
Protected Overridable Sub OnPaint(pe As PaintEventArgs)  
```  
  
```csharp  
protected virtual void OnPaint(PaintEventArgs pe);  
```  
  
 El método <xref:System.Windows.Forms.Control.OnPaint%2A> de la clase base <xref:System.Windows.Forms.Control> no implementa ninguna funcionalidad de dibujo, sino que se limita a invocar los delegados de evento registrados en el evento <xref:System.Windows.Forms.Control.Paint>.  Cuando se reemplaza <xref:System.Windows.Forms.Control.OnPaint%2A>, normalmente se invoca el método <xref:System.Windows.Forms.Control.OnPaint%2A> de la clase base para que los delegados registrados reciban el evento <xref:System.Windows.Forms.Control.Paint>.  Sin embargo, los controles que dibujan toda su superficie no deben invocar el método <xref:System.Windows.Forms.Control.OnPaint%2A> de la clase base, ya que esto causa parpadeos.  Para obtener un ejemplo del reemplazo del evento <xref:System.Windows.Forms.Control.OnPaint%2A>, vea [Cómo: Crear un control de formularios Windows Forms que muestre el progreso](../../../../docs/framework/winforms/controls/how-to-create-a-windows-forms-control-that-shows-progress.md).  
  
> [!NOTE]
>  No invoque <xref:System.Windows.Forms.Control.OnPaint%2A> directamente desde el control, invoque en su lugar el método <xref:System.Windows.Forms.Control.Invalidate%2A> \(heredado de <xref:System.Windows.Forms.Control>\) o algún otro método que invoque <xref:System.Windows.Forms.Control.Invalidate%2A>.  El método <xref:System.Windows.Forms.Control.Invalidate%2A> a su vez invoca <xref:System.Windows.Forms.Control.OnPaint%2A>.  El método <xref:System.Windows.Forms.Control.Invalidate%2A> está sobrecargado y, dependiendo de los argumentos que se suministren a <xref:System.Windows.Forms.Control.Invalidate%2A> `e`, un control volverá a dibujar todo el área de la pantalla o parte de ésta.  
  
 La clase base <xref:System.Windows.Forms.Control> define otro método que resulta de utilidad para dibujar, el método <xref:System.Windows.Forms.Control.OnPaintBackground%2A>.  
  
```vb  
Protected Overridable Sub OnPaintBackground(pevent As PaintEventArgs)  
```  
  
```csharp  
protected virtual void OnPaintBackground(PaintEventArgs pevent);  
```  
  
 <xref:System.Windows.Forms.Control.OnPaintBackground%2A> dibuja el fondo \(y por tanto la forma\) de la ventana y está garantizado como rápido, mientras que <xref:System.Windows.Forms.Control.OnPaint%2A> dibuja los detalles y posiblemente sea más lento, ya que las distintas solicitudes de dibujo se combinan en un solo evento <xref:System.Windows.Forms.Control.Paint> que abarca todas las áreas que han de volverse a dibujar.  Se puede invocar el método <xref:System.Windows.Forms.Control.OnPaintBackground%2A> si, por ejemplo, se va a dibujar un fondo en color degradado para el control.  
  
 Aunque <xref:System.Windows.Forms.Control.OnPaintBackground%2A> tiene una nomenclatura similar a la de los eventos y acepta los mismos argumentos que el método `OnPaint`, <xref:System.Windows.Forms.Control.OnPaintBackground%2A> no es un método de evento auténtico.  No hay ningún evento `PaintBackground` y <xref:System.Windows.Forms.Control.OnPaintBackground%2A> no invoca delegados de eventos.  Al reemplazar el método <xref:System.Windows.Forms.Control.OnPaintBackground%2A>, no se requiere una clase derivada para invocar el método <xref:System.Windows.Forms.Control.OnPaintBackground%2A> de su clase base.  
  
## Funciones básicas de GDI\+  
 La clase <xref:System.Drawing.Graphics> proporciona métodos para dibujar varias formas como círculos, triángulos, arcos y elipses, y métodos para mostrar texto.  El espacio de nombres <xref:System.Drawing?displayProperty=fullName> y sus subespacios de nombres contienen clases que encapsulan elementos gráficos, como formar \(círculos, rectángulos, arcos y otras\), colores, fuentes, pinceles, etc.  Para obtener más información sobre [!INCLUDE[ndptecgdi](../../../../includes/ndptecgdi-md.md)], vea [Utilizar clases gráficas administradas](../../../../docs/framework/winforms/advanced/using-managed-graphics-classes.md).  La información esencial de [!INCLUDE[ndptecgdi](../../../../includes/ndptecgdi-md.md)] también se describe en [Cómo: Crear un control de formularios Windows Forms que muestre el progreso](../../../../docs/framework/winforms/controls/how-to-create-a-windows-forms-control-that-shows-progress.md).  
  
## La geometría de la zona de dibujo.  
 La propiedad <xref:System.Windows.Forms.Control.ClientRectangle%2A> de un control especifica la zona rectangular disponible para el control en la pantalla del usuario, mientras que la propiedad <xref:System.Windows.Forms.PaintEventArgs.ClipRectangle%2A> de <xref:System.Windows.Forms.PaintEventArgs> especifica la zona dibujada en realidad.  \(Conviene recordar que el dibujo se realiza en el método <xref:System.Windows.Forms.Control.Paint> que toma una instancia <xref:System.Windows.Forms.PaintEventArgs> como su argumento.\)  Es posible que los controles sólo tengan que dibujar una parte del área disponible, como sucede cuando varía una pequeña sección de la apariencia del control.  En tales circunstancias, un desarrollador de controles deberá calcular el rectángulo real en el que se va a dibujar y pasarlo a <xref:System.Windows.Forms.Control.Invalidate%2A>.  Las versiones sobrecargadas del método <xref:System.Windows.Forms.Control.Invalidate%2A> que toma <xref:System.Drawing.Rectangle> o <xref:System.Drawing.Region> como argumento utilizan ese argumento para generar la propiedad <xref:System.Windows.Forms.PaintEventArgs.ClipRectangle%2A> de <xref:System.Windows.Forms.PaintEventArgs>.  
  
 En el siguiente fragmento de código se muestra cómo el control personalizado `FlashTrackBar` calcula el área rectangular en la que se va a dibujar.  La variable `client` denota la propiedad <xref:System.Windows.Forms.PaintEventArgs.ClipRectangle%2A>.  Para obtener el ejemplo completo, vea [Cómo: Crear un control de formularios Windows Forms que muestre el progreso](../../../../docs/framework/winforms/controls/how-to-create-a-windows-forms-control-that-shows-progress.md).  
  
 [!code-csharp[System.Windows.Forms.FlashTrackBar#6](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.FlashTrackBar/CS/FlashTrackBar.cs#6)]
 [!code-vb[System.Windows.Forms.FlashTrackBar#6](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.FlashTrackBar/VB/FlashTrackBar.vb#6)]  
  
## Liberar recursos gráficos  
 Los objetos gráficos son costosos ya que utilizan recursos del sistema.  Tales objetos incluyen instancias de la clase <xref:System.Drawing.Graphics?displayProperty=fullName> así como crea instancias de <xref:System.Drawing.Brush?displayProperty=fullName>, <xref:System.Drawing.Pen?displayProperty=fullName> y otras clases de gráficos.  Es importante que los recursos gráficos se creen sólo cuando sean necesarios y se liberen tan pronto como se terminen de usar.  Si se crea un tipo que implementa la interfaz <xref:System.IDisposable>, se puede llamar al método <xref:System.IDisposable.Dispose%2A> una vez se haya terminado de utilizar y así liberar recursos.  
  
 En el siguiente fragmento de código se muestra cómo el control personalizado `FlashTrackBar` crea y libera un recurso <xref:System.Drawing.Brush>.  Para el código fuente completo, vea [Cómo: Crear un control de formularios Windows Forms que muestre el progreso](../../../../docs/framework/winforms/controls/how-to-create-a-windows-forms-control-that-shows-progress.md).  
  
 [!code-csharp[System.Windows.Forms.FlashTrackBar#5](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.FlashTrackBar/CS/FlashTrackBar.cs#5)]
 [!code-vb[System.Windows.Forms.FlashTrackBar#5](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.FlashTrackBar/VB/FlashTrackBar.vb#5)]  
  
 [!code-csharp[System.Windows.Forms.FlashTrackBar#4](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.FlashTrackBar/CS/FlashTrackBar.cs#4)]
 [!code-vb[System.Windows.Forms.FlashTrackBar#4](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.FlashTrackBar/VB/FlashTrackBar.vb#4)]  
  
 [!code-csharp[System.Windows.Forms.FlashTrackBar#3](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.FlashTrackBar/CS/FlashTrackBar.cs#3)]
 [!code-vb[System.Windows.Forms.FlashTrackBar#3](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.FlashTrackBar/VB/FlashTrackBar.vb#3)]  
  
## Vea también  
 [Cómo: Crear un control de formularios Windows Forms que muestre el progreso](../../../../docs/framework/winforms/controls/how-to-create-a-windows-forms-control-that-shows-progress.md)