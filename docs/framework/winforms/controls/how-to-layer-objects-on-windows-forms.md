---
title: para objetos de capa
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- Windows Forms controls, layering
- controls [Windows Forms], layering
- z order
- controls [Windows Forms], positioning
- z-order
ms.assetid: 1acc4281-2976-4715-86f4-bda68134baaf
author: jillre
ms.author: jillfra
manager: jillfra
ms.openlocfilehash: 1615b9c4df222edd95cda9bceae622ba6f1d8d78
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/24/2020
ms.locfileid: "76736345"
---
# <a name="how-to-layer-objects-on-windows-forms"></a>Cómo: disponer objetos en capas en Windows Forms

Cuando se crea una interfaz de usuario compleja, o cuando se trabaja con un formulario de interfaz de múltiples documentos (MDI), a menudo se desea disponer en capas los controles y los formularios secundarios para crear interfaces de usuario (UI) más complejas. Para trasladar y realizar un seguimiento de los controles y ventanas dentro del contexto de un grupo, puede manipular su *orden z*. El orden z es el nivel visual de los controles en un formulario a lo largo del eje z (profundidad) del formulario. La ventana situada en la parte superior del orden z se superpone a todas las demás ventanas. Todas las demás ventanas se superponen a la ventana en la parte inferior del orden z.

## <a name="to-layer-controls-at-design-time"></a>Para capas de controles en tiempo de diseño

1. En Visual Studio, seleccione un control que desee capas.

2. En el menú **formato** , seleccione **pedido**y, a continuación, seleccione **traer al frente** o **enviar al fondo**.

## <a name="to-layer-controls-programmatically"></a>Para capas de controles mediante programación

Utilice los métodos <xref:System.Windows.Forms.Control.BringToFront%2A> y <xref:System.Windows.Forms.Control.SendToBack%2A> para manipular el orden z de los controles.

Por ejemplo, si un control de <xref:System.Windows.Forms.TextBox>, `txtFirstName`, está debajo de otro control y desea que esté en primer lugar, use el código siguiente:

```vb
txtFirstName.BringToFront()
```

```csharp
txtFirstName.BringToFront();
```

```cpp
txtFirstName->BringToFront();
```

> [!NOTE]
> Windows Forms admite la *contención de controles*. La contención de controles implica la colocación de varios controles dentro de un control contenedor, como varios controles <xref:System.Windows.Forms.RadioButton> dentro de un control <xref:System.Windows.Forms.GroupBox>. A continuación, puede disponer los controles en el control contenedor. Al mover el cuadro de grupo también se mueven los controles, ya que están incluidos en él.

## <a name="see-also"></a>Vea también

- [Controles de formularios Windows Forms](index.md)
- [Asignar etiquetas a controles individuales de formularios Windows Forms y proporcionar accesos directos a los mismos](labeling-individual-windows-forms-controls-and-providing-shortcuts-to-them.md)
- [Controles que se utilizan en Windows Forms](controls-to-use-on-windows-forms.md)
- [Controles de formularios Windows Forms por función](windows-forms-controls-by-function.md)
