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
ms.openlocfilehash: 28ae15165327a1bd72e1099460a2a1e3d337ca48
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54739159"
---
# <a name="constituent-controls"></a><span data-ttu-id="c58ea-102">Controles constituyentes</span><span class="sxs-lookup"><span data-stu-id="c58ea-102">Constituent Controls</span></span>
<span data-ttu-id="c58ea-103">Los controles que componen un control de usuario, o *controles constituyentes* tal como se denominan, son relativamente inflexibles en cuanto a la representación gráfica personalizada.</span><span class="sxs-lookup"><span data-stu-id="c58ea-103">The controls that make up a user control, or *constituent controls* as they are termed, are relatively inflexible when it comes to custom graphics rendering.</span></span> <span data-ttu-id="c58ea-104">Todos los controles de Windows Forms controlan su propia representación a través de sus propios <xref:System.Windows.Forms.Control.OnPaint%2A> método.</span><span class="sxs-lookup"><span data-stu-id="c58ea-104">All Windows Forms controls handle their own rendering through their own <xref:System.Windows.Forms.Control.OnPaint%2A> method.</span></span> <span data-ttu-id="c58ea-105">Como este método está protegido, no es accesible al desarrollador y por tanto no se puede evitar ejecutarlo cuando se dibuja el control.</span><span class="sxs-lookup"><span data-stu-id="c58ea-105">Because this method is protected, it is not accessible to the developer, and thus cannot be prevented from executing when the control is painted.</span></span> <span data-ttu-id="c58ea-106">Sin embargo, esto no significa que no se pueda agregar código que afecte a la apariencia de controles constituyentes.</span><span class="sxs-lookup"><span data-stu-id="c58ea-106">This does not mean, however, that you cannot add code to affect the appearance of constituent controls.</span></span> <span data-ttu-id="c58ea-107">Otras representaciones pueden realizarse mediante la adición de un controlador de eventos.</span><span class="sxs-lookup"><span data-stu-id="c58ea-107">Additional rendering can be accomplished by adding an event handler.</span></span> <span data-ttu-id="c58ea-108">Por ejemplo, suponga que está creando un <xref:System.Windows.Forms.UserControl> con un botón denominado `MyButton`.</span><span class="sxs-lookup"><span data-stu-id="c58ea-108">For example, suppose you were authoring a <xref:System.Windows.Forms.UserControl> with a button named `MyButton`.</span></span> <span data-ttu-id="c58ea-109">Si desea realizar una representación adicional más allá de la proporcionada por el <xref:System.Web.UI.WebControls.Button>, podría agregar código al control de usuario similar al siguiente:</span><span class="sxs-lookup"><span data-stu-id="c58ea-109">If you wished to have additional rendering beyond what was provided by the <xref:System.Web.UI.WebControls.Button>, you would add code to your user control similar to the following:</span></span>  
  
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
>  <span data-ttu-id="c58ea-110">Controla algunas formas de Windows, como <xref:System.Windows.Forms.TextBox>, se dibuja directamente en Windows.</span><span class="sxs-lookup"><span data-stu-id="c58ea-110">Some Windows Forms controls, such as <xref:System.Windows.Forms.TextBox>, are painted directly by Windows.</span></span> <span data-ttu-id="c58ea-111">En estos casos, el <xref:System.Windows.Forms.Control.OnPaint%2A> nunca se llama al método y, por tanto, nunca se llamará en el ejemplo anterior.</span><span class="sxs-lookup"><span data-stu-id="c58ea-111">In these instances, the <xref:System.Windows.Forms.Control.OnPaint%2A> method is never called, and thus the above example will never be called.</span></span>  
  
 <span data-ttu-id="c58ea-112">Esto crea un método que se ejecuta cada vez que se ejecuta el evento `MyButton.Paint`, agregando por tanto representación gráfica adicional al control.</span><span class="sxs-lookup"><span data-stu-id="c58ea-112">This creates a method that executes every time the `MyButton.Paint` event executes, thereby adding additional graphical representation to your control.</span></span> <span data-ttu-id="c58ea-113">Tenga en cuenta que esto no impide la ejecución de `MyButton.OnPaint` y, por tanto, toda la pintura realizada con un botón se llevará a cabo además en el dibujo personalizado.</span><span class="sxs-lookup"><span data-stu-id="c58ea-113">Note that this does not prevent the execution of `MyButton.OnPaint`, and thus all of the painting usually performed by a button will still be performed in addition to your custom painting.</span></span> <span data-ttu-id="c58ea-114">Para más información acerca de la tecnología GDI+ y de la representación personalizada, consulte [Crear imágenes gráficas con GDI+](../../../../docs/framework/winforms/advanced/how-to-create-graphics-objects-for-drawing.md).</span><span class="sxs-lookup"><span data-stu-id="c58ea-114">For details about GDI+ technology and custom rendering, see the [Creating Graphical Images with GDI+](../../../../docs/framework/winforms/advanced/how-to-create-graphics-objects-for-drawing.md).</span></span> <span data-ttu-id="c58ea-115">Si desea obtener una representación única del control, la mejor línea de acción es crear un control heredado y escribir código de representación personalizado para él.</span><span class="sxs-lookup"><span data-stu-id="c58ea-115">If you wish to have a unique representation of your control, your best course of action is to create an inherited control, and to write custom rendering code for it.</span></span> <span data-ttu-id="c58ea-116">Para más información, consulte [Controles dibujados por el usuario](../../../../docs/framework/winforms/controls/user-drawn-controls.md).</span><span class="sxs-lookup"><span data-stu-id="c58ea-116">For details, see [User-Drawn Controls](../../../../docs/framework/winforms/controls/user-drawn-controls.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c58ea-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="c58ea-117">See also</span></span>
- <xref:System.Windows.Forms.UserControl>
- <xref:System.Windows.Forms.Control.OnPaint%2A>
- [<span data-ttu-id="c58ea-118">Controles dibujados por el usuario</span><span class="sxs-lookup"><span data-stu-id="c58ea-118">User-Drawn Controls</span></span>](../../../../docs/framework/winforms/controls/user-drawn-controls.md)
- [<span data-ttu-id="c58ea-119">Cómo: Crear objetos Graphics para dibujar</span><span class="sxs-lookup"><span data-stu-id="c58ea-119">How to: Create Graphics Objects for Drawing</span></span>](../../../../docs/framework/winforms/advanced/how-to-create-graphics-objects-for-drawing.md)
- [<span data-ttu-id="c58ea-120">Variedades de controles personalizados</span><span class="sxs-lookup"><span data-stu-id="c58ea-120">Varieties of Custom Controls</span></span>](../../../../docs/framework/winforms/controls/varieties-of-custom-controls.md)
