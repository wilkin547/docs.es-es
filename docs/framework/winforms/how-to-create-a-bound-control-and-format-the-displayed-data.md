---
title: Procedimiento para crear un control enlazado y aplicar formato a los datos mostrados
ms.date: 03/30/2017
helpviewer_keywords:
- data [Windows Forms], formatting
- bound controls [Windows Forms], creating
- bound controls [Windows Forms], formatting data
ms.assetid: d5a56228-899d-41d9-8af8-87b3f4ec2f94
ms.openlocfilehash: 052e619acb23fb2e25f42daf7b4eaaacb0688f31
ms.sourcegitcommit: cf9515122fce716bcfb6618ba366e39b5a2eb81e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/15/2019
ms.locfileid: "69039424"
---
# <a name="how-to-create-a-bound-control-and-format-the-displayed-data"></a>Procedimiento para crear un control enlazado y aplicar formato a los datos mostrados

Con Windows Forms enlace de datos, puede dar formato a los datos mostrados en un control enlazado a datos mediante el cuadro de diálogo **formato y enlace avanzado** .


### <a name="to-bind-a-control-and-format-the-displayed-data"></a>Para enlazar un control y dar formato a los datos mostrados

1. Conéctese a un origen de datos.

     Para obtener más información, vea [conectarse a un origen de datos](../data/adonet/connecting-to-a-data-source.md).

2. En el formulario, seleccione el control y, después, abra la ventana Propiedades.

3. Expanda la propiedad **(DataBindings)** y, a continuación, en el cuadro **(avanzado)** , haga clic en el![botón de puntos suspensivos (el botón de puntos suspensivos (...)](./media/how-to-create-a-bound-control-and-format-the-displayed-data/visual-studio-ellipsis-button.png)en el ventana Propiedades de Visual Studio) para mostrar el **formato y opciones avanzadas.** Cuadro de diálogo de enlace, que tiene una lista completa de las propiedades de ese control.

4. Seleccione la propiedad que desea enlazar y, a continuación, haga clic en la flecha de **enlace** .

     Se muestra una lista de los orígenes de datos disponibles.

5. Expanda el origen de datos al que desea enlazar hasta que encuentre el elemento de datos que desea.

     Por ejemplo, si va a enlazar a un valor de columna en la tabla de un conjunto de datos, expanda el nombre del conjunto de datos y, después, expanda el nombre de la tabla para mostrar los nombres de columna.

6. Haga clic en el nombre del elemento al que se va a enlazar.

7. En el cuadro **tipo de formato** , haga clic en el formato que desea aplicar a los datos mostrados en el control.

     En cada caso, puede especificar el valor mostrado en el control si el origen de datos contiene <xref:System.DBNull>. De lo contrario, las opciones varían ligeramente, dependiendo del tipo de formato que elija. En la siguiente tabla se muestran los tipos de formato y las opciones.

    |Tipo de formato|Opción de formato|
    |-----------------|-----------------------|
    |Sin formato|No hay opciones.|
    |Numeric|Especifique el número de posiciones decimales mediante el control de flechas de **posiciones** decimales.|
    |Currency|Especifique el número de posiciones decimales mediante el control de flechas de **posiciones** decimales.|
    |Fecha Hora|Seleccione el modo en que se debe mostrar la fecha y la hora seleccionando uno de los elementos en el cuadro de selección **tipo** .|
    |Científica|Especifique el número de posiciones decimales mediante el control de flechas de **posiciones** decimales.|
    |Personalizados|Especifique una cadena de formato personalizado using.<br /><br /> Para obtener más información, consulte [Aplicar formato a tipos](../../standard/base-types/formatting-types.md). **Nota:**  No se garantiza que las cadenas de formato personalizado realicen correctamente el recorrido de ida y vuelta entre el origen de datos y el control enlazado. En su lugar, controle el evento <xref:System.Windows.Forms.Binding.Parse> o <xref:System.Windows.Forms.Binding.Format> del enlace y aplique el formato personalizado en el código de control de eventos.|

8. Haga clic en **Aceptar** para cerrar el cuadro de diálogo **formato y enlace avanzado** y volver al ventana Propiedades.

## <a name="see-also"></a>Vea también

- [Cómo: Crear un control de enlace simple en Windows Forms](how-to-create-a-simple-bound-control-on-a-windows-form.md)
- [Validación de los datos proporcionados por el usuario Windows Forms](user-input-validation-in-windows-forms.md)
- [Enlace de datos en Windows Forms](windows-forms-data-binding.md)
