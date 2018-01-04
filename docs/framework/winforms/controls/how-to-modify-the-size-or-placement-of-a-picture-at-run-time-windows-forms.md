---
title: "Cómo: Modificar el tamaño o la situación de una imagen en tiempo de ejecución (formularios Windows Forms)"
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
- cpp
helpviewer_keywords:
- images [Windows Forms], controlling placement in PictureBox control [Windows Forms]
- examples [Windows Forms], PictureBox control
- PictureBox control [Windows Forms], picture size and alignment
- pictures [Windows Forms], controlling placement in PictureBox control [Windows Forms]
ms.assetid: d0b332a3-fae2-4891-957c-dc3e17743326
caps.latest.revision: "12"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: e02ea1cbcb1fdd86d182bfba23241acb91c4b54a
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-modify-the-size-or-placement-of-a-picture-at-run-time-windows-forms"></a><span data-ttu-id="5d881-102">Cómo: Modificar el tamaño o la situación de una imagen en tiempo de ejecución (formularios Windows Forms)</span><span class="sxs-lookup"><span data-stu-id="5d881-102">How to: Modify the Size or Placement of a Picture at Run Time (Windows Forms)</span></span>
<span data-ttu-id="5d881-103">Si usa Windows Forms <xref:System.Windows.Forms.PictureBox> control en un formulario, puede establecer el <xref:System.Windows.Forms.PictureBox.SizeMode%2A> propiedad en ella para:</span><span class="sxs-lookup"><span data-stu-id="5d881-103">If you use the Windows Forms <xref:System.Windows.Forms.PictureBox> control on a form, you can set the <xref:System.Windows.Forms.PictureBox.SizeMode%2A> property on it to:</span></span>  
  
-   <span data-ttu-id="5d881-104">Alinear la esquina izquierda superior de la imagen con la esquina superior izquierda del control</span><span class="sxs-lookup"><span data-stu-id="5d881-104">Align the picture's upper left corner with the control's upper left corner</span></span>  
  
-   <span data-ttu-id="5d881-105">Centrar la imagen dentro del control</span><span class="sxs-lookup"><span data-stu-id="5d881-105">Center the picture within the control</span></span>  
  
-   <span data-ttu-id="5d881-106">Ajustar el tamaño del control para ajustarse a la imagen que muestra</span><span class="sxs-lookup"><span data-stu-id="5d881-106">Adjust the size of the control to fit the picture it displays</span></span>  
  
-   <span data-ttu-id="5d881-107">Ajustar cualquier imagen que se muestre para que se ajuste al control.</span><span class="sxs-lookup"><span data-stu-id="5d881-107">Stretch any picture it displays to fit the control</span></span>  
  
 <span data-ttu-id="5d881-108">Ajuste de una imagen (especialmente uno en formato de mapa de bits), puede producir una pérdida de calidad de la imagen.</span><span class="sxs-lookup"><span data-stu-id="5d881-108">Stretching a picture (especially one in bitmap format) can produce a loss in image quality.</span></span> <span data-ttu-id="5d881-109">Metarchivos, que son listas de instrucciones gráficas para dibujar imágenes en tiempo de ejecución, son más adecuados para el ajuste de mapas de bits.</span><span class="sxs-lookup"><span data-stu-id="5d881-109">Metafiles, which are lists of graphics instructions for drawing images at run time, are better suited for stretching than bitmaps are.</span></span>  
  
### <a name="to-set-the-sizemode-property-at-run-time"></a><span data-ttu-id="5d881-110">Para establecer la propiedad SizeMode en tiempo de ejecución</span><span class="sxs-lookup"><span data-stu-id="5d881-110">To set the SizeMode property at run time</span></span>  
  
