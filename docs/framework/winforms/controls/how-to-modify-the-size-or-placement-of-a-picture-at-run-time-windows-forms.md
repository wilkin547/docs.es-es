---
title: Procedimiento Modificar el tamaño o la ubicación de una imagen en tiempo de ejecución (formularios Windows Forms)
ms.date: 03/30/2017
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
ms.openlocfilehash: d0a86d7fe53dba3da6bd63587561f82877bc2f06
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61913736"
---
# <a name="how-to-modify-the-size-or-placement-of-a-picture-at-run-time-windows-forms"></a><span data-ttu-id="a75bf-102">Procedimiento Modificar el tamaño o la ubicación de una imagen en tiempo de ejecución (formularios Windows Forms)</span><span class="sxs-lookup"><span data-stu-id="a75bf-102">How to: Modify the Size or Placement of a Picture at Run Time (Windows Forms)</span></span>
<span data-ttu-id="a75bf-103">Si utiliza los formularios de Windows <xref:System.Windows.Forms.PictureBox> control en un formulario, puede establecer el <xref:System.Windows.Forms.PictureBox.SizeMode%2A> propiedad en él para:</span><span class="sxs-lookup"><span data-stu-id="a75bf-103">If you use the Windows Forms <xref:System.Windows.Forms.PictureBox> control on a form, you can set the <xref:System.Windows.Forms.PictureBox.SizeMode%2A> property on it to:</span></span>  
  
-   <span data-ttu-id="a75bf-104">Alinear esquina superior izquierda la imagen en la con la esquina superior izquierda del control</span><span class="sxs-lookup"><span data-stu-id="a75bf-104">Align the picture's upper left corner with the control's upper left corner</span></span>  
  
-   <span data-ttu-id="a75bf-105">Centrar la imagen dentro del control</span><span class="sxs-lookup"><span data-stu-id="a75bf-105">Center the picture within the control</span></span>  
  
-   <span data-ttu-id="a75bf-106">Ajustar el tamaño del control para que quepa la imagen que muestra</span><span class="sxs-lookup"><span data-stu-id="a75bf-106">Adjust the size of the control to fit the picture it displays</span></span>  
  
-   <span data-ttu-id="a75bf-107">Estirar cualquier imagen que se muestre para ajustar el control</span><span class="sxs-lookup"><span data-stu-id="a75bf-107">Stretch any picture it displays to fit the control</span></span>  
  
 <span data-ttu-id="a75bf-108">Ajuste de una imagen (especialmente uno en formato de mapa de bits) puede producirse una pérdida de calidad de imagen.</span><span class="sxs-lookup"><span data-stu-id="a75bf-108">Stretching a picture (especially one in bitmap format) can produce a loss in image quality.</span></span> <span data-ttu-id="a75bf-109">Los metarchivos, que son listas de instrucciones de gráficos para dibujar imágenes en tiempo de ejecución, son más adecuados para el ajuste de los mapas de bits.</span><span class="sxs-lookup"><span data-stu-id="a75bf-109">Metafiles, which are lists of graphics instructions for drawing images at run time, are better suited for stretching than bitmaps are.</span></span>  
  
### <a name="to-set-the-sizemode-property-at-run-time"></a><span data-ttu-id="a75bf-110">Para establecer la propiedad SizeMode en tiempo de ejecución</span><span class="sxs-lookup"><span data-stu-id="a75bf-110">To set the SizeMode property at run time</span></span>  
  
