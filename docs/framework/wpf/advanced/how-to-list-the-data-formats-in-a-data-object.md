---
title: Filtrar Mostrar los formatos de datos en un objeto de datos
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- drag-and-drop [WPF], listing data formats
- DataFormats class [WPF]
- data formats [WPF], listing
ms.assetid: 18e7ba4b-ccef-4815-ae2d-3a32891010c0
ms.openlocfilehash: c8e9f24a0e991fa44ddd3f4d778cc7ba640ae9c3
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/05/2019
ms.locfileid: "57370181"
---
# <a name="how-to-list-the-data-formats-in-a-data-object"></a>Filtrar Mostrar los formatos de datos en un objeto de datos
Los ejemplos siguientes muestran cómo usar el <xref:System.Windows.DataObject.GetFormats%2A> sobrecargas del método obtención una matriz de cadenas que denotan cada formato de datos que está disponible en un objeto de datos.  
  
## <a name="example"></a>Ejemplo  
  
### <a name="description"></a>Descripción  
 El código de ejemplo siguiente usa el <xref:System.Windows.DataObject.GetFormats%2A> sobrecarga para obtener una matriz de cadenas que denotan todos los formatos de datos disponibles en un objeto de datos (nativo y convertir automáticamente).  
  
### <a name="code"></a>Código  
 [!code-csharp[DragDrop_DragDropMiscCode#_DragDrop_GetAllDataFormats](~/samples/snippets/csharp/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/CSharp/Window1.xaml.cs#_dragdrop_getalldataformats)]
 [!code-vb[DragDrop_DragDropMiscCode#_DragDrop_GetAllDataFormats](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/visualbasic/window1.xaml.vb#_dragdrop_getalldataformats)]  
  
## <a name="example"></a>Ejemplo  
  
### <a name="description"></a>Descripción  
 El código de ejemplo siguiente usa el <xref:System.Windows.DataObject.GetFormats%2A> sobrecarga para obtener una matriz de cadenas que denotan sólo los formatos de datos disponibles en un objeto de datos (se filtran los formatos de datos automática convertible).  
  
### <a name="code"></a>Código  
 [!code-csharp[DragDrop_DragDropMiscCode#_DragDrop_GetAllDataFormats_NativeOnly](~/samples/snippets/csharp/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/CSharp/Window1.xaml.cs#_dragdrop_getalldataformats_nativeonly)]
 [!code-vb[DragDrop_DragDropMiscCode#_DragDrop_GetAllDataFormats_NativeOnly](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/visualbasic/window1.xaml.vb#_dragdrop_getalldataformats_nativeonly)]  
  
## <a name="see-also"></a>Vea también
- <xref:System.Windows.IDataObject>
- [Información general sobre la función de arrastrar y colocar](drag-and-drop-overview.md)
