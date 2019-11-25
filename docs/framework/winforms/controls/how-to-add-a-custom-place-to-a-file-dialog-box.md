---
title: 'Cómo: Agregar un lugar común a un cuadro de diálogo de archivos'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Custom Place to dialog box
- adding Custom Place to dialog box
- CustomPlaces collection
ms.assetid: 63f6469b-59cd-40f6-9e61-8b5831856780
ms.openlocfilehash: 7172e484451cf932413920910ec9124b3388bd76
ms.sourcegitcommit: f348c84443380a1959294cdf12babcb804cfa987
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/12/2019
ms.locfileid: "73976990"
---
# <a name="how-to-add-a-custom-place-to-a-file-dialog-box"></a>Cómo: Agregar un lugar común a un cuadro de diálogo de archivos
Los cuadros de diálogo abrir y guardar predeterminados de Windows Vista tienen un área en el lado izquierdo del cuadro de diálogo titulado **vínculos favoritos**. Esta área se denomina ubicaciones personalizadas. Las clases <xref:System.Windows.Forms.OpenFileDialog> y <xref:System.Windows.Forms.SaveFileDialog> permiten agregar carpetas a la colección de <xref:System.Windows.Forms.FileDialog.CustomPlaces%2A>.  
  
> [!NOTE]
> Para que una ubicación personalizada aparezca en el <xref:System.Windows.Forms.OpenFileDialog> o <xref:System.Windows.Forms.SaveFileDialog>, la propiedad <xref:System.Windows.Forms.FileDialog.AutoUpgradeEnabled%2A> debe estar establecida en `true` (valor predeterminado).  
  
### <a name="to-add-a-custom-place-to-a-file-dialog-box"></a>Para agregar una ubicación personalizada a un cuadro de diálogo de archivos  
  
- Agregue una ruta de acceso, un GUID de carpeta conocida o un objeto de <xref:System.Windows.Forms.FileDialogCustomPlace> a la colección de <xref:System.Windows.Forms.FileDialog.CustomPlaces%2A> del cuadro de diálogo.  
  
     En el siguiente ejemplo de código se muestra cómo agregar una ruta de acceso:  
  
    ```vb  
    OpenFileDialog1.CustomPlaces.Add("C:\MyCustomPlace")  
    ```  
  
    ```csharp  
    openFileDialog1.CustomPlaces.Add("C:\\MyCustomPlace");  
    ```  
  
## <a name="see-also"></a>Vea también

- <xref:System.Windows.Forms.FileDialog>
- <xref:System.Windows.Forms.FileDialogCustomPlacesCollection.Add%2A?displayProperty=nameWithType>
- [GUID de carpeta conocidos para lugares comunes de cuadros de diálogo de archivos](known-folder-guids-for-file-dialog-custom-places.md)
