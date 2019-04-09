---
title: Filtrar para colocar controles en formularios Windows Forms
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
ms.openlocfilehash: 22225c97ec082022cb609e47d3cafcdcc052143d
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59132800"
---
# <a name="how-to-position-controls-on-windows-forms"></a><span data-ttu-id="0518b-102">Filtrar para colocar controles en formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="0518b-102">How to: Position Controls on Windows Forms</span></span>
<span data-ttu-id="0518b-103">Para colocar los controles, utilizar el Diseñador de Windows Forms o especifique el <xref:System.Windows.Forms.Control.Location%2A> propiedad.</span><span class="sxs-lookup"><span data-stu-id="0518b-103">To position controls, use the Windows Forms Designer, or specify the <xref:System.Windows.Forms.Control.Location%2A> property.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="0518b-104">Los cuadros de diálogo y comandos de menú que se ven pueden diferir de los descritos en la Ayuda, en función de los valores de configuración o de edición activos.</span><span class="sxs-lookup"><span data-stu-id="0518b-104">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="0518b-105">Para cambiar la configuración, elija la opción **Importar y exportar configuraciones** del menú **Herramientas** .</span><span class="sxs-lookup"><span data-stu-id="0518b-105">To change your settings, choose **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="0518b-106">Para más información, vea [Personalizar el IDE de Visual Studio](/visualstudio/ide/personalizing-the-visual-studio-ide).</span><span class="sxs-lookup"><span data-stu-id="0518b-106">For more information, see [Personalize the Visual Studio IDE](/visualstudio/ide/personalizing-the-visual-studio-ide).</span></span>  
  
### <a name="to-position-a-control-on-the-design-surface-of-the-windows-forms-designer"></a><span data-ttu-id="0518b-107">Para colocar un control en la superficie de diseño del Diseñador de Windows Forms</span><span class="sxs-lookup"><span data-stu-id="0518b-107">To position a control on the design surface of the Windows Forms Designer</span></span>  
  
-   <span data-ttu-id="0518b-108">Arrastre el control a la ubicación adecuada con el mouse.</span><span class="sxs-lookup"><span data-stu-id="0518b-108">Drag the control to the appropriate location with the mouse.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="0518b-109">Seleccione el control y muévalo teclas con la flecha para colocarlo con más precisión.</span><span class="sxs-lookup"><span data-stu-id="0518b-109">Select the control and move it with the ARROW keys to position it more precisely.</span></span> <span data-ttu-id="0518b-110">Además, *las guías de alineación* le ayudarán a colocar controles en el formulario con precisión.</span><span class="sxs-lookup"><span data-stu-id="0518b-110">Also, *snaplines* assist you in placing controls precisely on your form.</span></span> <span data-ttu-id="0518b-111">Para obtener más información, vea [Tutorial: Organizar controles en Windows Forms mediante líneas de ajuste](walkthrough-arranging-controls-on-windows-forms-using-snaplines.md).</span><span class="sxs-lookup"><span data-stu-id="0518b-111">For more information, see [Walkthrough: Arranging Controls on Windows Forms Using Snaplines](walkthrough-arranging-controls-on-windows-forms-using-snaplines.md).</span></span>  
  
### <a name="to-position-a-control-using-the-properties-window"></a><span data-ttu-id="0518b-112">Para colocar un control mediante la ventana Propiedades</span><span class="sxs-lookup"><span data-stu-id="0518b-112">To position a control using the Properties window</span></span>  
  
1.  <span data-ttu-id="0518b-113">Haga clic en el control que desea colocar.</span><span class="sxs-lookup"><span data-stu-id="0518b-113">Click the control you want to position.</span></span>  
  
2.  <span data-ttu-id="0518b-114">En el **propiedades** ventana, escriba valores para el <xref:System.Windows.Forms.Control.Location%2A> propiedad, separados por comas, para colocar el control dentro de su contenedor.</span><span class="sxs-lookup"><span data-stu-id="0518b-114">In the **Properties** window, type values for the <xref:System.Windows.Forms.Control.Location%2A> property, separated by a comma, to position the control within its container.</span></span>  
  
     <span data-ttu-id="0518b-115">El primer número (X) es la distancia desde el borde izquierdo del contenedor; el segundo número (Y) es la distancia desde el borde superior del área de contenedor, medido en píxeles.</span><span class="sxs-lookup"><span data-stu-id="0518b-115">The first number (X) is the distance from the left border of the container; the second number (Y) is the distance from the upper border of the container area, measured in pixels.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="0518b-116">Puede expandir el <xref:System.Windows.Forms.Control.Location%2A> propiedad al tipo el **X** y **Y** valores individualmente.</span><span class="sxs-lookup"><span data-stu-id="0518b-116">You can expand the <xref:System.Windows.Forms.Control.Location%2A> property to type the **X** and **Y** values individually.</span></span>  
  
### <a name="to-position-a-control-programmatically"></a><span data-ttu-id="0518b-117">Para colocar un control mediante programación</span><span class="sxs-lookup"><span data-stu-id="0518b-117">To position a control programmatically</span></span>  
  
1.  <span data-ttu-id="0518b-118">Establecer el <xref:System.Windows.Forms.Control.Location%2A> propiedad del control a un <xref:System.Drawing.Point>.</span><span class="sxs-lookup"><span data-stu-id="0518b-118">Set the <xref:System.Windows.Forms.Control.Location%2A> property of the control to a <xref:System.Drawing.Point>.</span></span>  
  
    ```vb  
    Button1.Location = New Point(100, 100)  
    ```  
  
    ```csharp  
    button1.Location = new Point(100, 100);  
    ```  
  
    ```cpp  
    button1->Location = Point(100, 100);  
    ```  
  
