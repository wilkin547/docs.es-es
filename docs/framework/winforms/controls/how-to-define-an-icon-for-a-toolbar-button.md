---
title: "C&#243;mo: Definir un icono para un bot&#243;n ToolBar | Microsoft Docs"
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
  - "botones [Windows Forms], iconos"
  - "ejemplos [Windows Forms], barras de herramientas"
  - "iconos [Windows Forms], botones de la barra de herramientas"
  - "imágenes [Windows Forms], botones de la barra de herramientas"
  - "ToolBar (control) [Windows Forms], agregar iconos a los botones"
  - "barras de herramientas [Windows Forms], agregar iconos a los botones"
ms.assetid: 84db98b4-8566-49ce-b2c8-1fd66a5eb3a0
caps.latest.revision: 14
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 14
---
# C&#243;mo: Definir un icono para un bot&#243;n ToolBar
> [!NOTE]
>  Aunque el control <xref:System.Windows.Forms.ToolStrip> reemplaza y agrega funcionalidad al control <xref:System.Windows.Forms.ToolBar>, este control <xref:System.Windows.Forms.ToolBar> se conserva a efectos de compatibilidad con versiones anteriores y, en su caso, de uso futuro.  
  
 Los botones <xref:System.Windows.Forms.ToolBar> pueden mostrar iconos dentro de ellos para facilitar la identificación por parte de los usuarios.  Esto se logra agregando imágenes al componente [ImageList](../../../../docs/framework/winforms/controls/imagelist-component-windows-forms.md) y asociando el componente <xref:System.Windows.Forms.ImageList> al control <xref:System.Windows.Forms.ToolBar>.  
  
### Para establecer iconos de botones de la barra de herramientas mediante programación  
  
1.  En un procedimiento, genere una instancia del componente <xref:System.Windows.Forms.ImageList> y del control <xref:System.Windows.Forms.ToolBar>.  
  
2.  En el mismo procedimiento, asigne una imagen al componente <xref:System.Windows.Forms.ImageList>.  
  
3.  En el mismo procedimiento, asigne el control <xref:System.Windows.Forms.ImageList> al control <xref:System.Windows.Forms.ToolBar> y asigne la propiedad <xref:System.Windows.Forms.ToolBarButton.ImageIndex%2A> de los botones individuales de la barra de herramientas.  
  
     En el ejemplo de código siguiente, la ruta de acceso establecida para la ubicación de la imagen es la carpeta **Mis documentos**.  Se utiliza esta ubicación porque se puede asumir que la mayoría de los equipos que ejecuten el sistema operativo Windows tendrán este directorio.  Esto permite también a los usuarios con niveles de acceso mínimos ejecutar la aplicación de un modo seguro.  En el ejemplo siguiente suponemos que ya se ha agregado un control <xref:System.Windows.Forms.PictureBox> al formulario.  
  
     Siguiendo los pasos anteriores, debería haber escrito un código similar al que se muestra a continuación.  
  
    ```vb  
    Public Sub InitializeMyToolBar()  
    ' Instantiate an ImageList component and a ToolBar control.  
       Dim ToolBar1 as New ToolBar  
       Dim ImageList1 as New ImageList  
    ' Assign an image to the ImageList component.  
    ' You should replace the bold image  
    ' in the sample below with an icon of your own choosing.  
       Dim myImage As System.Drawing.Image = _   
          Image.FromFile Image.FromFile _  
          (System.Environment.GetFolderPath _  
          (System.Environment.SpecialFolder.Personal) _  
          & "\Image.gif")  
       ImageList1.Images.Add(myImage)  
    ' Create a ToolBarButton.  
       Dim ToolBarButton1 As New ToolBarButton()  
    ' Add the ToolBarButton to the ToolBar.  
       ToolBar1.Buttons.Add(toolBarButton1)  
    ' Assign an ImageList to the ToolBar.  
       ToolBar1.ImageList = ImageList1  
    ' Assign the ImageIndex property of the ToolBarButton.  
       ToolBarButton1.ImageIndex = 0  
    End Sub  
  
    ```  
  
    ```csharp  
    public void InitializeMyToolBar()  
    {  
       // Instantiate an ImageList component and a ToolBar control.  
       ToolBar toolBar1 = new  ToolBar();   
       ImageList imageList1 = new ImageList();  
       // Assign an image to the ImageList component.  
       // You should replace the bold image   
       // in the sample below with an icon of your own choosing.  
       // Note the escape character used (@) when specifying the path.  
       Image myImage = Image.FromFile  
       (System.Environment.GetFolderPath  
       (System.Environment.SpecialFolder.Personal)  
       + @"\Image.gif");  
       imageList1.Images.Add(myImage);  
       // Create a ToolBarButton.  
       ToolBarButton toolBarButton1 = new ToolBarButton();  
       // Add the ToolBarButton to the ToolBar.  
       toolBar1.Buttons.Add(toolBarButton1);  
       // Assign an ImageList to the ToolBar.  
       toolBar1.ImageList = imageList1;  
       // Assign ImageIndex property of the ToolBarButton.  
       toolBarButton1.ImageIndex = 0;  
    }  
  
    ```  
  
    ```cpp  
    public:  
       void InitializeMyToolBar()  
       {  
          // Instantiate an ImageList component and a ToolBar control.  
          ToolBar ^ toolBar1 = gcnew  ToolBar();   
          ImageList ^ imageList1 = gcnew ImageList();  
          // Assign an image to the ImageList component.  
          // You should replace the bold image   
          // in the sample below with an icon of your own choosing.  
          Image ^ myImage = Image::FromFile(String::Concat  
             (System::Environment::GetFolderPath  
             (System::Environment::SpecialFolder::Personal),  
             "\\Image.gif"));  
          imageList1->Images->Add(myImage);  
          // Create a ToolBarButton.  
          ToolBarButton ^ toolBarButton1 = gcnew ToolBarButton();  
          // Add the ToolBarButton to the ToolBar.  
          toolBar1->Buttons->Add(toolBarButton1);  
          // Assign an ImageList to the ToolBar.  
          toolBar1->ImageList = imageList1;  
          // Assign ImageIndex property of the ToolBarButton.  
          toolBarButton1->ImageIndex = 0;  
       }  
    ```  
  
## Vea también  
 <xref:System.Windows.Forms.ToolBar>   
 [Cómo: Desencadenar eventos de menú para los botones de la barra de herramientas](../../../../docs/framework/winforms/controls/how-to-trigger-menu-events-for-toolbar-buttons.md)   
 [Barra de herramientas \(Control\)](../../../../docs/framework/winforms/controls/toolbar-control-windows-forms.md)   
 [ImageList](../../../../docs/framework/winforms/controls/imagelist-component-windows-forms.md)