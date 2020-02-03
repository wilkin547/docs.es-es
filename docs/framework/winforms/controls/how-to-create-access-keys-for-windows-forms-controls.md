---
title: Crear claves de acceso para controles
ms.date: 08/20/2019
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
ms.openlocfilehash: 7f6b0a5838cacfc1189fba819a54b3423d567ea0
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/24/2020
ms.locfileid: "76731170"
---
# <a name="how-to-create-access-keys-for-windows-forms-controls"></a>Cómo: crear teclas de acceso para controles de Windows Forms

Una *tecla de acceso* es un carácter subrayado en el texto de un menú, un elemento de menú o la etiqueta de un control, como un botón. Con una tecla de acceso, el usuario puede hacer clic en un botón presionando la tecla Alt junto con la tecla de acceso predefinida. Por ejemplo, si un botón ejecuta un procedimiento para imprimir un formulario y, por tanto, su propiedad `Text` está establecida en "Imprimir", agregar un símbolo de y comercial antes de la letra "P" hace que la letra "P" esté subrayada en el texto del botón en tiempo de ejecución. El usuario puede ejecutar el comando asociado al botón presionando Alt + P.

Los controles que no pueden recibir el foco no pueden tener claves de acceso.

## <a name="programmatic"></a>Programático

Establezca la propiedad `Text` en una cadena que incluya una y comercial (&) delante de la letra que será el método abreviado.

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
> Para usar una y comercial en un título sin crear una tecla de acceso, incluya dos símbolos de y comercial (& &). Se muestra un carácter de y comercial único en el título y no hay ningún carácter subrayado.

## <a name="designer"></a>Diseñador

En la ventana **propiedades** de Visual Studio, establezca la propiedad **texto** en una cadena que incluya una y comercial (' & ') delante de la letra que será la tecla de acceso. Por ejemplo, para establecer la letra "P" como tecla de acceso, escriba **& imprimir**.

## <a name="see-also"></a>Consulte también

- <xref:System.Windows.Forms.Button>
- [Responder a clics de botones en Windows Forms](how-to-respond-to-windows-forms-button-clicks.md)
- [Establecer el texto mostrado por un control de Windows Forms](how-to-set-the-text-displayed-by-a-windows-forms-control.md)
- [Asignar etiquetas a controles individuales de formularios Windows Forms y proporcionar accesos directos a los mismos](labeling-individual-windows-forms-controls-and-providing-shortcuts-to-them.md)
