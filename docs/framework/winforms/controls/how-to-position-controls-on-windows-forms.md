---
title: para controles de posición
description: Obtenga información sobre cómo usar el Diseñador de Windows Forms en Visual Studio o la propiedad Location para colocar los controles.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
f1_keywords:
- Location
- Location.Y
- Location.X
helpviewer_keywords:
- controls [Windows Forms]
- controls [Windows Forms], moving
- snaplines
- controls [Windows Forms], positioning
ms.assetid: 4693977e-34a4-4f19-8221-68c3120c2b2b
author: jillre
ms.author: jillfra
manager: jillfra
ms.openlocfilehash: 0aa3faade71e0f7e0a9d5e676327a80747524b8c
ms.sourcegitcommit: 3824ff187947572b274b9715b60c11269335c181
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/17/2020
ms.locfileid: "84904304"
---
# <a name="how-to-position-controls-on-windows-forms"></a>Cómo: colocar controles en Windows Forms

Para colocar controles, use el Diseñador de Windows Forms en Visual Studio o especifique la <xref:System.Windows.Forms.Control.Location%2A> propiedad.

## <a name="position-a-control-on-the-design-surface-of-the-windows-forms-designer"></a>Colocar un control en la superficie de diseño del Diseñador de Windows Forms

En Visual Studio, arrastre el control hasta la ubicación adecuada con el mouse.

> [!NOTE]
> Seleccione el control y muévalo con las teclas de dirección para colocarlo con más precisión. Además, las *guías de alineación* le ayudan a colocar controles con precisión en el formulario. Para obtener más información, vea [Tutorial: organizar controles en Windows Forms mediante líneas de ajuste](walkthrough-arranging-controls-on-windows-forms-using-snaplines.md).

## <a name="position-a-control-using-the-properties-window"></a>Colocar un control mediante el ventana Propiedades

1. En Visual Studio, seleccione el control que desea colocar.

2. En la ventana **propiedades** , escriba valores para la <xref:System.Windows.Forms.Control.Location%2A> propiedad, separados por una coma, para colocar el control dentro de su contenedor.

   El primer número (X) es la distancia desde el borde izquierdo del contenedor. el segundo número (Y) es la distancia desde el borde superior del área de contenedor, medido en píxeles.

   > [!NOTE]
   > Puede expandir la <xref:System.Windows.Forms.Control.Location%2A> propiedad para escribir los valores **X** e **y** individualmente.

## <a name="position-a-control-programmatically"></a>Colocar un control mediante programación

1. Establezca la <xref:System.Windows.Forms.Control.Location%2A> propiedad del control en <xref:System.Drawing.Point> .

    ```vb
    Button1.Location = New Point(100, 100)
    ```

    ```csharp
    button1.Location = new Point(100, 100);
    ```

    ```cpp
    button1->Location = Point(100, 100);
    ```

2. Cambie la coordenada X de la ubicación del control mediante la <xref:System.Windows.Forms.Control.Left%2A> subpropiedad.

    ```vb
    Button1.Left = 300
    ```

    ```csharp
    button1.Left = 300;
    ```

    ```cpp
    button1->Left = 300;
    ```

## <a name="increment-a-controls-location-programmatically"></a>Incrementar la ubicación de un control mediante programación

Establezca la <xref:System.Windows.Forms.Control.Left%2A> subpropiedad para incrementar la coordenada X del control.

```vb
Button1.Left += 200
```

```csharp
button1.Left += 200;
```

```cpp
button1->Left += 200;
```

> [!NOTE]
> Utilice la <xref:System.Windows.Forms.Control.Location%2A> propiedad para establecer las posiciones X e y de un control simultáneamente. Para establecer una posición individualmente, use la <xref:System.Windows.Forms.Control.Left%2A> subpropiedad del control (**X**) o <xref:System.Windows.Forms.Control.Top%2A> (**Y**). No intente establecer implícitamente las coordenadas X e y de la <xref:System.Drawing.Point> estructura que representa la ubicación del botón, ya que esta estructura contiene una copia de las coordenadas del botón.

## <a name="see-also"></a>Consulte también

- [Windows Forms controles](index.md)
- [Tutorial: Organizar controles en formularios Windows Forms mediante líneas de ajuste](walkthrough-arranging-controls-on-windows-forms-using-snaplines.md)
- [Tutorial: Organizar controles en formularios Windows Forms mediante TableLayoutPanel](walkthrough-arranging-controls-on-windows-forms-using-a-tablelayoutpanel.md)
- [Tutorial: Organizar controles en formularios Windows Forms mediante FlowLayoutPanel](walkthrough-arranging-controls-on-windows-forms-using-a-flowlayoutpanel.md)
- [Asignar etiquetas a controles individuales de formularios Windows Forms y proporcionar accesos directos a los mismos](labeling-individual-windows-forms-controls-and-providing-shortcuts-to-them.md)
- [Controles que se utilizan en formularios Windows Forms](controls-to-use-on-windows-forms.md)
- [Controles de formularios Windows Forms por función](windows-forms-controls-by-function.md)
- [Cómo: Establecer la ubicación en pantalla de formularios Windows Forms](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/52aha046(v=vs.100))
