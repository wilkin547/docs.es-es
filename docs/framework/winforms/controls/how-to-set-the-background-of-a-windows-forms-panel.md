---
title: para establecer el fondo de un control Panel
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- background colors [Windows Forms], Windows Forms Panel controls
- background images [Windows Forms], Windows Forms Panel controls
- Panel control [Windows Forms], background
- colors [Windows Forms], Windows Forms Panel controls
ms.assetid: 096cbd8d-45cc-47b8-b1ef-a27f60ea8be0
ms.openlocfilehash: 36e552475334c25b9d5a6fafb82155c6ebcba266
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79182107"
---
# <a name="how-to-set-the-background-of-a-windows-forms-panel"></a><span data-ttu-id="a1a95-102">Cómo: Establecer el fondo de un control Panel de formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="a1a95-102">How to: Set the Background of a Windows Forms Panel</span></span>
<span data-ttu-id="a1a95-103">Un control <xref:System.Windows.Forms.Panel> de formularios Windows Forms puede mostrar un color de fondo y una imagen de fondo.</span><span class="sxs-lookup"><span data-stu-id="a1a95-103">A Windows Forms <xref:System.Windows.Forms.Panel> control can display both a background color and a background image.</span></span> <span data-ttu-id="a1a95-104">La <xref:System.Windows.Forms.Control.BackColor%2A> propiedad establece el color de fondo de los controles contenidos, como etiquetas y botones de opción.</span><span class="sxs-lookup"><span data-stu-id="a1a95-104">The <xref:System.Windows.Forms.Control.BackColor%2A> property sets the background color for the contained controls, such as labels and radio buttons.</span></span> <span data-ttu-id="a1a95-105">Si <xref:System.Windows.Forms.Control.BackgroundImage%2A> la propiedad no <xref:System.Windows.Forms.Control.BackColor%2A> está establecida, la selección rellenará todo el panel.</span><span class="sxs-lookup"><span data-stu-id="a1a95-105">If the <xref:System.Windows.Forms.Control.BackgroundImage%2A> property is not set, the <xref:System.Windows.Forms.Control.BackColor%2A> selection will fill the entire panel.</span></span> <span data-ttu-id="a1a95-106">Si <xref:System.Windows.Forms.Control.BackgroundImage%2A> se establece la propiedad, la imagen se mostrará detrás de los controles contenidos.</span><span class="sxs-lookup"><span data-stu-id="a1a95-106">If the <xref:System.Windows.Forms.Control.BackgroundImage%2A> property is set, the image will be displayed behind the contained controls.</span></span>  
  
### <a name="to-set-the-background-programmatically"></a><span data-ttu-id="a1a95-107">Para establecer el fondo mediante programación</span><span class="sxs-lookup"><span data-stu-id="a1a95-107">To set the background programmatically</span></span>  
  
1. <span data-ttu-id="a1a95-108">Establezca la propiedad <xref:System.Windows.Forms.Control.BackColor%2A> del panel en <xref:System.Drawing.Color?displayProperty=nameWithType>un valor de tipo .</span><span class="sxs-lookup"><span data-stu-id="a1a95-108">Set the panel's <xref:System.Windows.Forms.Control.BackColor%2A> property to a value of type <xref:System.Drawing.Color?displayProperty=nameWithType>.</span></span>  
  
    ```vb  
    Panel1.BackColor = Color.AliceBlue  
    ```  
  
    ```csharp  
    panel1.BackColor = Color.AliceBlue;  
    ```  
  
    ```cpp  
    panel1->BackColor = Color::AliceBlue;  
    ```  
  
2. <span data-ttu-id="a1a95-109">Establezca la propiedad <xref:System.Windows.Forms.Control.BackgroundImage%2A> del <xref:System.Drawing.Image.FromFile%2A> panel utilizando el método de la <xref:System.Drawing.Image?displayProperty=nameWithType> clase.</span><span class="sxs-lookup"><span data-stu-id="a1a95-109">Set the panel's <xref:System.Windows.Forms.Control.BackgroundImage%2A> property using the <xref:System.Drawing.Image.FromFile%2A> method of the <xref:System.Drawing.Image?displayProperty=nameWithType> class.</span></span>  
  
    ```vb  
    ' You should replace the bolded image
    ' in the sample below with an image of your own choosing.  
    Panel1.BackgroundImage = Image.FromFile _  
        (System.Environment.GetFolderPath _  
        (System.Environment.SpecialFolder.Personal) _  
        & "\Image.gif")  
    ```  
  
    ```csharp  
    // You should replace the bolded image
    // in the sample below with an image of your own choosing.  
    // Note the escape character used (@) when specifying the path.  
    panel1.BackgroundImage = Image.FromFile  
       (System.Environment.GetFolderPath  
       (System.Environment.SpecialFolder.Personal)  
       + @"\Image.gif");  
    ```  
  
    ```cpp  
    // You should replace the bolded image
    // in the sample below with an image of your own choosing.  
    panel1->BackgroundImage = Image::FromFile(String::Concat(  
       System::Environment::GetFolderPath  
       (System::Environment::SpecialFolder::Personal),  
       "\\Image.gif"));  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="a1a95-110">Consulte también</span><span class="sxs-lookup"><span data-stu-id="a1a95-110">See also</span></span>

- <xref:System.Windows.Forms.Control.BackColor%2A>
- <xref:System.Windows.Forms.Control.BackgroundImage%2A>
- [<span data-ttu-id="a1a95-111">Control Panel</span><span class="sxs-lookup"><span data-stu-id="a1a95-111">Panel Control</span></span>](panel-control-windows-forms.md)
- [<span data-ttu-id="a1a95-112">Información general sobre el control Panel</span><span class="sxs-lookup"><span data-stu-id="a1a95-112">Panel Control Overview</span></span>](panel-control-overview-windows-forms.md)
