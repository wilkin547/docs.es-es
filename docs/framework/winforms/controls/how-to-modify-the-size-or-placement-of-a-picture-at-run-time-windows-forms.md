---
title: 'Cómo: Modificar el tamaño o la situación de una imagen en tiempo de ejecución'
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
ms.openlocfilehash: fea813d7b9fe585e35b729b8b64e3a5f414ef76d
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79141971"
---
# <a name="how-to-modify-the-size-or-placement-of-a-picture-at-run-time-windows-forms"></a><span data-ttu-id="81f82-102">Cómo: Modificar el tamaño o la situación de una imagen en tiempo de ejecución (formularios Windows Forms)</span><span class="sxs-lookup"><span data-stu-id="81f82-102">How to: Modify the Size or Placement of a Picture at Run Time (Windows Forms)</span></span>
<span data-ttu-id="81f82-103">Si usa el <xref:System.Windows.Forms.PictureBox> control de formularios Windows Forms <xref:System.Windows.Forms.PictureBox.SizeMode%2A> en un formulario, puede establecer la propiedad en él en:</span><span class="sxs-lookup"><span data-stu-id="81f82-103">If you use the Windows Forms <xref:System.Windows.Forms.PictureBox> control on a form, you can set the <xref:System.Windows.Forms.PictureBox.SizeMode%2A> property on it to:</span></span>  
  
- <span data-ttu-id="81f82-104">Alinee la esquina superior izquierda de la imagen con la esquina superior izquierda del control</span><span class="sxs-lookup"><span data-stu-id="81f82-104">Align the picture's upper left corner with the control's upper left corner</span></span>  
  
- <span data-ttu-id="81f82-105">Centrar la imagen dentro del control</span><span class="sxs-lookup"><span data-stu-id="81f82-105">Center the picture within the control</span></span>  
  
- <span data-ttu-id="81f82-106">Ajuste el tamaño del control para que se ajuste a la imagen que muestra</span><span class="sxs-lookup"><span data-stu-id="81f82-106">Adjust the size of the control to fit the picture it displays</span></span>  
  
- <span data-ttu-id="81f82-107">Estirar cualquier imagen que muestre para ajustarse al control</span><span class="sxs-lookup"><span data-stu-id="81f82-107">Stretch any picture it displays to fit the control</span></span>  
  
 <span data-ttu-id="81f82-108">Estirar una imagen (especialmente una en formato de mapa de bits) puede producir una pérdida en la calidad de imagen.</span><span class="sxs-lookup"><span data-stu-id="81f82-108">Stretching a picture (especially one in bitmap format) can produce a loss in image quality.</span></span> <span data-ttu-id="81f82-109">Los metarchivos, que son listas de instrucciones gráficas para dibujar imágenes en tiempo de ejecución, son más adecuados para el estiramiento que los mapas de bits.</span><span class="sxs-lookup"><span data-stu-id="81f82-109">Metafiles, which are lists of graphics instructions for drawing images at run time, are better suited for stretching than bitmaps are.</span></span>  
  
### <a name="to-set-the-sizemode-property-at-run-time"></a><span data-ttu-id="81f82-110">Para establecer la propiedad SizeMode en tiempo de ejecución</span><span class="sxs-lookup"><span data-stu-id="81f82-110">To set the SizeMode property at run time</span></span>  
  
