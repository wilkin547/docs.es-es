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
ms.openlocfilehash: bd7ce150e4dc0ecfe53f92ec8b557459f1e14e3a
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/28/2019
ms.locfileid: "64651564"
---
# <a name="user-drawn-controls"></a><span data-ttu-id="c7b78-102">Controles dibujados por el usuario</span><span class="sxs-lookup"><span data-stu-id="c7b78-102">User-Drawn Controls</span></span>
<span data-ttu-id="c7b78-103">.NET Framework proporciona la capacidad de desarrollar fácilmente sus propios controles.</span><span class="sxs-lookup"><span data-stu-id="c7b78-103">The .NET Framework provides you with the ability to easily develop your own controls.</span></span> <span data-ttu-id="c7b78-104">Puede crear un control de usuario, que es un conjunto de controles estándares unidos mediante código, o puede diseñar su propio control desde el principio de seguridad.</span><span class="sxs-lookup"><span data-stu-id="c7b78-104">You can create a user control, which is a set of standard controls bound together by code, or you can design your own control from the ground up.</span></span> <span data-ttu-id="c7b78-105">Incluso puede usar la herencia para crear un control que hereda de un control existente y agregar a su funcionalidad inherente.</span><span class="sxs-lookup"><span data-stu-id="c7b78-105">You can even use inheritance to create a control that inherits from an existing control and add to its inherent functionality.</span></span> <span data-ttu-id="c7b78-106">El método que utilice, .NET Framework proporciona la funcionalidad para dibujar una interfaz gráfica personalizada para cualquier control que cree.</span><span class="sxs-lookup"><span data-stu-id="c7b78-106">Whatever approach you use, the .NET Framework provides the functionality to draw a custom graphical interface for any control you create.</span></span>  
  
 <span data-ttu-id="c7b78-107">Representación de un control se realiza mediante la ejecución de código en el control <xref:System.Windows.Forms.Control.OnPaint%2A> método.</span><span class="sxs-lookup"><span data-stu-id="c7b78-107">Painting of a control is accomplished by the execution of code in the control's <xref:System.Windows.Forms.Control.OnPaint%2A> method.</span></span> <span data-ttu-id="c7b78-108">El único argumento de la <xref:System.Windows.Forms.Control.OnPaint%2A> método es un <xref:System.Windows.Forms.PaintEventArgs> objeto que proporciona toda la información y funcionalidad necesarias para representar el control.</span><span class="sxs-lookup"><span data-stu-id="c7b78-108">The single argument of the <xref:System.Windows.Forms.Control.OnPaint%2A> method is a <xref:System.Windows.Forms.PaintEventArgs> object that provides all of the information and functionality required to render your control.</span></span> <span data-ttu-id="c7b78-109">El <xref:System.Windows.Forms.PaintEventArgs> proporciona como propiedades de dos objetos principales que se usará en la representación del control:</span><span class="sxs-lookup"><span data-stu-id="c7b78-109">The <xref:System.Windows.Forms.PaintEventArgs> provides as properties two principal objects that will be used in the rendering of your control:</span></span>  
  
- <span data-ttu-id="c7b78-110"><xref:System.Windows.Forms.PaintEventArgs.ClipRectangle%2A> objeto: el rectángulo que representa la parte del control que se va a dibujar.</span><span class="sxs-lookup"><span data-stu-id="c7b78-110"><xref:System.Windows.Forms.PaintEventArgs.ClipRectangle%2A> object - the rectangle that represents the part of the control that will be drawn.</span></span> <span data-ttu-id="c7b78-111">Puede tratarse de todo el control, o parte del control en función de cómo se dibuja el control.</span><span class="sxs-lookup"><span data-stu-id="c7b78-111">This can be the entire control, or part of the control depending on how the control is drawn.</span></span>  
  
