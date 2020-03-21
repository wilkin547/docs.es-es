---
title: Agregar o quitar imágenes con el componente ImageList
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- images [Windows Forms], removing from ImageList component
- images [Windows Forms], storing for controls
- ImageList component [Windows Forms], adding images
- ImageList component [Windows Forms], removing images
- images [Windows Forms], adding to ImageList component
- images [Windows Forms], displaying with controls
ms.assetid: c5eacc56-f769-4e2e-bfb7-f756620913db
ms.openlocfilehash: e045be7ea9407bc379b0c22282fcd2184ff5db51
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79182300"
---
# <a name="how-to-add-or-remove-images-with-the-windows-forms-imagelist-component"></a>Cómo: Agregar o quitar imágenes con el componente ImageList de formularios Windows Forms
El componente <xref:System.Windows.Forms.ImageList> de formularios Windows Forms normalmente se rellena con imágenes antes de que se asocie a un control. Sin embargo, puede agregar y quitar imágenes después de asociar la lista de imágenes con un control.  
  
> [!NOTE]
> Al quitar imágenes, <xref:System.Windows.Forms.ButtonBase.ImageIndex%2A> compruebe que la propiedad de los controles asociados sigue siendo válida.  
  
### <a name="to-add-images-programmatically"></a>Para agregar imágenes mediante programación  
  
- Utilice <xref:System.Windows.Forms.ImageList.ImageCollection.Add%2A> el método de la <xref:System.Windows.Forms.ImageList.Images%2A> propiedad de la lista de imágenes.  
  
     En el ejemplo de código siguiente, la ruta de acceso establecida para la ubicación de la imagen es la carpeta **Mis documentos.** Esta ubicación se utiliza porque puede suponer que la mayoría de los equipos que ejecutan el sistema operativo Windows incluirán esta carpeta. La elección de esta ubicación también permite a los usuarios que tienen niveles mínimos de acceso al sistema ejecutar la aplicación de forma más segura. En el ejemplo de código siguiente se <xref:System.Windows.Forms.ImageList> requiere que tenga un formulario con un control ya agregado.  
  
    ```vb  
    Public Sub LoadImage()  
       Dim myImage As System.Drawing.Image = _  
         Image.FromFile _  
       (System.Environment.GetFolderPath _  
       (System.Environment.SpecialFolder.Personal) _  
       & "\Image.gif")  
       ImageList1.Images.Add(myImage)  
    End Sub  
    ```  
  
    ```csharp  
    public void addImage()  
    {  
    // Be sure that you use an appropriate escape sequence (such as the
    // @) when specifying the location of the file.  
       System.Drawing.Image myImage =
         Image.FromFile  
       (System.Environment.GetFolderPath  
       (System.Environment.SpecialFolder.Personal)  
       + @"\Image.gif");  
       imageList1.Images.Add(myImage);  
    }  
    ```  
  
    ```cpp  
    public:  
       void addImage()  
       {  
       // Replace the bold image in the following sample
       // with your own icon.  
       // Be sure that you use an appropriate escape sequence (such as
       // \\) when specifying the location of the file.  
          System::Drawing::Image ^ myImage =
             Image::FromFile(String::Concat(  
             System::Environment::GetFolderPath(  
             System::Environment::SpecialFolder::Personal),  
             "\\Image.gif"));  
          imageList1->Images->Add(myImage);  
       }  
    ```  
  
### <a name="to-add-images-with-a-key-value"></a>Para añadir imágenes con un valor de clave.  
  
- Utilice uno <xref:System.Windows.Forms.ImageList.ImageCollection.Add%2A> de los métodos <xref:System.Windows.Forms.ImageList.Images%2A> de la propiedad de la lista de imágenes que toma un valor de clave.  
  
     En el ejemplo de código siguiente, la ruta de acceso establecida para la ubicación de la imagen es la carpeta **Mis documentos.** Esta ubicación se utiliza porque puede suponer que la mayoría de los equipos que ejecutan el sistema operativo Windows incluirán esta carpeta. La elección de esta ubicación también permite a los usuarios que tienen niveles mínimos de acceso al sistema ejecutar la aplicación de forma más segura. En el ejemplo de código siguiente se <xref:System.Windows.Forms.ImageList> requiere que tenga un formulario con un control ya agregado.  
  
    ```vb  
    Public Sub LoadImage()  
       Dim myImage As System.Drawing.Image = _  
         Image.FromFile _  
       (System.Environment.GetFolderPath _  
       (System.Environment.SpecialFolder.Personal) _  
       & "\Image.gif")  
       ImageList1.Images.Add("myPhoto", myImage)  
    End Sub  
    ```  
  
```csharp  
public void addImage()  
{  
// Be sure that you use an appropriate escape sequence (such as the
// @) when specifying the location of the file.  
   System.Drawing.Image myImage =
     Image.FromFile  
   (System.Environment.GetFolderPath  
   (System.Environment.SpecialFolder.Personal)  
   + @"\Image.gif");  
   imageList1.Images.Add("myPhoto", myImage);  
}  
```  
  
### <a name="to-remove-all-images-programmatically"></a>Para eliminar todas las imágenes mediante programación  
  
- Utilice <xref:System.Windows.Forms.ImageList.ImageCollection.Remove%2A> el método para eliminar una sola imagen  
  
     ,-o-  
  
     Utilice <xref:System.Windows.Forms.ImageList.ImageCollection.Clear%2A> el método para borrar todas las imágenes de la lista de imágenes.  
  
    ```vb  
    ' Removes the first image in the image list  
    ImageList1.Images.Remove(myImage)  
    ' Clears all images in the image list  
    ImageList1.Images.Clear()  
    ```  
  
```csharp  
// Removes the first image in the image list.  
imageList1.Images.Remove(myImage);  
// Clears all images in the image list.  
imageList1.Images.Clear();  
```  
  
### <a name="to-remove-images-by-key"></a>Para eliminar imágenes por tecla  
  
- Utilice <xref:System.Windows.Forms.ImageList.ImageCollection.RemoveByKey%2A> el método para eliminar una sola imagen por su clave.  
  
    ```vb  
    ' Removes the image named "myPhoto" from the list.  
    ImageList1.Images.RemoveByKey("myPhoto")  
    ```  
  
```csharp  
// Removes the image named "myPhoto" from the list.  
imageList1.Images.RemoveByKey("myPhoto");  
```  
  
## <a name="see-also"></a>Consulte también

- [Componente ImageList](imagelist-component-windows-forms.md)
- [Información general sobre el componente ImageList](imagelist-component-overview-windows-forms.md)
- [Imágenes, mapas de bits y metarchivos](../advanced/images-bitmaps-and-metafiles.md)
