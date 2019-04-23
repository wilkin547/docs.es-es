---
title: Procedimiento para obtener acceso a objetos enlazados a filas DataGridView de formularios Windows Forms
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- object binding [Windows Forms], accessing bound objects
- data grids [Windows Forms], accessing bound objects
- DataGridView control [Windows Forms], accessing objects bound to rows
ms.assetid: 0e05748f-4403-4eb8-8b2f-b098108181b5
ms.openlocfilehash: 50882ab9a1a498bf8f76381e3f4aac53876abbb8
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59217411"
---
# <a name="how-to-access-objects-bound-to-windows-forms-datagridview-rows"></a>Procedimiento para obtener acceso a objetos enlazados a filas DataGridView de formularios Windows Forms
A veces resulta útil mostrar una tabla de información almacenada en una colección de objetos comerciales. Al enlazar un control <xref:System.Windows.Forms.DataGridView> a este tipo de colección, cada propiedad pública se muestra en su propia columna a menos que la propiedad se haya marcado como no examinable con un <xref:System.ComponentModel.BrowsableAttribute>. Por ejemplo, una colección de objetos `Customer` tendría columnas como **Nombre** y **Dirección**.  
  
 Si estos objetos contienen información adicional y código al que quiere acceder, puede llegar a él a través de los objetos de fila. En el siguiente ejemplo de código, los usuarios pueden seleccionar varias filas y hacer clic en un botón para enviar una factura a cada uno de los clientes correspondientes.  
  
### <a name="to-access-row-bound-objects"></a>Para acceder a objetos enlazados a fila  
  
-   Utilice la propiedad <xref:System.Windows.Forms.DataGridViewRow.DataBoundItem%2A?displayProperty=nameWithType>.  
  
     [!code-csharp[System.Windows.Forms.DataGridViewObjectBinding#10](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewObjectBinding/CS/datagridviewobjectbinding.cs#10)]
     [!code-vb[System.Windows.Forms.DataGridViewObjectBinding#10](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewObjectBinding/VB/datagridviewobjectbinding.vb#10)]  
  
## <a name="example"></a>Ejemplo  
 El ejemplo de código completo incluye una implementación sencilla `Customer` y enlaza la <xref:System.Windows.Forms.DataGridView> a una <xref:System.Collections.ArrayList> que contiene algunos objetos `Customer`. El controlador de eventos <xref:System.Windows.Forms.Control.Click> del <xref:System.Windows.Forms.Button?displayProperty=nameWithType> debe acceder a los objetos `Customer` a través de las filas porque la colección del cliente no es accesible fuera del controlador de eventos <xref:System.Windows.Forms.Form.Load?displayProperty=nameWithType>.  
  
 [!code-csharp[System.Windows.Forms.DataGridViewObjectBinding#00](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewObjectBinding/CS/datagridviewobjectbinding.cs#00)]
 [!code-vb[System.Windows.Forms.DataGridViewObjectBinding#00](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewObjectBinding/VB/datagridviewobjectbinding.vb#00)]  
  
## <a name="compiling-the-code"></a>Compilar el código  
 Para este ejemplo se necesita:  
  
-   Referencias a los ensamblados System y System.Windows.Forms.  
  
 Para obtener información sobre cómo compilar este ejemplo desde la línea de comandos para Visual Basic o Visual C#, vea [compilar desde la línea de comandos](../../../visual-basic/reference/command-line-compiler/building-from-the-command-line.md) o [de línea de comandos con csc.exe](../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md). También puede compilar este ejemplo en Visual Studio pegando el código en un nuevo proyecto.  
  
## <a name="see-also"></a>Vea también

- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridViewRow>
- <xref:System.Windows.Forms.DataGridViewRow.DataBoundItem%2A?displayProperty=nameWithType>
- [Mostrar datos en el control DataGridView de Windows Forms](displaying-data-in-the-windows-forms-datagridview-control.md)
- [Cómo: Enlazar objetos a controles DataGridView de formularios Windows Forms](how-to-bind-objects-to-windows-forms-datagridview-controls.md)
