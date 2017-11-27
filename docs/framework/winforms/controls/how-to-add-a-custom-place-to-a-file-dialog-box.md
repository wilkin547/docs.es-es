---
title: "Cómo: Agregar un lugar común a un cuadro de diálogo de archivos"
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
- Custom Place to dialog box
- adding Custom Place to dialog box
- CustomPlaces collection
ms.assetid: 63f6469b-59cd-40f6-9e61-8b5831856780
caps.latest.revision: "13"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 9ce5efccfd2efda2f333b51868e375849f7c7752
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-add-a-custom-place-to-a-file-dialog-box"></a>Cómo: Agregar un lugar común a un cuadro de diálogo de archivos
Los cuadros de diálogo para abrir y guardar predeterminados en [!INCLUDE[wiprlhext](../../../../includes/wiprlhext-md.md)] tienen un área en el lado izquierdo titulada **Vínculos favoritos**. Esta área se denomina ubicaciones personalizadas. El <xref:System.Windows.Forms.OpenFileDialog> y <xref:System.Windows.Forms.SaveFileDialog> clases le permiten agregar carpetas a la <xref:System.Windows.Forms.FileDialog.CustomPlaces%2A> colección.  
  
> [!NOTE]
>  En el orden de una ubicación personalizada que aparezca en el <xref:System.Windows.Forms.OpenFileDialog> o <xref:System.Windows.Forms.SaveFileDialog>, el <xref:System.Windows.Forms.FileDialog.AutoUpgradeEnabled%2A> propiedad debe establecerse en `true` (valor predeterminado).  
  
### <a name="to-add-a-custom-place-to-a-file-dialog-box"></a>Para agregar una ubicación personalizada a un cuadro de diálogo de archivos  
  
-   Agregar una ruta de acceso, un GUID de carpetas conocidas, o un <xref:System.Windows.Forms.FileDialogCustomPlace> el objeto a la <xref:System.Windows.Forms.FileDialog.CustomPlaces%2A> colección del cuadro de diálogo.  
  
     En el siguiente ejemplo de código se muestra cómo agregar una ruta de acceso:  
  
    ```vb  
    OpenFileDialog1.CustomPlaces.Add("C:\MyCustomPlace")  
    ```  
  
    ```csharp  
    openFileDialog1.CustomPlaces.Add("C:\\MyCustomPlace");  
    ```  
  
## <a name="see-also"></a>Vea también  
 <xref:System.Windows.Forms.FileDialog>  
 <xref:System.Windows.Forms.FileDialogCustomPlacesCollection.Add%2A?displayProperty=nameWithType>  
 [GUID de carpeta conocidos para lugares comunes de cuadros de diálogo de archivos](../../../../docs/framework/winforms/controls/known-folder-guids-for-file-dialog-custom-places.md)
