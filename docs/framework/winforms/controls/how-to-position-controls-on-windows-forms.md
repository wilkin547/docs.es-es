---
title: Procedimiento para colocar controles en formularios Windows Forms
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
ms.openlocfilehash: 241edbe60c327493c9123c6cf7bdc19b7ba2b724
ms.sourcegitcommit: 0d0a6e96737dfe24d3257b7c94f25d9500f383ea
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/07/2019
ms.locfileid: "65211650"
---
# <a name="how-to-position-controls-on-windows-forms"></a>Procedimiento para colocar controles en formularios Windows Forms

Para colocar los controles, utilizar el Diseñador de Windows Forms en Visual Studio o especificar el <xref:System.Windows.Forms.Control.Location%2A> propiedad.

## <a name="position-a-control-on-the-design-surface-of-the-windows-forms-designer"></a>Colocar un control en la superficie de diseño del Diseñador de Windows Forms

En Visual Studio, arrastre el control a la ubicación adecuada con el mouse.

> [!NOTE]
> Seleccione el control y muévalo teclas con la flecha para colocarlo con más precisión. Además, *las guías de alineación* le ayudarán a colocar controles en el formulario con precisión. Para obtener más información, vea [Tutorial: Organizar controles en Windows Forms mediante líneas de ajuste](walkthrough-arranging-controls-on-windows-forms-using-snaplines.md).

## <a name="position-a-control-using-the-properties-window"></a>Colocar un control mediante la ventana Propiedades

1. En Visual Studio, haga clic en el control que desea colocar.

2. En el **propiedades** ventana, escriba valores para el <xref:System.Windows.Forms.Control.Location%2A> propiedad, separados por comas, para colocar el control dentro de su contenedor.

     El primer número (X) es la distancia desde el borde izquierdo del contenedor; el segundo número (Y) es la distancia desde el borde superior del área de contenedor, medido en píxeles.

    > [!NOTE]
    > Puede expandir el <xref:System.Windows.Forms.Control.Location%2A> propiedad al tipo el **X** y **Y** valores individualmente.

## <a name="position-a-control-programmatically"></a>Colocar un control mediante programación

1. Establecer el <xref:System.Windows.Forms.Control.Location%2A> propiedad del control a un <xref:System.Drawing.Point>.

    ```vb
    Button1.Location = New Point(100, 100)
    ```

    ```csharp
    button1.Location = new Point(100, 100);
    ```

    ```cpp
    button1->Location = Point(100, 100);
    ```

2. Cambie la coordenada X de la ubicación del control mediante la <xref:System.Windows.Forms.Control.Left%2A> subpropiedades.

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

Establecer el <xref:System.Windows.Forms.Control.Left%2A> subpropiedad para incrementar la coordenada X del control.

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
> Use el <xref:System.Windows.Forms.Control.Location%2A> propiedad para establecer un control X e Y se coloca al mismo tiempo. Para establecer una posición individualmente, utilice el control <xref:System.Windows.Forms.Control.Left%2A> (**X**) o <xref:System.Windows.Forms.Control.Top%2A> (**Y**) subpropiedades. No intente establecer implícitamente las coordenadas X e Y de la <xref:System.Drawing.Point> estructura que representa la ubicación del botón, porque esta estructura contiene una copia de las coordenadas del botón.

## <a name="see-also"></a>Vea también

- [Controles de formularios Windows Forms](index.md)
- [Tutorial: Organizar controles en formularios de Windows Forms mediante líneas de ajuste](walkthrough-arranging-controls-on-windows-forms-using-snaplines.md)
- [Tutorial: Organizar controles en formularios de Windows Forms mediante TableLayoutPanel](walkthrough-arranging-controls-on-windows-forms-using-a-tablelayoutpanel.md)
- [Tutorial: Organizar controles en formularios de Windows Forms mediante FlowLayoutPanel](walkthrough-arranging-controls-on-windows-forms-using-a-flowlayoutpanel.md)
- [Organizar controles en formularios Windows Forms](arranging-controls-on-windows-forms.md)
- [Asignar etiquetas a controles individuales de formularios Windows Forms y proporcionar accesos directos a los mismos](labeling-individual-windows-forms-controls-and-providing-shortcuts-to-them.md)
- [Controles que se utilizan en formularios Windows Forms](controls-to-use-on-windows-forms.md)
- [Controles de formularios Windows Forms por función](windows-forms-controls-by-function.md)
- [Cómo: Establecer la ubicación de pantalla de Windows Forms](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/52aha046(v=vs.100))
