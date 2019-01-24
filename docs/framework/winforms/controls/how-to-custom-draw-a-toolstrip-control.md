---
title: Procedimiento Dibujar un Control ToolStrip personalizada
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- toolbars [Windows Forms], custom drawing
- drawing [Windows Forms], owner
- ProfessionalColorTable class [Windows Forms], overriding
- examples [Windows Forms], toolbars
- drawing [Windows Forms], custom
- toolbars [Windows Forms], changing colors
- ToolStrip control [Windows Forms], drawing
- ToolStrip control [Windows Forms], changing colors
- custom drawing
- owner drawing
ms.assetid: 94e7d7bd-a752-441c-b5b3-7acf98881163
ms.openlocfilehash: 6df1f2bf3190fb1453930c0553266cc27234f46d
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54701435"
---
# <a name="how-to-custom-draw-a-toolstrip-control"></a><span data-ttu-id="50e71-102">Procedimiento Dibujar un Control ToolStrip personalizada</span><span class="sxs-lookup"><span data-stu-id="50e71-102">How to: Custom Draw a ToolStrip Control</span></span>
<span data-ttu-id="50e71-103">Los controles <xref:System.Windows.Forms.ToolStrip> tienen las siguientes clases de representación (dibujo) asociadas:</span><span class="sxs-lookup"><span data-stu-id="50e71-103">The <xref:System.Windows.Forms.ToolStrip> controls have the following associated rendering (painting) classes:</span></span>  
  
-   <span data-ttu-id="50e71-104"><xref:System.Windows.Forms.ToolStripSystemRenderer> proporciona la apariencia y el estilo del sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="50e71-104"><xref:System.Windows.Forms.ToolStripSystemRenderer> provides the appearance and style of your operating system.</span></span>  
  
-   <span data-ttu-id="50e71-105"><xref:System.Windows.Forms.ToolStripProfessionalRenderer> proporciona la apariencia y el estilo de Microsoft Office.</span><span class="sxs-lookup"><span data-stu-id="50e71-105"><xref:System.Windows.Forms.ToolStripProfessionalRenderer> provides the appearance and style of Microsoft Office.</span></span>  
  
-   <span data-ttu-id="50e71-106"><xref:System.Windows.Forms.ToolStripRenderer> es la clase base abstracta para las otras dos clases de representación.</span><span class="sxs-lookup"><span data-stu-id="50e71-106"><xref:System.Windows.Forms.ToolStripRenderer> is the abstract base class for the other two rendering classes.</span></span>  
  
 <span data-ttu-id="50e71-107">Para dibujar de forma personalizada un <xref:System.Windows.Forms.ToolStrip> (lo que también se conoce como dibujado por el propietario), puede invalidar una de las clases del representador y cambiar algún aspecto de la lógica de representación.</span><span class="sxs-lookup"><span data-stu-id="50e71-107">To custom draw (also known as owner draw) a <xref:System.Windows.Forms.ToolStrip>, you can override one of the renderer classes and change an aspect of the rendering logic.</span></span>  
  
 <span data-ttu-id="50e71-108">Los procedimientos siguientes describen distintos aspectos del dibujo personalizado.</span><span class="sxs-lookup"><span data-stu-id="50e71-108">The following procedures describe various aspects of custom drawing.</span></span>  
  
### <a name="to-switch-between-the-provided-renderers"></a><span data-ttu-id="50e71-109">Para cambiar entre los representadores proporcionados</span><span class="sxs-lookup"><span data-stu-id="50e71-109">To switch between the provided renderers</span></span>  
  
-   <span data-ttu-id="50e71-110">Establezca la propiedad <xref:System.Windows.Forms.ToolStrip.RenderMode%2A> en el valor <xref:System.Windows.Forms.ToolStripRenderMode> que desee.</span><span class="sxs-lookup"><span data-stu-id="50e71-110">Set the <xref:System.Windows.Forms.ToolStrip.RenderMode%2A> property to the <xref:System.Windows.Forms.ToolStripRenderMode> value you want.</span></span>  
  
     <span data-ttu-id="50e71-111">Con <xref:System.Windows.Forms.ToolStripRenderMode.ManagerRenderMode>, el <xref:System.Windows.Forms.ToolStrip.RenderMode%2A> estático determina el representador de su aplicación.</span><span class="sxs-lookup"><span data-stu-id="50e71-111">With <xref:System.Windows.Forms.ToolStripRenderMode.ManagerRenderMode>, the static <xref:System.Windows.Forms.ToolStrip.RenderMode%2A> determines the renderer for your application.</span></span> <span data-ttu-id="50e71-112">Los demás valores de <xref:System.Windows.Forms.ToolStripRenderMode> son <xref:System.Windows.Forms.ToolStripRenderMode.Custom>, <xref:System.Windows.Forms.ToolStripRenderMode.Professional> y <xref:System.Windows.Forms.ToolStripRenderMode.System>.</span><span class="sxs-lookup"><span data-stu-id="50e71-112">The other values of <xref:System.Windows.Forms.ToolStripRenderMode> are <xref:System.Windows.Forms.ToolStripRenderMode.Custom>, <xref:System.Windows.Forms.ToolStripRenderMode.Professional>, and <xref:System.Windows.Forms.ToolStripRenderMode.System>.</span></span>  
  
