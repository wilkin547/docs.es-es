---
title: Procedimiento Cargar una imagen mediante el diseñador (Windows Forms)
ms.date: 03/30/2017
helpviewer_keywords:
- picture formats
- images [Windows Forms], displaying on Windows Forms
- pictures [Windows Forms], displaying
- forms [Windows Forms], displaying images
- PictureBox control [Windows Forms], adding pictures
ms.assetid: 4dc7b973-afb1-4276-8322-20825af96655
ms.openlocfilehash: 818bc63b5b3bea6c73804f716a72ba3cd1a62b4c
ms.sourcegitcommit: cf9515122fce716bcfb6618ba366e39b5a2eb81e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/15/2019
ms.locfileid: "69039678"
---
# <a name="how-to-load-a-picture-using-the-designer-windows-forms"></a><span data-ttu-id="9f152-102">Procedimiento Cargar una imagen mediante el diseñador (Windows Forms)</span><span class="sxs-lookup"><span data-stu-id="9f152-102">How to: Load a Picture Using the Designer (Windows Forms)</span></span>

<span data-ttu-id="9f152-103">Con el control <xref:System.Windows.Forms.PictureBox> Windows Forms, puede cargar y mostrar una imagen en un formulario en tiempo de diseño si establece la <xref:System.Windows.Forms.PictureBox.Image%2A> propiedad en una imagen válida.</span><span class="sxs-lookup"><span data-stu-id="9f152-103">With the Windows Forms <xref:System.Windows.Forms.PictureBox> control, you can load and display a picture on a form at design time by setting the <xref:System.Windows.Forms.PictureBox.Image%2A> property to a valid picture.</span></span> <span data-ttu-id="9f152-104">En la tabla siguiente se muestran los tipos de archivo aceptables.</span><span class="sxs-lookup"><span data-stu-id="9f152-104">The following table shows the acceptable file types.</span></span>

|<span data-ttu-id="9f152-105">Type</span><span class="sxs-lookup"><span data-stu-id="9f152-105">Type</span></span>|<span data-ttu-id="9f152-106">Extensión de nombre de archivo</span><span class="sxs-lookup"><span data-stu-id="9f152-106">File name extension</span></span>|
|---|---|
|<span data-ttu-id="9f152-107">Bitmap</span><span class="sxs-lookup"><span data-stu-id="9f152-107">Bitmap</span></span>|<span data-ttu-id="9f152-108">. bmp</span><span class="sxs-lookup"><span data-stu-id="9f152-108">.bmp</span></span>|
|<span data-ttu-id="9f152-109">Iconos</span><span class="sxs-lookup"><span data-stu-id="9f152-109">Icon</span></span>|<span data-ttu-id="9f152-110">.ico</span><span class="sxs-lookup"><span data-stu-id="9f152-110">.ico</span></span>|
|<span data-ttu-id="9f152-111">GIF</span><span class="sxs-lookup"><span data-stu-id="9f152-111">GIF</span></span>|<span data-ttu-id="9f152-112">.gif</span><span class="sxs-lookup"><span data-stu-id="9f152-112">.gif</span></span>|
|<span data-ttu-id="9f152-113">CGM</span><span class="sxs-lookup"><span data-stu-id="9f152-113">Metafile</span></span>|<span data-ttu-id="9f152-114">. WMF</span><span class="sxs-lookup"><span data-stu-id="9f152-114">.wmf</span></span>|
|<span data-ttu-id="9f152-115">JPEG</span><span class="sxs-lookup"><span data-stu-id="9f152-115">JPEG</span></span>|<span data-ttu-id="9f152-116">.jpg</span><span class="sxs-lookup"><span data-stu-id="9f152-116">.jpg</span></span>|

## <a name="to-display-a-picture-at-design-time"></a><span data-ttu-id="9f152-117">Para mostrar una imagen en tiempo de diseño</span><span class="sxs-lookup"><span data-stu-id="9f152-117">To display a picture at design time</span></span>

1. <span data-ttu-id="9f152-118">Dibuje un <xref:System.Windows.Forms.PictureBox> control en un formulario.</span><span class="sxs-lookup"><span data-stu-id="9f152-118">Draw a <xref:System.Windows.Forms.PictureBox> control on a form.</span></span>

2. <span data-ttu-id="9f152-119">En la ventana **propiedades** , seleccione la <xref:System.Windows.Forms.PictureBox.Image%2A> propiedad y, a continuación, seleccione el botón de puntos suspensivos para mostrar el cuadro de diálogo **abrir** .</span><span class="sxs-lookup"><span data-stu-id="9f152-119">In the **Properties** window, select the <xref:System.Windows.Forms.PictureBox.Image%2A> property, then select the ellipsis button to display the **Open** dialog box.</span></span>

3. <span data-ttu-id="9f152-120">Si está buscando un tipo de archivo específico (por ejemplo, archivos. gif), selecciónelo en el cuadro **archivos de tipo** .</span><span class="sxs-lookup"><span data-stu-id="9f152-120">If you're looking for a specific file type (for example, .gif files), select it in the **Files of type** box.</span></span>

4. <span data-ttu-id="9f152-121">Seleccione el archivo que desea mostrar.</span><span class="sxs-lookup"><span data-stu-id="9f152-121">Select the file you want to display.</span></span>

## <a name="to-clear-the-picture-at-design-time"></a><span data-ttu-id="9f152-122">Para borrar la imagen en tiempo de diseño</span><span class="sxs-lookup"><span data-stu-id="9f152-122">To clear the picture at design time</span></span>

1. <span data-ttu-id="9f152-123">En la ventana **propiedades** , seleccione la <xref:System.Windows.Forms.PictureBox.Image%2A> propiedad.</span><span class="sxs-lookup"><span data-stu-id="9f152-123">In the **Properties** window, select the <xref:System.Windows.Forms.PictureBox.Image%2A> property.</span></span> <span data-ttu-id="9f152-124">Haga clic con el botón secundario en la pequeña imagen en miniatura que aparece a la izquierda del nombre del objeto de imagen y, a continuación, elija **restablecer**.</span><span class="sxs-lookup"><span data-stu-id="9f152-124">Right-click the small thumbnail image that appears to the left of the name of the image object, and then choose **Reset**.</span></span>

## <a name="see-also"></a><span data-ttu-id="9f152-125">Vea también</span><span class="sxs-lookup"><span data-stu-id="9f152-125">See also</span></span>

- <xref:System.Windows.Forms.PictureBox>
- [<span data-ttu-id="9f152-126">Información general del control PictureBox</span><span class="sxs-lookup"><span data-stu-id="9f152-126">PictureBox Control Overview</span></span>](picturebox-control-overview-windows-forms.md)
- [<span data-ttu-id="9f152-127">Cómo: Modificar el tamaño o la posición de una imagen en tiempo de ejecución</span><span class="sxs-lookup"><span data-stu-id="9f152-127">How to: Modify the Size or Placement of a Picture at Run Time</span></span>](how-to-modify-the-size-or-placement-of-a-picture-at-run-time-windows-forms.md)
- [<span data-ttu-id="9f152-128">Procedimientos: Establecer imágenes en tiempo de ejecución</span><span class="sxs-lookup"><span data-stu-id="9f152-128">How to: Set Pictures at Run Time</span></span>](how-to-set-pictures-at-run-time-windows-forms.md)
- [<span data-ttu-id="9f152-129">PictureBox (control)</span><span class="sxs-lookup"><span data-stu-id="9f152-129">PictureBox Control</span></span>](picturebox-control-windows-forms.md)
