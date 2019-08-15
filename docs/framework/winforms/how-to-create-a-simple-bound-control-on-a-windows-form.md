---
title: Procedimiento para crear un control con enlace simple en formularios Windows Forms
ms.date: 03/30/2017
helpviewer_keywords:
- data binding [Windows Forms], simple data binding
- Windows Forms controls, data binding
ms.assetid: 3bcaded8-0f1a-4cc0-8830-f59be253bf4e
ms.openlocfilehash: ed1d0e423a3cdf77a242ec3214720f1466f65897
ms.sourcegitcommit: cf9515122fce716bcfb6618ba366e39b5a2eb81e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/15/2019
ms.locfileid: "69039504"
---
# <a name="how-to-create-a-simple-bound-control-on-a-windows-form"></a>Procedimiento para crear un control con enlace simple en formularios Windows Forms

Con el *enlace simple*, puede mostrar un único elemento de datos, como un valor de columna de una tabla de conjunto de datos, en un control. Puede enlazar de forma sencilla cualquier propiedad de un control con un valor de datos.

### <a name="to-simple-bind-a-control"></a>Para enlazar un control de forma simple

1. Conéctese a un origen de datos. Para obtener más información, vea [conectarse a un origen de datos](../data/adonet/connecting-to-a-data-source.md).

2. En el formulario, seleccione el control y muestre la ventana **propiedades** .

3. Expanda la propiedad **(DataBindings)** .

     Las propiedades que se enlazan con mayor frecuencia se muestran debajo de la propiedad **(DataBindings)** . Por ejemplo, en la mayoría de los controles, la propiedad de **texto** se enlaza con mayor frecuencia.

4. Si la propiedad que desea enlazar no es una de las propiedades enlazadas normalmente, haga clic en el![botón de **puntos suspensivos** (el botón de puntos suspensivos (...)](./media/how-to-create-a-simple-bound-control-on-a-windows-form/visual-studio-ellipsis-button.png)en el ventana Propiedades de Visual Studio) en el cuadro **(avanzado)** para mostrar el  **Cuadro de diálogo formato y enlace avanzado** con una lista completa de las propiedades de ese control.

5. Seleccione la propiedad que desea enlazar y haga clic en la flecha desplegable situada debajo de **enlace**.

     Se muestra una lista de los orígenes de datos disponibles.

6. Expanda el origen de datos al que desea enlazar hasta que encuentre el elemento de datos que desea. Por ejemplo, si va a enlazar a un valor de columna en la tabla de un conjunto de datos, expanda el nombre del conjunto de datos y, después, expanda el nombre de la tabla para mostrar los nombres de columna.

7. Haga clic en el nombre del elemento al que se va a enlazar.

8. Si está trabajando en el cuadro de diálogo **formato y enlace avanzado** , haga clic en **Aceptar** para volver a la ventana **propiedades** .

9. Si desea enlazar propiedades adicionales del control, repita los pasos del 3 al 7.

    > [!NOTE]
    > Dado que los controles enlazados simples solo muestran un único elemento de datos, es muy habitual incluir la lógica de navegación en Windows Forms con controles enlazados de forma simple.

## <a name="see-also"></a>Vea también

- <xref:System.Windows.Forms.Binding>
- [Enlace de datos en Windows Forms](windows-forms-data-binding.md)
- [Enlace de datos y Windows Forms](data-binding-and-windows-forms.md)
