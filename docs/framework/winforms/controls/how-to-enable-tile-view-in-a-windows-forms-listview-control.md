---
title: Procedimiento para habilitar la vista en mosaico en un control ListView de formularios Windows Forms
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- tile view feature
- tiling
- Windows Forms, controls
- ListView control [Windows Forms], tile view
ms.assetid: c20e67a3-2d94-413d-9fcf-ecbd0fe251da
ms.openlocfilehash: 14eb21fa0285275e510b865c5cee7d1fc82fd0fd
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61941548"
---
# <a name="how-to-enable-tile-view-in-a-windows-forms-listview-control"></a>Procedimiento para habilitar la vista en mosaico en un control ListView de formularios Windows Forms
Con la característica de vista de mosaico del control <xref:System.Windows.Forms.ListView>, puede proporcionar equilibrio visual entre la información gráfica y de texto. La información de texto que se muestra para un elemento en la vista de mosaico es igual que la información de columna definida para la vista de detalles. La vista de mosaico funciona en combinación con las características de marca de inserción o agrupación del control <xref:System.Windows.Forms.ListView>.  
  
 La vista de mosaico usa un icono de 32 x 32 píxeles y varias líneas de texto, tal y como se muestra en las siguientes imágenes.  
  
 ![Vista en mosaico en un ListView Control](./media/how-to-enable-tile-view-in-a-windows-forms-listview-control/tile-view-in-listview-control.gif "icono Ver iconos y texto")  
 
 Para habilitar la vista de mosaico, establezca la propiedad <xref:System.Windows.Forms.ListView.View%2A> en <xref:System.Windows.Forms.View.Tile>. Puede ajustar el tamaño de los mosaicos estableciendo la propiedad <xref:System.Windows.Forms.ListView.TileSize%2A>, y el número de líneas de texto que se muestran en el mosaico ajustando la colección <xref:System.Windows.Forms.ListView.Columns%2A>.  
  
> [!NOTE]
>  La vista de mosaico solo está disponible en [!INCLUDE[WinXpFamily](../../../../includes/winxpfamily-md.md)] cuando la aplicación llama al método <xref:System.Windows.Forms.Application.EnableVisualStyles%2A?displayProperty=nameWithType>. En sistemas operativos anteriores, el código relacionado con la vista de mosaico no tiene ningún efecto y el control <xref:System.Windows.Forms.ListView> se muestra en la vista de iconos grandes. Para obtener más información, consulta <xref:System.Windows.Forms.ListView.View%2A?displayProperty=nameWithType>.  
  
### <a name="to-set-tile-view-programmatically"></a>Para establecer la vista de mosaico mediante programación  
  
1. Use la enumeración <xref:System.Windows.Forms.View> del control <xref:System.Windows.Forms.ListView>.  
  
    ```vb  
    ListView1.View = View.Tile  
    ```  
  
    ```csharp  
    listView1.View = View.Tile;  
    ```  
  
## <a name="example"></a>Ejemplo  
 En el siguiente ejemplo de código completo se muestra la vista de mosaico con mosaicos modificados para mostrar tres líneas de texto. El tamaño del mosaico se ha adaptado para evitar el ajuste de línea.  
  
 [!code-cpp[System.Windows.Forms.ListView.Tiling#1](~/samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.ListView.Tiling/CPP/listviewtilingexample.cpp#1)]
 [!code-csharp[System.Windows.Forms.ListView.Tiling#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ListView.Tiling/CS/listviewtilingexample.cs#1)]
 [!code-vb[System.Windows.Forms.ListView.Tiling#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ListView.Tiling/VB/listviewtilingexample.vb#1)]  
  
## <a name="compiling-the-code"></a>Compilar el código  
 Para este ejemplo se necesita:  
  
- Referencias a los ensamblados System y System.Windows.Forms.  
  
- Un archivo de icono llamado book.ico en el mismo directorio que el archivo ejecutable.  
  
 Para obtener información sobre cómo compilar este ejemplo desde la línea de comandos para Visual Basic o Visual C#, vea [compilar desde la línea de comandos](../../../visual-basic/reference/command-line-compiler/building-from-the-command-line.md) o [de línea de comandos con csc.exe](../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md). También puede compilar este ejemplo en Visual Studio pegando el código en un nuevo proyecto.  
  
## <a name="see-also"></a>Vea también

- <xref:System.Windows.Forms.ListView>
- <xref:System.Windows.Forms.ListView.TileSize%2A>
- [ListView (Control)](listview-control-windows-forms.md)
- [Información general del control ListView](listview-control-overview-windows-forms.md)