- <span data-ttu-id="c7b78-112"><xref:System.Drawing.Graphics> objeto: encapsula varios objetos orientados a gráficos y los métodos que proporcionan la funcionalidad necesaria para dibujar el control.</span><span class="sxs-lookup"><span data-stu-id="c7b78-112"><xref:System.Drawing.Graphics> object - encapsulates several graphics-oriented objects and methods that provide the functionality necessary to draw your control.</span></span>  
  
 <span data-ttu-id="c7b78-113">Para obtener más información sobre la <xref:System.Drawing.Graphics> objeto y cómo usarlo, vea [Cómo: Crear objetos Graphics para dibujar](../advanced/how-to-create-graphics-objects-for-drawing.md).</span><span class="sxs-lookup"><span data-stu-id="c7b78-113">For more information on the <xref:System.Drawing.Graphics> object and how to use it, see [How to: Create Graphics Objects for Drawing](../advanced/how-to-create-graphics-objects-for-drawing.md).</span></span>  
  
 <span data-ttu-id="c7b78-114">El <xref:System.Windows.Forms.Control.OnPaint%2A> evento se desencadena cada vez que se dibuja el control o se actualiza en la pantalla y el <xref:System.Windows.Forms.PaintEventArgs.ClipRectangle%2A> objeto representa el rectángulo en el que llevará a cabo pintura.</span><span class="sxs-lookup"><span data-stu-id="c7b78-114">The <xref:System.Windows.Forms.Control.OnPaint%2A> event is fired whenever the control is drawn or refreshed on the screen, and the <xref:System.Windows.Forms.PaintEventArgs.ClipRectangle%2A> object represents the rectangle in which painting will take place.</span></span> <span data-ttu-id="c7b78-115">Si el control completo debe actualizarse, la <xref:System.Windows.Forms.PaintEventArgs.ClipRectangle%2A> representará el tamaño de todo el control.</span><span class="sxs-lookup"><span data-stu-id="c7b78-115">If the entire control needs to be refreshed, the <xref:System.Windows.Forms.PaintEventArgs.ClipRectangle%2A> will represent the size of the entire control.</span></span> <span data-ttu-id="c7b78-116">Si solo parte del control debe actualizarse, sin embargo, la <xref:System.Windows.Forms.PaintEventArgs.ClipRectangle%2A> objeto representará únicamente la región que se debe volver a dibujar.</span><span class="sxs-lookup"><span data-stu-id="c7b78-116">If only part of the control needs to be refreshed, however, the <xref:System.Windows.Forms.PaintEventArgs.ClipRectangle%2A> object will represent only the region that needs to be redrawn.</span></span> <span data-ttu-id="c7b78-117">Un ejemplo de este caso sería cuando un control se parcialmente tapado por otro control o formulario en la interfaz de usuario.</span><span class="sxs-lookup"><span data-stu-id="c7b78-117">An example of such a case would be when a control was partially obscured by another control or form in the user interface.</span></span>  
  
 <span data-ttu-id="c7b78-118">Al heredar de la <xref:System.Windows.Forms.Control> (clase), debe invalidar el <xref:System.Windows.Forms.Control.OnPaint%2A> método y proporcionar código de representación de gráficos.</span><span class="sxs-lookup"><span data-stu-id="c7b78-118">When inheriting from the <xref:System.Windows.Forms.Control> class, you must override the <xref:System.Windows.Forms.Control.OnPaint%2A> method and provide graphics-rendering code within.</span></span> <span data-ttu-id="c7b78-119">Si desea proporcionar una interfaz gráfica personalizada a un control de usuario o un control heredado, puede hacerlo mediante la invalidación de la <xref:System.Windows.Forms.Control.OnPaint%2A> método.</span><span class="sxs-lookup"><span data-stu-id="c7b78-119">If you want to provide a custom graphical interface to a user control or an inherited control, you can also do so by overriding the <xref:System.Windows.Forms.Control.OnPaint%2A> method.</span></span> <span data-ttu-id="c7b78-120">A continuación se muestra un ejemplo:</span><span class="sxs-lookup"><span data-stu-id="c7b78-120">An example is shown below:</span></span>  
  
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
  
 <span data-ttu-id="c7b78-121">El ejemplo anterior muestra cómo representar un control con una representación gráfica muy sencilla.</span><span class="sxs-lookup"><span data-stu-id="c7b78-121">The preceding example demonstrates how to render a control with a very simple graphical representation.</span></span> <span data-ttu-id="c7b78-122">Lo llama el <xref:System.Windows.Forms.Control.OnPaint%2A> método de la clase base, crea un <xref:System.Drawing.Pen> objeto con el que se va a dibujar y, por último, dibuja una elipse en el rectángulo determinado por la <xref:System.Windows.Forms.Control.Location%2A> y <xref:System.Windows.Forms.Control.Size%2A> del control.</span><span class="sxs-lookup"><span data-stu-id="c7b78-122">It calls the <xref:System.Windows.Forms.Control.OnPaint%2A> method of the base class, it creates a <xref:System.Drawing.Pen> object with which to draw, and finally draws an ellipse in the rectangle determined by the <xref:System.Windows.Forms.Control.Location%2A> and <xref:System.Windows.Forms.Control.Size%2A> of the control.</span></span> <span data-ttu-id="c7b78-123">Aunque la mayoría del código representación será mucho más complicada de esto, en este ejemplo muestra el uso de la <xref:System.Drawing.Graphics> objeto dentro de la <xref:System.Windows.Forms.PaintEventArgs> objeto.</span><span class="sxs-lookup"><span data-stu-id="c7b78-123">Although most rendering code will be significantly more complicated than this, this example demonstrates the use of the <xref:System.Drawing.Graphics> object contained within the <xref:System.Windows.Forms.PaintEventArgs> object.</span></span> <span data-ttu-id="c7b78-124">Tenga en cuenta que si se hereda de una clase que ya tiene una representación gráfica, como <xref:System.Windows.Forms.UserControl> o <xref:System.Windows.Forms.Button>y no desea incorporar esa representación a la representación, no debe llamar a la clase base <xref:System.Windows.Forms.Control.OnPaint%2A> método.</span><span class="sxs-lookup"><span data-stu-id="c7b78-124">Note that if you are inheriting from a class that already has a graphical representation, such as <xref:System.Windows.Forms.UserControl> or <xref:System.Windows.Forms.Button>, and you do not wish to incorporate that representation into your rendering, you should not call your base class's <xref:System.Windows.Forms.Control.OnPaint%2A> method.</span></span>  
  
 <span data-ttu-id="c7b78-125">El código en el <xref:System.Windows.Forms.Control.OnPaint%2A> método del control se ejecutará cuando el control se dibuja primero, y siempre que se actualice.</span><span class="sxs-lookup"><span data-stu-id="c7b78-125">The code in the <xref:System.Windows.Forms.Control.OnPaint%2A> method of your control will execute when the control is first drawn, and whenever it is refreshed.</span></span> <span data-ttu-id="c7b78-126">Para asegurarse de que se vuelve a dibujar el control cada vez que se cambia el tamaño, agregue la línea siguiente al constructor del control:</span><span class="sxs-lookup"><span data-stu-id="c7b78-126">To ensure that your control is redrawn every time it is resized, add the following line to the constructor of your control:</span></span>  
  
