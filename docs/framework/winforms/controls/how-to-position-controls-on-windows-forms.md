---
title: para controles de posición
description: Obtenga información sobre cómo usar el Diseñador de Windows Forms en Visual Studio o la propiedad Location para colocar los controles.
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
ms.openlocfilehash: 0aa3faade71e0f7e0a9d5e676327a80747524b8c
ms.sourcegitcommit: 3824ff187947572b274b9715b60c11269335c181
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/17/2020
ms.locfileid: "84904304"
---
# <a name="how-to-position-controls-on-windows-forms"></a><span data-ttu-id="15911-103">Cómo: colocar controles en Windows Forms</span><span class="sxs-lookup"><span data-stu-id="15911-103">How to: Position controls on Windows Forms</span></span>

<span data-ttu-id="15911-104">Para colocar controles, use el Diseñador de Windows Forms en Visual Studio o especifique la <xref:System.Windows.Forms.Control.Location%2A> propiedad.</span><span class="sxs-lookup"><span data-stu-id="15911-104">To position controls, use the Windows Forms Designer in Visual Studio or specify the <xref:System.Windows.Forms.Control.Location%2A> property.</span></span>

## <a name="position-a-control-on-the-design-surface-of-the-windows-forms-designer"></a><span data-ttu-id="15911-105">Colocar un control en la superficie de diseño del Diseñador de Windows Forms</span><span class="sxs-lookup"><span data-stu-id="15911-105">Position a control on the design surface of the Windows Forms Designer</span></span>

<span data-ttu-id="15911-106">En Visual Studio, arrastre el control hasta la ubicación adecuada con el mouse.</span><span class="sxs-lookup"><span data-stu-id="15911-106">In Visual Studio, drag the control to the appropriate location with the mouse.</span></span>

> [!NOTE]
> <span data-ttu-id="15911-107">Seleccione el control y muévalo con las teclas de dirección para colocarlo con más precisión.</span><span class="sxs-lookup"><span data-stu-id="15911-107">Select the control and move it with the ARROW keys to position it more precisely.</span></span> <span data-ttu-id="15911-108">Además, las *guías de alineación* le ayudan a colocar controles con precisión en el formulario.</span><span class="sxs-lookup"><span data-stu-id="15911-108">Also, *snaplines* assist you in placing controls precisely on your form.</span></span> <span data-ttu-id="15911-109">Para obtener más información, vea [Tutorial: organizar controles en Windows Forms mediante líneas de ajuste](walkthrough-arranging-controls-on-windows-forms-using-snaplines.md).</span><span class="sxs-lookup"><span data-stu-id="15911-109">For more information, see [Walkthrough: Arranging Controls on Windows Forms Using Snaplines](walkthrough-arranging-controls-on-windows-forms-using-snaplines.md).</span></span>

## <a name="position-a-control-using-the-properties-window"></a><span data-ttu-id="15911-110">Colocar un control mediante el ventana Propiedades</span><span class="sxs-lookup"><span data-stu-id="15911-110">Position a control using the Properties window</span></span>

1. <span data-ttu-id="15911-111">En Visual Studio, seleccione el control que desea colocar.</span><span class="sxs-lookup"><span data-stu-id="15911-111">In Visual Studio, select the control you want to position.</span></span>

2. <span data-ttu-id="15911-112">En la ventana **propiedades** , escriba valores para la <xref:System.Windows.Forms.Control.Location%2A> propiedad, separados por una coma, para colocar el control dentro de su contenedor.</span><span class="sxs-lookup"><span data-stu-id="15911-112">In the **Properties** window, enter values for the <xref:System.Windows.Forms.Control.Location%2A> property, separated by a comma, to position the control within its container.</span></span>

   <span data-ttu-id="15911-113">El primer número (X) es la distancia desde el borde izquierdo del contenedor. el segundo número (Y) es la distancia desde el borde superior del área de contenedor, medido en píxeles.</span><span class="sxs-lookup"><span data-stu-id="15911-113">The first number (X) is the distance from the left border of the container; the second number (Y) is the distance from the upper border of the container area, measured in pixels.</span></span>

   > [!NOTE]
   > <span data-ttu-id="15911-114">Puede expandir la <xref:System.Windows.Forms.Control.Location%2A> propiedad para escribir los valores **X** e **y** individualmente.</span><span class="sxs-lookup"><span data-stu-id="15911-114">You can expand the <xref:System.Windows.Forms.Control.Location%2A> property to type the **X** and **Y** values individually.</span></span>

## <a name="position-a-control-programmatically"></a><span data-ttu-id="15911-115">Colocar un control mediante programación</span><span class="sxs-lookup"><span data-stu-id="15911-115">Position a control programmatically</span></span>

1. <span data-ttu-id="15911-116">Establezca la <xref:System.Windows.Forms.Control.Location%2A> propiedad del control en <xref:System.Drawing.Point> .</span><span class="sxs-lookup"><span data-stu-id="15911-116">Set the <xref:System.Windows.Forms.Control.Location%2A> property of the control to a <xref:System.Drawing.Point>.</span></span>

    ```vb
    Button1.Location = New Point(100, 100)
    ```

    ```csharp
    button1.Location = new Point(100, 100);
    ```

    ```cpp
    button1->Location = Point(100, 100);
    ```

