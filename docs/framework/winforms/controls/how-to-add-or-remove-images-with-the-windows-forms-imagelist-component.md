---
title: Filtrar Agregar o quitar imágenes con el componente ImageList de formularios Windows Forms
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
ms.openlocfilehash: 81c85186d2f15917a6aa1067814a0119edf3f460
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/09/2019
ms.locfileid: "57705173"
---
# <a name="how-to-add-or-remove-images-with-the-windows-forms-imagelist-component"></a>Procedimiento Agregar o quitar imágenes con el componente ImageList de formularios Windows Forms
Los formularios de Windows <xref:System.Windows.Forms.ImageList> componente normalmente se rellena con las imágenes antes de asociarlo con un control. Sin embargo, puede agregar y quitar imágenes después de asociar la lista de imágenes con un control.  
  
> [!NOTE]
>  Al quitar las imágenes, compruebe que la <xref:System.Windows.Forms.ButtonBase.ImageIndex%2A> sigue siendo válida la propiedad de los controles asociados.  
  
### <a name="to-add-images-programmatically"></a>Para agregar imágenes mediante programación  
  
-   Use la <xref:System.Windows.Forms.ImageList.ImageCollection.Add%2A> método de la lista de imágenes <xref:System.Windows.Forms.ImageList.Images%2A> propiedad.  
  
     En el ejemplo de código siguiente establece la ruta de acceso para la ubicación de la imagen es la **Mis documentos** carpeta. Se utiliza esta ubicación porque se puede suponer que la mayoría de los equipos que ejecuta el sistema operativo Windows incluirá esta carpeta. Al elegir esta ubicación también permite a los usuarios que tienen acceso niveles mínimos más ejecutar de forma segura la aplicación. El siguiente ejemplo de código requiere que tenga un formulario con un <xref:System.Windows.Forms.ImageList> control ya se ha agregado.  
  
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
  
### <a name="to-add-images-with-a-key-value"></a>Para agregar las imágenes con un valor de clave.  
  
-   Utilice uno de los <xref:System.Windows.Forms.ImageList.ImageCollection.Add%2A> métodos de la lista de imágenes <xref:System.Windows.Forms.ImageList.Images%2A> propiedad que toma un valor de clave.  
  
     En el ejemplo de código siguiente establece la ruta de acceso para la ubicación de la imagen es la **Mis documentos** carpeta. Se utiliza esta ubicación porque se puede suponer que la mayoría de los equipos que ejecuta el sistema operativo Windows incluirá esta carpeta. Al elegir esta ubicación también permite a los usuarios que tienen acceso niveles mínimos más ejecutar de forma segura la aplicación. El siguiente ejemplo de código requiere que tenga un formulario con un <xref:System.Windows.Forms.ImageList> control ya se ha agregado.  
  
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
  
-   Use el <xref:System.Windows.Forms.ImageList.ImageCollection.Remove%2A> método para quitar una sola imagen  
  
     , - o -  
  
     Use el <xref:System.Windows.Forms.ImageList.ImageCollection.Clear%2A> método para borrar todas las imágenes en la lista de imágenes.  
  
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
  
### <a name="to-remove-images-by-key"></a>Para quitar las imágenes por clave  
  
-   Use el <xref:System.Windows.Forms.ImageList.ImageCollection.RemoveByKey%2A> método para quitar una sola imagen por su clave.  
  
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
