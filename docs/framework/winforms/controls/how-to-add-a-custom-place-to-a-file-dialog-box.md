---
title: "C&#243;mo: Agregar un lugar com&#250;n a un cuadro de di&#225;logo de archivos | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-winforms"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "Custom Place a cuadro de diálogo"
  - "agregar Custom Place a cuadro de diálogo"
  - "CustomPlaces (colección)"
ms.assetid: 63f6469b-59cd-40f6-9e61-8b5831856780
caps.latest.revision: 13
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 13
---
# C&#243;mo: Agregar un lugar com&#250;n a un cuadro de di&#225;logo de archivos
El valor predeterminado, abrir y guardar cuadros de diálogo en [!INCLUDE[wiprlhext](../../../../includes/wiprlhext-md.md)] tiene un área en el lado izquierdo del cuadro de diálogo titulado **vínculos favoritos**. Esta área se denomina ubicaciones personalizadas. El <xref:System.Windows.Forms.OpenFileDialog> y <xref:System.Windows.Forms.SaveFileDialog> clases le permiten agregar carpetas a la <xref:System.Windows.Forms.FileDialog.CustomPlaces%2A> colección.  
  
> [!NOTE]
>  En el orden de una ubicación personalizada que aparezca en el <xref:System.Windows.Forms.OpenFileDialog> o <xref:System.Windows.Forms.SaveFileDialog>, el <xref:System.Windows.Forms.FileDialog.AutoUpgradeEnabled%2A> propiedad debe establecerse en `true` (valor predeterminado).  
  
### <a name="to-add-a-custom-place-to-a-file-dialog-box"></a>Para agregar una ubicación personalizada a un cuadro de diálogo de archivo  
  
-   Agregar una ruta de acceso, un GUID de carpetas conocidas, o un <xref:System.Windows.Forms.FileDialogCustomPlace> objeto a la <xref:System.Windows.Forms.FileDialog.CustomPlaces%2A> colección del cuadro de diálogo.  
  
     En el ejemplo de código siguiente se muestra cómo agregar una ruta de acceso:  
  
    ```vb  
    OpenFileDialog1.CustomPlaces.Add("C:\MyCustomPlace")  
    ```  
  
    ```csharp  
    openFileDialog1.CustomPlaces.Add("C:\\MyCustomPlace");  
    ```  
  
## <a name="see-also"></a>Vea también  
 <xref:System.Windows.Forms.FileDialog>   
 <xref:System.Windows.Forms.FileDialogCustomPlacesCollection.Add%2A?displayProperty=fullName>   
 [GUIDs de carpeta conocidos para lugares personalizados del cuadro de diálogo de archivo](../../../../docs/framework/winforms/controls/known-folder-guids-for-file-dialog-custom-places.md)