1. <span data-ttu-id="81f82-111">Establézalo <xref:System.Windows.Forms.PictureBox.SizeMode%2A> en <xref:System.Windows.Forms.PictureBoxSizeMode.Normal> (valor predeterminado), <xref:System.Windows.Forms.PictureBoxSizeMode.AutoSize>, <xref:System.Windows.Forms.PictureBoxSizeMode.CenterImage>o <xref:System.Windows.Forms.PictureBoxSizeMode.StretchImage>.</span><span class="sxs-lookup"><span data-stu-id="81f82-111">Set <xref:System.Windows.Forms.PictureBox.SizeMode%2A> to <xref:System.Windows.Forms.PictureBoxSizeMode.Normal> (the default), <xref:System.Windows.Forms.PictureBoxSizeMode.AutoSize>, <xref:System.Windows.Forms.PictureBoxSizeMode.CenterImage>, or <xref:System.Windows.Forms.PictureBoxSizeMode.StretchImage>.</span></span> <span data-ttu-id="81f82-112"><xref:System.Windows.Forms.PictureBoxSizeMode.Normal>significa que la imagen se coloca en la esquina superior izquierda del control; si la imagen es más grande que el control, sus bordes inferior y derecho se recortan.</span><span class="sxs-lookup"><span data-stu-id="81f82-112"><xref:System.Windows.Forms.PictureBoxSizeMode.Normal> means that the image is placed in the control's upper-left corner; if the image is larger than the control, its lower and right edges are clipped.</span></span> <span data-ttu-id="81f82-113"><xref:System.Windows.Forms.PictureBoxSizeMode.CenterImage>significa que la imagen está centrada dentro del control; si la imagen es más grande que el control, los bordes exteriores de la imagen se recortan.</span><span class="sxs-lookup"><span data-stu-id="81f82-113"><xref:System.Windows.Forms.PictureBoxSizeMode.CenterImage> means that the image is centered within the control; if the image is larger than the control, the picture's outside edges are clipped.</span></span> <span data-ttu-id="81f82-114"><xref:System.Windows.Forms.PictureBoxSizeMode.AutoSize>significa que el tamaño del control se ajusta al tamaño de la imagen.</span><span class="sxs-lookup"><span data-stu-id="81f82-114"><xref:System.Windows.Forms.PictureBoxSizeMode.AutoSize> means that the size of the control is adjusted to the size of the image.</span></span> <span data-ttu-id="81f82-115"><xref:System.Windows.Forms.PictureBoxSizeMode.StretchImage>es lo contrario, y significa que el tamaño de la imagen se ajusta al tamaño del control.</span><span class="sxs-lookup"><span data-stu-id="81f82-115"><xref:System.Windows.Forms.PictureBoxSizeMode.StretchImage> is the reverse, and means that the size of the image is adjusted to the size of the control.</span></span>  
  
     <span data-ttu-id="81f82-116">En el ejemplo siguiente, la ruta establecida para la ubicación de la imagen es la carpeta Mis documentos.</span><span class="sxs-lookup"><span data-stu-id="81f82-116">In the example below, the path set for the location of the image is the My Documents folder.</span></span> <span data-ttu-id="81f82-117">Esto se hace, porque puede suponer que la mayoría de los equipos que ejecutan el sistema operativo Windows incluirán este directorio.</span><span class="sxs-lookup"><span data-stu-id="81f82-117">This is done, because you can assume that most computers running the Windows operating system will include this directory.</span></span> <span data-ttu-id="81f82-118">Esto permite también a los usuarios con niveles de acceso mínimos ejecutar la aplicación de forma segura.</span><span class="sxs-lookup"><span data-stu-id="81f82-118">This also allows users with minimal system access levels to safely run the application.</span></span> <span data-ttu-id="81f82-119">En el ejemplo siguiente se <xref:System.Windows.Forms.PictureBox> supone un formulario con un control ya agregado.</span><span class="sxs-lookup"><span data-stu-id="81f82-119">The example below assumes a form with a <xref:System.Windows.Forms.PictureBox> control already added.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="81f82-120">Consulte también</span><span class="sxs-lookup"><span data-stu-id="81f82-120">See also</span></span>

- <xref:System.Windows.Forms.PictureBox>
- [<span data-ttu-id="81f82-121">Cómo: Cargar una imagen mediante el Diseñador</span><span class="sxs-lookup"><span data-stu-id="81f82-121">How to: Load a Picture Using the Designer</span></span>](how-to-load-a-picture-using-the-designer-windows-forms.md)
- [<span data-ttu-id="81f82-122">Información general del control PictureBox</span><span class="sxs-lookup"><span data-stu-id="81f82-122">PictureBox Control Overview</span></span>](picturebox-control-overview-windows-forms.md)
- [<span data-ttu-id="81f82-123">Cómo: Establecer imágenes en tiempo de ejecución</span><span class="sxs-lookup"><span data-stu-id="81f82-123">How to: Set Pictures at Run Time</span></span>](how-to-set-pictures-at-run-time-windows-forms.md)
- [<span data-ttu-id="81f82-124">PictureBox (Control)</span><span class="sxs-lookup"><span data-stu-id="81f82-124">PictureBox Control</span></span>](picturebox-control-windows-forms.md)
