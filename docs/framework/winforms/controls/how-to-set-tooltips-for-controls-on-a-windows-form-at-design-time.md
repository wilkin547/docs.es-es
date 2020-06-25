---
title: Procedimiento para establecer información sobre herramientas en controles de formularios Windows Forms en tiempo de diseño
description: Obtenga información sobre cómo establecer la información sobre herramientas para los controles mediante programación o en el Diseñador de Windows Forms en Visual Studio.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- tooltips [Windows Forms], for controls
- examples [Windows Forms], tooltips
ms.assetid: c4b60637-4c0a-44c2-a103-f66dff887936
ms.openlocfilehash: 15134b38d11de30d0e6a2f998f6ea266affc40d7
ms.sourcegitcommit: dc2feef0794cf41dbac1451a13b8183258566c0e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/24/2020
ms.locfileid: "85325971"
---
# <a name="how-to-set-tooltips-for-controls-on-a-windows-form-at-design-time"></a>Cómo: establecer la información sobre herramientas para los controles de Windows Forms en tiempo de diseño

Puede establecer una <xref:System.Windows.Forms.ToolTip> cadena en el código o en el diseñador de Windows Forms en Visual Studio. Para obtener más información sobre el <xref:System.Windows.Forms.ToolTip> componente, vea información general sobre los [componentes de información sobre herramientas](tooltip-component-overview-windows-forms.md).

## <a name="set-a-tooltip-programmatically"></a>Establecer una información sobre herramientas mediante programación

1. Agregue el control que mostrará la información sobre herramientas.

2. Use el <xref:System.Windows.Forms.ToolTip.SetToolTip%2A> método del <xref:System.Windows.Forms.ToolTip> componente.

    ```vb
    ' In this example, Button1 is the control to display the ToolTip.
    ToolTip1.SetToolTip(Button1, "Save changes")
    ```

    ```csharp
    // In this example, button1 is the control to display the ToolTip.
    toolTip1.SetToolTip(button1, "Save changes");
    ```

    ```cpp
    // In this example, button1 is the control to display the ToolTip.
    toolTip1->SetToolTip(button1, "Save changes");
    ```

## <a name="set-a-tooltip-in-the-designer"></a>Establecer una información sobre herramientas en el diseñador

1. En Visual Studio, agregue un <xref:System.Windows.Forms.ToolTip> componente al formulario.

2. Seleccione el control que mostrará la información sobre herramientas o agréguelo al formulario.

3. En la ventana **propiedades** , establezca la **información sobre herramientas en** el valor ToolTip1 en una cadena de texto adecuada.

### <a name="to-remove-a-tooltip-programmatically"></a>Para quitar una información sobre herramientas mediante programación

1. Use el <xref:System.Windows.Forms.ToolTip.SetToolTip%2A> método del <xref:System.Windows.Forms.ToolTip> componente.

    ```vb
    ' In this example, Button1 is the control displaying the ToolTip.
    ToolTip1.SetToolTip(Button1, Nothing)
    ```

    ```csharp
    // In this example, button1 is the control displaying the ToolTip.
    toolTip1.SetToolTip(button1, null);
    ```

    ```cpp
    // In this example, button1 is the control displaying the ToolTip.
    toolTip1->SetToolTip(button1, NULL);
    ```

## <a name="remove-a-tooltip-in-the-designer"></a>Quitar una información sobre herramientas en el diseñador

1. En Visual Studio, seleccione el control que muestra la información sobre herramientas.

2. En la ventana **propiedades** , elimine el texto de la **información sobre herramientas en ToolTip1**.

## <a name="see-also"></a>Vea también

- [Información general sobre el componente ToolTip](tooltip-component-overview-windows-forms.md)
- [Procedimiento para cambiar el retardo del componente ToolTip de formularios Windows Forms](how-to-change-the-delay-of-the-windows-forms-tooltip-component.md)
- [ToolTip](tooltip-component-windows-forms.md)
