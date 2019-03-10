---
title: Filtrar Enlazar datos al control DataGridView de formularios Windows Forms
ms.date: 02/08/2019
dev_langs:
- csharp
- vb
helpviewer_keywords:
- data binding [Windows Forms], grids
- data binding [Windows Forms], DataGridView control
- DataGridView control [Windows Forms], data binding
ms.assetid: 1660f69c-5711-45d2-abc1-e25bc6779124
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: cbcc04625a14ebc23cacfb567951bf8f76f14985
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/09/2019
ms.locfileid: "57725108"
---
# <a name="how-to-bind-data-to-the-windows-forms-datagridview-control"></a>Filtrar Enlazar datos al control DataGridView de formularios Windows Forms

El <xref:System.Windows.Forms.DataGridView> control admite el modelo de enlace de datos de Windows Forms estándar, por lo que se puede enlazar a una variedad de orígenes de datos. Por lo general, enlaza a un <xref:System.Windows.Forms.BindingSource> que administra la interacción con el origen de datos. El <xref:System.Windows.Forms.BindingSource> puede ser cualquier origen de datos de Windows Forms, que proporciona gran flexibilidad al elegir o modificar la ubicación de sus datos. Para obtener más información acerca de los orígenes de datos la <xref:System.Windows.Forms.DataGridView> control admite, vea la [información general del control DataGridView](datagridview-control-overview-windows-forms.md).  

Visual Studio tiene una amplia compatibilidad para el enlace de datos para el control DataGridView de formularios. Para obtener más información, vea [Cómo: Enlazar datos al control DataGridView de formularios Windows Forms mediante el diseñador](bind-data-to-the-datagrid-using-the-designer.md).  

Para conectar un control DataGridView a datos:

1. Implementar un método para controlar los detalles de recuperación de los datos. El siguiente ejemplo de código implementa un `GetData` método que inicializa un <xref:System.Data.SqlClient.SqlDataAdapter>y lo usa para rellenar un <xref:System.Data.DataTable>. A continuación, enlaza la <xref:System.Data.DataTable> a la <xref:System.Windows.Forms.BindingSource>. 

2. En el formulario <xref:System.Windows.Forms.Form.Load> controlador de eventos, enlace el <xref:System.Windows.Forms.DataGridView> el control a la <xref:System.Windows.Forms.BindingSource>y llamar a la `GetData` método para recuperar los datos.  

## <a name="example"></a>Ejemplo

En este ejemplo de código completo se recupera datos de una base de datos para rellenar un control DataGridView en un formulario de Windows. El formulario también tiene botones para volver a cargar datos y enviar cambios a la base de datos.  

Para este ejemplo se necesita: 

- Acceso a una base de datos de ejemplo Northwind de SQL Server. Para obtener más información acerca de cómo instalar la base de datos de ejemplo Northwind, vea [obtener las bases de datos de ejemplo para obtener ejemplos de código ADO.NET](../../data/adonet/sql/linq/downloading-sample-databases.md). 

- Referencias a los ensamblados System, System.Windows.Forms, System.Data y System.Xml.  

Para compilar y ejecutar este ejemplo, pegue el código en el *Form1* archivo de código en un nuevo proyecto de Windows Forms. Para obtener información sobre la compilación desde el C# o línea de comandos de Visual Basic, vea [de línea de comandos para compilar con csc.exe](../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md) o [construido a partir de la línea de comandos](../../../visual-basic/reference/command-line-compiler/building-from-the-command-line.md).  
  
Rellenar el `connectionString` variable en el ejemplo con los valores para la conexión de base de datos de ejemplo Northwind de SQL Server. Autenticación de Windows, también denominada seguridad integrada, es una forma más segura para conectarse a la base de datos que el almacenamiento de una contraseña en la cadena de conexión. Para obtener más información acerca de la seguridad de conexión, consulte [proteger la información de conexión](../../data/adonet/protecting-connection-information.md).  

[!code-csharp[System.Windows.Forms.DataGridViewBoundEditable](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewBoundEditable/CS/datagridviewboundeditable.cs)]
[!code-vb[System.Windows.Forms.DataGridViewBoundEditable](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewBoundEditable/VB/datagridviewboundeditable.vb)]  
  
## <a name="see-also"></a>Vea también
- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridView.DataSource%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.BindingSource>
- [Mostrar datos en el control DataGridView de formularios Windows Forms](displaying-data-in-the-windows-forms-datagridview-control.md)
- [Proteger la información de conexión](../../data/adonet/protecting-connection-information.md)
