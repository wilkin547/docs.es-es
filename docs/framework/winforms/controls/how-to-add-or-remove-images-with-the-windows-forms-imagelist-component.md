---
title: Procedimiento para agregar o quitar imágenes con el componente ImageList de formularios Windows Forms
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
ms.openlocfilehash: 430b7f573b115c21b9e2fa87f0ace74205717285
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "69925122"
---
# <a name="how-to-add-or-remove-images-with-the-windows-forms-imagelist-component"></a>Procedimiento para agregar o quitar imágenes con el componente ImageList de formularios Windows Forms
El componente <xref:System.Windows.Forms.ImageList> de Windows Forms se rellena normalmente con imágenes antes de asociarse a un control. Sin embargo, puede Agregar y quitar imágenes después de asociar la lista de imágenes con un control.  
  
> [!NOTE]
> Al quitar imágenes, compruebe que la <xref:System.Windows.Forms.ButtonBase.ImageIndex%2A> propiedad de los controles asociados todavía es válida.  
  
### <a name="to-add-images-programmatically"></a>Para agregar imágenes mediante programación  
  
- Use el <xref:System.Windows.Forms.ImageList.ImageCollection.Add%2A> método de la <xref:System.Windows.Forms.ImageList.Images%2A> propiedad de la lista de imágenes.  
  
     En el ejemplo de código siguiente, la ruta de acceso establecida para la ubicación de la imagen es la carpeta **Mis documentos** . Esta ubicación se usa porque puede suponer que la mayoría de los equipos que ejecutan el sistema operativo Windows incluirán esta carpeta. La elección de esta ubicación también permite a los usuarios con niveles de acceso del sistema mínimos ejecutar la aplicación de forma más segura. El siguiente ejemplo de código requiere que tenga un formulario con un <xref:System.Windows.Forms.ImageList> control ya agregado.  
  
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
  
### <a name="to-add-images-with-a-key-value"></a>Para agregar imágenes con un valor de clave.  
  
- Use uno de los <xref:System.Windows.Forms.ImageList.ImageCollection.Add%2A> métodos de la <xref:System.Windows.Forms.ImageList.Images%2A> propiedad de la lista de imágenes que toma un valor de clave.  
  
     En el ejemplo de código siguiente, la ruta de acceso establecida para la ubicación de la imagen es la carpeta **Mis documentos** . Esta ubicación se usa porque puede suponer que la mayoría de los equipos que ejecutan el sistema operativo Windows incluirán esta carpeta. La elección de esta ubicación también permite a los usuarios con niveles de acceso del sistema mínimos ejecutar la aplicación de forma más segura. El siguiente ejemplo de código requiere que tenga un formulario con un <xref:System.Windows.Forms.ImageList> control ya agregado.  
  
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
  
### <a name="to-remove-all-images-programmatically"></a>Para quitar todas las imágenes mediante programación  
  
- Usar el <xref:System.Windows.Forms.ImageList.ImageCollection.Remove%2A> método para quitar una sola imagen  
  
     , o bien  
  
     Use el <xref:System.Windows.Forms.ImageList.ImageCollection.Clear%2A> método para borrar todas las imágenes de la lista de imágenes.  
  
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
  
### <a name="to-remove-images-by-key"></a>Para quitar imágenes por clave  
  
- Use el <xref:System.Windows.Forms.ImageList.ImageCollection.RemoveByKey%2A> método para quitar una sola imagen por su clave.  
  
    ```vb  
    ' Removes the image named "myPhoto" from the list.  
    ImageList1.Images.RemoveByKey("myPhoto")  
    ```  
  
```csharp  
// Removes the image named "myPhoto" from the list.  
imageList1.Images.RemoveByKey("myPhoto");  
```  
  
## <a name="see-also"></a>Vea también

- [ImageList (componente)](imagelist-component-windows-forms.md)
- [Información general sobre el componente ImageList](imagelist-component-overview-windows-forms.md)
- [Imágenes, mapas de bits y metarchivos](../advanced/images-bitmaps-and-metafiles.md)
