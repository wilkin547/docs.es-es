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
ms.openlocfilehash: 76a5a4f9b02a71616d247a1bb0f03cc0aec1d70d
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61956080"
---
# <a name="constituent-controls"></a>Controles constituyentes
Los controles que componen un control de usuario, o *controles constituyentes* tal como se denominan, son relativamente inflexibles en cuanto a la representación gráfica personalizada. Todos los controles de Windows Forms controlan su propia representación a través de sus propios <xref:System.Windows.Forms.Control.OnPaint%2A> método. Como este método está protegido, no es accesible al desarrollador y por tanto no se puede evitar ejecutarlo cuando se dibuja el control. Sin embargo, esto no significa que no se pueda agregar código que afecte a la apariencia de controles constituyentes. Otras representaciones pueden realizarse mediante la adición de un controlador de eventos. Por ejemplo, suponga que está creando un <xref:System.Windows.Forms.UserControl> con un botón denominado `MyButton`. Si desea realizar una representación adicional más allá de la proporcionada por el <xref:System.Web.UI.WebControls.Button>, podría agregar código al control de usuario similar al siguiente:  
  
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
>  Controla algunas formas de Windows, como <xref:System.Windows.Forms.TextBox>, se dibuja directamente en Windows. En estos casos, el <xref:System.Windows.Forms.Control.OnPaint%2A> nunca se llama al método y, por tanto, nunca se llamará en el ejemplo anterior.  
  
 Esto crea un método que se ejecuta cada vez que se ejecuta el evento `MyButton.Paint`, agregando por tanto representación gráfica adicional al control. Tenga en cuenta que esto no impide la ejecución de `MyButton.OnPaint` y, por tanto, toda la pintura realizada con un botón se llevará a cabo además en el dibujo personalizado. Para más información acerca de la tecnología GDI+ y de la representación personalizada, consulte [Crear imágenes gráficas con GDI+](../advanced/how-to-create-graphics-objects-for-drawing.md). Si desea obtener una representación única del control, la mejor línea de acción es crear un control heredado y escribir código de representación personalizado para él. Para más información, consulte [Controles dibujados por el usuario](user-drawn-controls.md).  
  
## <a name="see-also"></a>Vea también

- <xref:System.Windows.Forms.UserControl>
- <xref:System.Windows.Forms.Control.OnPaint%2A>
- [Controles dibujados por el usuario](user-drawn-controls.md)
- [Cómo: Crear objetos Graphics para dibujar](../advanced/how-to-create-graphics-objects-for-drawing.md)
- [Variedades de controles personalizados](varieties-of-custom-controls.md)
