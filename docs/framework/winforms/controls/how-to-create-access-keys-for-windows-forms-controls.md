---
title: Filtrar para crear teclas de acceso para controles de Windows Forms
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- controls [Windows Forms], access keys
- Button control [Windows Forms], access keys
- dialog box controls [Windows Forms], mnemonics
- access keys [Windows Forms], creating for controls
- mnemonics [Windows Forms], adding to dialog box controls
- mnemonics
- ampersand character in shortcut key
- Windows Forms controls, access keys
- examples [Windows Forms], controls
- Text property [Windows Forms], specifying access keys for controls
- keyboard shortcuts [Windows Forms], creating for controls
- access keys [Windows Forms], Windows Forms
- ALT key
ms.assetid: 4faa0991-28ec-4eca-91db-51dc2cd6a7ac
ms.openlocfilehash: fefd322afb938453ec1ea23e8ff6de9f9ae2a851
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59141640"
---
# <a name="how-to-create-access-keys-for-windows-forms-controls"></a>Filtrar para crear teclas de acceso para controles de Windows Forms
Un *clave de acceso* es un carácter subrayado en el texto de un menú, elemento de menú o la etiqueta de un control como un botón. Con una clave de acceso, el usuario puede "haga clic en" un botón presionando la tecla ALT en combinación con la clave de acceso predefinidas. Por ejemplo, si un botón ejecuta un procedimiento para imprimir un formulario y por lo tanto, su `Text` propiedad está establecida en "Print", agregar una y comercial antes de la letra "P" hace que la letra "P" para subrayada en el texto del botón en tiempo de ejecución. El usuario puede ejecutar el comando asociado con el botón presionando ALT + P. No puede tener una clave de acceso para un control que no se puede recibir el foco.  
  
### <a name="to-create-an-access-key-for-a-control"></a>Para crear una clave de acceso para un control  
  
1.  Establecer el `Text` propiedad en una cadena que incluye una y comercial (&) delante de la letra que será el acceso directo.  
  
    ```vb  
    ' Set the letter "P" as an access key.  
    Button1.Text = "&Print"  
    ```  
  
    ```csharp  
    // Set the letter "P" as an access key.  
    button1.Text = "&Print";  
    ```  
  
    ```cpp  
    // Set the letter "P" as an access key.  
    button1->Text = "&Print";  
    ```  
  
    > [!NOTE]
    >  Para incluir una y comercial en un título sin crear una clave de acceso, incluya dos símbolos de y comercial (& &). Un solo carácter & se muestra en la leyenda y no está subrayados ningún carácter.  
  
## <a name="see-also"></a>Vea también

- <xref:System.Windows.Forms.Button>
- [Filtrar para responder a clics de botones en formularios Windows Forms](how-to-respond-to-windows-forms-button-clicks.md)
- [Filtrar para establecer el texto mostrado por un control de formularios Windows Forms](how-to-set-the-text-displayed-by-a-windows-forms-control.md)
- [Asignar etiquetas a controles individuales de formularios Windows Forms y proporcionar accesos directos a los mismos](labeling-individual-windows-forms-controls-and-providing-shortcuts-to-them.md)
