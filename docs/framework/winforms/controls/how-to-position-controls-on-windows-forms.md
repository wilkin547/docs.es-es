---
title: 'Cómo: Colocar los controles en formularios Windows Forms'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
f1_keywords:
- Location
- Location.Y
- Location.X
helpviewer_keywords:
- controls [Windows Forms]
- controls [Windows Forms], moving
- snaplines
- controls [Windows Forms], positioning
ms.assetid: 4693977e-34a4-4f19-8221-68c3120c2b2b
author: jillre
ms.author: jillfra
manager: jillfra
ms.openlocfilehash: bb57d14397a4626e01c41dd687dfed7331282a10
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/03/2019
ms.locfileid: "73458329"
---
# <a name="how-to-position-controls-on-windows-forms"></a><span data-ttu-id="13241-102">Cómo: colocar controles en Windows Forms</span><span class="sxs-lookup"><span data-stu-id="13241-102">How to: Position controls on Windows Forms</span></span>

<span data-ttu-id="13241-103">Para colocar controles, use el Diseñador de Windows Forms en Visual Studio o especifique la propiedad <xref:System.Windows.Forms.Control.Location%2A>.</span><span class="sxs-lookup"><span data-stu-id="13241-103">To position controls, use the Windows Forms Designer in Visual Studio or specify the <xref:System.Windows.Forms.Control.Location%2A> property.</span></span>

## <a name="position-a-control-on-the-design-surface-of-the-windows-forms-designer"></a><span data-ttu-id="13241-104">Colocar un control en la superficie de diseño del Diseñador de Windows Forms</span><span class="sxs-lookup"><span data-stu-id="13241-104">Position a control on the design surface of the Windows Forms Designer</span></span>

<span data-ttu-id="13241-105">En Visual Studio, arrastre el control hasta la ubicación adecuada con el mouse.</span><span class="sxs-lookup"><span data-stu-id="13241-105">In Visual Studio, drag the control to the appropriate location with the mouse.</span></span>

> [!NOTE]
> <span data-ttu-id="13241-106">Seleccione el control y muévalo con las teclas de dirección para colocarlo con más precisión.</span><span class="sxs-lookup"><span data-stu-id="13241-106">Select the control and move it with the ARROW keys to position it more precisely.</span></span> <span data-ttu-id="13241-107">Además, las *guías de alineación* le ayudan a colocar controles con precisión en el formulario.</span><span class="sxs-lookup"><span data-stu-id="13241-107">Also, *snaplines* assist you in placing controls precisely on your form.</span></span> <span data-ttu-id="13241-108">Para obtener más información, vea [Tutorial: organizar controles en Windows Forms mediante líneas de ajuste](walkthrough-arranging-controls-on-windows-forms-using-snaplines.md).</span><span class="sxs-lookup"><span data-stu-id="13241-108">For more information, see [Walkthrough: Arranging Controls on Windows Forms Using Snaplines](walkthrough-arranging-controls-on-windows-forms-using-snaplines.md).</span></span>

## <a name="position-a-control-using-the-properties-window"></a><span data-ttu-id="13241-109">Colocar un control mediante el ventana Propiedades</span><span class="sxs-lookup"><span data-stu-id="13241-109">Position a control using the Properties window</span></span>

1. <span data-ttu-id="13241-110">En Visual Studio, seleccione el control que desea colocar.</span><span class="sxs-lookup"><span data-stu-id="13241-110">In Visual Studio, select the control you want to position.</span></span>

2. <span data-ttu-id="13241-111">En la ventana **propiedades** , escriba valores para la propiedad <xref:System.Windows.Forms.Control.Location%2A>, separados por una coma, para colocar el control dentro de su contenedor.</span><span class="sxs-lookup"><span data-stu-id="13241-111">In the **Properties** window, enter values for the <xref:System.Windows.Forms.Control.Location%2A> property, separated by a comma, to position the control within its container.</span></span>

   <span data-ttu-id="13241-112">El primer número (X) es la distancia desde el borde izquierdo del contenedor. el segundo número (Y) es la distancia desde el borde superior del área de contenedor, medido en píxeles.</span><span class="sxs-lookup"><span data-stu-id="13241-112">The first number (X) is the distance from the left border of the container; the second number (Y) is the distance from the upper border of the container area, measured in pixels.</span></span>

   > [!NOTE]
   > <span data-ttu-id="13241-113">Puede expandir la propiedad <xref:System.Windows.Forms.Control.Location%2A> para escribir los valores **X** e **y individualmente** .</span><span class="sxs-lookup"><span data-stu-id="13241-113">You can expand the <xref:System.Windows.Forms.Control.Location%2A> property to type the **X** and **Y** values individually.</span></span>

## <a name="position-a-control-programmatically"></a><span data-ttu-id="13241-114">Colocar un control mediante programación</span><span class="sxs-lookup"><span data-stu-id="13241-114">Position a control programmatically</span></span>

1. <span data-ttu-id="13241-115">Establezca la propiedad <xref:System.Windows.Forms.Control.Location%2A> del control en un <xref:System.Drawing.Point>.</span><span class="sxs-lookup"><span data-stu-id="13241-115">Set the <xref:System.Windows.Forms.Control.Location%2A> property of the control to a <xref:System.Drawing.Point>.</span></span>

    ```vb
    Button1.Location = New Point(100, 100)
    ```

    ```csharp
    button1.Location = new Point(100, 100);
    ```

    ```cpp
    button1->Location = Point(100, 100);
    ```

