---
title: Controles constituyentes
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- custom controls [Windows Forms], constituent controls
- constituent controls [Windows Forms]
- user controls [Windows Forms], constituent controls
ms.assetid: 5565e720-198b-4bbd-a2bd-c447ba641798
ms.openlocfilehash: 2865a3d85bd56151038ee90c18d199d3a584b5d4
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79182410"
---
# <a name="constituent-controls"></a>Controles constituyentes
Los controles que componen un control de usuario, o *controles constituyentes* tal como se denominan, son relativamente inflexibles en cuanto a la representación gráfica personalizada. Todos los controles de formularios Windows <xref:System.Windows.Forms.Control.OnPaint%2A> Forms controlan su propia representación a través de su propio método. Como este método está protegido, no es accesible al desarrollador y por tanto no se puede evitar ejecutarlo cuando se dibuja el control. Sin embargo, esto no significa que no se pueda agregar código que afecte a la apariencia de controles constituyentes. Otras representaciones pueden realizarse mediante la adición de un controlador de eventos. Por ejemplo, supongamos que <xref:System.Windows.Forms.UserControl> estaba autorizando un botón denominado `MyButton`. Si desea tener una representación adicional más <xref:System.Web.UI.WebControls.Button>allá de lo proporcionado por el , agregaría código al control de usuario similar a lo siguiente:  
  
```vb  
Public Sub MyPaint(ByVal sender as Object, e as PaintEventArgs) Handles _  
   MyButton.Paint  
   'Additional rendering code goes here  
End Sub  
```  
  
```csharp  
// Add the event handler to the button's Paint event.  
MyButton.Paint +=
   new System.Windows.Forms.PaintEventHandler (this.MyPaint);  
// Create the custom painting method.  
protected void MyPaint (object sender,
System.Windows.Forms.PaintEventArgs e)  
{  
   // Additional rendering code goes here.  
}  
```  
  
> [!NOTE]
> Algunos controles de formularios <xref:System.Windows.Forms.TextBox>Windows Forms, como , están pintados directamente por Windows. En estos casos, <xref:System.Windows.Forms.Control.OnPaint%2A> nunca se llama al método y, por lo tanto, nunca se llamará al ejemplo anterior.  
  
 Esto crea un método que se ejecuta cada vez que se ejecuta el evento `MyButton.Paint`, agregando por tanto representación gráfica adicional al control. Tenga en cuenta que esto no impide la ejecución de `MyButton.OnPaint` y, por tanto, toda la pintura realizada con un botón se llevará a cabo además en el dibujo personalizado. Para más información acerca de la tecnología GDI+ y de la representación personalizada, consulte [Crear imágenes gráficas con GDI+](../advanced/how-to-create-graphics-objects-for-drawing.md). Si desea obtener una representación única del control, la mejor línea de acción es crear un control heredado y escribir código de representación personalizado para él. Para más información, consulte [Controles dibujados por el usuario](user-drawn-controls.md).  
  
## <a name="see-also"></a>Consulte también

- <xref:System.Windows.Forms.UserControl>
- <xref:System.Windows.Forms.Control.OnPaint%2A>
- [Controles dibujados por el usuario](user-drawn-controls.md)
- [Cómo: Crear objetos Graphics para dibujar](../advanced/how-to-create-graphics-objects-for-drawing.md)
- [Variedades de controles personalizados](varieties-of-custom-controls.md)
