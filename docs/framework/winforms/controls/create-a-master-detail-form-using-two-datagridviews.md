---
title: Procedimiento Crear un formulario principal-detalle mediante dos controles DataGridView de formularios Windows Forms
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- DataGridView control [Windows Forms], master/detail form
- parent-child tables [Windows Forms], displaying on Windows Forms
- master-details lists [Windows Forms], creating
ms.assetid: 99f6e876-3f7f-4139-9063-e36587c95b02
ms.openlocfilehash: ccd9354d623cf1b452bc3890b7fd9a5248cb69c8
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "62011533"
---
# <a name="how-to-create-a-masterdetail-form-using-two-windows-forms-datagridview-controls"></a>Procedimiento para crear un formulario maestro y detalle mediante dos controles DataGridView de formularios Windows Forms
En el ejemplo de código siguiente se crea un formulario Maestro y detalles mediante dos controles <xref:System.Windows.Forms.DataGridView> enlazados a dos componentes <xref:System.Windows.Forms.BindingSource>. El origen de datos es un <xref:System.Data.DataSet> que contiene las tablas `Customers` y `Orders` de la base de datos de ejemplo de SQL Server Northwind, junto con una <xref:System.Data.DataRelation> que relaciona las dos mediante la columna `CustomerID`.  
  
 Un <xref:System.Windows.Forms.BindingSource> se enlaza a la tabla primaria `Customers` del conjunto de datos. Estos datos se muestran en el control maestro <xref:System.Windows.Forms.DataGridView>. El otro <xref:System.Windows.Forms.BindingSource> se enlaza al primer conector de datos. La propiedad <xref:System.Windows.Forms.BindingSource.DataMember%2A> del segundo <xref:System.Windows.Forms.BindingSource> se establece en el nombre <xref:System.Data.DataRelation>. Esto hace que el control de detalles asociados <xref:System.Windows.Forms.DataGridView> muestre las filas de la tabla secundaria `Orders` que corresponden a la fila actual del control maestro <xref:System.Windows.Forms.DataGridView>.  
  
 Para obtener una explicación completa de este ejemplo de código, vea [Tutorial: Creación de un formulario principal-detalle mediante dos Windows Forms DataGridView controles](creating-a-master-detail-form-using-two-datagridviews.md).  
  
## <a name="example"></a>Ejemplo  
 [!code-csharp[System.Windows.Forms.DataGridViewMasterDetails#00](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMasterDetails/CS/masterdetails.cs#00)]
 [!code-vb[System.Windows.Forms.DataGridViewMasterDetails#00](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMasterDetails/VB/masterdetails.vb#00)]  
  
## <a name="compiling-the-code"></a>Compilar el código  
 Para este ejemplo se necesita:  
  
 Referencias a los ensamblados System, System.Data, System.Windows.Forms y System.XML.  
  
- Para obtener información sobre cómo compilar este ejemplo desde la línea de comandos para Visual Basic o Visual C#, vea [compilar desde la línea de comandos](../../../visual-basic/reference/command-line-compiler/building-from-the-command-line.md) o [de línea de comandos con csc.exe](../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md). También puede compilar este ejemplo en Visual Studio pegando el código en un nuevo proyecto.  
  
## <a name="net-framework-security"></a>Seguridad de .NET Framework  
 Almacenar información confidencial, como una contraseña, en la cadena de conexión puede afectar a la seguridad de la aplicación. El uso de la autenticación de Windows (también conocida como seguridad integrada) es un modo más seguro de controlar el acceso a una base de datos. Para más información, consulte [Proteger la información de conexión](../../data/adonet/protecting-connection-information.md).  
  
## <a name="see-also"></a>Vea también

- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.BindingSource>
- [Tutorial: Creación de un formulario principal-detalle mediante dos controles DataGridView de formularios Windows Forms](creating-a-master-detail-form-using-two-datagridviews.md)
- [Mostrar datos en el control DataGridView de Windows Forms](displaying-data-in-the-windows-forms-datagridview-control.md)
- [Proteger la información de conexión](../../data/adonet/protecting-connection-information.md)
