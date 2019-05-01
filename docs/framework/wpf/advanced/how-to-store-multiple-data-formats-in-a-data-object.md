---
title: Procedimiento Almacenar varios formatos de datos en un objeto de datos
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- DataObject class [WPF], storing multiple formats
- DataFormats class [WPF], storing multiple formats
- drag-and-drop [WPF], storing multiple formats
ms.assetid: 941ace29-29c4-4c26-b75b-ea7d06aa0d69
ms.openlocfilehash: 3f8e7233e1d28fec1f7dac114b04287aa3aff49f
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "62052383"
---
# <a name="how-to-store-multiple-data-formats-in-a-data-object"></a>Procedimiento Almacenar varios formatos de datos en un objeto de datos
El ejemplo siguiente muestra cómo usar el <xref:System.Windows.DataObject.SetData%28System.String%2CSystem.Object%29> para agregar datos a un objeto de datos en varios formatos.  
  
## <a name="example"></a>Ejemplo  
  
### <a name="description"></a>Descripción  
  
### <a name="code"></a>Código  
 [!code-csharp[DragDrop_DragDropMiscCode#_DragDrop_StoreMultipleFormats](~/samples/snippets/csharp/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/CSharp/Window1.xaml.cs#_dragdrop_storemultipleformats)]
 [!code-vb[DragDrop_DragDropMiscCode#_DragDrop_StoreMultipleFormats](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/visualbasic/window1.xaml.vb#_dragdrop_storemultipleformats)]  
  
## <a name="see-also"></a>Vea también

- <xref:System.Windows.IDataObject>
- [Información general sobre la función de arrastrar y colocar](drag-and-drop-overview.md)
