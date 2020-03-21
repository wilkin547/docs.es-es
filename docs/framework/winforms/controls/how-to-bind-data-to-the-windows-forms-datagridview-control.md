---
title: Enlazar datos al control DataGridView
ms.date: 02/08/2019
dev_langs:
- csharp
- vb
helpviewer_keywords:
- data binding [Windows Forms], grids
- data binding [Windows Forms], DataGridView control
- DataGridView control [Windows Forms], data binding
ms.assetid: 1660f69c-5711-45d2-abc1-e25bc6779124
ms.openlocfilehash: 643dcd37cd1bb3f8b5938fedff66c67cd68278ff
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79182274"
---
# <a name="how-to-bind-data-to-the-windows-forms-datagridview-control"></a>Cómo: enlazar datos al control DataGridView de formularios Windows Forms

El <xref:System.Windows.Forms.DataGridView> control admite el modelo de enlace de datos estándar de formularios Windows Forms, por lo que puede enlazar a una variedad de orígenes de datos. Normalmente, se <xref:System.Windows.Forms.BindingSource> enlaza a un que administra la interacción con el origen de datos. Puede <xref:System.Windows.Forms.BindingSource> ser cualquier origen de datos de formularios Windows Forms, lo que le proporciona una gran flexibilidad al elegir o modificar la ubicación de los datos. Para obtener más información <xref:System.Windows.Forms.DataGridView> acerca de los orígenes de datos que admite el control, vea información general del [control DataGridView](datagridview-control-overview-windows-forms.md).  

Visual Studio tiene una amplia compatibilidad para el enlace de datos a la DataGridView control. Para obtener más información, vea [Cómo: enlazar datos al control DataGridView](bind-data-to-the-datagrid-using-the-designer.md)de formularios Windows Forms mediante el Diseñador .  

Para conectar un control DataGridView a los datos:

1. Implemente un método para controlar los detalles de la recuperación de los datos. En el ejemplo de `GetData` código siguiente <xref:System.Data.SqlClient.SqlDataAdapter>se implementa un método <xref:System.Data.DataTable>que inicializa un , y lo usa para rellenar un archivo . A continuación, <xref:System.Data.DataTable> se <xref:System.Windows.Forms.BindingSource>une al archivo .

2. En el controlador <xref:System.Windows.Forms.Form.Load> de eventos <xref:System.Windows.Forms.DataGridView> del formulario, enlace el control a la <xref:System.Windows.Forms.BindingSource>, y llame al `GetData` método para recuperar los datos.  

## <a name="example"></a>Ejemplo

Este ejemplo de código completo recupera datos de una base de datos para rellenar un DataGridView control en un formulario Windows. El formulario también tiene botones para volver a cargar datos y enviar cambios a la base de datos.  

Para este ejemplo se necesita:

- Acceso a una base de datos de ejemplo de Northwind SQL Server. Para obtener más información acerca de la instalación de la base de datos de ejemplo Northwind, vea Obtener las bases de datos de [ejemplo para ADO.NET ejemplos](../../data/adonet/sql/linq/downloading-sample-databases.md)de código.

- Referencias a los ensamblados System, System.Windows.Forms, System.Data y System.Xml.  

Para compilar y ejecutar este ejemplo, pegue el código en el archivo de código *Form1* en un nuevo proyecto de Windows Forms. Para obtener información acerca de la creación desde la línea de comandos de C o Visual Basic, vea Creación de línea de [comandos con csc.exe](../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md) o Compilación desde la línea de [comandos](../../../visual-basic/reference/command-line-compiler/building-from-the-command-line.md).  
  
Rellene `connectionString` la variable en el ejemplo con los valores de la conexión de base de datos de ejemplo de Northwind SQL Server . La autenticación de Windows, también denominada seguridad integrada, es una forma más segura de conectarse a la base de datos que almacenar una contraseña en la cadena de conexión. Para obtener más información acerca de la seguridad de la conexión, consulte [Proteger la información](../../data/adonet/protecting-connection-information.md)de conexión .  

[!code-csharp[System.Windows.Forms.DataGridViewBoundEditable](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewBoundEditable/CS/datagridviewboundeditable.cs)]
[!code-vb[System.Windows.Forms.DataGridViewBoundEditable](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewBoundEditable/VB/datagridviewboundeditable.vb)]  
  
## <a name="see-also"></a>Consulte también

- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridView.DataSource%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.BindingSource>
- [Mostrar datos en el control DataGridView de formularios Windows Forms](displaying-data-in-the-windows-forms-datagridview-control.md)
- [Proteger la información de conexión](../../data/adonet/protecting-connection-information.md)
