---
title: "Cómo: Extraer el icono asociado a un archivo en Windows Forms"
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
- displaying a file name and its file type icon in a ListView control [Windows Forms]
- file name extension icons [Windows Forms], displaying in a ListView
- extracting icons associated with a file type [Windows Forms]
ms.assetid: 88e2ad8b-c34f-415a-84f2-dad756b5c928
caps.latest.revision: "5"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: a5153f6389c4477a18c647d7cdaf7b49b43bb7ca
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-extract-the-icon-associated-with-a-file-in-windows-forms"></a>Cómo: Extraer el icono asociado a un archivo en Windows Forms
Muchos archivos tienen iconos incrustados que proporcionan una representación visual del tipo de archivo asociado. Por ejemplo, documentos de Microsoft Word contienen un icono que los identifica como documentos de Word. Al mostrar archivos en un control de lista o tabla, puede que desee mostrar el icono que representa el tipo de archivo junto a cada nombre de archivo. Puede hacer esto fácilmente mediante el uso de la <xref:System.Drawing.Icon.ExtractAssociatedIcon%2A> método.  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo de código siguiente se muestra cómo extraer el icono asociado a un archivo y mostrar el nombre de archivo y el icono asociado en un <xref:System.Windows.Forms.ListView> control.  
  
 [!code-csharp[System.Drawing.Icon.ExtractAssociatedIconEx#1](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.Icon.ExtractAssociatedIconEx/CS/Form1.cs#1)]
 [!code-vb[System.Drawing.Icon.ExtractAssociatedIconEx#1](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.Icon.ExtractAssociatedIconEx/VB/Form1.vb#1)]  
  
## <a name="compiling-the-code"></a>Compilar el código  
 Para compilar el ejemplo:  
  
-   Pegue el código anterior en un formulario Windows Forms y llame a la `ExtractAssociatedIconExample` método desde el constructor del formulario o <xref:System.Windows.Forms.Form.Load> método de control de eventos.  
  
     Debe asegurarse de que el formulario se importa el <xref:System.IO> espacio de nombres.  
  
## <a name="see-also"></a>Vea también  
 [Imágenes, mapas de bits y metarchivos](../../../../docs/framework/winforms/advanced/images-bitmaps-and-metafiles.md)  
 [ListView (Control)](../../../../docs/framework/winforms/controls/listview-control-windows-forms.md)
