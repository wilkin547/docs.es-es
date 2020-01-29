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
ms.openlocfilehash: 9bb094ce0b7945f23a2e9b8614e56c9492d5f832
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/24/2020
ms.locfileid: "76736026"
---
# <a name="how-to-modify-the-size-or-placement-of-a-picture-at-run-time-windows-forms"></a><span data-ttu-id="2a502-102">Cómo: Modificar el tamaño o la situación de una imagen en tiempo de ejecución (formularios Windows Forms)</span><span class="sxs-lookup"><span data-stu-id="2a502-102">How to: Modify the Size or Placement of a Picture at Run Time (Windows Forms)</span></span>
<span data-ttu-id="2a502-103">Si usa el control Windows Forms <xref:System.Windows.Forms.PictureBox> en un formulario, puede establecer la propiedad <xref:System.Windows.Forms.PictureBox.SizeMode%2A> en él en:</span><span class="sxs-lookup"><span data-stu-id="2a502-103">If you use the Windows Forms <xref:System.Windows.Forms.PictureBox> control on a form, you can set the <xref:System.Windows.Forms.PictureBox.SizeMode%2A> property on it to:</span></span>  
  
- <span data-ttu-id="2a502-104">Alinea la esquina superior izquierda de la imagen con la esquina superior izquierda del control</span><span class="sxs-lookup"><span data-stu-id="2a502-104">Align the picture's upper left corner with the control's upper left corner</span></span>  
  
- <span data-ttu-id="2a502-105">Centrar la imagen dentro del control</span><span class="sxs-lookup"><span data-stu-id="2a502-105">Center the picture within the control</span></span>  
  
- <span data-ttu-id="2a502-106">Ajustar el tamaño del control para que se ajuste a la imagen que se muestra</span><span class="sxs-lookup"><span data-stu-id="2a502-106">Adjust the size of the control to fit the picture it displays</span></span>  
  
- <span data-ttu-id="2a502-107">Ajustar cualquier imagen que se muestre para ajustarla al control</span><span class="sxs-lookup"><span data-stu-id="2a502-107">Stretch any picture it displays to fit the control</span></span>  
  
 <span data-ttu-id="2a502-108">La ampliación de una imagen (especialmente una en formato de mapa de bits) puede producir una pérdida en la calidad de la imagen.</span><span class="sxs-lookup"><span data-stu-id="2a502-108">Stretching a picture (especially one in bitmap format) can produce a loss in image quality.</span></span> <span data-ttu-id="2a502-109">Los metaarchivos, que son listas de instrucciones de gráficos para dibujar imágenes en tiempo de ejecución, son más adecuados para la ampliación que los mapas de bits.</span><span class="sxs-lookup"><span data-stu-id="2a502-109">Metafiles, which are lists of graphics instructions for drawing images at run time, are better suited for stretching than bitmaps are.</span></span>  
  
### <a name="to-set-the-sizemode-property-at-run-time"></a><span data-ttu-id="2a502-110">Para establecer la propiedad SizeMode en tiempo de ejecución</span><span class="sxs-lookup"><span data-stu-id="2a502-110">To set the SizeMode property at run time</span></span>  
  
