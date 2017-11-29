---
title: "Cómo: Establecer la imagen que muestra un control de formularios Windows Forms"
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
- Button control [Windows Forms], images
- Windows Forms controls, images
- controls [Windows Forms], images
- images [Windows Forms], Windows Forms controls
- examples [Windows Forms], controls
ms.assetid: 9445af8f-4f62-48b0-a3f6-068058964b9f
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 6d9f4d806b39e6e1272ddbb60befdaf8c76e46b3
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-set-the-image-displayed-by-a-windows-forms-control"></a><span data-ttu-id="064b7-102">Cómo: Establecer la imagen que muestra un control de formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="064b7-102">How to: Set the Image Displayed by a Windows Forms Control</span></span>
<span data-ttu-id="064b7-103">Varios controles de formularios Windows Forms pueden mostrar imágenes.</span><span class="sxs-lookup"><span data-stu-id="064b7-103">Several Windows Forms controls can display images.</span></span> <span data-ttu-id="064b7-104">Estas imágenes pueden ser iconos que clarifican el propósito del control, como un icono del disquete en un botón que denota el **guardar** comando.</span><span class="sxs-lookup"><span data-stu-id="064b7-104">These images can be icons that clarify the purpose of the control, such as a diskette icon on a button denoting the **Save** command.</span></span> <span data-ttu-id="064b7-105">Como alternativa, los iconos pueden ser imágenes de fondo para proporcionar el control de la apariencia y el comportamiento que desee.</span><span class="sxs-lookup"><span data-stu-id="064b7-105">Alternatively, the icons can be background images to give the control the appearance and behavior you want.</span></span>  
  
### <a name="to-set-the-image-displayed-by-a-control"></a><span data-ttu-id="064b7-106">Para establecer la imagen que muestra un control</span><span class="sxs-lookup"><span data-stu-id="064b7-106">To set the image displayed by a control</span></span>  
  
1.  <span data-ttu-id="064b7-107">Establecer el control `Image` o `BackgroundImage` propiedad a un objeto de tipo <xref:System.Drawing.Image>.</span><span class="sxs-lookup"><span data-stu-id="064b7-107">Set the control's `Image` or `BackgroundImage` property to an object of type <xref:System.Drawing.Image>.</span></span> <span data-ttu-id="064b7-108">Por lo general, se carga la imagen desde un archivo mediante el uso de la <xref:System.Drawing.Image.FromFile%2A> método.</span><span class="sxs-lookup"><span data-stu-id="064b7-108">Generally, you will be loading the image from a file by using the <xref:System.Drawing.Image.FromFile%2A> method.</span></span>  
  
     <span data-ttu-id="064b7-109">En el ejemplo de código siguiente, la ruta de acceso establecida para la ubicación de la imagen es la **Mis imágenes** carpeta.</span><span class="sxs-lookup"><span data-stu-id="064b7-109">In the following code example, the path set for the location of the image is the **My Pictures** folder.</span></span> <span data-ttu-id="064b7-110">Mayoría de los equipos ejecutan el sistema operativo Windows tendrán este directorio.</span><span class="sxs-lookup"><span data-stu-id="064b7-110">Most computers running the Windows operating system will include this directory.</span></span> <span data-ttu-id="064b7-111">Esto también permite a los usuarios con niveles de acceso de sistema mínimos ejecutar la aplicación de forma segura.</span><span class="sxs-lookup"><span data-stu-id="064b7-111">This also enables users with minimal system access levels to run the application safely.</span></span> <span data-ttu-id="064b7-112">El siguiente ejemplo de código requiere que ya tenga un formulario con un <xref:System.Windows.Forms.PictureBox> control agregado.</span><span class="sxs-lookup"><span data-stu-id="064b7-112">The following code example requires that you already have a form with a <xref:System.Windows.Forms.PictureBox> control added.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="064b7-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="064b7-113">See Also</span></span>  
 <xref:System.Drawing.Image.FromFile%2A>  
 <xref:System.Drawing.Image>  
 <xref:System.Windows.Forms.Control.BackgroundImage%2A>
