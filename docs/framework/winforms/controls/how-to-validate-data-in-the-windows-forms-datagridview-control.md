---
title: Procedimiento para validar datos en el control DataGridView de formularios Windows Forms
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- data [Windows Forms], validation
- DataGridView control [Windows Forms], data validation
- data grids [Windows Forms], validating data
- data validation [Windows Forms], Windows Forms
ms.assetid: d10aef35-701e-4a3c-a684-2a2ed1aeaca6
ms.openlocfilehash: 349ea28fe1fd82c1b547018f62273be89ff2db8d
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/28/2019
ms.locfileid: "64591414"
---
# <a name="how-to-validate-data-in-the-windows-forms-datagridview-control"></a>Procedimiento para validar datos en el control DataGridView de formularios Windows Forms
El ejemplo de código siguiente muestra cómo validar datos introducidos por un usuario en un control <xref:System.Windows.Forms.DataGridView>. En este ejemplo, <xref:System.Windows.Forms.DataGridView> se rellena con filas de la tabla `Customers` de la base de datos de ejemplo Northwind. Cuando el usuario edita una celda en la columna `CompanyName`, se comprueba la validez de su valor verificando que no está vacío. Si el controlador de eventos del evento <xref:System.Windows.Forms.DataGridView.CellValidating> detecta que el valor es una cadena vacía, <xref:System.Windows.Forms.DataGridView> impide que el usuario salga de la celda hasta que se especifique una cadena que no esté vacía.  
  
 Para obtener una explicación completa de este ejemplo de código, vea [Tutorial: Validar datos en el Windows Forms DataGridView Control](walkthrough-validating-data-in-the-windows-forms-datagridview-control.md).  
  
## <a name="example"></a>Ejemplo  
 [!code-csharp[System.Windows.Forms.DataGridViewDataValidation#00](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewDataValidation/CS/datavalidation.cs#00)]
 [!code-vb[System.Windows.Forms.DataGridViewDataValidation#00](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewDataValidation/VB/datavalidation.vb#00)]  
  
## <a name="compiling-the-code"></a>Compilar el código  
 Para este ejemplo se necesita:  
  
- Referencias a los ensamblados System, System.Data, System.Windows.Forms y System.XML.  
  
 Para obtener información sobre cómo compilar este ejemplo desde la línea de comandos para Visual Basic o Visual C#, vea [compilar desde la línea de comandos](../../../visual-basic/reference/command-line-compiler/building-from-the-command-line.md) o [de línea de comandos con csc.exe](../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md). También puede compilar este ejemplo en Visual Studio pegando el código en un nuevo proyecto.  
  
## <a name="net-framework-security"></a>Seguridad de .NET Framework  
 Almacenar información confidencial, como una contraseña, en la cadena de conexión puede afectar a la seguridad de la aplicación. El uso de la autenticación de Windows (también conocida como seguridad integrada) es un modo más seguro de controlar el acceso a una base de datos. Para más información, consulte [Proteger la información de conexión](../../data/adonet/protecting-connection-information.md).  
  
## <a name="see-also"></a>Vea también

- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.BindingSource>
- [Tutorial: Validar datos en el Control DataGridView de Windows Forms](walkthrough-validating-data-in-the-windows-forms-datagridview-control.md)
- [Entrada de datos en el control DataGridView de Windows Forms](data-entry-in-the-windows-forms-datagridview-control.md)
- [Tutorial: Controlar los errores que se producen durante la entrada de datos en el Control DataGridView de Windows Forms](handling-errors-that-occur-during-data-entry-in-the-datagrid.md)
- [Proteger la información de conexión](../../data/adonet/protecting-connection-information.md)
