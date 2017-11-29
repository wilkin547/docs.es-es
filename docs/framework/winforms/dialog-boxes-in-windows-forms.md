---
title: "Cuadros de diálogo en formularios Windows Forms"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- dialog boxes [Windows Forms], Windows Forms
- Windows Forms dialog boxes
- dialogs [Windows Forms], using in Windows Forms
ms.assetid: d43d022b-451b-490d-9386-dc79d98fbf8a
caps.latest.revision: "13"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 1660bf08f10a7d4e0db4b7ae8d58fd631986974c
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/22/2017
---
# <a name="dialog-boxes-in-windows-forms"></a><span data-ttu-id="73e3b-102">Cuadros de diálogo en formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="73e3b-102">Dialog Boxes in Windows Forms</span></span>
<span data-ttu-id="73e3b-103">Los cuadros de diálogo se usan para interactuar con el usuario y recuperar información.</span><span class="sxs-lookup"><span data-stu-id="73e3b-103">Dialog boxes are used to interact with the user and retrieve information.</span></span> <span data-ttu-id="73e3b-104">En términos sencillos, un cuadro de diálogo es un formulario cuya propiedad de enumeración <xref:System.Windows.Forms.FormBorderStyle> está establecida en `FixedDialog`.</span><span class="sxs-lookup"><span data-stu-id="73e3b-104">In simple terms, a dialog box is a form with its <xref:System.Windows.Forms.FormBorderStyle> enumeration property set to `FixedDialog`.</span></span> <span data-ttu-id="73e3b-105">Puede construir sus propios cuadros de diálogo personalizados con el Diseñador de Windows Forms en [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)].</span><span class="sxs-lookup"><span data-stu-id="73e3b-105">You can construct your own custom dialog boxes by using the Windows Forms Designer in [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)].</span></span> <span data-ttu-id="73e3b-106">Agregue controles como `Label`, `Textbox` y `Button` para personalizar los cuadros de diálogo según sus necesidades específicas.</span><span class="sxs-lookup"><span data-stu-id="73e3b-106">Add controls such as `Label`, `Textbox`, and `Button` to customize dialog boxes to your specific needs.</span></span> <span data-ttu-id="73e3b-107">El [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] también incluye cuadros de diálogo predefinidos, como **abrir archivo** y cuadros de mensaje, que se pueden adaptar para sus propias aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="73e3b-107">The [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] also includes predefined dialog boxes, such as **File Open** and message boxes, which you can adapt for your own applications.</span></span> <span data-ttu-id="73e3b-108">Para obtener más información, consulte [componentes y controles de cuadro de diálogo](../../../docs/framework/winforms/controls/dialog-box-controls-and-components-windows-forms.md).</span><span class="sxs-lookup"><span data-stu-id="73e3b-108">For more information, see [Dialog-Box Controls and Components](../../../docs/framework/winforms/controls/dialog-box-controls-and-components-windows-forms.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="73e3b-109">En esta sección</span><span class="sxs-lookup"><span data-stu-id="73e3b-109">In This Section</span></span>  
 [<span data-ttu-id="73e3b-110">Mostrar cuadros de diálogo de Windows Forms</span><span class="sxs-lookup"><span data-stu-id="73e3b-110">How to: Display Dialog Boxes for Windows Forms</span></span>](../../../docs/framework/winforms/how-to-display-dialog-boxes-for-windows-forms.md)  
 <span data-ttu-id="73e3b-111">Proporciona instrucciones para mostrar cuadros de diálogo.</span><span class="sxs-lookup"><span data-stu-id="73e3b-111">Gives directions for showing dialog boxes.</span></span>  
  
-   <span data-ttu-id="73e3b-112">[Cómo: recuperar información del cuadro de diálogo selectivamente mediante múltiples propiedades](http://msdn.microsoft.com/library/56taefba\(v=vs.110\))</span><span class="sxs-lookup"><span data-stu-id="73e3b-112">[How to: Retrieve Dialog Box Information Selectively Using Multiple Properties](http://msdn.microsoft.com/library/56taefba\(v=vs.110\))</span></span>  
  
-   <span data-ttu-id="73e3b-113">[Cómo: recuperar información del formulario primario de un cuadro de diálogo](http://msdn.microsoft.com/library/k70t19bb\(v=vs.110\))</span><span class="sxs-lookup"><span data-stu-id="73e3b-113">[How to: Retrieve Information from the Parent Form of a Dialog Box](http://msdn.microsoft.com/library/k70t19bb\(v=vs.110\))</span></span>  
  
-   <span data-ttu-id="73e3b-114">[Proporcionados por el usuario a los cuadros de diálogo](http://msdn.microsoft.com/library/1s9ws53w\(v=vs.110\))</span><span class="sxs-lookup"><span data-stu-id="73e3b-114">[User Input to Dialog Boxes](http://msdn.microsoft.com/library/1s9ws53w\(v=vs.110\))</span></span>  
  
-   <span data-ttu-id="73e3b-115">[Cómo: recuperar el resultado para cuadros de diálogo](http://msdn.microsoft.com/library/40x40td1\(v=vs.110\))</span><span class="sxs-lookup"><span data-stu-id="73e3b-115">[How to: Retrieve the Result for Dialog Boxes](http://msdn.microsoft.com/library/40x40td1\(v=vs.110\))</span></span>  
  
-   <span data-ttu-id="73e3b-116">[Tutorial: Recuperar la información del cuadro de diálogo colectivamente mediante objetos](http://msdn.microsoft.com/library/cakx2hdw\(v=vs.110\))</span><span class="sxs-lookup"><span data-stu-id="73e3b-116">[Walkthrough: Retrieving Dialog Box Information Collectively Using Objects](http://msdn.microsoft.com/library/cakx2hdw\(v=vs.110\))</span></span>  
  
-   <span data-ttu-id="73e3b-117">[Cómo: cerrar cuadros de diálogo y conservar proporcionados por el usuario](http://msdn.microsoft.com/library/65ad5907\(v=vs.110\))</span><span class="sxs-lookup"><span data-stu-id="73e3b-117">[How to: Close Dialog Boxes and Retain User Input](http://msdn.microsoft.com/library/65ad5907\(v=vs.110\))</span></span>  
  
-   <span data-ttu-id="73e3b-118">[Cómo: crear cuadros de diálogo en tiempo de diseño](http://msdn.microsoft.com/library/55cz5x2c\(v=vs.110\))</span><span class="sxs-lookup"><span data-stu-id="73e3b-118">[How to: Create Dialog Boxes at Design Time](http://msdn.microsoft.com/library/55cz5x2c\(v=vs.110\))</span></span>  
  
-   <span data-ttu-id="73e3b-119">[Cómo: mostrar cuadros de mensaje](http://msdn.microsoft.com/library/3tt9e94f\(v=vs.110\))</span><span class="sxs-lookup"><span data-stu-id="73e3b-119">[How to: Display Message Boxes](http://msdn.microsoft.com/library/3tt9e94f\(v=vs.110\))</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="73e3b-120">Secciones relacionadas</span><span class="sxs-lookup"><span data-stu-id="73e3b-120">Related Sections</span></span>  
 [<span data-ttu-id="73e3b-121">Controles y componentes de cuadros de diálogo</span><span class="sxs-lookup"><span data-stu-id="73e3b-121">Dialog-Box Controls and Components</span></span>](../../../docs/framework/winforms/controls/dialog-box-controls-and-components-windows-forms.md)  
 <span data-ttu-id="73e3b-122">Enumera los controles de cuadro de diálogo predefinidos.</span><span class="sxs-lookup"><span data-stu-id="73e3b-122">Lists the predefined dialog box controls.</span></span>  
  
 [<span data-ttu-id="73e3b-123">Cambiar la apariencia de Windows Forms</span><span class="sxs-lookup"><span data-stu-id="73e3b-123">Changing the Appearance of Windows Forms</span></span>](../../../docs/framework/winforms/changing-the-appearance-of-windows-forms.md)  
 <span data-ttu-id="73e3b-124">Contiene vínculos a temas que describen cómo cambiar la apariencia de las aplicaciones de Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="73e3b-124">Contains links to topics that describe how to change the appearance of Windows Forms applications.</span></span>  
  
 [<span data-ttu-id="73e3b-125">Información general del control TabControl</span><span class="sxs-lookup"><span data-stu-id="73e3b-125">TabControl Control Overview</span></span>](../../../docs/framework/winforms/controls/tabcontrol-control-overview-windows-forms.md)  
 <span data-ttu-id="73e3b-126">Explica cómo incorporar el control de pestaña en un cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="73e3b-126">Explains how you incorporate the tab control into a dialog box.</span></span>
