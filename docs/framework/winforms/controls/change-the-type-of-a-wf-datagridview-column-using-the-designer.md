---
title: Cambiar el tipo de una columna DataGridView mediante el diseñador
ms.date: 03/30/2017
helpviewer_keywords:
- Windows Forms, columns
- columns [Windows Forms], types
- DataGridView control [Windows Forms], changing column type
- data [Windows Forms], displaying
ms.assetid: 7f994d45-600d-4190-a187-35803214b40c
ms.openlocfilehash: 976f257d38dc7be5c904e63da47c61486bd3301c
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/24/2020
ms.locfileid: "76737134"
---
# <a name="how-to-change-the-type-of-a-windows-forms-datagridview-column-using-the-designer"></a>Cómo: Cambiar el tipo de una columna DataGridView de formularios Windows Forms mediante el Diseñador
A veces, querrá cambiar el tipo de una columna que ya se ha agregado a un Windows Forms <xref:System.Windows.Forms.DataGridView> control. Por ejemplo, puede que desee modificar los tipos de algunas de las columnas que se generan automáticamente al enlazar el control a un origen de datos. Esto resulta útil cuando la tabla que se muestra tiene columnas que contienen claves externas en las filas de una tabla relacionada. En este caso, puede que desee reemplazar las columnas de cuadro de texto que muestran estas claves externas por columnas de cuadro combinado que muestran valores más significativos de la tabla relacionada.

 El procedimiento siguiente requiere un proyecto de **aplicación Windows** con un formulario que contenga un control <xref:System.Windows.Forms.DataGridView>. Para obtener información sobre cómo configurar este tipo de proyecto, vea [Cómo: crear un proyecto de aplicación de Windows Forms](/visualstudio/ide/step-1-create-a-windows-forms-application-project) y [Cómo: agregar controles a Windows Forms](how-to-add-controls-to-windows-forms.md).

### <a name="to-change-the-type-of-a-column-using-the-designer"></a>Para cambiar el tipo de una columna mediante el diseñador

1. Haga clic en el glifo de etiqueta inteligente (![glifo de etiqueta inteligente](./media/vs-winformsmttagglyph.gif "VS_WinFormSmtTagGlyph")) en la esquina superior derecha del control <xref:System.Windows.Forms.DataGridView> y, a continuación, seleccione **Editar columnas**.

2. Seleccione una columna de la lista **columnas seleccionadas** .

3. En la cuadrícula **propiedades de columna** , establezca la propiedad `ColumnType` en el nuevo tipo de columna.

    > [!NOTE]
    > La propiedad `ColumnType` es una propiedad de solo tiempo de diseño que indica la clase que representa el tipo de columna. No es una propiedad real definida en una clase de columna.

## <a name="see-also"></a>Vea también

- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridViewColumn>
- [Cómo: crear un proyecto de aplicación de Windows Forms](/visualstudio/ide/step-1-create-a-windows-forms-application-project)
- [Cómo: Agregar controles a Windows Forms](how-to-add-controls-to-windows-forms.md)