2. <span data-ttu-id="13241-116">Cambie la coordenada X de la ubicación del control mediante la subpropiedad <xref:System.Windows.Forms.Control.Left%2A>.</span><span class="sxs-lookup"><span data-stu-id="13241-116">Change the X coordinate of the control's location using the <xref:System.Windows.Forms.Control.Left%2A> subproperty.</span></span>

    ```vb
    Button1.Left = 300
    ```

    ```csharp
    button1.Left = 300;
    ```

    ```cpp
    button1->Left = 300;
    ```

## <a name="increment-a-controls-location-programmatically"></a><span data-ttu-id="13241-117">Incrementar la ubicación de un control mediante programación</span><span class="sxs-lookup"><span data-stu-id="13241-117">Increment a control's location programmatically</span></span>

<span data-ttu-id="13241-118">Establezca la subpropiedad <xref:System.Windows.Forms.Control.Left%2A> para incrementar la coordenada X del control.</span><span class="sxs-lookup"><span data-stu-id="13241-118">Set the <xref:System.Windows.Forms.Control.Left%2A> subproperty to increment the X coordinate of the control.</span></span>

```vb
Button1.Left += 200
```

```csharp
button1.Left += 200;
```

```cpp
button1->Left += 200;
```

> [!NOTE]
> <span data-ttu-id="13241-119">Use la propiedad <xref:System.Windows.Forms.Control.Location%2A> para establecer simultáneamente las posiciones X e y de un control.</span><span class="sxs-lookup"><span data-stu-id="13241-119">Use the <xref:System.Windows.Forms.Control.Location%2A> property to set a control's X and Y positions simultaneously.</span></span> <span data-ttu-id="13241-120">Para establecer una posición individualmente, use la subpropiedad <xref:System.Windows.Forms.Control.Left%2A> (**X**) o <xref:System.Windows.Forms.Control.Top%2A> (**Y**) del control.</span><span class="sxs-lookup"><span data-stu-id="13241-120">To set a position individually, use the control's <xref:System.Windows.Forms.Control.Left%2A> (**X**) or <xref:System.Windows.Forms.Control.Top%2A> (**Y**) subproperty.</span></span> <span data-ttu-id="13241-121">No intente establecer implícitamente las coordenadas X e y de la estructura <xref:System.Drawing.Point> que representa la ubicación del botón, porque esta estructura contiene una copia de las coordenadas del botón.</span><span class="sxs-lookup"><span data-stu-id="13241-121">Do not try to implicitly set the X and Y coordinates of the <xref:System.Drawing.Point> structure that represents the button's location, because this structure contains a copy of the button's coordinates.</span></span>

## <a name="see-also"></a><span data-ttu-id="13241-122">Vea también</span><span class="sxs-lookup"><span data-stu-id="13241-122">See also</span></span>

- [<span data-ttu-id="13241-123">Controles de formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="13241-123">Windows Forms Controls</span></span>](index.md)
- [<span data-ttu-id="13241-124">Tutorial: Organizar controles en formularios Windows Forms mediante líneas de ajuste</span><span class="sxs-lookup"><span data-stu-id="13241-124">Walkthrough: Arranging Controls on Windows Forms Using Snaplines</span></span>](walkthrough-arranging-controls-on-windows-forms-using-snaplines.md)
- [<span data-ttu-id="13241-125">Tutorial: Organizar controles en Windows Forms mediante TableLayoutPanel</span><span class="sxs-lookup"><span data-stu-id="13241-125">Walkthrough: Arranging Controls on Windows Forms Using a TableLayoutPanel</span></span>](walkthrough-arranging-controls-on-windows-forms-using-a-tablelayoutpanel.md)
- [<span data-ttu-id="13241-126">Tutorial: Organizar controles en Windows Forms mediante FlowLayoutPanel</span><span class="sxs-lookup"><span data-stu-id="13241-126">Walkthrough: Arranging Controls on Windows Forms Using a FlowLayoutPanel</span></span>](walkthrough-arranging-controls-on-windows-forms-using-a-flowlayoutpanel.md)
- [<span data-ttu-id="13241-127">Asignar etiquetas a controles individuales de formularios Windows Forms y proporcionar accesos directos a los mismos</span><span class="sxs-lookup"><span data-stu-id="13241-127">Labeling Individual Windows Forms Controls and Providing Shortcuts to Them</span></span>](labeling-individual-windows-forms-controls-and-providing-shortcuts-to-them.md)
- [<span data-ttu-id="13241-128">Controles que se utilizan en formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="13241-128">Controls to Use on Windows Forms</span></span>](controls-to-use-on-windows-forms.md)
- [<span data-ttu-id="13241-129">Controles de formularios Windows Forms por función</span><span class="sxs-lookup"><span data-stu-id="13241-129">Windows Forms Controls by Function</span></span>](windows-forms-controls-by-function.md)
- <span data-ttu-id="13241-130">[Cómo: establecer la ubicación de la pantalla de Windows Forms](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/52aha046(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="13241-130">[How to: Set the Screen Location of Windows Forms](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/52aha046(v=vs.100))</span></span>
