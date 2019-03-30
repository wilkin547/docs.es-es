---
title: Filtrar Mostrar una marca de inserción en un Control ListView de formularios de Windows
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- ListView control [Windows Forms], drag operations
- graphics [Windows Forms], insertion marks
- drop and drag [Windows Forms], insertion marks
- insertion marks
ms.assetid: 88d0a15b-25fd-4dc3-a685-297351311940
ms.openlocfilehash: 1c588053f9603a796d74fd706254ea150d21573a
ms.sourcegitcommit: 15ab532fd5e1f8073a4b678922d93b68b521bfa0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/29/2019
ms.locfileid: "58654164"
---
# <a name="how-to-display-an-insertion-mark-in-a-windows-forms-listview-control"></a>Filtrar Mostrar una marca de inserción en un Control ListView de formularios de Windows
La marca de inserción del control <xref:System.Windows.Forms.ListView> muestra a los usuarios el punto en el que se insertarán los elementos arrastrados. Cuando un usuario arrastra un elemento a un punto entre otros dos elementos, la marca de inserción muestra la nueva ubicación esperada del elemento.  
  
> [!NOTE]
>  La característica de marca de inserción solo está disponible en [!INCLUDE[WinXpFamily](../../../../includes/winxpfamily-md.md)] cuando la aplicación llama al método <xref:System.Windows.Forms.Application.EnableVisualStyles%2A?displayProperty=nameWithType>. En sistemas operativos anteriores, cualquier código relacionado con la marca de inserción no tiene ningún efecto y la marca de inserción no aparecerá. Para obtener más información, consulta <xref:System.Windows.Forms.ListViewInsertionMark>.  
  
 La siguiente imagen muestra una marca de inserción:  
  
 ![Captura de pantalla que muestra una marca de inserción de ListView. ](./media/how-to-display-an-insertion-mark-in-a-windows-forms-listview-control/listview-insertion-mark.gif "ListViewInsertion")  
  
 El ejemplo de código siguiente muestra cómo utilizar esta característica.  
  
## <a name="example"></a>Ejemplo  
 [!code-cpp[System.Windows.Forms.ListView.InsertionMark#1](~/samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.ListView.InsertionMark/CPP/listviewinsertionmarkexample.cpp#1)]
 [!code-csharp[System.Windows.Forms.ListView.InsertionMark#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ListView.InsertionMark/CS/listviewinsertionmarkexample.cs#1)]
 [!code-vb[System.Windows.Forms.ListView.InsertionMark#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ListView.InsertionMark/VB/listviewinsertionmarkexample.vb#1)]  
  
## <a name="compiling-the-code"></a>Compilar el código  
 Para este ejemplo se necesita:  
  
-   Referencias a los ensamblados System y System.Windows.Forms.  
  
 Para obtener información sobre cómo compilar este ejemplo desde la línea de comandos para Visual Basic o Visual C#, vea [compilar desde la línea de comandos](../../../visual-basic/reference/command-line-compiler/building-from-the-command-line.md) o [de línea de comandos con csc.exe](../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md). También puede compilar este ejemplo en Visual Studio pegando el código en un nuevo proyecto.  
  
## <a name="see-also"></a>Vea también
- <xref:System.Windows.Forms.ListView>
- <xref:System.Windows.Forms.ListView.InsertionMark%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.ListViewInsertionMark>
- [ListView (Control)](listview-control-windows-forms.md)
- [Información general del control ListView](listview-control-overview-windows-forms.md)
- [Tutorial: Realizar una operación de arrastrar y colocar en Windows Forms](../advanced/walkthrough-performing-a-drag-and-drop-operation-in-windows-forms.md)
