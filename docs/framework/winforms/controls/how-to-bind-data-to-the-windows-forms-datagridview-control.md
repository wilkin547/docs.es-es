---
title: Enlazar datos al control DataGridView
ms.date: 02/08/2019
description: Obtenga información sobre cómo el control DataGridView admite el modelo de enlace de datos de Windows Forms estándar para que se pueda enlazar a una variedad de orígenes de datos.
dev_langs:
- csharp
- vb
helpviewer_keywords:
- data binding [Windows Forms], grids
- data binding [Windows Forms], DataGridView control
- DataGridView control [Windows Forms], data binding
ms.assetid: 1660f69c-5711-45d2-abc1-e25bc6779124
ms.openlocfilehash: 3c3502804d1bc4a5eeffc22b4ec5f2773411ef69
ms.sourcegitcommit: 3824ff187947572b274b9715b60c11269335c181
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/17/2020
ms.locfileid: "84904421"
---
# <a name="how-to-bind-data-to-the-windows-forms-datagridview-control"></a>Cómo: enlazar datos al control DataGridView Windows Forms

El <xref:System.Windows.Forms.DataGridView> control admite el modelo de enlace de datos de Windows Forms estándar, por lo que se puede enlazar a una variedad de orígenes de datos. Normalmente, se enlaza a un <xref:System.Windows.Forms.BindingSource> que administra la interacción con el origen de datos. <xref:System.Windows.Forms.BindingSource>Puede ser cualquier origen de datos Windows Forms, lo que proporciona una gran flexibilidad a la hora de elegir o modificar la ubicación de los datos. Para obtener más información sobre los orígenes de datos que <xref:System.Windows.Forms.DataGridView> admite el control, vea [información general sobre el control DataGridView](datagridview-control-overview-windows-forms.md).  

Visual Studio ofrece una amplia compatibilidad para el enlace de datos al control DataGridView. Para obtener más información, vea [Cómo: enlazar datos al control DataGridView Windows Forms mediante el diseñador](bind-data-to-the-datagrid-using-the-designer.md).  

Para conectar un control DataGridView a datos:

1. Implemente un método para controlar los detalles de la recuperación de los datos. En el ejemplo de código siguiente se implementa un `GetData` método que inicializa un <xref:System.Data.SqlClient.SqlDataAdapter> y lo utiliza para rellenar un <xref:System.Data.DataTable> . A continuación, enlaza el <xref:System.Data.DataTable> a <xref:System.Windows.Forms.BindingSource> .

2. En el controlador de <xref:System.Windows.Forms.Form.Load> eventos del formulario, enlace el <xref:System.Windows.Forms.DataGridView> control al <xref:System.Windows.Forms.BindingSource> y llame al `GetData` método para recuperar los datos.  

## <a name="example"></a>Ejemplo

En este ejemplo de código completo se recuperan datos de una base de datos para rellenar un control DataGridView en Windows Forms. El formulario también tiene botones para volver a cargar los datos y enviar los cambios a la base de datos.  

Para este ejemplo se necesita:

- Acceso a una base de datos de ejemplo Northwind SQL Server. Para obtener más información sobre cómo instalar la base de datos de ejemplo Northwind, vea [obtener las bases de datos de ejemplo para ejemplos de código de ADO.net](../../data/adonet/sql/linq/downloading-sample-databases.md).

- Referencias a los ensamblados System, System. Windows. Forms, System. Data y System.Xml.  

Para compilar y ejecutar este ejemplo, pegue el código en el archivo de código *Form1* en un nuevo proyecto de Windows Forms. Para obtener información sobre cómo compilar desde la línea de comandos de C# o Visual Basic, vea [compilar mediante línea de comandos con csc.exe](../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md) o [compilar desde la línea de comandos](../../../visual-basic/reference/command-line-compiler/building-from-the-command-line.md).  
  
Rellene la `connectionString` variable en el ejemplo con los valores de la conexión de base de datos de ejemplo Northwind SQL Server. La autenticación de Windows, también denominada seguridad integrada, es una forma más segura de conectarse a la base de datos que almacenar una contraseña en la cadena de conexión. Para obtener más información sobre la seguridad de la conexión, consulte [proteger la información de conexión](../../data/adonet/protecting-connection-information.md).  

[!code-csharp[System.Windows.Forms.DataGridViewBoundEditable](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewBoundEditable/CS/datagridviewboundeditable.cs)]
[!code-vb[System.Windows.Forms.DataGridViewBoundEditable](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewBoundEditable/VB/datagridviewboundeditable.vb)]  
  
## <a name="see-also"></a>Consulte también

- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridView.DataSource%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.BindingSource>
- [Mostrar datos en el control DataGridView Windows Forms](displaying-data-in-the-windows-forms-datagridview-control.md)
- [Proteger la información de conexión](../../data/adonet/protecting-connection-information.md)