1.  <span data-ttu-id="5d881-111">Establecer <xref:System.Windows.Forms.PictureBox.SizeMode%2A> a <xref:System.Windows.Forms.PictureBoxSizeMode.Normal> (valor predeterminado), <xref:System.Windows.Forms.PictureBoxSizeMode.AutoSize>, <xref:System.Windows.Forms.PictureBoxSizeMode.CenterImage>, o <xref:System.Windows.Forms.PictureBoxSizeMode.StretchImage>.</span><span class="sxs-lookup"><span data-stu-id="5d881-111">Set <xref:System.Windows.Forms.PictureBox.SizeMode%2A> to <xref:System.Windows.Forms.PictureBoxSizeMode.Normal> (the default), <xref:System.Windows.Forms.PictureBoxSizeMode.AutoSize>, <xref:System.Windows.Forms.PictureBoxSizeMode.CenterImage>, or <xref:System.Windows.Forms.PictureBoxSizeMode.StretchImage>.</span></span> <span data-ttu-id="5d881-112"><xref:System.Windows.Forms.PictureBoxSizeMode.Normal>significa que la imagen se coloca en la esquina superior izquierda del control; Si la imagen es mayor que el control, se recortan los bordes inferior y derecho.</span><span class="sxs-lookup"><span data-stu-id="5d881-112"><xref:System.Windows.Forms.PictureBoxSizeMode.Normal> means that the image is placed in the control's upper-left corner; if the image is larger than the control, its lower and right edges are clipped.</span></span> <span data-ttu-id="5d881-113"><xref:System.Windows.Forms.PictureBoxSizeMode.CenterImage>significa que la imagen se centra dentro del control. Si la imagen es mayor que el control, se recortan los bordes exteriores de la imagen.</span><span class="sxs-lookup"><span data-stu-id="5d881-113"><xref:System.Windows.Forms.PictureBoxSizeMode.CenterImage> means that the image is centered within the control; if the image is larger than the control, the picture's outside edges are clipped.</span></span> <span data-ttu-id="5d881-114"><xref:System.Windows.Forms.PictureBoxSizeMode.AutoSize>significa que el tamaño del control se ajusta al tamaño de la imagen.</span><span class="sxs-lookup"><span data-stu-id="5d881-114"><xref:System.Windows.Forms.PictureBoxSizeMode.AutoSize> means that the size of the control is adjusted to the size of the image.</span></span> <span data-ttu-id="5d881-115"><xref:System.Windows.Forms.PictureBoxSizeMode.StretchImage>es el inverso al orden y significa que el tamaño de la imagen se ajusta al tamaño del control.</span><span class="sxs-lookup"><span data-stu-id="5d881-115"><xref:System.Windows.Forms.PictureBoxSizeMode.StretchImage> is the reverse, and means that the size of the image is adjusted to the size of the control.</span></span>  
  
     <span data-ttu-id="5d881-116">En el ejemplo siguiente, la ruta de acceso establecida para la ubicación de la imagen es la carpeta Mis documentos.</span><span class="sxs-lookup"><span data-stu-id="5d881-116">In the example below, the path set for the location of the image is the My Documents folder.</span></span> <span data-ttu-id="5d881-117">Para ello, porque se puede asumir que la mayoría de los equipos ejecutan el sistema operativo Windows incluirá este directorio.</span><span class="sxs-lookup"><span data-stu-id="5d881-117">This is done, because you can assume that most computers running the Windows operating system will include this directory.</span></span> <span data-ttu-id="5d881-118">Esto permite también a los usuarios con niveles de acceso mínimos ejecutar la aplicación de forma segura.</span><span class="sxs-lookup"><span data-stu-id="5d881-118">This also allows users with minimal system access levels to safely run the application.</span></span> <span data-ttu-id="5d881-119">El ejemplo siguiente supone un formulario con un <xref:System.Windows.Forms.PictureBox> control ya se ha agregado.</span><span class="sxs-lookup"><span data-stu-id="5d881-119">The example below assumes a form with a <xref:System.Windows.Forms.PictureBox> control already added.</span></span>  
  
    ```vb  
    Private Sub StretchPic()  
       ' Stretch the picture to fit the control.  
       PictureBox1.SizeMode = PictureBoxSizeMode.StretchImage  
       ' Load the picture into the control.  
       ' You should replace the bold image   
       ' in the sample below with an icon of your own choosing.  
       PictureBox1.Image = Image.FromFile _  
       (System.Environment.GetFolderPath _  
       (System.Environment.SpecialFolder.Personal) _  
       & "\Image.gif")  
    End Sub  
    ```  
  
    ```csharp  
    private void StretchPic(){  
       // Stretch the picture to fit the control.  
       PictureBox1.SizeMode = PictureBoxSizeMode.StretchImage;  
       // Load the picture into the control.  
       // You should replace the bold image   
       // in the sample below with an icon of your own choosing.  
       // Note the escape character used (@) when specifying the path.  
       PictureBox1.Image = Image.FromFile _  
       (System.Environment.GetFolderPath _  
       (System.Environment.SpecialFolder.Personal) _  
       + @"\Image.gif")  
    }  
    ```  
  
    ```cpp  
    private:  
       void StretchPic()  
       {  
          // Stretch the picture to fit the control.  
          pictureBox1->SizeMode = PictureBoxSizeMode::StretchImage;  
          // Load the picture into the control.  
          // You should replace the bold image   
          // in the sample below with an icon of your own choosing.  
          pictureBox1->Image = Image::FromFile(String::Concat(  
             System::Environment::GetFolderPath(  
             System::Environment::SpecialFolder::Personal),  
             "\\Image.gif"));  
       }  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="5d881-120">Vea también</span><span class="sxs-lookup"><span data-stu-id="5d881-120">See Also</span></span>  
 <xref:System.Windows.Forms.PictureBox>  
 [<span data-ttu-id="5d881-121">Cargar una imagen mediante el Diseñador</span><span class="sxs-lookup"><span data-stu-id="5d881-121">How to: Load a Picture Using the Designer</span></span>](../../../../docs/framework/winforms/controls/how-to-load-a-picture-using-the-designer-windows-forms.md)  
 [<span data-ttu-id="5d881-122">Información general del control PictureBox</span><span class="sxs-lookup"><span data-stu-id="5d881-122">PictureBox Control Overview</span></span>](../../../../docs/framework/winforms/controls/picturebox-control-overview-windows-forms.md)  
 [<span data-ttu-id="5d881-123">Establecer imágenes en tiempo de ejecución</span><span class="sxs-lookup"><span data-stu-id="5d881-123">How to: Set Pictures at Run Time</span></span>](../../../../docs/framework/winforms/controls/how-to-set-pictures-at-run-time-windows-forms.md)  
 [<span data-ttu-id="5d881-124">PictureBox (control)</span><span class="sxs-lookup"><span data-stu-id="5d881-124">PictureBox Control</span></span>](../../../../docs/framework/winforms/controls/picturebox-control-windows-forms.md)
