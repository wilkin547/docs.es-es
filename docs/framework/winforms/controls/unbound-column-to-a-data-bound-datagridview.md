---
title: Filtrar Agregar una columna independiente a un Control DataGridView de formularios de Windows enlazados a datos
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- columns [Windows Forms], unbound data
- data grids [Windows Forms], adding unbound columns
- DataGridView control [Windows Forms], unbound data
ms.assetid: f7bdc4d8-ba8e-421b-ad62-82d936f01372
ms.openlocfilehash: 563e9a55f5e019847acb4acadf8ece82fa14bc57
ms.sourcegitcommit: 8f95d3a37e591963ebbb9af6e90686fd5f3b8707
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/23/2019
ms.locfileid: "56747588"
---
# <a name="how-to-add-an-unbound-column-to-a-data-bound-windows-forms-datagridview-control"></a>Procedimiento Agregar una columna independiente a un Control DataGridView de formularios de Windows enlazados a datos
Los datos que muestra en el control <xref:System.Windows.Forms.DataGridView> proceden por lo general de un origen de datos, pero es posible que desee mostrar una columna de datos que no proceda de dicho origen de datos. Este tipo de columna se denomina columna independiente. Las columnas independientes pueden adoptar muchas formas. Con frecuencia, se utilizan para permitir acceder a los detalles de una fila de datos.  
  
 En el ejemplo de código siguiente se muestra cómo crear una columna independiente de **detalles** botones para mostrar una tabla secundaria relacionada con una fila determinada en una tabla primaria al implementar un escenario principal-detalle. Para responder a los clics en los botones, implemente un controlador de eventos <xref:System.Windows.Forms.DataGridView.CellClick?displayProperty=nameWithType> que muestra un formulario que contiene la tabla secundaria.   
  
 Visual Studio es compatible con esta tarea.  Consulte también [Cómo: Agregar y quitar columnas en la Windows Forms mediante el Diseñador de Control de DataGridView](add-and-remove-columns-in-the-datagrid-using-the-designer.md).  
  
## <a name="example"></a>Ejemplo  
 [!code-csharp[System.Windows.Forms.DataGridViewMisc#010](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#010)]
 [!code-vb[System.Windows.Forms.DataGridViewMisc#010](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#010)]  
  
## <a name="compiling-the-code"></a>Compilar el código  
 Para este ejemplo se necesita:  
  
-   Control <xref:System.Windows.Forms.DataGridView> denominado `dataGridView1`.  
  
-   Referencias a los ensamblados <xref:System?displayProperty=nameWithType> y <xref:System.Windows.Forms?displayProperty=nameWithType>.  
  
## <a name="see-also"></a>Vea también
- <xref:System.Windows.Forms.DataGridView>
- [Mostrar datos en el control DataGridView de Windows Forms](../../../../docs/framework/winforms/controls/displaying-data-in-the-windows-forms-datagridview-control.md)
- [Modos de presentación de datos en el control DataGridView de Windows Forms](../../../../docs/framework/winforms/controls/data-display-modes-in-the-windows-forms-datagridview-control.md)
