---
title: "Cómo: crear un formulario principal-detalle mediante dos controles DataGridView de Windows Forms"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- DataGridView control [Windows Forms], master/detail form
- parent-child tables [Windows Forms], displaying on Windows Forms
- master-details lists [Windows Forms], creating
ms.assetid: 99f6e876-3f7f-4139-9063-e36587c95b02
caps.latest.revision: "23"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 4a7d61af639e14948ab84c5e1a4d57030ecff122
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-create-a-masterdetail-form-using-two-windows-forms-datagridview-controls"></a>Cómo: Crear un formulario principal-detalle mediante dos controles DataGridView de formularios Windows Forms
En el ejemplo de código siguiente se crea un formulario Maestro y detalles mediante dos controles <xref:System.Windows.Forms.DataGridView> enlazados a dos componentes <xref:System.Windows.Forms.BindingSource>. El origen de datos es un <xref:System.Data.DataSet> que contiene las tablas `Customers` y `Orders` de la base de datos de ejemplo de SQL Server Northwind, junto con una <xref:System.Data.DataRelation> que relaciona las dos mediante la columna `CustomerID`.  
  
 Un <xref:System.Windows.Forms.BindingSource> se enlaza a la tabla primaria `Customers` del conjunto de datos. Estos datos se muestran en el control maestro <xref:System.Windows.Forms.DataGridView>. El otro <xref:System.Windows.Forms.BindingSource> se enlaza al primer conector de datos. La propiedad <xref:System.Windows.Forms.BindingSource.DataMember%2A> del segundo <xref:System.Windows.Forms.BindingSource> se establece en el nombre <xref:System.Data.DataRelation>. Esto hace que el control de detalles asociados <xref:System.Windows.Forms.DataGridView> muestre las filas de la tabla secundaria `Orders` que corresponden a la fila actual del control maestro <xref:System.Windows.Forms.DataGridView>.  
  
 Para obtener una explicación completa de este ejemplo de código, vea [Tutorial: crear un principal-detalle formulario usando dos controles Windows Forms DataGridView](../../../../docs/framework/winforms/controls/creating-a-master-detail-form-using-two-datagridviews.md).  
  
## <a name="example"></a>Ejemplo  
 [!code-csharp[System.Windows.Forms.DataGridViewMasterDetails#00](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMasterDetails/CS/masterdetails.cs#00)]
 [!code-vb[System.Windows.Forms.DataGridViewMasterDetails#00](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMasterDetails/VB/masterdetails.vb#00)]  
  
## <a name="compiling-the-code"></a>Compilar el código  
 Para este ejemplo se necesita:  
  
 Referencias a los ensamblados System, System.Data, System.Windows.Forms y System.XML.  
  
 Para información sobre cómo compilar este ejemplo desde la línea de comandos para [!INCLUDE[vbprvb](../../../../includes/vbprvb-md.md)] o [!INCLUDE[csprcs](../../../../includes/csprcs-md.md)], consulte [Compilación desde la línea de comandos](~/docs/visual-basic/reference/command-line-compiler/building-from-the-command-line.md) o [Compilar desde la línea de comandos con csc.exe](~/docs/csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md). También puede compilar este ejemplo en [!INCLUDE[vsprvs](../../../../includes/vsprvs-md.md)] pegando el código en un nuevo proyecto.  Consulte también [Cómo: compilar y ejecutar un completo Windows Forms código de ejemplo en Visual Studio](http://msdn.microsoft.com/library/Bb129228\(v=vs.110\))  
  
## <a name="net-framework-security"></a>Seguridad de .NET Framework  
 Almacenar información confidencial, como una contraseña, en la cadena de conexión puede afectar a la seguridad de la aplicación. El uso de la autenticación de Windows (también conocida como seguridad integrada) es un modo más seguro de controlar el acceso a una base de datos. Para más información, consulte [Proteger la información de conexión](../../../../docs/framework/data/adonet/protecting-connection-information.md).  
  
## <a name="see-also"></a>Vea también  
 <xref:System.Windows.Forms.DataGridView>  
 <xref:System.Windows.Forms.BindingSource>  
 [Tutorial: Crear un formulario principal-detalle mediante dos controles DataGridView de formularios Windows Forms](../../../../docs/framework/winforms/controls/creating-a-master-detail-form-using-two-datagridviews.md)  
 [Mostrar datos en el control DataGridView de Windows Forms](../../../../docs/framework/winforms/controls/displaying-data-in-the-windows-forms-datagridview-control.md)  
 [Proteger la información de conexión](../../../../docs/framework/data/adonet/protecting-connection-information.md)