### <a name="to-change-the-microsoft-officestyle-borders-to-straight"></a><span data-ttu-id="50e71-113">Para cambiar los bordes de estilo Microsoft Office por rectos</span><span class="sxs-lookup"><span data-stu-id="50e71-113">To change the Microsoft Office–style borders to straight</span></span>  
  
-   <span data-ttu-id="50e71-114">Invalide <xref:System.Windows.Forms.ToolStripProfessionalRenderer.OnRenderToolStripBorder%2A?displayProperty=nameWithType>, pero no llame a la clase base.</span><span class="sxs-lookup"><span data-stu-id="50e71-114">Override <xref:System.Windows.Forms.ToolStripProfessionalRenderer.OnRenderToolStripBorder%2A?displayProperty=nameWithType>, but do not call the base class.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="50e71-115">Hay una versión de este método para <xref:System.Windows.Forms.ToolStripRenderer>, <xref:System.Windows.Forms.ToolStripSystemRenderer> y <xref:System.Windows.Forms.ToolStripProfessionalRenderer>.</span><span class="sxs-lookup"><span data-stu-id="50e71-115">There is a version of this method for <xref:System.Windows.Forms.ToolStripRenderer>, <xref:System.Windows.Forms.ToolStripSystemRenderer>, and <xref:System.Windows.Forms.ToolStripProfessionalRenderer>.</span></span>  
  
### <a name="to-change-the-professionalcolortable"></a><span data-ttu-id="50e71-116">Para cambiar la clase ProfessionalColorTable</span><span class="sxs-lookup"><span data-stu-id="50e71-116">To change the ProfessionalColorTable</span></span>  
  
-   <span data-ttu-id="50e71-117">Invalide <xref:System.Windows.Forms.ProfessionalColorTable> y cambie los colores que desee.</span><span class="sxs-lookup"><span data-stu-id="50e71-117">Override <xref:System.Windows.Forms.ProfessionalColorTable> and change the colors you want.</span></span>  
  
    ```vb  
    Private Sub Form1_Load(ByVal sender As System.Object, ByVal e As _  
    System.EventArgs) Handles Me.Load  
        Dim t As MyColorTable = New MyColorTable  
        ToolStrip1.Renderer = New ToolStripProfessionalRenderer(t)  
    End Sub  
  
    Class MyColorTable   
    Inherits ProfessionalColorTable  
  
    Public Overrides ReadOnly Property ButtonPressedGradientBegin() As Color  
        Get  
            Return Color.Red  
        End Get  
    End Property  
  
    Public Overrides ReadOnly Property ButtonPressedGradientMiddle() _  
    As System.Drawing.Color  
        Get  
            Return Color.Blue  
        End Get  
            End Property  
  
    Public Overrides ReadOnly Property ButtonPressedGradientEnd() _  
    As System.Drawing.Color  
        Get  
            Return Color.Green  
        End Get  
    End Property  
  
    Public Overrides ReadOnly Property ButtonSelectedGradientBegin() _  
    As Color  
        Get  
            Return Color.Yellow  
        End Get  
    End Property  
  
    Public Overrides ReadOnly Property ButtonSelectedGradientMiddle() As System.Drawing.Color  
        Get  
            Return Color.Orange  
        End Get  
    End Property  
  
    Public Overrides ReadOnly Property ButtonSelectedGradientEnd() _  
    As System.Drawing.Color  
        Get  
            Return Color.Violet  
        End Get  
    End Property  
    End Class  
    ```  
  
### <a name="to-change-the-rendering-for-all-toolstrip-controls-in-your-application"></a><span data-ttu-id="50e71-118">Para cambiar la representación de todos los controles ToolStrip de su aplicación</span><span class="sxs-lookup"><span data-stu-id="50e71-118">To change the rendering for all ToolStrip controls in your application</span></span>  
  
