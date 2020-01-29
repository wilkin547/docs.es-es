---
title: Establecer el texto mostrado por un control
ms.date: 08/20/2019
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
ms.openlocfilehash: eb02cbc3b335b0d5856f786b21d1d202cf444211
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/24/2020
ms.locfileid: "76738420"
---
# <a name="how-to-set-the-text-displayed-by-a-windows-forms-control"></a>Cómo: establecer el texto mostrado por un control Windows Forms

Windows Forms controles suelen mostrar algún texto relacionado con la función principal del control. Por ejemplo, un control de <xref:System.Windows.Forms.Button> normalmente muestra un título que indica la acción que se realizará si se hace clic en el botón. Para todos los controles, puede establecer o devolver el texto usando la propiedad <xref:System.Windows.Forms.Control.Text%2A>. Puede cambiar la fuente usando la propiedad <xref:System.Windows.Forms.Control.Font%2A>.

También puede establecer el texto mediante el [Diseñador](#designer).

## <a name="programmatic"></a>Programas

1. Establezca la propiedad <xref:System.Windows.Forms.Control.Text%2A> en una cadena.

   Para crear una tecla de acceso subrayada, incluye una y comercial (&) delante de la letra que será la tecla de acceso.

2. Establezca la propiedad <xref:System.Windows.Forms.Control.Font%2A> en un objeto del tipo <xref:System.Drawing.Font>.

    ```vb
    Button1.Text = "Click here to save changes"
    Button1.Font = New Font("Arial", 10, FontStyle.Bold, GraphicsUnit.Point)
    ```

    ```csharp
    button1.Text = "Click here to save changes";
    button1.Font = new Font("Arial", 10, FontStyle.Bold, GraphicsUnit.Point);
    ```

    ```cpp
    button1->Text = "Click here to save changes";
    button1->Font = new System::Drawing::Font("Arial", 10, FontStyle::Bold, GraphicsUnit::Point);
    ```

    > [!NOTE]
    > Puede usar un carácter de escape para mostrar un carácter especial en elementos de la interfaz de usuario que normalmente interpretarían de forma distinta, por ejemplo, elementos de menú. Por ejemplo, la siguiente línea de código establece el texto del elemento de menú para que se lea "& Now para algo completamente diferente":

    ```vb
    MPMenuItem.Text = "&& Now For Something Completely Different"
    ```

    ```csharp
    mpMenuItem.Text = "&& Now For Something Completely Different";
    ```

    ```cpp
    mpMenuItem->Text = "&& Now For Something Completely Different";
    ```

## <a name="designer"></a>Diseñador de

1. En la ventana **propiedades** de Visual Studio, establezca la propiedad **texto** del control en una cadena adecuada.

   Para crear una tecla de método abreviado subrayada, incluye una y comercial (&) delante de la letra que será la tecla de método abreviado.

2. En la ventana **propiedades** , seleccione el botón de puntos suspensivos (![botón de puntos suspensivos (...) en el ventana Propiedades de Visual Studio](./media/visual-studio-ellipsis-button.png)) junto a la propiedad **Font** .

   En el cuadro de diálogo fuente estándar, seleccione la fuente, el estilo de fuente, el tamaño, los efectos (como tachado o subrayado) y el script que desee.

## <a name="see-also"></a>Vea también

- <xref:System.Windows.Forms.Control.Text%2A?displayProperty=nameWithType>
- [Crear teclas de acceso para controles de Windows Forms](how-to-create-access-keys-for-windows-forms-controls.md)
- [Responder a clics de botones en Windows Forms](how-to-respond-to-windows-forms-button-clicks.md)
