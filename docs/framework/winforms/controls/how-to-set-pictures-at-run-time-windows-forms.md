---
title: Procedimiento Establecer imágenes en tiempo de ejecución (formularios Windows Forms)
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- pictures [Windows Forms], setting display
- examples [Windows Forms], PictureBox control
- bitmaps [Windows Forms], displaying in PictureBox control [Windows Forms]
- PictureBox control [Windows Forms], adding images
- images [Windows Forms], adding with PictureBox control [Windows Forms]
- PictureBox control [Windows Forms], adding pictures
ms.assetid: 18ca41d0-68a5-4660-985e-a6c1fbc01d76
ms.openlocfilehash: c7a65bcc65710324a4457c17dd728b4771550c06
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54694079"
---
# <a name="how-to-set-pictures-at-run-time-windows-forms"></a><span data-ttu-id="26a02-102">Procedimiento Establecer imágenes en tiempo de ejecución (formularios Windows Forms)</span><span class="sxs-lookup"><span data-stu-id="26a02-102">How to: Set Pictures at Run Time (Windows Forms)</span></span>
<span data-ttu-id="26a02-103">Puede establecer mediante programación la imagen que muestra un formulario Windows Forms <xref:System.Windows.Forms.PictureBox> control.</span><span class="sxs-lookup"><span data-stu-id="26a02-103">You can programmatically set the image displayed by a Windows Forms <xref:System.Windows.Forms.PictureBox> control.</span></span>  
  
### <a name="to-set-a-picture-programmatically"></a><span data-ttu-id="26a02-104">Para establecer una imagen mediante programación</span><span class="sxs-lookup"><span data-stu-id="26a02-104">To set a picture programmatically</span></span>  
  
-   <span data-ttu-id="26a02-105">Establecer el <xref:System.Windows.Forms.PictureBox.Image%2A> propiedad utilizando el <xref:System.Drawing.Image.FromFile%2A> método de la <xref:System.Drawing.Image> clase.</span><span class="sxs-lookup"><span data-stu-id="26a02-105">Set the <xref:System.Windows.Forms.PictureBox.Image%2A> property using the <xref:System.Drawing.Image.FromFile%2A> method of the <xref:System.Drawing.Image> class.</span></span>  
  
     <span data-ttu-id="26a02-106">En el ejemplo siguiente, la ruta de acceso establecida para la ubicación de la imagen es la carpeta Mis documentos.</span><span class="sxs-lookup"><span data-stu-id="26a02-106">In the example below, the path set for the location of the image is the My Documents folder.</span></span> <span data-ttu-id="26a02-107">Hecho esto, ya que puede asumir que la mayoría de los equipos que ejecutan el sistema operativo de Windows tendrán este directorio.</span><span class="sxs-lookup"><span data-stu-id="26a02-107">This is done, because you can assume that most computers running the Windows operating system will include this directory.</span></span> <span data-ttu-id="26a02-108">Esto permite también a los usuarios con niveles de acceso mínimos ejecutar la aplicación de forma segura.</span><span class="sxs-lookup"><span data-stu-id="26a02-108">This also allows users with minimal system access levels to safely run the application.</span></span> <span data-ttu-id="26a02-109">El ejemplo siguiente se da por supuesto un formulario con un <xref:System.Windows.Forms.PictureBox> control ya se ha agregado.</span><span class="sxs-lookup"><span data-stu-id="26a02-109">The example below assumes a form with a <xref:System.Windows.Forms.PictureBox> control already added.</span></span>  
  
    ```vb  
    Private Sub LoadNewPict()  
       ' You should replace the bold image   
       ' in the sample below with an icon of your own choosing.  
       PictureBox1.Image = Image.FromFile _  
       (System.Environment.GetFolderPath _  
       (System.Environment.SpecialFolder.Personal) _  
       & "\Image.gif")  
    End Sub  
    ```  
  
    ```csharp  
    private void LoadNewPict(){  
       // You should replace the bold image   
       // in the sample below with an icon of your own choosing.  
       // Note the escape character used (@) when specifying the path.  
       pictureBox1.Image = Image.FromFile  
       (System.Environment.GetFolderPath  
       (System.Environment.SpecialFolder.Personal)  
       + @"\Image.gif");  
    }  
    ```  
  
    ```cpp  
    private:  
       void LoadNewPict()  
       {  
          // You should replace the bold image   
          // in the sample below with an icon of your own choosing.  
          pictureBox1->Image = Image::FromFile(String::Concat(  
             System::Environment::GetFolderPath(  
             System::Environment::SpecialFolder::Personal),  
             "\\Image.gif"));  
       }  
    ```  
  
