---
title: Procedimiento para establecer la imagen mostrada por un control de formularios Windows Forms
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- Button control [Windows Forms], images
- Windows Forms controls, images
- controls [Windows Forms], images
- images [Windows Forms], Windows Forms controls
- examples [Windows Forms], controls
ms.assetid: 9445af8f-4f62-48b0-a3f6-068058964b9f
ms.openlocfilehash: 1de835bda5ac906837ac3fbd97b87f68f14d1953
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "62013145"
---
# <a name="how-to-set-the-image-displayed-by-a-windows-forms-control"></a><span data-ttu-id="658bf-102">Procedimiento para establecer la imagen mostrada por un control de formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="658bf-102">How to: Set the Image Displayed by a Windows Forms Control</span></span>
<span data-ttu-id="658bf-103">Varios controles de Windows Forms pueden mostrar imágenes.</span><span class="sxs-lookup"><span data-stu-id="658bf-103">Several Windows Forms controls can display images.</span></span> <span data-ttu-id="658bf-104">Estas imágenes pueden ser iconos que aclarar el propósito del control, como un icono de disquete en un botón que denota el **guardar** comando.</span><span class="sxs-lookup"><span data-stu-id="658bf-104">These images can be icons that clarify the purpose of the control, such as a diskette icon on a button denoting the **Save** command.</span></span> <span data-ttu-id="658bf-105">Como alternativa, los iconos pueden ser las imágenes de fondo para proporcionar el control de la apariencia y comportamiento que desee.</span><span class="sxs-lookup"><span data-stu-id="658bf-105">Alternatively, the icons can be background images to give the control the appearance and behavior you want.</span></span>  
  
### <a name="to-set-the-image-displayed-by-a-control"></a><span data-ttu-id="658bf-106">Para establecer la imagen que muestra un control</span><span class="sxs-lookup"><span data-stu-id="658bf-106">To set the image displayed by a control</span></span>  
  
1. <span data-ttu-id="658bf-107">Establecer el control `Image` o `BackgroundImage` propiedad a un objeto de tipo <xref:System.Drawing.Image>.</span><span class="sxs-lookup"><span data-stu-id="658bf-107">Set the control's `Image` or `BackgroundImage` property to an object of type <xref:System.Drawing.Image>.</span></span> <span data-ttu-id="658bf-108">Por lo general, se carga la imagen desde un archivo mediante el uso de la <xref:System.Drawing.Image.FromFile%2A> método.</span><span class="sxs-lookup"><span data-stu-id="658bf-108">Generally, you will be loading the image from a file by using the <xref:System.Drawing.Image.FromFile%2A> method.</span></span>  
  
     <span data-ttu-id="658bf-109">En el ejemplo de código siguiente establece la ruta de acceso para la ubicación de la imagen es la **Mis imágenes** carpeta.</span><span class="sxs-lookup"><span data-stu-id="658bf-109">In the following code example, the path set for the location of the image is the **My Pictures** folder.</span></span> <span data-ttu-id="658bf-110">Mayoría de los equipos que ejecutan el sistema operativo de Windows tendrán este directorio.</span><span class="sxs-lookup"><span data-stu-id="658bf-110">Most computers running the Windows operating system will include this directory.</span></span> <span data-ttu-id="658bf-111">Esto también permite a los usuarios con niveles de acceso mínimos ejecutar la aplicación de forma segura.</span><span class="sxs-lookup"><span data-stu-id="658bf-111">This also enables users with minimal system access levels to run the application safely.</span></span> <span data-ttu-id="658bf-112">El siguiente ejemplo de código requiere que ya tiene un formulario con un <xref:System.Windows.Forms.PictureBox> control agregado.</span><span class="sxs-lookup"><span data-stu-id="658bf-112">The following code example requires that you already have a form with a <xref:System.Windows.Forms.PictureBox> control added.</span></span>  
  
    ```vb  
    ' Replace the image named below  
    ' with an icon of your own choosing.  
    PictureBox1.Image = Image.FromFile _  
       (System.Environment.GetFolderPath _  
       (System.Environment.SpecialFolder.MyPictures) _  
       & "\Image.gif")  
    ```  
  
    ```csharp  
    // Replace the image named below  
    // with an icon of your own choosing.  
    // Note the escape character used (@) when specifying the path.  
    pictureBox1.Image = Image.FromFile  
       (System.Environment.GetFolderPath  
       (System.Environment.SpecialFolder.MyPictures)  
       + @"\Image.gif");  
    ```  
  
    ```cpp  
    // Replace the image named below  
    // with an icon of your own choosing.  
    pictureBox1->Image = Image::FromFile(String::Concat  
       (System::Environment::GetFolderPath  
       (System::Environment::SpecialFolder::MyPictures),  
       "\\Image.gif"));  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="658bf-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="658bf-113">See also</span></span>

- <xref:System.Drawing.Image.FromFile%2A>
- <xref:System.Drawing.Image>
- <xref:System.Windows.Forms.Control.BackgroundImage%2A>
