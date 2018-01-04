---
title: "Cómo: Cambiar la apariencia del texto y las imágenes de ToolStrip en formularios Windows Forms"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- ToolStrip control [Windows Forms], appearance
- toolbars [Windows Forms], images
- examples [Windows Forms], toolbars
- toolbars [Windows Forms], appearance
- ToolStrip control [Windows Forms], images
- ToolStrip control [Windows Forms], text
- toolbars [Windows Forms], text
ms.assetid: d62dc9d1-2edd-4dfa-aed7-1335d6e13d86
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: fe88ff8d31a83b8516b11cd9aadd4bc2d4bf99a9
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-change-the-appearance-of-toolstrip-text-and-images-in-windows-forms"></a><span data-ttu-id="15d7f-102">Cómo: Cambiar la apariencia del texto y las imágenes de ToolStrip en formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="15d7f-102">How to: Change the Appearance of ToolStrip Text and Images in Windows Forms</span></span>
<span data-ttu-id="15d7f-103">Puede controlar si el texto y las imágenes se muestran en un <xref:System.Windows.Forms.ToolStripItem> y cómo se alinean entre sí y la <xref:System.Windows.Forms.ToolStrip>.</span><span class="sxs-lookup"><span data-stu-id="15d7f-103">You can control whether text and images are displayed on a <xref:System.Windows.Forms.ToolStripItem> and how they are aligned relative to each other and the <xref:System.Windows.Forms.ToolStrip>.</span></span>  
  
### <a name="to-define-what-is-displayed-on-a-toolstripitem"></a><span data-ttu-id="15d7f-104">Para definir lo que se muestra en un elemento ToolStripItem</span><span class="sxs-lookup"><span data-stu-id="15d7f-104">To define what is displayed on a ToolStripItem</span></span>  
  
-   <span data-ttu-id="15d7f-105">Establecer el <xref:System.Windows.Forms.ToolStripItem.DisplayStyle%2A> en el valor deseado.</span><span class="sxs-lookup"><span data-stu-id="15d7f-105">Set the <xref:System.Windows.Forms.ToolStripItem.DisplayStyle%2A> property to the desired value.</span></span> <span data-ttu-id="15d7f-106">Las posibilidades son `Image`, `ImageAndText`, `None`, y `Text`.</span><span class="sxs-lookup"><span data-stu-id="15d7f-106">The possibilities are `Image`, `ImageAndText`, `None`, and `Text`.</span></span> <span data-ttu-id="15d7f-107">De manera predeterminada, es `ImageAndText`.</span><span class="sxs-lookup"><span data-stu-id="15d7f-107">The default is `ImageAndText`.</span></span>  
  
    ```vb  
    ToolStripButton2.DisplayStyle = _  
        System.Windows.Forms.ToolStripItemDisplayStyle.Image  
    ```  
  
    ```csharp  
    toolStripButton2.DisplayStyle = System.Windows.Forms.ToolStripItemDisplayStyle.Image;  
    ```  
  
### <a name="to-align-text-on-a-toolstripitem"></a><span data-ttu-id="15d7f-108">Para alinear el texto en un elemento ToolStripItem</span><span class="sxs-lookup"><span data-stu-id="15d7f-108">To align text on a ToolStripItem</span></span>  
  
-   <span data-ttu-id="15d7f-109">Establecer el <xref:System.Windows.Forms.ToolStripItem.TextAlign%2A> en el valor deseado.</span><span class="sxs-lookup"><span data-stu-id="15d7f-109">Set the <xref:System.Windows.Forms.ToolStripItem.TextAlign%2A> property to the desired value.</span></span> <span data-ttu-id="15d7f-110">Las posibilidades son cualquier combinación de parte superior, medio e inferior con izquierda, centro y derecha.</span><span class="sxs-lookup"><span data-stu-id="15d7f-110">The possibilities are any combination of top, middle, and bottom with left, center, and right.</span></span> <span data-ttu-id="15d7f-111">De manera predeterminada, es `MiddleCenter`.</span><span class="sxs-lookup"><span data-stu-id="15d7f-111">The default is `MiddleCenter`.</span></span>  
  
    ```vb  
    ToolStripSplitButton1.TextAlign = _  
        System.Drawing.ContentAlignment.MiddleRight  
    ```  
  
    ```csharp  
    toolStripSplitButton1.TextAlign = System.Drawing.ContentAlignment.MiddleRight;  
    ```  
  
