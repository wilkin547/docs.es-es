---
title: para establecer el fondo de un control Panel
description: Obtenga información sobre cómo establecer el color de fondo y la imagen de fondo de un panel de Windows Forms mediante el diseñador.
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
ms.openlocfilehash: 109ff6184de9c79d1576207bbeb29ad939670b6f
ms.sourcegitcommit: cb27c01a8b0b4630148374638aff4e2221f90b22
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/09/2020
ms.locfileid: "86173385"
---
# <a name="how-to-set-the-background-of-a-windows-forms-panel"></a><span data-ttu-id="f3a4d-103">Cómo: Establecer el fondo de un control Panel de formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="f3a4d-103">How to: Set the Background of a Windows Forms Panel</span></span>
<span data-ttu-id="f3a4d-104">Un control de Windows Forms <xref:System.Windows.Forms.Panel> puede mostrar un color de fondo y una imagen de fondo.</span><span class="sxs-lookup"><span data-stu-id="f3a4d-104">A Windows Forms <xref:System.Windows.Forms.Panel> control can display both a background color and a background image.</span></span> <span data-ttu-id="f3a4d-105">La <xref:System.Windows.Forms.Control.BackColor%2A> propiedad establece el color de fondo de los controles contenidos, como etiquetas y botones de radio.</span><span class="sxs-lookup"><span data-stu-id="f3a4d-105">The <xref:System.Windows.Forms.Control.BackColor%2A> property sets the background color for the contained controls, such as labels and radio buttons.</span></span> <span data-ttu-id="f3a4d-106">Si <xref:System.Windows.Forms.Control.BackgroundImage%2A> no se establece la propiedad, la <xref:System.Windows.Forms.Control.BackColor%2A> selección rellenará todo el panel.</span><span class="sxs-lookup"><span data-stu-id="f3a4d-106">If the <xref:System.Windows.Forms.Control.BackgroundImage%2A> property is not set, the <xref:System.Windows.Forms.Control.BackColor%2A> selection will fill the entire panel.</span></span> <span data-ttu-id="f3a4d-107">Si <xref:System.Windows.Forms.Control.BackgroundImage%2A> se establece la propiedad, la imagen se mostrará detrás de los controles contenidos.</span><span class="sxs-lookup"><span data-stu-id="f3a4d-107">If the <xref:System.Windows.Forms.Control.BackgroundImage%2A> property is set, the image will be displayed behind the contained controls.</span></span>  
  
### <a name="to-set-the-background-programmatically"></a><span data-ttu-id="f3a4d-108">Para establecer el fondo mediante programación</span><span class="sxs-lookup"><span data-stu-id="f3a4d-108">To set the background programmatically</span></span>  
  
1. <span data-ttu-id="f3a4d-109">Establezca la propiedad del panel <xref:System.Windows.Forms.Control.BackColor%2A> en un valor de tipo <xref:System.Drawing.Color?displayProperty=nameWithType> .</span><span class="sxs-lookup"><span data-stu-id="f3a4d-109">Set the panel's <xref:System.Windows.Forms.Control.BackColor%2A> property to a value of type <xref:System.Drawing.Color?displayProperty=nameWithType>.</span></span>  
  
    ```vb  
    Panel1.BackColor = Color.AliceBlue  
    ```  
  
    ```csharp  
    panel1.BackColor = Color.AliceBlue;  
    ```  
  
    ```cpp  
    panel1->BackColor = Color::AliceBlue;  
    ```  
  
2. <span data-ttu-id="f3a4d-110">Establezca la propiedad del panel <xref:System.Windows.Forms.Control.BackgroundImage%2A> mediante el <xref:System.Drawing.Image.FromFile%2A> método de la <xref:System.Drawing.Image?displayProperty=nameWithType> clase.</span><span class="sxs-lookup"><span data-stu-id="f3a4d-110">Set the panel's <xref:System.Windows.Forms.Control.BackgroundImage%2A> property using the <xref:System.Drawing.Image.FromFile%2A> method of the <xref:System.Drawing.Image?displayProperty=nameWithType> class.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="f3a4d-111">Vea también</span><span class="sxs-lookup"><span data-stu-id="f3a4d-111">See also</span></span>

- <xref:System.Windows.Forms.Control.BackColor%2A>
- <xref:System.Windows.Forms.Control.BackgroundImage%2A>
- [<span data-ttu-id="f3a4d-112">Control Panel</span><span class="sxs-lookup"><span data-stu-id="f3a4d-112">Panel Control</span></span>](panel-control-windows-forms.md)
- [<span data-ttu-id="f3a4d-113">Información general sobre el control Panel</span><span class="sxs-lookup"><span data-stu-id="f3a4d-113">Panel Control Overview</span></span>](panel-control-overview-windows-forms.md)
