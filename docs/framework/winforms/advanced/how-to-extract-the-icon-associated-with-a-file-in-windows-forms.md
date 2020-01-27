---
title: 'Cómo: extraer el icono asociado a un archivo'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- displaying a file name and its file type icon in a ListView control [Windows Forms]
- file name extension icons [Windows Forms], displaying in a ListView
- extracting icons associated with a file type [Windows Forms]
ms.assetid: 88e2ad8b-c34f-415a-84f2-dad756b5c928
ms.openlocfilehash: 28769144b0e1c631a31c3c541747a6215f861d0e
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/24/2020
ms.locfileid: "76742544"
---
# <a name="how-to-extract-the-icon-associated-with-a-file-in-windows-forms"></a>Cómo: Extraer el icono asociado a un archivo en Windows Forms
Muchos archivos tienen iconos incrustados que proporcionan una representación visual del tipo de archivo asociado. Por ejemplo, los documentos de Microsoft Word contienen un icono que los identifica como documentos de Word. Al mostrar archivos en un control de lista o en un control de tabla, puede que desee mostrar el icono que representa el tipo de archivo junto a cada nombre de archivo. Puede hacerlo fácilmente con el método <xref:System.Drawing.Icon.ExtractAssociatedIcon%2A>.  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo de código siguiente se muestra cómo extraer el icono asociado a un archivo y mostrar el nombre de archivo y su icono asociado en un control de <xref:System.Windows.Forms.ListView>.  
  
 [!code-csharp[System.Drawing.Icon.ExtractAssociatedIconEx#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.Icon.ExtractAssociatedIconEx/CS/Form1.cs#1)]
 [!code-vb[System.Drawing.Icon.ExtractAssociatedIconEx#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.Icon.ExtractAssociatedIconEx/VB/Form1.vb#1)]  
  
## <a name="compiling-the-code"></a>Compilar el código  
 Para compilar el ejemplo:  
  
- Pegue el código anterior en un Windows Form y llame al método `ExtractAssociatedIconExample` desde el constructor del formulario o <xref:System.Windows.Forms.Form.Load> método de control de eventos.  
  
     Tendrá que asegurarse de que el formulario importa el espacio de nombres <xref:System.IO>.  
  
## <a name="see-also"></a>Vea también

- [Imágenes, mapas de bits y metarchivos](images-bitmaps-and-metafiles.md)
- [ListView (control)](../controls/listview-control-windows-forms.md)
