---
title: "C&#243;mo: Cargar una imagen mediante el Dise&#241;ador (formularios Windows Forms) | Microsoft Docs"
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
  - "formularios, mostrar imágenes"
  - "imágenes [Windows Forms], mostrar en Windows Forms"
  - "formatos de imagen"
  - "PictureBox (control) [Windows Forms], agregar imágenes"
  - "imágenes, mostrar"
ms.assetid: 4dc7b973-afb1-4276-8322-20825af96655
caps.latest.revision: 9
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 9
---
# C&#243;mo: Cargar una imagen mediante el Dise&#241;ador (formularios Windows Forms)
Con el control <xref:System.Windows.Forms.PictureBox> de formularios Windows Forms, puede cargar y mostrar una imagen en un formulario en tiempo de diseño; para ello, establezca una imagen válida como la propiedad <xref:System.Windows.Forms.PictureBox.Image%2A>.  En la tabla siguiente se muestran los tipos de archivo aceptables.  
  
|Tipo|Extensión de nombre de archivo|  
|----------|------------------------------------|  
|Mapa de bits|.bmp|  
|Icono|.ico|  
|GIF|.gif|  
|Metarchivo|.wmf|  
|JPEG|.jpg|  
  
> [!NOTE]
>  Los cuadros de diálogo y comandos de menú que se ven pueden diferir de los descritos en la Ayuda, en función de los valores de configuración o de edición activos.  Para cambiar la configuración, elija **Importar y exportar configuraciones** en el menú **Herramientas**.  Para obtener más información, vea [Customizing Development Settings in Visual Studio](http://msdn.microsoft.com/es-es/22c4debb-4e31-47a8-8f19-16f328d7dcd3).  
  
### Para mostrar una imagen en tiempo de diseño  
  
1.  Dibuje un control <xref:System.Windows.Forms.PictureBox> en un formulario.  
  
2.  En la ventana Propiedades, seleccione la propiedad <xref:System.Windows.Forms.PictureBox.Image%2A> y, a continuación, haga clic en el botón de puntos suspensivos para mostrar el cuadro de diálogo **Abrir**.  
  
3.  Si busca un tipo de archivo específico \(por ejemplo, archivos .gif\), selecciónelo en el cuadro **Tipo de archivos**.  
  
4.  Seleccione el archivo que desee mostrar.  
  
### Para borrar la imagen en tiempo de diseño  
  
1.  En la ventana **Propiedades**, seleccione la propiedad <xref:System.Windows.Forms.PictureBox.Image%2A> y haga clic con el botón secundario del mouse en la imagen en miniatura que aparece a la izquierda del nombre del objeto de imagen.  Elija **Restablecer**.  
  
## Vea también  
 <xref:System.Windows.Forms.PictureBox>   
 [Información general del control PictureBox](../../../../docs/framework/winforms/controls/picturebox-control-overview-windows-forms.md)   
 [Cómo: Modificar el tamaño o la situación de una imagen en tiempo de ejecución](../../../../docs/framework/winforms/controls/how-to-modify-the-size-or-placement-of-a-picture-at-run-time-windows-forms.md)   
 [Cómo: Establecer imágenes en tiempo de ejecución](../../../../docs/framework/winforms/controls/how-to-set-pictures-at-run-time-windows-forms.md)   
 [PictureBox \(Control\)](../../../../docs/framework/winforms/controls/picturebox-control-windows-forms.md)