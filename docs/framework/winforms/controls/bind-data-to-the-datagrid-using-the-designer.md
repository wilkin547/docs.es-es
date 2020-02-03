---
title: Enlazar datos al control DataGridView mediante el diseñador
ms.date: 03/30/2017
helpviewer_keywords:
- Windows Forms controls, binding to a data source
- data sources [Windows Forms], binding to Windows Forms controls
- DataGridView control [Windows Forms], data binding
ms.assetid: f4f46009-cec2-441b-8668-6b5af057558b
ms.openlocfilehash: d5fab6acc53e5b8be247e958bdba78f0d3647fdc
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/24/2020
ms.locfileid: "76744118"
---
# <a name="how-to-bind-data-to-the-windows-forms-datagridview-control-using-the-designer"></a>Cómo: Enlazar datos al control DataGridView de formularios Windows Forms mediante el diseñador
Puede usar el diseñador para conectar un control de <xref:System.Windows.Forms.DataGridView> a orígenes de datos de varias variedades diferentes, como bases de datos, objetos comerciales o servicios Web. Al enlazar el control a un origen de datos mediante el diseñador, el control se enlaza automáticamente a un <xref:System.Windows.Forms.BindingSource> componente que representa el origen de datos. Además, las columnas se generan automáticamente en el control para coincidir con la información del esquema proporcionada por el origen de datos.

 Después de generar las columnas, puede modificarlas para satisfacer sus necesidades. Por ejemplo, puede quitar u ocultar aquellas columnas que no desee mostrar, puede reorganizar las columnas o puede modificar los tipos de columna. Para más información sobre la modificación de columnas, consulte los temas mostrados en la sección Vea también.

 También puede enlazar varios controles <xref:System.Windows.Forms.DataGridView> a las tablas relacionadas para crear relaciones principal-detalle. En esta configuración, un control muestra una tabla primaria y otro control muestra solo aquellas filas de una tabla secundaria que están relacionadas con la fila actual de la tabla primaria. Para más información, consulte [Cómo: Mostrar datos relacionados en una aplicación de Windows Forms](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/57tx3hhe(v=vs.120)).

 El procedimiento siguiente requiere un proyecto de **aplicación Windows** con un formulario que contenga un control <xref:System.Windows.Forms.DataGridView> o dos controles para una relación principal-detalle. Para obtener información sobre cómo iniciar este tipo de proyecto, vea [Cómo: crear un proyecto de aplicación de Windows Forms](/visualstudio/ide/step-1-create-a-windows-forms-application-project) y [Cómo: agregar controles a Windows Forms](how-to-add-controls-to-windows-forms.md).

## <a name="to-bind-the-control-to-a-data-source"></a>Para enlazar el control a un origen de datos

1. Haga clic en el glifo de etiqueta inteligente (![glifo de etiqueta inteligente](./media/vs-winformsmttagglyph.gif "VS_WinFormSmtTagGlyph")) en la esquina superior derecha del control <xref:System.Windows.Forms.DataGridView>.

2. Haga clic en la flecha de lista desplegable de la opción **Elegir origen de datos**.

3. Si su proyecto aún no tiene un origen de datos, haga clic en **Agregar origen de datos del proyecto** y siga los pasos indicados por el asistente.

     Para más información, consulte [Asistente para la configuración de orígenes de datos](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/w4dd7z6t(v=vs.120)). El nuevo origen de datos aparecerá en la ventana desplegable **Elegir origen de datos**. Si el nuevo origen de datos contiene solo un miembro, como una única tabla de base de datos, el control se enlazará automáticamente a dicho miembro. De lo contrario, continúe con el paso siguiente.

4. Expanda los nodos **Otros orígenes de datos** y **Orígenes de datos del proyecto** si aún no están expandidos y, después, seleccione el origen datos al que desea enlazar el control.

5. Si el origen de datos contiene más de un miembro, por ejemplo, si ha creado una <xref:System.Data.DataSet?displayProperty=nameWithType> que contiene varias tablas, expanda el origen de datos y, a continuación, seleccione el miembro específico al que se va a enlazar.

6. Para crear una relación principal-detalle, en la ventana desplegable **elegir origen de datos** para un segundo control de <xref:System.Windows.Forms.DataGridView>, expanda el <xref:System.Windows.Forms.BindingSource> creado para la tabla primaria y, a continuación, seleccione la tabla secundaria relacionada en la lista que se muestra.

    > [!NOTE]
    > Si el proyecto ya tiene un origen de datos, también puede usar la ventaja **Orígenes de datos** para crear un formulario de datos. Para más información, consulte [Orígenes de datos (ventana)](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/6ckyxa83(v=vs.120)).

## <a name="see-also"></a>Consulte también

- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.BindingSource>
- <xref:System.Windows.Forms.DataGridView.DataMember%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridView.DataSource%2A?displayProperty=nameWithType>
- [Cómo: Conectarse a los datos de una base de datos](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/fxk9yw1t(v=vs.120))
- [Agregar y quitar columnas en el control DataGridView de Windows Forms mediante el Diseñador](add-and-remove-columns-in-the-datagrid-using-the-designer.md)
- [Cambiar el orden de las columnas en el control DataGridView de Windows Forms mediante el Diseñador](change-the-order-of-columns-in-the-datagrid-using-the-designer.md)
- [Cambiar el tipo de una columna DataGridView de Windows Forms mediante el Diseñador](change-the-type-of-a-wf-datagridview-column-using-the-designer.md)
- [Inmovilizar columnas en el control DataGridView de Windows Forms mediante el Diseñador](freeze-columns-in-the-datagrid-using-the-designer.md)
- [Ocultar columnas en el control DataGridView de Windows Forms mediante el Diseñador](hide-columns-in-the-datagrid-using-the-designer.md)
- [Crear columnas de sólo lectura en el control DataGridView de Windows Forms mediante el Diseñador](make-columns-read-only-in-the-datagrid-using-the-designer.md)
- [Cómo: crear un proyecto de aplicación de Windows Forms](/visualstudio/ide/step-1-create-a-windows-forms-application-project)
- [Cómo: Agregar controles a Windows Forms](how-to-add-controls-to-windows-forms.md)
- [Ventana orígenes de datos](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/6ckyxa83(v=vs.120))
- [Cómo: Mostrar datos relacionados en una aplicación de Windows Forms](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/57tx3hhe(v=vs.120))