```vb  
SetStyle(ControlStyles.ResizeRedraw, True)  
```  
  
```csharp  
SetStyle(ControlStyles.ResizeRedraw, true);  
```  
  
> [!NOTE]
>  <span data-ttu-id="c7b78-127">Use el <xref:System.Windows.Forms.Control.Region%2A?displayProperty=nameWithType> propiedad para implementar un control no rectangulares.</span><span class="sxs-lookup"><span data-stu-id="c7b78-127">Use the <xref:System.Windows.Forms.Control.Region%2A?displayProperty=nameWithType> property to implement a non-rectangular control.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c7b78-128">Vea también</span><span class="sxs-lookup"><span data-stu-id="c7b78-128">See also</span></span>

- <xref:System.Windows.Forms.Control.Region%2A>
- <xref:System.Windows.Forms.ControlStyles>
- <xref:System.Drawing.Graphics>
- <xref:System.Windows.Forms.Control.OnPaint%2A>
- <xref:System.Windows.Forms.PaintEventArgs>
- [<span data-ttu-id="c7b78-129">Cómo: Crear objetos Graphics para dibujar</span><span class="sxs-lookup"><span data-stu-id="c7b78-129">How to: Create Graphics Objects for Drawing</span></span>](../advanced/how-to-create-graphics-objects-for-drawing.md)
- [<span data-ttu-id="c7b78-130">Controles constituyentes</span><span class="sxs-lookup"><span data-stu-id="c7b78-130">Constituent Controls</span></span>](constituent-controls.md)
- [<span data-ttu-id="c7b78-131">Variedades de controles personalizados</span><span class="sxs-lookup"><span data-stu-id="c7b78-131">Varieties of Custom Controls</span></span>](varieties-of-custom-controls.md)
