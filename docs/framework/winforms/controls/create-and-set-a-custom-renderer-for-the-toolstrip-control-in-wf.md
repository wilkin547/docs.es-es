---
title: Procedimiento para crear y establecer un representador personalizado para el control ToolStrip de formularios Windows Forms
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
ms.openlocfilehash: c354ace3a7d3ce43f549dd1295a85fbee004eb22
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "69929739"
---
# <a name="how-to-create-and-set-a-custom-renderer-for-the-toolstrip-control-in-windows-forms"></a><span data-ttu-id="eb106-102">Procedimiento para crear y establecer un representador personalizado para el control ToolStrip de formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="eb106-102">How to: Create and Set a Custom Renderer for the ToolStrip Control in Windows Forms</span></span>
<span data-ttu-id="eb106-103"><xref:System.Windows.Forms.ToolStrip>los controles proporcionan una compatibilidad sencilla con los temas y estilos.</span><span class="sxs-lookup"><span data-stu-id="eb106-103"><xref:System.Windows.Forms.ToolStrip> controls give easy support to themes and styles.</span></span> <span data-ttu-id="eb106-104">Puede lograr una apariencia y un comportamiento completamente personalizados (aspecto y funcionamiento) estableciendo la <xref:System.Windows.Forms.ToolStrip.Renderer%2A?displayProperty=nameWithType> propiedad o la <xref:System.Windows.Forms.ToolStripManager.Renderer%2A?displayProperty=nameWithType> propiedad en un representador personalizado.</span><span class="sxs-lookup"><span data-stu-id="eb106-104">You can achieve completely custom appearance and behavior (look and feel) by setting either the <xref:System.Windows.Forms.ToolStrip.Renderer%2A?displayProperty=nameWithType> property or the <xref:System.Windows.Forms.ToolStripManager.Renderer%2A?displayProperty=nameWithType> property to a custom renderer.</span></span>  
  
 <span data-ttu-id="eb106-105">Puede asignar representadores a cada control <xref:System.Windows.Forms.ToolStrip>individual <xref:System.Windows.Forms.MenuStrip> <xref:System.Windows.Forms.ContextMenuStrip>,, o <xref:System.Windows.Forms.StatusStrip> , o puede usar la <xref:System.Windows.Forms.ToolStripManager.Renderer%2A> propiedad para afectar a todos los objetos estableciendo la <xref:System.Windows.Forms.ToolStrip.RenderMode%2A?displayProperty=nameWithType> propiedad en <xref:System.Windows.Forms.ToolStripRenderMode.ManagerRenderMode?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="eb106-105">You can assign renderers to each individual <xref:System.Windows.Forms.ToolStrip>, <xref:System.Windows.Forms.MenuStrip>, <xref:System.Windows.Forms.ContextMenuStrip>, or <xref:System.Windows.Forms.StatusStrip> control, or you can use the <xref:System.Windows.Forms.ToolStripManager.Renderer%2A> property to affect all objects by setting the <xref:System.Windows.Forms.ToolStrip.RenderMode%2A?displayProperty=nameWithType> property to <xref:System.Windows.Forms.ToolStripRenderMode.ManagerRenderMode?displayProperty=nameWithType>.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="eb106-106"><xref:System.Windows.Forms.ToolStrip.RenderMode%2A>Devuelve <xref:System.Windows.Forms.ToolStripRenderMode.Custom> solo si el valor de <xref:System.Windows.Forms.ToolStrip.Renderer%2A?displayProperty=nameWithType> no `null`es.</span><span class="sxs-lookup"><span data-stu-id="eb106-106"><xref:System.Windows.Forms.ToolStrip.RenderMode%2A> returns <xref:System.Windows.Forms.ToolStripRenderMode.Custom> only if the value of <xref:System.Windows.Forms.ToolStrip.Renderer%2A?displayProperty=nameWithType> is not `null`.</span></span>  
  
### <a name="to-create-a-custom-renderer"></a><span data-ttu-id="eb106-107">Para crear un representador personalizado</span><span class="sxs-lookup"><span data-stu-id="eb106-107">To create a custom renderer</span></span>  
  
