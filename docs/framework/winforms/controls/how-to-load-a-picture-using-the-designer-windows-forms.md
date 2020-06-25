---
title: Procedimiento para cargar una imagen mediante el diseñador
description: Aprenda a usar el control Windows Forms PictureBox para cargar y mostrar una imagen en un formulario en tiempo de diseño.
ms.date: 03/30/2017
helpviewer_keywords:
- picture formats
- images [Windows Forms], displaying on Windows Forms
- pictures [Windows Forms], displaying
- forms [Windows Forms], displaying images
- PictureBox control [Windows Forms], adding pictures
ms.assetid: 4dc7b973-afb1-4276-8322-20825af96655
ms.openlocfilehash: a05ffe19412fc7a4e3e02f01336d89cce39fac8a
ms.sourcegitcommit: dc2feef0794cf41dbac1451a13b8183258566c0e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/24/2020
ms.locfileid: "85325601"
---
# <a name="how-to-load-a-picture-using-the-designer-windows-forms"></a><span data-ttu-id="dc93f-103">Cómo: Cargar una imagen mediante el Diseñador (formularios Windows Forms)</span><span class="sxs-lookup"><span data-stu-id="dc93f-103">How to: Load a Picture Using the Designer (Windows Forms)</span></span>

<span data-ttu-id="dc93f-104">Con el <xref:System.Windows.Forms.PictureBox> control Windows Forms, puede cargar y mostrar una imagen en un formulario en tiempo de diseño si establece la <xref:System.Windows.Forms.PictureBox.Image%2A> propiedad en una imagen válida.</span><span class="sxs-lookup"><span data-stu-id="dc93f-104">With the Windows Forms <xref:System.Windows.Forms.PictureBox> control, you can load and display a picture on a form at design time by setting the <xref:System.Windows.Forms.PictureBox.Image%2A> property to a valid picture.</span></span> <span data-ttu-id="dc93f-105">En la tabla siguiente se muestran los tipos de archivo aceptables.</span><span class="sxs-lookup"><span data-stu-id="dc93f-105">The following table shows the acceptable file types.</span></span>

|<span data-ttu-id="dc93f-106">Tipo</span><span class="sxs-lookup"><span data-stu-id="dc93f-106">Type</span></span>|<span data-ttu-id="dc93f-107">Extensión de nombre de archivo</span><span class="sxs-lookup"><span data-stu-id="dc93f-107">File name extension</span></span>|
|---|---|
|<span data-ttu-id="dc93f-108">Bitmap</span><span class="sxs-lookup"><span data-stu-id="dc93f-108">Bitmap</span></span>|<span data-ttu-id="dc93f-109">.bmp</span><span class="sxs-lookup"><span data-stu-id="dc93f-109">.bmp</span></span>|
|<span data-ttu-id="dc93f-110">Icon</span><span class="sxs-lookup"><span data-stu-id="dc93f-110">Icon</span></span>|<span data-ttu-id="dc93f-111">.ico</span><span class="sxs-lookup"><span data-stu-id="dc93f-111">.ico</span></span>|
|<span data-ttu-id="dc93f-112">GIF</span><span class="sxs-lookup"><span data-stu-id="dc93f-112">GIF</span></span>|<span data-ttu-id="dc93f-113">.gif</span><span class="sxs-lookup"><span data-stu-id="dc93f-113">.gif</span></span>|
|<span data-ttu-id="dc93f-114">Metarchivo de </span><span class="sxs-lookup"><span data-stu-id="dc93f-114">Metafile</span></span>|<span data-ttu-id="dc93f-115">.wmf</span><span class="sxs-lookup"><span data-stu-id="dc93f-115">.wmf</span></span>|
|<span data-ttu-id="dc93f-116">JPEG</span><span class="sxs-lookup"><span data-stu-id="dc93f-116">JPEG</span></span>|<span data-ttu-id="dc93f-117">.jpg</span><span class="sxs-lookup"><span data-stu-id="dc93f-117">.jpg</span></span>|

