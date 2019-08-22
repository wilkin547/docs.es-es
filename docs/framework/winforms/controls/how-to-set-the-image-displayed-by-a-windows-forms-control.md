---
title: Filtrar para establecer la imagen mostrada por un control de formularios Windows Forms
ms.date: 08/20/2019
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
ms.openlocfilehash: b1b1dbbb50c3b19cf8d8a7d7030d0bc168afb6a7
ms.sourcegitcommit: cdf67135a98a5a51913dacddb58e004a3c867802
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/21/2019
ms.locfileid: "69666187"
---
# <a name="how-to-set-the-image-displayed-by-a-windows-forms-control"></a><span data-ttu-id="a1d74-102">Filtrar Establecer la imagen mostrada por un control Windows Forms</span><span class="sxs-lookup"><span data-stu-id="a1d74-102">How to: Set the image displayed by a Windows Forms control</span></span>

<span data-ttu-id="a1d74-103">Varios controles Windows Forms pueden mostrar imágenes.</span><span class="sxs-lookup"><span data-stu-id="a1d74-103">Several Windows Forms controls can display images.</span></span> <span data-ttu-id="a1d74-104">Estas imágenes pueden ser iconos que clarifican el propósito del control, como un icono de disquete en un botón que denota el comando Save.</span><span class="sxs-lookup"><span data-stu-id="a1d74-104">These images can be icons that clarify the purpose of the control, such as a diskette icon on a button denoting the Save command.</span></span> <span data-ttu-id="a1d74-105">Como alternativa, los iconos pueden ser imágenes de fondo para dar al control la apariencia y el comportamiento que desea.</span><span class="sxs-lookup"><span data-stu-id="a1d74-105">Alternatively, the icons can be background images to give the control the appearance and behavior you want.</span></span>

## <a name="programmatic"></a><span data-ttu-id="a1d74-106">Programas</span><span class="sxs-lookup"><span data-stu-id="a1d74-106">Programmatic</span></span>

<span data-ttu-id="a1d74-107">Establezca la propiedad o `Image` `BackgroundImage` del control en un objeto de tipo <xref:System.Drawing.Image>.</span><span class="sxs-lookup"><span data-stu-id="a1d74-107">Set the control's `Image` or `BackgroundImage` property to an object of type <xref:System.Drawing.Image>.</span></span> <span data-ttu-id="a1d74-108">Por lo general, se cargará la imagen desde un archivo mediante el <xref:System.Drawing.Image.FromFile%2A> método.</span><span class="sxs-lookup"><span data-stu-id="a1d74-108">Generally, you'll be loading the image from a file by using the <xref:System.Drawing.Image.FromFile%2A> method.</span></span>

<span data-ttu-id="a1d74-109">En el ejemplo de código siguiente, la ruta de acceso establecida para la ubicación de la imagen es la carpeta **Mis imágenes** .</span><span class="sxs-lookup"><span data-stu-id="a1d74-109">In the following code example, the path set for the location of the image is the **My Pictures** folder.</span></span> <span data-ttu-id="a1d74-110">La mayoría de los equipos que ejecutan el sistema operativo Windows incluyen este directorio.</span><span class="sxs-lookup"><span data-stu-id="a1d74-110">Most computers running the Windows operating system include this directory.</span></span> <span data-ttu-id="a1d74-111">Esto también permite a los usuarios con niveles de acceso mínimos del sistema ejecutar la aplicación de forma segura.</span><span class="sxs-lookup"><span data-stu-id="a1d74-111">This also enables users with minimal system access levels to run the application safely.</span></span> <span data-ttu-id="a1d74-112">El siguiente ejemplo de código requiere que ya tenga un formulario con un <xref:System.Windows.Forms.PictureBox> control agregado.</span><span class="sxs-lookup"><span data-stu-id="a1d74-112">The following code example requires that you already have a form with a <xref:System.Windows.Forms.PictureBox> control added.</span></span>

```vb
' Replace the image named below with your own icon.
PictureBox1.Image = Image.FromFile _
   (System.Environment.GetFolderPath _
   (System.Environment.SpecialFolder.MyPictures) _
   & "\Image.gif")
```

```csharp
// Replace the image named below with your own icon.
// Note the escape character used (@) when specifying the path.
pictureBox1.Image = Image.FromFile
   (System.Environment.GetFolderPath
   (System.Environment.SpecialFolder.MyPictures)
   + @"\Image.gif");
```

```cpp
// Replace the image named below with your own icon.
pictureBox1->Image = Image::FromFile(String::Concat
   (System::Environment::GetFolderPath
   (System::Environment::SpecialFolder::MyPictures),
   "\\Image.gif"));
```

## <a name="designer"></a><span data-ttu-id="a1d74-113">Diseñador</span><span class="sxs-lookup"><span data-stu-id="a1d74-113">Designer</span></span>

1. <span data-ttu-id="a1d74-114">En la ventana **propiedades** de Visual Studio, seleccione la **propiedad imagen** o **BackgroundImage** del control y, a continuación, seleccione los puntos![suspensivos (botón de puntos](./media/visual-studio-ellipsis-button.png)suspensivos en Visual Studio) para mostrar la **selección** Cuadro de diálogo de recursos.</span><span class="sxs-lookup"><span data-stu-id="a1d74-114">In the **Properties** window of Visual Studio, select the **Image** or **BackgroundImage** property of the control, and then select the ellipsis (![Ellipsis button in Visual Studio](./media/visual-studio-ellipsis-button.png)) to display the **Select Resource** dialog box.</span></span>

2. <span data-ttu-id="a1d74-115">Seleccione la imagen que desea mostrar.</span><span class="sxs-lookup"><span data-stu-id="a1d74-115">Select the image you want to display.</span></span>

## <a name="see-also"></a><span data-ttu-id="a1d74-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="a1d74-116">See also</span></span>

- <xref:System.Drawing.Image.FromFile%2A>
- <xref:System.Drawing.Image>
- <xref:System.Windows.Forms.Control.BackgroundImage%2A>
