---
title: 'Cómo: Crear y establecer un renderizador personalizado para el ToolStrip Control'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- ToolStrip control [Windows Forms], custom rendering
- toolbars [Windows Forms], rendering
- examples [Windows Forms], toolbars
- ToolStrip control [Windows Forms], rendering
ms.assetid: 88a804ba-679f-4ba3-938a-0dc396199c5b
ms.openlocfilehash: 49db0d785155f19b7220ac64011eaf4253aaa7e9
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79182403"
---
# <a name="how-to-create-and-set-a-custom-renderer-for-the-toolstrip-control-in-windows-forms"></a><span data-ttu-id="5bf69-102">Cómo: Crear y establecer un representador personalizado para el control ToolStrip de formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="5bf69-102">How to: Create and Set a Custom Renderer for the ToolStrip Control in Windows Forms</span></span>
<span data-ttu-id="5bf69-103"><xref:System.Windows.Forms.ToolStrip>los controles dan un fácil apoyo a los temas y estilos.</span><span class="sxs-lookup"><span data-stu-id="5bf69-103"><xref:System.Windows.Forms.ToolStrip> controls give easy support to themes and styles.</span></span> <span data-ttu-id="5bf69-104">Puede lograr una apariencia y un comportamiento completamente personalizados (aspecto y sensación) estableciendo la <xref:System.Windows.Forms.ToolStrip.Renderer%2A?displayProperty=nameWithType> propiedad o la <xref:System.Windows.Forms.ToolStripManager.Renderer%2A?displayProperty=nameWithType> propiedad en un representador personalizado.</span><span class="sxs-lookup"><span data-stu-id="5bf69-104">You can achieve completely custom appearance and behavior (look and feel) by setting either the <xref:System.Windows.Forms.ToolStrip.Renderer%2A?displayProperty=nameWithType> property or the <xref:System.Windows.Forms.ToolStripManager.Renderer%2A?displayProperty=nameWithType> property to a custom renderer.</span></span>  
  
 <span data-ttu-id="5bf69-105">Puede asignar representadores a <xref:System.Windows.Forms.ToolStrip> <xref:System.Windows.Forms.MenuStrip>cada <xref:System.Windows.Forms.ContextMenuStrip>control <xref:System.Windows.Forms.StatusStrip> individual, , , <xref:System.Windows.Forms.ToolStripManager.Renderer%2A> o , o puede <xref:System.Windows.Forms.ToolStrip.RenderMode%2A?displayProperty=nameWithType> utilizar <xref:System.Windows.Forms.ToolStripRenderMode.ManagerRenderMode?displayProperty=nameWithType>la propiedad para afectar a todos los objetos estableciendo la propiedad en .</span><span class="sxs-lookup"><span data-stu-id="5bf69-105">You can assign renderers to each individual <xref:System.Windows.Forms.ToolStrip>, <xref:System.Windows.Forms.MenuStrip>, <xref:System.Windows.Forms.ContextMenuStrip>, or <xref:System.Windows.Forms.StatusStrip> control, or you can use the <xref:System.Windows.Forms.ToolStripManager.Renderer%2A> property to affect all objects by setting the <xref:System.Windows.Forms.ToolStrip.RenderMode%2A?displayProperty=nameWithType> property to <xref:System.Windows.Forms.ToolStripRenderMode.ManagerRenderMode?displayProperty=nameWithType>.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="5bf69-106"><xref:System.Windows.Forms.ToolStrip.RenderMode%2A>devuelve <xref:System.Windows.Forms.ToolStripRenderMode.Custom> solo si <xref:System.Windows.Forms.ToolStrip.Renderer%2A?displayProperty=nameWithType> el `null`valor de no es .</span><span class="sxs-lookup"><span data-stu-id="5bf69-106"><xref:System.Windows.Forms.ToolStrip.RenderMode%2A> returns <xref:System.Windows.Forms.ToolStripRenderMode.Custom> only if the value of <xref:System.Windows.Forms.ToolStrip.Renderer%2A?displayProperty=nameWithType> is not `null`.</span></span>  
  
### <a name="to-create-a-custom-renderer"></a><span data-ttu-id="5bf69-107">Para crear un representador personalizado</span><span class="sxs-lookup"><span data-stu-id="5bf69-107">To create a custom renderer</span></span>  
  
1. <span data-ttu-id="5bf69-108">Amplíe <xref:System.Windows.Forms.ToolStripRenderer> la clase.</span><span class="sxs-lookup"><span data-stu-id="5bf69-108">Extend the <xref:System.Windows.Forms.ToolStripRenderer> class.</span></span>  
  
