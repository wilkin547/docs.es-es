---
title: Filtrar para crear un control DataGridView sin enlazar en formularios Windows Forms
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- DataGridView control [Windows Forms], unbound data
- DataGridView control [Windows Forms], displaying data without binding to a data source
- data [Windows Forms], unbound
ms.assetid: b5d4b47d-9a28-4d88-9dba-0a3c90fba71d
ms.openlocfilehash: 9bfffac3d6970aceea3842df95f4bcae970b42e7
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59167913"
---
# <a name="how-to-create-an-unbound-windows-forms-datagridview-control"></a>Filtrar para crear un control DataGridView sin enlazar en formularios Windows Forms
En el ejemplo de código siguiente se muestra cómo rellenar un control <xref:System.Windows.Forms.DataGridView> mediante programación sin enlazarlo a un origen de datos. Resulta de utilidad cuando tiene una pequeña cantidad de datos que quiere que se muestren en un formato de tabla.  
  
 Para obtener una explicación completa de este ejemplo de código, vea [Tutorial: Crear una independiente de Windows Forms DataGridView Control](walkthrough-creating-an-unbound-windows-forms-datagridview-control.md).  
  
## <a name="example"></a>Ejemplo  
 [!code-csharp[System.Windows.Forms.DataGridViewSimpleUnbound#00](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewSimpleUnbound/CS/simpleunbound.cs#00)]
 [!code-vb[System.Windows.Forms.DataGridViewSimpleUnbound#00](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewSimpleUnbound/VB/simpleunbound.vb#00)]  
  
## <a name="compiling-the-code"></a>Compilar el código  
 Para este ejemplo se necesita:  
  
-   Referencias a los ensamblados System, System.Drawing y System.Windows.Forms.  
  
 Para obtener información sobre cómo compilar este ejemplo desde la línea de comandos para Visual Basic o Visual C#, vea [compilar desde la línea de comandos](../../../visual-basic/reference/command-line-compiler/building-from-the-command-line.md) o [de línea de comandos con csc.exe](../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md). También puede compilar este ejemplo en Visual Studio pegando el código en un nuevo proyecto.  

## <a name="see-also"></a>Vea también

- <xref:System.Windows.Forms.DataGridView>
- [Tutorial: Crear un control DataGridView sin enlazar en formularios Windows Forms](walkthrough-creating-an-unbound-windows-forms-datagridview-control.md)
- [Mostrar datos en el control DataGridView de formularios Windows Forms](displaying-data-in-the-windows-forms-datagridview-control.md)
- [Modos de presentación de datos en el control DataGridView de formularios Windows Forms](data-display-modes-in-the-windows-forms-datagridview-control.md)
