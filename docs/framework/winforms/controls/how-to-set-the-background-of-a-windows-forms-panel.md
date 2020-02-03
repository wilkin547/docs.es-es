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
ms.openlocfilehash: ba2619354403793aea7ca15d43649da9637079a6
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/24/2020
ms.locfileid: "76744743"
---
# <a name="how-to-set-the-background-of-a-windows-forms-panel"></a>Cómo: Establecer el fondo de un control Panel de formularios Windows Forms
Un control de <xref:System.Windows.Forms.Panel> de Windows Forms puede mostrar un color de fondo y una imagen de fondo. La propiedad <xref:System.Windows.Forms.Control.BackColor%2A> establece el color de fondo de los controles contenidos, como etiquetas y botones de radio. Si no se establece la propiedad <xref:System.Windows.Forms.Control.BackgroundImage%2A>, la selección de <xref:System.Windows.Forms.Control.BackColor%2A> llenará todo el panel. Si se establece la propiedad <xref:System.Windows.Forms.Control.BackgroundImage%2A>, la imagen se mostrará detrás de los controles contenidos.  
  
### <a name="to-set-the-background-programmatically"></a>Para establecer el fondo mediante programación  
  
1. Establezca la propiedad <xref:System.Windows.Forms.Control.BackColor%2A> del panel en un valor de tipo <xref:System.Drawing.Color?displayProperty=nameWithType>.  
  
    ```vb  
    Panel1.BackColor = Color.AliceBlue  
    ```  
  
    ```csharp  
    panel1.BackColor = Color.AliceBlue;  
    ```  
  
    ```cpp  
    panel1->BackColor = Color::AliceBlue;  
    ```  
  
2. Establezca la propiedad <xref:System.Windows.Forms.Control.BackgroundImage%2A> del panel con el método <xref:System.Drawing.Image.FromFile%2A> de la clase <xref:System.Drawing.Image?displayProperty=nameWithType>.  
  
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
  
## <a name="see-also"></a>Consulte también

- <xref:System.Windows.Forms.Control.BackColor%2A>
- <xref:System.Windows.Forms.Control.BackgroundImage%2A>
- [Panel (control)](panel-control-windows-forms.md)
- [Información general del control Panel](panel-control-overview-windows-forms.md)