1.  <span data-ttu-id="50e71-119">Use la propiedad <xref:System.Windows.Forms.ToolStripManager.RenderMode%2A?displayProperty=nameWithType> para elegir uno de los representadores proporcionados.</span><span class="sxs-lookup"><span data-stu-id="50e71-119">Use the <xref:System.Windows.Forms.ToolStripManager.RenderMode%2A?displayProperty=nameWithType> property to choose one of the provided renderers.</span></span>  
  
2.  <span data-ttu-id="50e71-120">Use <xref:System.Windows.Forms.ToolStripManager.Renderer%2A?displayProperty=nameWithType> para asignar un representador personalizado.</span><span class="sxs-lookup"><span data-stu-id="50e71-120">Use <xref:System.Windows.Forms.ToolStripManager.Renderer%2A?displayProperty=nameWithType> to assign a custom renderer.</span></span>  
  
3.  <span data-ttu-id="50e71-121">Asegúrese de que <xref:System.Windows.Forms.ToolStrip.RenderMode%2A?displayProperty=nameWithType> está establecido en el valor predeterminado de <xref:System.Windows.Forms.ToolStripRenderMode.ManagerRenderMode>.</span><span class="sxs-lookup"><span data-stu-id="50e71-121">Ensure that <xref:System.Windows.Forms.ToolStrip.RenderMode%2A?displayProperty=nameWithType> is set to the default value of <xref:System.Windows.Forms.ToolStripRenderMode.ManagerRenderMode>.</span></span>  
  
### <a name="to-turn-off-the-microsoft-office-colors-for-the-entire-application"></a><span data-ttu-id="50e71-122">Para desactivar los colores de Microsoft Office para toda la aplicación</span><span class="sxs-lookup"><span data-stu-id="50e71-122">To turn off the Microsoft Office colors for the entire application</span></span>  
  
-   <span data-ttu-id="50e71-123">Establezca <xref:System.Windows.Forms.ToolStripManager.VisualStylesEnabled%2A?displayProperty=nameWithType> en `false`.</span><span class="sxs-lookup"><span data-stu-id="50e71-123">Set <xref:System.Windows.Forms.ToolStripManager.VisualStylesEnabled%2A?displayProperty=nameWithType> to `false`.</span></span>  
  
### <a name="to-turn-off-the-microsoft-office-colors-for-one-toolstrip-control"></a><span data-ttu-id="50e71-124">Para desactivar los colores de Microsoft Office para un control ToolStrip</span><span class="sxs-lookup"><span data-stu-id="50e71-124">To turn off the Microsoft Office colors for one ToolStrip control</span></span>  
  
-   <span data-ttu-id="50e71-125">Use código similar al ejemplo de código siguiente.</span><span class="sxs-lookup"><span data-stu-id="50e71-125">Use code similar to the following code example.</span></span>  
  
    ```vb  
    Dim colorTable As ProfessionalColorTable()  
    colorTable.UseSystemColors = True  
    Dim toolStrip.Renderer As ToolStripProfessionalRenderer(colorTable)  
    ```  
  
    ```csharp  
    ProfessionalColorTable colorTable = new ProfessionalColorTable();  
    colorTable.UseSystemColors = true;  
    toolStrip.Renderer = new ToolStripProfessionalRenderer(colorTable);  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="50e71-126">Vea también</span><span class="sxs-lookup"><span data-stu-id="50e71-126">See also</span></span>
- <xref:System.Windows.Forms.ToolStripSystemRenderer>
- <xref:System.Windows.Forms.ToolStripProfessionalRenderer>
- <xref:System.Windows.Forms.ToolStripRenderer>
- [<span data-ttu-id="50e71-127">Controles compatibles con dibujos propietarios integrados</span><span class="sxs-lookup"><span data-stu-id="50e71-127">Controls with Built-In Owner-Drawing Support</span></span>](../../../../docs/framework/winforms/controls/controls-with-built-in-owner-drawing-support.md)
- [<span data-ttu-id="50e71-128">Cómo: Crear y establecer a un representador personalizado para el Control ToolStrip de Windows Forms</span><span class="sxs-lookup"><span data-stu-id="50e71-128">How to: Create and Set a Custom Renderer for the ToolStrip Control in Windows Forms</span></span>](../../../../docs/framework/winforms/controls/create-and-set-a-custom-renderer-for-the-toolstrip-control-in-wf.md)
- [<span data-ttu-id="50e71-129">Información sobre el control ToolStrip</span><span class="sxs-lookup"><span data-stu-id="50e71-129">ToolStrip Control Overview</span></span>](../../../../docs/framework/winforms/controls/toolstrip-control-overview-windows-forms.md)
