---
title: Procedimiento para crear teclas de acceso para controles de formularios Windows Forms mediante el diseñador
ms.date: 03/30/2017
helpviewer_keywords:
- controls [Windows Forms], access keys
- Button control [Windows Forms], access keys
- dialog box controls [Windows Forms], mnemonics
- access keys [Windows Forms], creating for controls
- mnemonics [Windows Forms], adding to dialog box controls
- ampersand character in shortcut key
- Windows Forms controls, access keys
- examples [Windows Forms], controls
- Text property [Windows Forms], specifying access keys for controls
- keyboard shortcuts [Windows Forms], creating for controls
- access keys [Windows Forms], Windows Forms
- ALT key
ms.assetid: 4c374c4c-4ca9-4a68-ac96-9dc3ab0f518a
ms.openlocfilehash: 01bed04483702ba2e62162b675aa1138bc1b0e01
ms.sourcegitcommit: cf9515122fce716bcfb6618ba366e39b5a2eb81e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/15/2019
ms.locfileid: "69039520"
---
# <a name="how-to-create-access-keys-for-windows-forms-controls-using-the-designer"></a>Procedimiento para crear teclas de acceso para controles de formularios Windows Forms mediante el diseñador
Una *tecla de acceso* es un carácter subrayado en el texto de un menú, un elemento de menú o la etiqueta de un control, como un botón. Permite al usuario "hacer clic" en un botón presionando la tecla ALT en combinación con la tecla de acceso predefinida. Por ejemplo, si un botón ejecuta un procedimiento para imprimir un formulario y, por tanto `Text` , su propiedad se establece en "Imprimir", agregar un símbolo de y comercial (&) antes de la letra "p" hace que la letra "p" esté subrayada en el texto del botón en tiempo de ejecución. El usuario puede ejecutar el comando asociado al botón presionando ALT + P. No puede tener una tecla de acceso para un control que no puede recibir el foco.

## <a name="to-create-an-access-key-for-a-control"></a>Para crear una tecla de acceso para un control

1. En la ventana **propiedades** , establezca la `Text` propiedad en una cadena que incluya una y comercial (&) delante de la letra que será la tecla de acceso. Por ejemplo, para establecer la letra "P" como tecla de acceso, escriba **& imprimir** en la cuadrícula.

## <a name="see-also"></a>Vea también

- <xref:System.Windows.Forms.Button>
- [Cómo: Responder a clics de botón de Windows Forms](how-to-respond-to-windows-forms-button-clicks.md)
- [Cómo: Establecer el texto mostrado por un control de Windows Forms](how-to-set-the-text-displayed-by-a-windows-forms-control.md)
- [Asignar etiquetas a controles individuales de formularios Windows Forms y proporcionar accesos directos a los mismos](labeling-individual-windows-forms-controls-and-providing-shortcuts-to-them.md)
