---
title: "C&#243;mo: Agregar o quitar im&#225;genes con el componente ImageList de formularios Windows Forms | Microsoft Docs"
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
  - "ImageList (componente) [Windows Forms], agregar imágenes"
  - "ImageList (componente) [Windows Forms], quitar imágenes"
  - "imágenes [Windows Forms], agregar al componente ImageList"
  - "imágenes [Windows Forms], mostrar con controles"
  - "imágenes [Windows Forms], quitar del componente ImageList"
  - "imágenes [Windows Forms], almacenar para controles"
ms.assetid: c5eacc56-f769-4e2e-bfb7-f756620913db
caps.latest.revision: 15
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 15
---
# C&#243;mo: Agregar o quitar im&#225;genes con el componente ImageList de formularios Windows Forms
Se suele llenar el componente <xref:System.Windows.Forms.ImageList> de formularios Windows Forms con imágenes antes de asociarlo a un control.  Sin embargo, es posible agregar y quitar imágenes después de asociar la lista de imágenes con un control.  
  
> [!NOTE]
>  Cuando quite imágenes, compruebe que la propiedad <xref:System.Windows.Forms.ButtonBase.ImageIndex%2A> de los controles asociados siga siendo válida.  
  
### Para agregar imágenes mediante programación  
  
-   Utilice el método <xref:System.Windows.Forms.ImageList.ImageCollection.Add%2A> de la propiedad <xref:System.Windows.Forms.ImageList.Images%2A> de la lista de imágenes.  
  
     En el ejemplo de código siguiente, la ruta de acceso establecida para la ubicación de la imagen es la carpeta **Mis documentos**.  Se utiliza esta ubicación porque se puede asumir que la mayoría de los equipos que ejecuten el sistema operativo Windows tendrán esta carpeta.  Al elegir esta ubicación, también se permite a los usuarios con niveles de acceso mínimos ejecutar la aplicación de un modo más seguro.  El ejemplo de código siguiente requiere que tenga un formulario con un control <xref:System.Windows.Forms.ImageList> ya agregado.  
  
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
  
### Para agregar imágenes con un valor de clave.  
  
-   Utilice uno de los métodos <xref:System.Windows.Forms.ImageList.ImageCollection.Add%2A> de la propiedad <xref:System.Windows.Forms.ImageList.Images%2A> de la lista de imágenes que toma un valor de clave.  
  
     En el ejemplo de código siguiente, la ruta de acceso establecida para la ubicación de la imagen es la carpeta **Mis documentos**.  Se utiliza esta ubicación porque se puede asumir que la mayoría de los equipos que ejecuten el sistema operativo Windows tendrán esta carpeta.  Al elegir esta ubicación, también se permite a los usuarios con niveles de acceso mínimos ejecutar la aplicación de un modo más seguro.  El ejemplo de código siguiente requiere que tenga un formulario con un control <xref:System.Windows.Forms.ImageList> ya agregado.  
  
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
  
### Para quitar todas las imágenes mediante programación  
  
-   Utilice el método <xref:System.Windows.Forms.ImageList.ImageCollection.Remove%2A> para quitar una sola imagen.  
  
     O bien,  
  
     Utilice el método <xref:System.Windows.Forms.ImageList.ImageCollection.Clear%2A> para borrar todas las imágenes de la lista de imágenes.  
  
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
  
### Para quitar las imágenes por clave  
  
-   Utilice el método <xref:System.Windows.Forms.ImageList.ImageCollection.RemoveByKey%2A> para quitar una sola imagen por su clave.  
  
    ```vb  
    ' Removes the image named "myPhoto" from the list.  
    ImageList1.Images.RemoveByKey("myPhoto")  
  
    ```  
  
```csharp  
// Removes the image named "myPhoto" from the list.  
imageList1.Images.RemoveByKey("myPhoto");  
  
```  
  
## Vea también  
 [ImageList](../../../../docs/framework/winforms/controls/imagelist-component-windows-forms.md)   
 [Información general sobre el componente ImageList](../../../../docs/framework/winforms/controls/imagelist-component-overview-windows-forms.md)   
 [Imágenes, mapas de bits y metarchivos](../../../../docs/framework/winforms/advanced/images-bitmaps-and-metafiles.md)