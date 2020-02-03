---
title: para controles de posición
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
ms.openlocfilehash: 144a0021c74f0fb5afec1d511315168fb28528e9
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/24/2020
ms.locfileid: "76735912"
---
# <a name="how-to-position-controls-on-windows-forms"></a>Cómo: colocar controles en Windows Forms

Para colocar controles, use el Diseñador de Windows Forms en Visual Studio o especifique la propiedad <xref:System.Windows.Forms.Control.Location%2A>.

## <a name="position-a-control-on-the-design-surface-of-the-windows-forms-designer"></a>Colocar un control en la superficie de diseño del Diseñador de Windows Forms

En Visual Studio, arrastre el control hasta la ubicación adecuada con el mouse.

> [!NOTE]
> Seleccione el control y muévalo con las teclas de dirección para colocarlo con más precisión. Además, las *guías de alineación* le ayudan a colocar controles con precisión en el formulario. Para obtener más información, vea [Tutorial: organizar controles en Windows Forms mediante líneas de ajuste](walkthrough-arranging-controls-on-windows-forms-using-snaplines.md).

## <a name="position-a-control-using-the-properties-window"></a>Colocar un control mediante el ventana Propiedades

1. En Visual Studio, seleccione el control que desea colocar.

2. En la ventana **propiedades** , escriba valores para la propiedad <xref:System.Windows.Forms.Control.Location%2A>, separados por una coma, para colocar el control dentro de su contenedor.

   El primer número (X) es la distancia desde el borde izquierdo del contenedor. el segundo número (Y) es la distancia desde el borde superior del área de contenedor, medido en píxeles.

   > [!NOTE]
   > Puede expandir la propiedad <xref:System.Windows.Forms.Control.Location%2A> para escribir los valores **X** e **y individualmente** .

## <a name="position-a-control-programmatically"></a>Colocar un control mediante programación

1. Establezca la propiedad <xref:System.Windows.Forms.Control.Location%2A> del control en un <xref:System.Drawing.Point>.

    ```vb
    Button1.Location = New Point(100, 100)
    ```

    ```csharp
    button1.Location = new Point(100, 100);
    ```

    ```cpp
    button1->Location = Point(100, 100);
    ```

2. Cambie la coordenada X de la ubicación del control mediante la subpropiedad <xref:System.Windows.Forms.Control.Left%2A>.

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

Establezca la subpropiedad <xref:System.Windows.Forms.Control.Left%2A> para incrementar la coordenada X del control.

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
> Use la propiedad <xref:System.Windows.Forms.Control.Location%2A> para establecer simultáneamente las posiciones X e y de un control. Para establecer una posición individualmente, use la subpropiedad <xref:System.Windows.Forms.Control.Left%2A> (**X**) o <xref:System.Windows.Forms.Control.Top%2A> (**Y**) del control. No intente establecer implícitamente las coordenadas X e y de la estructura <xref:System.Drawing.Point> que representa la ubicación del botón, porque esta estructura contiene una copia de las coordenadas del botón.

## <a name="see-also"></a>Consulte también

- [Controles de Windows Forms](index.md)
- [Tutorial: Organizar controles en formularios Windows Forms mediante líneas de ajuste](walkthrough-arranging-controls-on-windows-forms-using-snaplines.md)
- [Tutorial: Organizar controles en Windows Forms mediante TableLayoutPanel](walkthrough-arranging-controls-on-windows-forms-using-a-tablelayoutpanel.md)
- [Tutorial: Organizar controles en Windows Forms mediante FlowLayoutPanel](walkthrough-arranging-controls-on-windows-forms-using-a-flowlayoutpanel.md)
- [Asignar etiquetas a controles individuales de formularios Windows Forms y proporcionar accesos directos a los mismos](labeling-individual-windows-forms-controls-and-providing-shortcuts-to-them.md)
- [Controles que se utilizan en formularios Windows Forms](controls-to-use-on-windows-forms.md)
- [Controles de formularios Windows Forms por función](windows-forms-controls-by-function.md)
- [Cómo: establecer la ubicación de la pantalla de Windows Forms](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/52aha046(v=vs.100))