1. <span data-ttu-id="eb106-108">Extienda la <xref:System.Windows.Forms.ToolStripRenderer> clase.</span><span class="sxs-lookup"><span data-stu-id="eb106-108">Extend the <xref:System.Windows.Forms.ToolStripRenderer> class.</span></span>  
  
2. <span data-ttu-id="eb106-109">Implemente la representación personalizada deseada invalidando adecuado *en...*</span><span class="sxs-lookup"><span data-stu-id="eb106-109">Implement desired custom rendering by overriding appropriate *On…*</span></span> <span data-ttu-id="eb106-110">miembros</span><span class="sxs-lookup"><span data-stu-id="eb106-110">members</span></span>  
  
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
  
### <a name="to-set-the-custom-renderer-to-be-the-current-renderer"></a><span data-ttu-id="eb106-111">Para establecer que el representador personalizado sea el representador actual</span><span class="sxs-lookup"><span data-stu-id="eb106-111">To set the custom renderer to be the current renderer</span></span>  
  
1. <span data-ttu-id="eb106-112">Para establecer el representador personalizado para <xref:System.Windows.Forms.ToolStrip>uno, establezca <xref:System.Windows.Forms.ToolStrip.Renderer%2A?displayProperty=nameWithType> la propiedad en el representador personalizado.</span><span class="sxs-lookup"><span data-stu-id="eb106-112">To set the custom renderer for one <xref:System.Windows.Forms.ToolStrip>, set the <xref:System.Windows.Forms.ToolStrip.Renderer%2A?displayProperty=nameWithType> property to the custom renderer.</span></span>  
  
    ```vb  
    toolStrip1.Renderer = New RedTextRenderer()  
    ```  
  
    ```csharp  
    toolStrip1.Renderer = new RedTextRenderer();  
    ```  
  
2. <span data-ttu-id="eb106-113">O bien, para establecer el representador <xref:System.Windows.Forms.ToolStrip> personalizado para todas las clases incluidas en la aplicación: Establezca la <xref:System.Windows.Forms.ToolStripManager.Renderer%2A?displayProperty=nameWithType> propiedad en el representador personalizado y establezca <xref:System.Windows.Forms.ToolStrip.RenderMode%2A> la propiedad <xref:System.Windows.Forms.ToolStripRenderMode.ManagerRenderMode>en.</span><span class="sxs-lookup"><span data-stu-id="eb106-113">Or to set the custom renderer for all <xref:System.Windows.Forms.ToolStrip> classes contained in your application: Set the <xref:System.Windows.Forms.ToolStripManager.Renderer%2A?displayProperty=nameWithType> property to the custom renderer and set the <xref:System.Windows.Forms.ToolStrip.RenderMode%2A> property to <xref:System.Windows.Forms.ToolStripRenderMode.ManagerRenderMode>.</span></span>  
  
    ```vb  
    toolStrip1.RenderMode = ToolStripRenderMode.ManagerRenderMode  
    ToolStripManager.Renderer = New RedTextRenderer()  
    ```  
  
    ```csharp  
    toolStrip1.RenderMode = ToolStripRenderMode.ManagerRenderMode;  
    ToolStripManager.Renderer = new RedTextRenderer();  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="eb106-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="eb106-114">See also</span></span>

- <xref:System.Windows.Forms.ToolStripManager.Renderer%2A>
- <xref:System.Windows.Forms.ToolStripRenderer>
- <xref:System.Windows.Forms.ToolStrip.RenderMode%2A>
- [<span data-ttu-id="eb106-115">Información sobre el control ToolStrip</span><span class="sxs-lookup"><span data-stu-id="eb106-115">ToolStrip Control Overview</span></span>](toolstrip-control-overview-windows-forms.md)
- [<span data-ttu-id="eb106-116">Arquitectura del control ToolStrip</span><span class="sxs-lookup"><span data-stu-id="eb106-116">ToolStrip Control Architecture</span></span>](toolstrip-control-architecture.md)
- [<span data-ttu-id="eb106-117">Resumen de la tecnología ToolStrip</span><span class="sxs-lookup"><span data-stu-id="eb106-117">ToolStrip Technology Summary</span></span>](toolstrip-technology-summary.md)
