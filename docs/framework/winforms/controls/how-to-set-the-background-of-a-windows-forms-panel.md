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
# <a name="how-to-set-the-background-of-a-windows-forms-panel"></a>Cómo: Establecer el fondo de un control Panel de formularios Windows Forms
Un control <xref:System.Windows.Forms.Panel> de formularios Windows Forms puede mostrar un color de fondo y una imagen de fondo. La <xref:System.Windows.Forms.Control.BackColor%2A> propiedad establece el color de fondo de los controles contenidos, como etiquetas y botones de opción. Si <xref:System.Windows.Forms.Control.BackgroundImage%2A> la propiedad no <xref:System.Windows.Forms.Control.BackColor%2A> está establecida, la selección rellenará todo el panel. Si <xref:System.Windows.Forms.Control.BackgroundImage%2A> se establece la propiedad, la imagen se mostrará detrás de los controles contenidos.  
  
### <a name="to-set-the-background-programmatically"></a>Para establecer el fondo mediante programación  
  
1. Establezca la propiedad <xref:System.Windows.Forms.Control.BackColor%2A> del panel en <xref:System.Drawing.Color?displayProperty=nameWithType>un valor de tipo .  
  
    ```vb  
    Panel1.BackColor = Color.AliceBlue  
    ```  
  
    ```csharp  
    panel1.BackColor = Color.AliceBlue;  
    ```  
  
    ```cpp  
    panel1->BackColor = Color::AliceBlue;  
    ```  
  
2. Establezca la propiedad <xref:System.Windows.Forms.Control.BackgroundImage%2A> del <xref:System.Drawing.Image.FromFile%2A> panel utilizando el método de la <xref:System.Drawing.Image?displayProperty=nameWithType> clase.  
  
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
- [Control Panel](panel-control-windows-forms.md)
- [Información general sobre el control Panel](panel-control-overview-windows-forms.md)