### <a name="to-align-an-image-on-a-toolstripitem"></a><span data-ttu-id="15d7f-112">Para alinear una imagen en un elemento ToolStripItem</span><span class="sxs-lookup"><span data-stu-id="15d7f-112">To align an image on a ToolStripItem</span></span>  
  
-   <span data-ttu-id="15d7f-113">Establecer el <xref:System.Windows.Forms.ToolStripItem.ImageAlign%2A> en el valor deseado.</span><span class="sxs-lookup"><span data-stu-id="15d7f-113">Set the <xref:System.Windows.Forms.ToolStripItem.ImageAlign%2A> property to the desired value.</span></span> <span data-ttu-id="15d7f-114">Las posibilidades son cualquier combinación de parte superior, medio e inferior con izquierda, centro y derecha.</span><span class="sxs-lookup"><span data-stu-id="15d7f-114">The possibilities are any combination of top, middle, and bottom with left, center, and right.</span></span> <span data-ttu-id="15d7f-115">De manera predeterminada, es `MiddleLeft`.</span><span class="sxs-lookup"><span data-stu-id="15d7f-115">The default is `MiddleLeft`.</span></span>  
  
    ```vb  
    ToolStripSplitButton1.ImageAlign = _  
        System.Drawing.ContentAlignment.MiddleRight  
    ```  
  
    ```csharp  
    toolStripSplitButton1.ImageAlign = System.Drawing.ContentAlignment.MiddleRight;  
    ```  
  
### <a name="to-define-how-toolstripitem-text-and-images-are-displayed-relative-to-each-other"></a><span data-ttu-id="15d7f-116">Para definir cómo se muestran imágenes y texto de ToolStripItem relacionados entre sí</span><span class="sxs-lookup"><span data-stu-id="15d7f-116">To define how ToolStripItem text and images are displayed relative to each other</span></span>  
  
-   <span data-ttu-id="15d7f-117">Establecer el <xref:System.Windows.Forms.ToolStripItem.TextImageRelation%2A> en el valor deseado.</span><span class="sxs-lookup"><span data-stu-id="15d7f-117">Set the <xref:System.Windows.Forms.ToolStripItem.TextImageRelation%2A> property to the desired value.</span></span> <span data-ttu-id="15d7f-118">Las posibilidades son `ImageAboveText`, `ImageBeforeText`, `Overlay`, `TextAboveImage`, y `TextBeforeImage`.</span><span class="sxs-lookup"><span data-stu-id="15d7f-118">The possibilities are `ImageAboveText`, `ImageBeforeText`, `Overlay`, `TextAboveImage`, and `TextBeforeImage`.</span></span> <span data-ttu-id="15d7f-119">De manera predeterminada, es `ImageBeforeText`.</span><span class="sxs-lookup"><span data-stu-id="15d7f-119">The default is `ImageBeforeText`.</span></span>  
  
    ```vb  
    ToolStripButton1.TextImageRelation = _  
        System.Windows.Forms.TextImageRelation.ImageAboveText  
    ```  
  
    ```csharp  
    toolStripButton1.TextImageRelation = System.Windows.Forms.TextImageRelation.ImageAboveText;  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="15d7f-120">Vea también</span><span class="sxs-lookup"><span data-stu-id="15d7f-120">See Also</span></span>  
 <xref:System.Windows.Forms.ToolStrip>  
 [<span data-ttu-id="15d7f-121">Información sobre el control ToolStrip</span><span class="sxs-lookup"><span data-stu-id="15d7f-121">ToolStrip Control Overview</span></span>](../../../../docs/framework/winforms/controls/toolstrip-control-overview-windows-forms.md)  
 [<span data-ttu-id="15d7f-122">Arquitectura del control ToolStrip</span><span class="sxs-lookup"><span data-stu-id="15d7f-122">ToolStrip Control Architecture</span></span>](../../../../docs/framework/winforms/controls/toolstrip-control-architecture.md)  
 [<span data-ttu-id="15d7f-123">Resumen de la tecnología ToolStrip</span><span class="sxs-lookup"><span data-stu-id="15d7f-123">ToolStrip Technology Summary</span></span>](../../../../docs/framework/winforms/controls/toolstrip-technology-summary.md)