2. <span data-ttu-id="15911-117">Cambie la coordenada X de la ubicación del control mediante la <xref:System.Windows.Forms.Control.Left%2A> subpropiedad.</span><span class="sxs-lookup"><span data-stu-id="15911-117">Change the X coordinate of the control's location using the <xref:System.Windows.Forms.Control.Left%2A> subproperty.</span></span>

    ```vb
    Button1.Left = 300
    ```

    ```csharp
    button1.Left = 300;
    ```

    ```cpp
    button1->Left = 300;
    ```

## <a name="increment-a-controls-location-programmatically"></a><span data-ttu-id="15911-118">Incrementar la ubicación de un control mediante programación</span><span class="sxs-lookup"><span data-stu-id="15911-118">Increment a control's location programmatically</span></span>

<span data-ttu-id="15911-119">Establezca la <xref:System.Windows.Forms.Control.Left%2A> subpropiedad para incrementar la coordenada X del control.</span><span class="sxs-lookup"><span data-stu-id="15911-119">Set the <xref:System.Windows.Forms.Control.Left%2A> subproperty to increment the X coordinate of the control.</span></span>

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
> <span data-ttu-id="15911-120">Utilice la <xref:System.Windows.Forms.Control.Location%2A> propiedad para establecer las posiciones X e y de un control simultáneamente.</span><span class="sxs-lookup"><span data-stu-id="15911-120">Use the <xref:System.Windows.Forms.Control.Location%2A> property to set a control's X and Y positions simultaneously.</span></span> <span data-ttu-id="15911-121">Para establecer una posición individualmente, use la <xref:System.Windows.Forms.Control.Left%2A> subpropiedad del control (**X**) o <xref:System.Windows.Forms.Control.Top%2A> (**Y**).</span><span class="sxs-lookup"><span data-stu-id="15911-121">To set a position individually, use the control's <xref:System.Windows.Forms.Control.Left%2A> (**X**) or <xref:System.Windows.Forms.Control.Top%2A> (**Y**) subproperty.</span></span> <span data-ttu-id="15911-122">No intente establecer implícitamente las coordenadas X e y de la <xref:System.Drawing.Point> estructura que representa la ubicación del botón, ya que esta estructura contiene una copia de las coordenadas del botón.</span><span class="sxs-lookup"><span data-stu-id="15911-122">Do not try to implicitly set the X and Y coordinates of the <xref:System.Drawing.Point> structure that represents the button's location, because this structure contains a copy of the button's coordinates.</span></span>

## <a name="see-also"></a><span data-ttu-id="15911-123">Consulte también</span><span class="sxs-lookup"><span data-stu-id="15911-123">See also</span></span>

- [<span data-ttu-id="15911-124">Windows Forms controles</span><span class="sxs-lookup"><span data-stu-id="15911-124">Windows Forms Controls</span></span>](index.md)
- [<span data-ttu-id="15911-125">Tutorial: Organizar controles en formularios Windows Forms mediante líneas de ajuste</span><span class="sxs-lookup"><span data-stu-id="15911-125">Walkthrough: Arranging Controls on Windows Forms Using Snaplines</span></span>](walkthrough-arranging-controls-on-windows-forms-using-snaplines.md)
- [<span data-ttu-id="15911-126">Tutorial: Organizar controles en formularios Windows Forms mediante TableLayoutPanel</span><span class="sxs-lookup"><span data-stu-id="15911-126">Walkthrough: Arranging Controls on Windows Forms Using a TableLayoutPanel</span></span>](walkthrough-arranging-controls-on-windows-forms-using-a-tablelayoutpanel.md)
- [<span data-ttu-id="15911-127">Tutorial: Organizar controles en formularios Windows Forms mediante FlowLayoutPanel</span><span class="sxs-lookup"><span data-stu-id="15911-127">Walkthrough: Arranging Controls on Windows Forms Using a FlowLayoutPanel</span></span>](walkthrough-arranging-controls-on-windows-forms-using-a-flowlayoutpanel.md)
- [<span data-ttu-id="15911-128">Asignar etiquetas a controles individuales de formularios Windows Forms y proporcionar accesos directos a los mismos</span><span class="sxs-lookup"><span data-stu-id="15911-128">Labeling Individual Windows Forms Controls and Providing Shortcuts to Them</span></span>](labeling-individual-windows-forms-controls-and-providing-shortcuts-to-them.md)
- [<span data-ttu-id="15911-129">Controles que se utilizan en formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="15911-129">Controls to Use on Windows Forms</span></span>](controls-to-use-on-windows-forms.md)
- [<span data-ttu-id="15911-130">Controles de formularios Windows Forms por función</span><span class="sxs-lookup"><span data-stu-id="15911-130">Windows Forms Controls by Function</span></span>](windows-forms-controls-by-function.md)
- <span data-ttu-id="15911-131">[Cómo: Establecer la ubicación en pantalla de formularios Windows Forms](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/52aha046(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="15911-131">[How to: Set the Screen Location of Windows Forms](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/52aha046(v=vs.100))</span></span>
