---
title: "Cómo: Cargar una imagen mediante el Diseñador (formularios Windows Forms)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- picture formats
- images [Windows Forms], displaying on Windows Forms
- pictures [Windows Forms], displaying
- forms [Windows Forms], displaying images
- PictureBox control [Windows Forms], adding pictures
ms.assetid: 4dc7b973-afb1-4276-8322-20825af96655
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 9ca3e3eef1aa9e7414d3c279de5943585703bf9f
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-load-a-picture-using-the-designer-windows-forms"></a><span data-ttu-id="ecf9f-102">Cómo: Cargar una imagen mediante el Diseñador (formularios Windows Forms)</span><span class="sxs-lookup"><span data-stu-id="ecf9f-102">How to: Load a Picture Using the Designer (Windows Forms)</span></span>
<span data-ttu-id="ecf9f-103">Con los formularios Windows Forms <xref:System.Windows.Forms.PictureBox> (control), puede cargar y mostrar una imagen en un formulario en tiempo de diseño estableciendo la <xref:System.Windows.Forms.PictureBox.Image%2A> propiedad en una imagen válida.</span><span class="sxs-lookup"><span data-stu-id="ecf9f-103">With the Windows Forms <xref:System.Windows.Forms.PictureBox> control, you can load and display a picture on a form at design time by setting the <xref:System.Windows.Forms.PictureBox.Image%2A> property to a valid picture.</span></span> <span data-ttu-id="ecf9f-104">En la tabla siguiente muestra los tipos de archivo aceptables.</span><span class="sxs-lookup"><span data-stu-id="ecf9f-104">The following table shows the acceptable file types.</span></span>  
  
|<span data-ttu-id="ecf9f-105">Tipo</span><span class="sxs-lookup"><span data-stu-id="ecf9f-105">Type</span></span>|<span data-ttu-id="ecf9f-106">Extensión de nombre de archivo</span><span class="sxs-lookup"><span data-stu-id="ecf9f-106">File name extension</span></span>|  
|----------|-------------------------|  
|<span data-ttu-id="ecf9f-107">Bitmap</span><span class="sxs-lookup"><span data-stu-id="ecf9f-107">Bitmap</span></span>|<span data-ttu-id="ecf9f-108">.bmp</span><span class="sxs-lookup"><span data-stu-id="ecf9f-108">.bmp</span></span>|  
|<span data-ttu-id="ecf9f-109">Iconos</span><span class="sxs-lookup"><span data-stu-id="ecf9f-109">Icon</span></span>|<span data-ttu-id="ecf9f-110">.ico</span><span class="sxs-lookup"><span data-stu-id="ecf9f-110">.ico</span></span>|  
|<span data-ttu-id="ecf9f-111">GIF</span><span class="sxs-lookup"><span data-stu-id="ecf9f-111">GIF</span></span>|<span data-ttu-id="ecf9f-112">.gif</span><span class="sxs-lookup"><span data-stu-id="ecf9f-112">.gif</span></span>|  
|<span data-ttu-id="ecf9f-113">Metarchivo</span><span class="sxs-lookup"><span data-stu-id="ecf9f-113">Metafile</span></span>|<span data-ttu-id="ecf9f-114">.wmf</span><span class="sxs-lookup"><span data-stu-id="ecf9f-114">.wmf</span></span>|  
|<span data-ttu-id="ecf9f-115">JPEG</span><span class="sxs-lookup"><span data-stu-id="ecf9f-115">JPEG</span></span>|<span data-ttu-id="ecf9f-116">.jpg</span><span class="sxs-lookup"><span data-stu-id="ecf9f-116">.jpg</span></span>|  
  