### <a name="to-clear-a-graphic"></a><span data-ttu-id="26a02-110">Para borrar un gráfico</span><span class="sxs-lookup"><span data-stu-id="26a02-110">To clear a graphic</span></span>  
  
-   <span data-ttu-id="26a02-111">En primer lugar, liberar la memoria utilizada por la imagen y, a continuación, desactive el gráfico.</span><span class="sxs-lookup"><span data-stu-id="26a02-111">First, release the memory being used by the image, and then clear the graphic.</span></span> <span data-ttu-id="26a02-112">Colección de elementos no utilizados liberará la memoria más adelante si la administración de memoria se convierte en un problema.</span><span class="sxs-lookup"><span data-stu-id="26a02-112">Garbage collection will free up the memory later if memory management becomes a problem.</span></span>  
  
    ```vb  
    If Not (PictureBox1.Image Is Nothing) Then  
       PictureBox1.Image.Dispose()  
       PictureBox1.Image = Nothing  
    End If  
    ```  
  
    ```csharp  
    if (pictureBox1.Image != null)   
    {  
       pictureBox1.Image.Dispose();  
       pictureBox1.Image = null;  
    }  
    ```  
  
    ```cpp  
    if (pictureBox1->Image != nullptr)  
    {  
       pictureBox1->Image->Dispose();  
       pictureBox1->Image = nullptr;  
    }  
    ```  
  
    > [!NOTE]
    >  <span data-ttu-id="26a02-113">Para obtener más información sobre por qué debería usar el <xref:System.Drawing.Image.Dispose%2A> método de este modo, consulte [limpiar recursos no administrados](../../../../docs/standard/garbage-collection/unmanaged.md).</span><span class="sxs-lookup"><span data-stu-id="26a02-113">For more information on why you should use the <xref:System.Drawing.Image.Dispose%2A> method in this way, see [Cleaning Up Unmanaged Resources](../../../../docs/standard/garbage-collection/unmanaged.md).</span></span>  
  
     <span data-ttu-id="26a02-114">Este código borrará la imagen incluso si se ha cargado un gráfico en el control en tiempo de diseño.</span><span class="sxs-lookup"><span data-stu-id="26a02-114">This code will clear the image even if a graphic was loaded into the control at design time.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="26a02-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="26a02-115">See also</span></span>
- <xref:System.Windows.Forms.PictureBox>
- <xref:System.Drawing.Image.FromFile%2A?displayProperty=nameWithType>
- [<span data-ttu-id="26a02-116">Información general del control PictureBox</span><span class="sxs-lookup"><span data-stu-id="26a02-116">PictureBox Control Overview</span></span>](../../../../docs/framework/winforms/controls/picturebox-control-overview-windows-forms.md)
- [<span data-ttu-id="26a02-117">Cómo: Cargar una imagen mediante el diseñador</span><span class="sxs-lookup"><span data-stu-id="26a02-117">How to: Load a Picture Using the Designer</span></span>](../../../../docs/framework/winforms/controls/how-to-load-a-picture-using-the-designer-windows-forms.md)
- [<span data-ttu-id="26a02-118">Cómo: Modificar el tamaño o la ubicación de una imagen en tiempo de ejecución</span><span class="sxs-lookup"><span data-stu-id="26a02-118">How to: Modify the Size or Placement of a Picture at Run Time</span></span>](../../../../docs/framework/winforms/controls/how-to-modify-the-size-or-placement-of-a-picture-at-run-time-windows-forms.md)
- [<span data-ttu-id="26a02-119">PictureBox (control)</span><span class="sxs-lookup"><span data-stu-id="26a02-119">PictureBox Control</span></span>](../../../../docs/framework/winforms/controls/picturebox-control-windows-forms.md)