2.  <span data-ttu-id="0518b-119">Cambie la coordenada X de la ubicación del control mediante la <xref:System.Windows.Forms.Control.Left%2A> subpropiedades.</span><span class="sxs-lookup"><span data-stu-id="0518b-119">Change the X coordinate of the control's location using the <xref:System.Windows.Forms.Control.Left%2A> subproperty.</span></span>  
  
    ```vb  
    Button1.Left = 300  
    ```  
  
    ```csharp  
    button1.Left = 300;  
    ```  
  
    ```cpp  
    button1->Left = 300;  
    ```  
  
### <a name="to-increment-a-controls-location-programmatically"></a><span data-ttu-id="0518b-120">Para incrementar la ubicación de un control mediante programación</span><span class="sxs-lookup"><span data-stu-id="0518b-120">To increment a control's location programmatically</span></span>  
  
1.  <span data-ttu-id="0518b-121">Establecer el <xref:System.Windows.Forms.Control.Left%2A> subpropiedad para incrementar la coordenada X del control.</span><span class="sxs-lookup"><span data-stu-id="0518b-121">Set the <xref:System.Windows.Forms.Control.Left%2A> subproperty to increment the X coordinate of the control.</span></span>  
  
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
    >  <span data-ttu-id="0518b-122">Use el <xref:System.Windows.Forms.Control.Location%2A> propiedad para establecer un control X e Y se coloca al mismo tiempo.</span><span class="sxs-lookup"><span data-stu-id="0518b-122">Use the <xref:System.Windows.Forms.Control.Location%2A> property to set a control's X and Y positions simultaneously.</span></span> <span data-ttu-id="0518b-123">Para establecer una posición individualmente, utilice el control <xref:System.Windows.Forms.Control.Left%2A> (**X**) o <xref:System.Windows.Forms.Control.Top%2A> (**Y**) subpropiedades.</span><span class="sxs-lookup"><span data-stu-id="0518b-123">To set a position individually, use the control's <xref:System.Windows.Forms.Control.Left%2A> (**X**) or <xref:System.Windows.Forms.Control.Top%2A> (**Y**) subproperty.</span></span> <span data-ttu-id="0518b-124">No intente establecer implícitamente las coordenadas X e Y de la <xref:System.Drawing.Point> estructura que representa la ubicación del botón, porque esta estructura contiene una copia de las coordenadas del botón.</span><span class="sxs-lookup"><span data-stu-id="0518b-124">Do not try to implicitly set the X and Y coordinates of the <xref:System.Drawing.Point> structure that represents the button's location, because this structure contains a copy of the button's coordinates.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0518b-125">Vea también</span><span class="sxs-lookup"><span data-stu-id="0518b-125">See also</span></span>

- [<span data-ttu-id="0518b-126">Controles de Windows Forms</span><span class="sxs-lookup"><span data-stu-id="0518b-126">Windows Forms Controls</span></span>](index.md)
- [<span data-ttu-id="0518b-127">Tutorial: Organizar controles en formularios Windows Forms mediante guías de alineación</span><span class="sxs-lookup"><span data-stu-id="0518b-127">Walkthrough: Arranging Controls on Windows Forms Using Snaplines</span></span>](walkthrough-arranging-controls-on-windows-forms-using-snaplines.md)
- [<span data-ttu-id="0518b-128">Tutorial: Organizar controles en formularios Windows Forms mediante TableLayoutPanel</span><span class="sxs-lookup"><span data-stu-id="0518b-128">Walkthrough: Arranging Controls on Windows Forms Using a TableLayoutPanel</span></span>](walkthrough-arranging-controls-on-windows-forms-using-a-tablelayoutpanel.md)
- [<span data-ttu-id="0518b-129">Tutorial: Organizar controles en formularios Windows Forms mediante FlowLayoutPanel</span><span class="sxs-lookup"><span data-stu-id="0518b-129">Walkthrough: Arranging Controls on Windows Forms Using a FlowLayoutPanel</span></span>](walkthrough-arranging-controls-on-windows-forms-using-a-flowlayoutpanel.md)
- [<span data-ttu-id="0518b-130">Organizar controles en formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="0518b-130">Arranging Controls on Windows Forms</span></span>](arranging-controls-on-windows-forms.md)
- [<span data-ttu-id="0518b-131">Asignar etiquetas a controles individuales de formularios Windows Forms y proporcionar accesos directos a los mismos</span><span class="sxs-lookup"><span data-stu-id="0518b-131">Labeling Individual Windows Forms Controls and Providing Shortcuts to Them</span></span>](labeling-individual-windows-forms-controls-and-providing-shortcuts-to-them.md)
- [<span data-ttu-id="0518b-132">Controles que se utilizan en formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="0518b-132">Controls to Use on Windows Forms</span></span>](controls-to-use-on-windows-forms.md)
- [<span data-ttu-id="0518b-133">Controles de formularios Windows Forms por función</span><span class="sxs-lookup"><span data-stu-id="0518b-133">Windows Forms Controls by Function</span></span>](windows-forms-controls-by-function.md)
- [<span data-ttu-id="0518b-134">Filtrar Establecer la ubicación de pantalla de Windows Forms</span><span class="sxs-lookup"><span data-stu-id="0518b-134">How to: Set the Screen Location of Windows Forms</span></span>](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/52aha046(v=vs.100))