2. <span data-ttu-id="5bf69-109">Implemente la representación personalizada deseada reemplazando el *on...*</span><span class="sxs-lookup"><span data-stu-id="5bf69-109">Implement desired custom rendering by overriding appropriate *On…*</span></span> <span data-ttu-id="5bf69-110">members</span><span class="sxs-lookup"><span data-stu-id="5bf69-110">members</span></span>  
  
    ```vb  
    Public Class RedTextRenderer  
        Inherits System.Windows.Forms.ToolStripRenderer  
        Protected Overrides Sub OnRenderItemText(ByVal e As _  
            ToolStripItemTextRenderEventArgs)
            e.TextColor = Color.Red  
            e.TextFont = New Font("Helvetica", 7, FontStyle.Bold)  
            MyBase.OnRenderItemText(e)  
        End Sub  
    End Class  
    ```  
  
    ```csharp  
    public class RedTextRenderer : _  
        System.Windows.Forms.ToolStripRenderer  
    {  
        protected override void _  
            OnRenderItemText(ToolStripItemTextRenderEventArgs e)  
        {  
            e.TextColor = Color.Red;  
            e.TextFont = new Font("Helvetica", 7, FontStyle.Bold);  
           base.OnRenderItemText(e);  
        }  
    }  
    ```  
  
### <a name="to-set-the-custom-renderer-to-be-the-current-renderer"></a><span data-ttu-id="5bf69-111">Para establecer el representador personalizado para que sea el representador actual</span><span class="sxs-lookup"><span data-stu-id="5bf69-111">To set the custom renderer to be the current renderer</span></span>  
  
1. <span data-ttu-id="5bf69-112">Para establecer el representador personalizado para uno, <xref:System.Windows.Forms.ToolStrip>establezca la propiedad en <xref:System.Windows.Forms.ToolStrip.Renderer%2A?displayProperty=nameWithType> el representador personalizado.</span><span class="sxs-lookup"><span data-stu-id="5bf69-112">To set the custom renderer for one <xref:System.Windows.Forms.ToolStrip>, set the <xref:System.Windows.Forms.ToolStrip.Renderer%2A?displayProperty=nameWithType> property to the custom renderer.</span></span>  
  
    ```vb  
    toolStrip1.Renderer = New RedTextRenderer()  
    ```  
  
    ```csharp  
    toolStrip1.Renderer = new RedTextRenderer();  
    ```  
  
2. <span data-ttu-id="5bf69-113">O bien, para establecer <xref:System.Windows.Forms.ToolStrip> el representador personalizado para <xref:System.Windows.Forms.ToolStripManager.Renderer%2A?displayProperty=nameWithType> todas las clases <xref:System.Windows.Forms.ToolStrip.RenderMode%2A> contenidas <xref:System.Windows.Forms.ToolStripRenderMode.ManagerRenderMode>en la aplicación: establezca la propiedad en el representador personalizado y establezca la propiedad en .</span><span class="sxs-lookup"><span data-stu-id="5bf69-113">Or to set the custom renderer for all <xref:System.Windows.Forms.ToolStrip> classes contained in your application: Set the <xref:System.Windows.Forms.ToolStripManager.Renderer%2A?displayProperty=nameWithType> property to the custom renderer and set the <xref:System.Windows.Forms.ToolStrip.RenderMode%2A> property to <xref:System.Windows.Forms.ToolStripRenderMode.ManagerRenderMode>.</span></span>  
  
    ```vb  
    toolStrip1.RenderMode = ToolStripRenderMode.ManagerRenderMode  
    ToolStripManager.Renderer = New RedTextRenderer()  
    ```  
  
    ```csharp  
    toolStrip1.RenderMode = ToolStripRenderMode.ManagerRenderMode;  
    ToolStripManager.Renderer = new RedTextRenderer();  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="5bf69-114">Consulte también</span><span class="sxs-lookup"><span data-stu-id="5bf69-114">See also</span></span>

- <xref:System.Windows.Forms.ToolStripManager.Renderer%2A>
- <xref:System.Windows.Forms.ToolStripRenderer>
- <xref:System.Windows.Forms.ToolStrip.RenderMode%2A>
- [<span data-ttu-id="5bf69-115">Información sobre el control ToolStrip</span><span class="sxs-lookup"><span data-stu-id="5bf69-115">ToolStrip Control Overview</span></span>](toolstrip-control-overview-windows-forms.md)
- [<span data-ttu-id="5bf69-116">Arquitectura del control ToolStrip</span><span class="sxs-lookup"><span data-stu-id="5bf69-116">ToolStrip Control Architecture</span></span>](toolstrip-control-architecture.md)
- [<span data-ttu-id="5bf69-117">Resumen de la tecnología ToolStrip</span><span class="sxs-lookup"><span data-stu-id="5bf69-117">ToolStrip Technology Summary</span></span>](toolstrip-technology-summary.md)