1. <span data-ttu-id="a75bf-111">Establecer <xref:System.Windows.Forms.PictureBox.SizeMode%2A> a <xref:System.Windows.Forms.PictureBoxSizeMode.Normal> (valor predeterminado), <xref:System.Windows.Forms.PictureBoxSizeMode.AutoSize>, <xref:System.Windows.Forms.PictureBoxSizeMode.CenterImage>, o <xref:System.Windows.Forms.PictureBoxSizeMode.StretchImage>.</span><span class="sxs-lookup"><span data-stu-id="a75bf-111">Set <xref:System.Windows.Forms.PictureBox.SizeMode%2A> to <xref:System.Windows.Forms.PictureBoxSizeMode.Normal> (the default), <xref:System.Windows.Forms.PictureBoxSizeMode.AutoSize>, <xref:System.Windows.Forms.PictureBoxSizeMode.CenterImage>, or <xref:System.Windows.Forms.PictureBoxSizeMode.StretchImage>.</span></span> <span data-ttu-id="a75bf-112"><xref:System.Windows.Forms.PictureBoxSizeMode.Normal> significa que la imagen se coloca en la esquina superior izquierda del control; Si la imagen es mayor que el control, se recortan los bordes derecho e inferiores.</span><span class="sxs-lookup"><span data-stu-id="a75bf-112"><xref:System.Windows.Forms.PictureBoxSizeMode.Normal> means that the image is placed in the control's upper-left corner; if the image is larger than the control, its lower and right edges are clipped.</span></span> <span data-ttu-id="a75bf-113"><xref:System.Windows.Forms.PictureBoxSizeMode.CenterImage> significa que la imagen se centra dentro del control. Si la imagen es mayor que el control, se recortan los bordes exteriores de la imagen.</span><span class="sxs-lookup"><span data-stu-id="a75bf-113"><xref:System.Windows.Forms.PictureBoxSizeMode.CenterImage> means that the image is centered within the control; if the image is larger than the control, the picture's outside edges are clipped.</span></span> <span data-ttu-id="a75bf-114"><xref:System.Windows.Forms.PictureBoxSizeMode.AutoSize> significa que el tamaño del control se ajusta al tamaño de la imagen.</span><span class="sxs-lookup"><span data-stu-id="a75bf-114"><xref:System.Windows.Forms.PictureBoxSizeMode.AutoSize> means that the size of the control is adjusted to the size of the image.</span></span> <span data-ttu-id="a75bf-115"><xref:System.Windows.Forms.PictureBoxSizeMode.StretchImage> es el inverso y significa que el tamaño de la imagen se ajusta al tamaño del control.</span><span class="sxs-lookup"><span data-stu-id="a75bf-115"><xref:System.Windows.Forms.PictureBoxSizeMode.StretchImage> is the reverse, and means that the size of the image is adjusted to the size of the control.</span></span>  
  
     <span data-ttu-id="a75bf-116">En el ejemplo siguiente, la ruta de acceso establecida para la ubicación de la imagen es la carpeta Mis documentos.</span><span class="sxs-lookup"><span data-stu-id="a75bf-116">In the example below, the path set for the location of the image is the My Documents folder.</span></span> <span data-ttu-id="a75bf-117">Hecho esto, ya que puede asumir que la mayoría de los equipos que ejecutan el sistema operativo de Windows tendrán este directorio.</span><span class="sxs-lookup"><span data-stu-id="a75bf-117">This is done, because you can assume that most computers running the Windows operating system will include this directory.</span></span> <span data-ttu-id="a75bf-118">Esto permite también a los usuarios con niveles de acceso mínimos ejecutar la aplicación de forma segura.</span><span class="sxs-lookup"><span data-stu-id="a75bf-118">This also allows users with minimal system access levels to safely run the application.</span></span> <span data-ttu-id="a75bf-119">El ejemplo siguiente se da por supuesto un formulario con un <xref:System.Windows.Forms.PictureBox> control ya se ha agregado.</span><span class="sxs-lookup"><span data-stu-id="a75bf-119">The example below assumes a form with a <xref:System.Windows.Forms.PictureBox> control already added.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="a75bf-120">Vea también</span><span class="sxs-lookup"><span data-stu-id="a75bf-120">See also</span></span>

- <xref:System.Windows.Forms.PictureBox>
- [<span data-ttu-id="a75bf-121">Cómo: Cargar una imagen mediante el diseñador</span><span class="sxs-lookup"><span data-stu-id="a75bf-121">How to: Load a Picture Using the Designer</span></span>](how-to-load-a-picture-using-the-designer-windows-forms.md)
- [<span data-ttu-id="a75bf-122">Información general del control PictureBox</span><span class="sxs-lookup"><span data-stu-id="a75bf-122">PictureBox Control Overview</span></span>](picturebox-control-overview-windows-forms.md)
- [<span data-ttu-id="a75bf-123">Cómo: Establecer imágenes en tiempo de ejecución</span><span class="sxs-lookup"><span data-stu-id="a75bf-123">How to: Set Pictures at Run Time</span></span>](how-to-set-pictures-at-run-time-windows-forms.md)
- [<span data-ttu-id="a75bf-124">PictureBox (control)</span><span class="sxs-lookup"><span data-stu-id="a75bf-124">PictureBox Control</span></span>](picturebox-control-windows-forms.md)
