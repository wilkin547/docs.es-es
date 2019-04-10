---
title: Filtrar para enlazar el control DataGrid de formularios Windows Forms a un origen de datos mediante el diseñador
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- datasets [Windows Forms], binding to DataGrid control
- data binding [Windows Forms], DataGrid control
- DataGrid control [Windows Forms], data binding
- Windows Forms controls, data binding
- bound controls [Windows Forms]
ms.assetid: 4e96e3d0-b1cc-4de1-8774-bc9970ec4554
ms.openlocfilehash: fe54c650e1d19f36d681053c7da47e12527c5827
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/09/2019
ms.locfileid: "59320891"
---
# <a name="how-to-bind-the-windows-forms-datagrid-control-to-a-data-source-using-the-designer"></a>Filtrar para enlazar el control DataGrid de formularios Windows Forms a un origen de datos mediante el diseñador

> [!NOTE]
>  El control <xref:System.Windows.Forms.DataGridView> reemplaza y agrega funcionalidad al control <xref:System.Windows.Forms.DataGrid>; sin embargo, el control <xref:System.Windows.Forms.DataGrid> se conserva a efectos de compatibilidad con versiones anteriores y uso futuro, en su caso. Para obtener más información, consulte [Differences Between the Windows Forms DataGridView and DataGrid Controls](differences-between-the-windows-forms-datagridview-and-datagrid-controls.md) (Diferencias entre los controles DataGridView y DataGrid de formularios Windows Forms).  
  
 Los formularios de Windows <xref:System.Windows.Forms.DataGrid> control está diseñado específicamente para mostrar información de un origen de datos. Enlazar el control en tiempo de diseño estableciendo el <xref:System.Windows.Forms.DataGrid.DataSource%2A> y <xref:System.Windows.Forms.DataGrid.DataMember%2A> propiedades, o en tiempo de ejecución mediante una llamada a la <xref:System.Windows.Forms.DataGrid.SetDataBinding%2A> método. Aunque se pueden mostrar datos desde una variedad de orígenes de datos, los orígenes más habituales son las vistas de datos y conjuntos de datos.  
  
 Si el origen de datos está disponible en tiempo de diseño, por ejemplo, si el formulario contiene una instancia de un conjunto de datos o una vista de datos, puede enlazar la cuadrícula al origen de datos en tiempo de diseño. A continuación, puede ver qué aspecto tendrá los datos en la cuadrícula.  
  
 También puede enlazar mediante programación, la cuadrícula en tiempo de ejecución. Esto es útil cuando desea establecer un origen de datos basado en información que se obtiene en tiempo de ejecución. Por ejemplo, la aplicación puede que el usuario especifique el nombre de tabla que desea ver. También es necesario en situaciones donde el origen de datos no existe en tiempo de diseño. Esto incluye los orígenes de datos, como lectores de datos, conjuntos de datos sin tipo, colecciones y matrices.  
  
 El procedimiento siguiente requiere una **aplicación Windows** proyecto con un formulario que contenga un <xref:System.Windows.Forms.DataGrid> control. Para obtener información acerca de cómo configurar un proyecto de este tipo, vea [Cómo: Cree un proyecto de aplicación de Windows Forms](/visualstudio/ide/step-1-create-a-windows-forms-application-project) y [Cómo: Agregar controles a Windows Forms](how-to-add-controls-to-windows-forms.md). En Visual Studio 2005, el <xref:System.Windows.Forms.DataGrid> control no está en el **cuadro de herramientas** de forma predeterminada. Para obtener información sobre cómo agregarlo, vea [Cómo: Agregar elementos al cuadro de herramientas](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/ms165355(v=vs.100)). Además de Visual Studio 2005, puede usar el **orígenes de datos** ventana para el enlace de datos en tiempo de diseño. Para obtener más información, consulte [enlazar controles a datos en Visual Studio](/visualstudio/data-tools/bind-controls-to-data-in-visual-studio).  
  
> [!NOTE]
>  Los cuadros de diálogo y comandos de menú que se ven pueden diferir de los descritos en la Ayuda, en función de los valores de configuración o de edición activos. Para cambiar la configuración, elija la opción **Importar y exportar configuraciones** del menú **Herramientas** . Para más información, vea [Personalizar el IDE de Visual Studio](/visualstudio/ide/personalizing-the-visual-studio-ide).  
  
### <a name="to-data-bind-the-datagrid-control-to-a-single-table-in-the-designer"></a>Para enlazar el control DataGrid a una única tabla en el diseñador  
  
1. Establecer el control <xref:System.Windows.Forms.DataGrid.DataSource%2A> propiedad para el objeto que contiene los elementos de datos que desea enlazar.  
  
2. Si el origen de datos es un conjunto de datos, establezca el <xref:System.Windows.Forms.DataGrid.DataMember%2A> propiedad en el nombre de la tabla para enlazar a.  
  
3. Si el origen de datos es un conjunto de datos o una vista de datos basado en una tabla de conjunto de datos, agregue código al formulario para rellenar el conjunto de datos.  
  
     El código exacto que utilice depende de donde obtiene datos del conjunto de datos. Si el conjunto de datos se rellena directamente desde una base de datos, normalmente se invoca el `Fill` método de un adaptador de datos, como se muestra en el ejemplo de código siguiente, que rellena un conjunto de datos denominado `DsCategories1`:  
  
    ```vb  
    sqlDataAdapter1.Fill(DsCategories1)  
    ```  
  
    ```csharp  
    sqlDataAdapter1.Fill(DsCategories1);  
    ```  
  
    ```cpp  
    sqlDataAdapter1->Fill(dsCategories1);  
    ```  
  
4. (Opcional) Agregar los estilos de tabla adecuada y estilos de columna a la cuadrícula.  
  
     Si no hay ningún estilo de tabla, verá la tabla, pero con un formato mínimo y con todas las columnas visibles.  
  
### <a name="to-data-bind-the-datagrid-control-to-multiple-tables-in-a-dataset-in-the-designer"></a>Para enlazar el control DataGrid a varias tablas en un conjunto de datos en el diseñador  
  
1. Establecer el control <xref:System.Windows.Forms.DataGrid.DataSource%2A> propiedad para el objeto que contiene los elementos de datos que desea enlazar.  
  
2. Si el conjunto de datos contiene tablas relacionadas (es decir, si contiene un objeto relation), establezca el <xref:System.Windows.Forms.DataGrid.DataMember%2A> propiedad en el nombre de la tabla primaria.  
  
3. Escribir código para llenar el conjunto de datos.  
  
## <a name="see-also"></a>Vea también

- [Información general sobre el control DataGrid](datagrid-control-overview-windows-forms.md)
- [Filtrar para agregar tablas y columnas al control DataGrid de Windows Forms](how-to-add-tables-and-columns-to-the-windows-forms-datagrid-control.md)
- [Control DataGrid](datagrid-control-windows-forms.md)
- [Enlace de datos en Windows Forms](../windows-forms-data-binding.md)
- [Acceso a datos en Visual Studio](/visualstudio/data-tools/accessing-data-in-visual-studio)