## <a name="to-display-a-picture-at-design-time"></a><span data-ttu-id="dc93f-118">Para mostrar una imagen en tiempo de diseño</span><span class="sxs-lookup"><span data-stu-id="dc93f-118">To display a picture at design time</span></span>

1. <span data-ttu-id="dc93f-119">Dibuje un <xref:System.Windows.Forms.PictureBox> control en un formulario.</span><span class="sxs-lookup"><span data-stu-id="dc93f-119">Draw a <xref:System.Windows.Forms.PictureBox> control on a form.</span></span>

2. <span data-ttu-id="dc93f-120">En la ventana **propiedades** , seleccione la <xref:System.Windows.Forms.PictureBox.Image%2A> propiedad y, a continuación, seleccione el botón de puntos suspensivos para mostrar el cuadro de diálogo **abrir** .</span><span class="sxs-lookup"><span data-stu-id="dc93f-120">In the **Properties** window, select the <xref:System.Windows.Forms.PictureBox.Image%2A> property, then select the ellipsis button to display the **Open** dialog box.</span></span>

3. <span data-ttu-id="dc93f-121">Si está buscando un tipo de archivo específico (por ejemplo, archivos. gif), selecciónelo en el cuadro **archivos de tipo** .</span><span class="sxs-lookup"><span data-stu-id="dc93f-121">If you're looking for a specific file type (for example, .gif files), select it in the **Files of type** box.</span></span>

4. <span data-ttu-id="dc93f-122">Seleccione el archivo que desea mostrar.</span><span class="sxs-lookup"><span data-stu-id="dc93f-122">Select the file you want to display.</span></span>

## <a name="to-clear-the-picture-at-design-time"></a><span data-ttu-id="dc93f-123">Para borrar la imagen en tiempo de diseño</span><span class="sxs-lookup"><span data-stu-id="dc93f-123">To clear the picture at design time</span></span>

1. <span data-ttu-id="dc93f-124">En la ventana **propiedades** , seleccione la <xref:System.Windows.Forms.PictureBox.Image%2A> propiedad.</span><span class="sxs-lookup"><span data-stu-id="dc93f-124">In the **Properties** window, select the <xref:System.Windows.Forms.PictureBox.Image%2A> property.</span></span> <span data-ttu-id="dc93f-125">Haga clic con el botón secundario en la pequeña imagen en miniatura que aparece a la izquierda del nombre del objeto de imagen y, a continuación, elija **restablecer**.</span><span class="sxs-lookup"><span data-stu-id="dc93f-125">Right-click the small thumbnail image that appears to the left of the name of the image object, and then choose **Reset**.</span></span>

## <a name="see-also"></a><span data-ttu-id="dc93f-126">Vea también</span><span class="sxs-lookup"><span data-stu-id="dc93f-126">See also</span></span>

- <xref:System.Windows.Forms.PictureBox>
- [<span data-ttu-id="dc93f-127">Información general sobre el control PictureBox</span><span class="sxs-lookup"><span data-stu-id="dc93f-127">PictureBox Control Overview</span></span>](picturebox-control-overview-windows-forms.md)
- [<span data-ttu-id="dc93f-128">Procedimiento para modificar el tamaño o la situación de una imagen en tiempo de ejecución</span><span class="sxs-lookup"><span data-stu-id="dc93f-128">How to: Modify the Size or Placement of a Picture at Run Time</span></span>](how-to-modify-the-size-or-placement-of-a-picture-at-run-time-windows-forms.md)
- [<span data-ttu-id="dc93f-129">Procedimiento para establecer imágenes en tiempo de ejecución</span><span class="sxs-lookup"><span data-stu-id="dc93f-129">How to: Set Pictures at Run Time</span></span>](how-to-set-pictures-at-run-time-windows-forms.md)
- [<span data-ttu-id="dc93f-130">Control PictureBox</span><span class="sxs-lookup"><span data-stu-id="dc93f-130">PictureBox Control</span></span>](picturebox-control-windows-forms.md)