1. <span data-ttu-id="2a502-111">Establezca <xref:System.Windows.Forms.PictureBox.SizeMode%2A> en <xref:System.Windows.Forms.PictureBoxSizeMode.Normal> (valor predeterminado), <xref:System.Windows.Forms.PictureBoxSizeMode.AutoSize>, <xref:System.Windows.Forms.PictureBoxSizeMode.CenterImage>o <xref:System.Windows.Forms.PictureBoxSizeMode.StretchImage>.</span><span class="sxs-lookup"><span data-stu-id="2a502-111">Set <xref:System.Windows.Forms.PictureBox.SizeMode%2A> to <xref:System.Windows.Forms.PictureBoxSizeMode.Normal> (the default), <xref:System.Windows.Forms.PictureBoxSizeMode.AutoSize>, <xref:System.Windows.Forms.PictureBoxSizeMode.CenterImage>, or <xref:System.Windows.Forms.PictureBoxSizeMode.StretchImage>.</span></span> <span data-ttu-id="2a502-112"><xref:System.Windows.Forms.PictureBoxSizeMode.Normal> significa que la imagen se coloca en la esquina superior izquierda del control. Si la imagen es mayor que el control, se recortan los bordes inferior y derecho.</span><span class="sxs-lookup"><span data-stu-id="2a502-112"><xref:System.Windows.Forms.PictureBoxSizeMode.Normal> means that the image is placed in the control's upper-left corner; if the image is larger than the control, its lower and right edges are clipped.</span></span> <span data-ttu-id="2a502-113"><xref:System.Windows.Forms.PictureBoxSizeMode.CenterImage> significa que la imagen se centra dentro del control; Si la imagen es mayor que el control, se recortan los bordes exteriores de la imagen.</span><span class="sxs-lookup"><span data-stu-id="2a502-113"><xref:System.Windows.Forms.PictureBoxSizeMode.CenterImage> means that the image is centered within the control; if the image is larger than the control, the picture's outside edges are clipped.</span></span> <span data-ttu-id="2a502-114"><xref:System.Windows.Forms.PictureBoxSizeMode.AutoSize> significa que el tamaño del control se ajusta al tamaño de la imagen.</span><span class="sxs-lookup"><span data-stu-id="2a502-114"><xref:System.Windows.Forms.PictureBoxSizeMode.AutoSize> means that the size of the control is adjusted to the size of the image.</span></span> <span data-ttu-id="2a502-115"><xref:System.Windows.Forms.PictureBoxSizeMode.StretchImage> es el inverso y significa que el tamaño de la imagen se ajusta al tamaño del control.</span><span class="sxs-lookup"><span data-stu-id="2a502-115"><xref:System.Windows.Forms.PictureBoxSizeMode.StretchImage> is the reverse, and means that the size of the image is adjusted to the size of the control.</span></span>  
  
     <span data-ttu-id="2a502-116">En el ejemplo siguiente, la ruta de acceso establecida para la ubicación de la imagen es la carpeta Mis documentos.</span><span class="sxs-lookup"><span data-stu-id="2a502-116">In the example below, the path set for the location of the image is the My Documents folder.</span></span> <span data-ttu-id="2a502-117">Esto se hace porque puede suponer que la mayoría de los equipos que ejecutan el sistema operativo Windows incluirán este directorio.</span><span class="sxs-lookup"><span data-stu-id="2a502-117">This is done, because you can assume that most computers running the Windows operating system will include this directory.</span></span> <span data-ttu-id="2a502-118">Esto permite también a los usuarios con niveles de acceso mínimos ejecutar la aplicación de forma segura.</span><span class="sxs-lookup"><span data-stu-id="2a502-118">This also allows users with minimal system access levels to safely run the application.</span></span> <span data-ttu-id="2a502-119">En el ejemplo siguiente se supone que ya se ha agregado un formulario con un control <xref:System.Windows.Forms.PictureBox>.</span><span class="sxs-lookup"><span data-stu-id="2a502-119">The example below assumes a form with a <xref:System.Windows.Forms.PictureBox> control already added.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="2a502-120">Vea también</span><span class="sxs-lookup"><span data-stu-id="2a502-120">See also</span></span>

- <xref:System.Windows.Forms.PictureBox>
- [<span data-ttu-id="2a502-121">Cargar una imagen mediante el Diseñador</span><span class="sxs-lookup"><span data-stu-id="2a502-121">How to: Load a Picture Using the Designer</span></span>](how-to-load-a-picture-using-the-designer-windows-forms.md)
- [<span data-ttu-id="2a502-122">Información general del control PictureBox</span><span class="sxs-lookup"><span data-stu-id="2a502-122">PictureBox Control Overview</span></span>](picturebox-control-overview-windows-forms.md)
- [<span data-ttu-id="2a502-123">Establecer imágenes en tiempo de ejecución</span><span class="sxs-lookup"><span data-stu-id="2a502-123">How to: Set Pictures at Run Time</span></span>](how-to-set-pictures-at-run-time-windows-forms.md)
- [<span data-ttu-id="2a502-124">PictureBox (control)</span><span class="sxs-lookup"><span data-stu-id="2a502-124">PictureBox Control</span></span>](picturebox-control-windows-forms.md)
