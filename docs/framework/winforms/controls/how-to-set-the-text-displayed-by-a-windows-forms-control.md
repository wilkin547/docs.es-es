---
title: Procedimiento para establecer el texto mostrado por un control de formularios Windows Forms
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- Windows Forms, captions
- Button control [Windows Forms], button text
- StdFont object and CommandButton caption
- captions [Windows Forms], Windows Forms controls
- Text property [Windows Forms], Windows Forms control
- Button control [Windows Forms], text display
- labels [Windows Forms], adding to CommandButton control
- buttons [Windows Forms], text
- captions [Windows Forms], setting
- text
- examples [Windows Forms], controls
- text [Windows Forms], Windows Forms controls
- controls [Windows Forms], captions
- forms [Windows Forms], captions
ms.assetid: 36b95bff-8780-479d-b86a-f1a0673653aa
ms.openlocfilehash: 59570af89e6236e3c13866d45dc5361d52b84274
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "62013093"
---
# <a name="how-to-set-the-text-displayed-by-a-windows-forms-control"></a>Procedimiento para establecer el texto mostrado por un control de formularios Windows Forms
Normalmente, los controles de Windows Forms muestran algún texto relacionado con la función principal del control. Por ejemplo, un control <xref:System.Windows.Forms.Button> suele mostrar un título que indica qué acción se realizará al hacer clic en el botón. Para todos los controles, puede establecer o devolver el texto usando la propiedad <xref:System.Windows.Forms.Control.Text%2A>. Puede cambiar la fuente usando la propiedad <xref:System.Windows.Forms.Control.Font%2A>. También puede establecer el texto mediante el diseñador.  Consulte también [Cómo: Crear teclas de acceso para Windows Forms mediante el Diseñador de controles](how-to-create-access-keys-for-windows-forms-controls-using-the-designer.md), [Cómo: Establecer el texto mostrado por un Windows Forms mediante el Diseñador de Control](how-to-set-the-text-displayed-by-a-windows-forms-control-using-the-designer.md), [Cómo: Establecer la imagen que muestra un Windows Forms mediante el Diseñador de Control](how-to-set-the-image-displayed-by-a-windows-forms-control-using-the-designer.md).  
  
### <a name="to-set-the-text-displayed-by-a-control-programmatically"></a>Para establecer mediante programación el texto que un control muestra  
  
1. Establezca la propiedad <xref:System.Windows.Forms.Control.Text%2A> en una cadena.  
  
     Para crear una clave de acceso subrayada, incluya una y comercial (&) delante de la letra que será la clave de acceso.  
  
2. Establezca la propiedad <xref:System.Windows.Forms.Control.Font%2A> en un objeto del tipo <xref:System.Drawing.Font>.  
  
    ```vb  
    Button1.Text = "Click here to save changes"  
    Button1.Font = New Font("Arial", 10, FontStyle.Bold, GraphicsUnit.Point)  
    ```  
  
    ```csharp  
    button1.Text = "Click here to save changes";  
    button1.Font = new Font("Arial", 10, FontStyle.Bold,  
       GraphicsUnit.Point);  
    ```  
  
    ```cpp  
    button1->Text = "Click here to save changes";  
    button1->Font = new System::Drawing::Font("Arial",  
       10, FontStyle::Bold, GraphicsUnit::Point);  
    ```  
  
    > [!NOTE]
    >  Puede usar un carácter de escape para mostrar un carácter especial en elementos de la interfaz de usuario que normalmente interpretarían de forma distinta, por ejemplo, elementos de menú. Por ejemplo, la siguiente línea de código establece el texto del elemento de menú para leer "& Now For Something completamente diferente":  
  
    ```vb  
    MPMenuItem.Text = "&& Now For Something Completely Different"  
    ```  
  
    ```csharp  
    mpMenuItem.Text = "&& Now For Something Completely Different";  
    ```  
  
    ```cpp  
    mpMenuItem->Text = "&& Now For Something Completely Different";  
    ```  
  
## <a name="see-also"></a>Vea también

- <xref:System.Windows.Forms.Control.Text%2A?displayProperty=nameWithType>
- [Cómo: Crear teclas de acceso para controles de formularios Windows Forms](how-to-create-access-keys-for-windows-forms-controls.md)
- [Cómo: Responder a clics de botón de Windows Forms](how-to-respond-to-windows-forms-button-clicks.md)