> [!NOTE]
>  <span data-ttu-id="ecf9f-117">Los cuadros de diálogo y comandos de menú que se ven pueden diferir de los descritos en la Ayuda, en función de los valores de configuración o de edición activos.</span><span class="sxs-lookup"><span data-stu-id="ecf9f-117">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="ecf9f-118">Para cambiar la configuración, elija la opción **Importar y exportar configuraciones** del menú **Herramientas** .</span><span class="sxs-lookup"><span data-stu-id="ecf9f-118">To change your settings, choose **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="ecf9f-119">Para obtener más información, consulte [Personalizar la configuración de desarrollo en Visual Studio](http://msdn.microsoft.com/en-us/22c4debb-4e31-47a8-8f19-16f328d7dcd3).</span><span class="sxs-lookup"><span data-stu-id="ecf9f-119">For more information, see [Customizing Development Settings in Visual Studio](http://msdn.microsoft.com/en-us/22c4debb-4e31-47a8-8f19-16f328d7dcd3).</span></span>  
  
### <a name="to-display-a-picture-at-design-time"></a><span data-ttu-id="ecf9f-120">Para mostrar una imagen en tiempo de diseño</span><span class="sxs-lookup"><span data-stu-id="ecf9f-120">To display a picture at design time</span></span>  
  
1.  <span data-ttu-id="ecf9f-121">Dibujar un <xref:System.Windows.Forms.PictureBox> control en un formulario.</span><span class="sxs-lookup"><span data-stu-id="ecf9f-121">Draw a <xref:System.Windows.Forms.PictureBox> control on a form.</span></span>  
  
2.  <span data-ttu-id="ecf9f-122">En la ventana Propiedades, seleccione la <xref:System.Windows.Forms.PictureBox.Image%2A> propiedad y, a continuación, haga clic en botón de los puntos suspensivos para mostrar el **abiertos** cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="ecf9f-122">On the Properties window, select the <xref:System.Windows.Forms.PictureBox.Image%2A> property, then click the ellipsis button to display the **Open** dialog box.</span></span>  
  
3.  <span data-ttu-id="ecf9f-123">Si desea obtener un tipo de archivo específico (por ejemplo, archivos .gif), selecciónela en la **archivos de tipo** cuadro.</span><span class="sxs-lookup"><span data-stu-id="ecf9f-123">If you are looking for a specific file type (for example, .gif files), select it in the **Files of type** box.</span></span>  
  
4.  <span data-ttu-id="ecf9f-124">Seleccione el archivo que desea mostrar.</span><span class="sxs-lookup"><span data-stu-id="ecf9f-124">Select the file you want to display.</span></span>  
  
### <a name="to-clear-the-picture-at-design-time"></a><span data-ttu-id="ecf9f-125">Para borrar la imagen en tiempo de diseño</span><span class="sxs-lookup"><span data-stu-id="ecf9f-125">To clear the picture at design time</span></span>  
  
1.  <span data-ttu-id="ecf9f-126">En el **propiedades** ventana, seleccione el <xref:System.Windows.Forms.PictureBox.Image%2A> propiedad y menú contextual de la imagen en miniatura que aparece a la izquierda del nombre del objeto de imagen.</span><span class="sxs-lookup"><span data-stu-id="ecf9f-126">On the **Properties** window, select the <xref:System.Windows.Forms.PictureBox.Image%2A> property and right-click the small thumbnail image that appears to the left of the name of the image object.</span></span> <span data-ttu-id="ecf9f-127">Elija **restablecer**.</span><span class="sxs-lookup"><span data-stu-id="ecf9f-127">Choose **Reset**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ecf9f-128">Vea también</span><span class="sxs-lookup"><span data-stu-id="ecf9f-128">See Also</span></span>  
 <xref:System.Windows.Forms.PictureBox>  
 [<span data-ttu-id="ecf9f-129">Información general del control PictureBox</span><span class="sxs-lookup"><span data-stu-id="ecf9f-129">PictureBox Control Overview</span></span>](../../../../docs/framework/winforms/controls/picturebox-control-overview-windows-forms.md)  
 [<span data-ttu-id="ecf9f-130">Modificar el tamaño o la situación de una imagen en tiempo de ejecución</span><span class="sxs-lookup"><span data-stu-id="ecf9f-130">How to: Modify the Size or Placement of a Picture at Run Time</span></span>](../../../../docs/framework/winforms/controls/how-to-modify-the-size-or-placement-of-a-picture-at-run-time-windows-forms.md)  
 [<span data-ttu-id="ecf9f-131">Establecer imágenes en tiempo de ejecución</span><span class="sxs-lookup"><span data-stu-id="ecf9f-131">How to: Set Pictures at Run Time</span></span>](../../../../docs/framework/winforms/controls/how-to-set-pictures-at-run-time-windows-forms.md)  
 [<span data-ttu-id="ecf9f-132">PictureBox (control)</span><span class="sxs-lookup"><span data-stu-id="ecf9f-132">PictureBox Control</span></span>](../../../../docs/framework/winforms/controls/picturebox-control-windows-forms.md)
