---
title: Cómo agregar una ubicación personalizada a un cuadro de diálogo de archivos
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Custom Place to dialog box
- adding Custom Place to dialog box
- CustomPlaces collection
ms.assetid: 63f6469b-59cd-40f6-9e61-8b5831856780
ms.openlocfilehash: 824c948fafd0a0995ad261389414d2d79918c8a1
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "69916348"
---
# <a name="how-to-add-a-custom-place-to-a-file-dialog-box"></a>Cómo agregar una ubicación personalizada a un cuadro de diálogo de archivos
Los cuadros de diálogo para abrir y guardar predeterminados en [!INCLUDE[wiprlhext](../../../../includes/wiprlhext-md.md)] tienen un área en el lado izquierdo titulada **Vínculos favoritos**. Esta área se denomina ubicaciones personalizadas. Las <xref:System.Windows.Forms.OpenFileDialog> clases <xref:System.Windows.Forms.SaveFileDialog> y permiten agregar carpetas a la <xref:System.Windows.Forms.FileDialog.CustomPlaces%2A> colección.  
  
> [!NOTE]
> Para que una ubicación personalizada aparezca <xref:System.Windows.Forms.OpenFileDialog> en o <xref:System.Windows.Forms.SaveFileDialog>, la <xref:System.Windows.Forms.FileDialog.AutoUpgradeEnabled%2A> propiedad debe establecerse `true` en (valor predeterminado).  
  
### <a name="to-add-a-custom-place-to-a-file-dialog-box"></a>Para agregar una ubicación personalizada a un cuadro de diálogo de archivos  
  
- Agregue una ruta de acceso, un GUID de carpeta conocida <xref:System.Windows.Forms.FileDialogCustomPlace> o un objeto <xref:System.Windows.Forms.FileDialog.CustomPlaces%2A> a la colección del cuadro de diálogo.  
  
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
