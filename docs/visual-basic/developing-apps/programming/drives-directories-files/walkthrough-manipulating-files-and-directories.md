---
title: "Tutorial: Manipular archivos y directorios en Visual Basic | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "acceso a archivos, tutoriales"
  - "archivos, leer texto"
  - "archivos, escribir texto"
  - "E/S [Visual Basic], leer texto de archivos"
  - "E/S [Visual Basic], tutoriales"
  - "E/S [Visual Basic], escribir texto en archivos"
  - "leer archivos, texto"
  - "leer texto de archivos, tutoriales"
  - "texto, leer de archivos"
  - "texto, escribir en archivos"
  - "código de Visual Basic, acceso a archivos"
  - "escribir en archivos, tutoriales"
ms.assetid: cae77565-9f78-4e46-8e42-eb2f9f8e1ffd
caps.latest.revision: 49
caps.handback.revision: 49
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Tutorial: Manipular archivos y directorios en Visual Basic
[!INCLUDE[vs2017banner](../../../../csharp/includes/vs2017banner.md)]

Este tutorial ofrece una introducción a los fundamentos de la E\/S de archivos en [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)].  Describe cómo crear una aplicación pequeña que enumera y examina los archivos de texto en un directorio.  Para cada archivo de texto seleccionado, la aplicación proporciona atributos de archivo y la primera línea de contenido.  Hay una opción para escribir información en un archivo de registro.  
  
 Este tutorial utiliza miembros de `My.Computer.FileSystem Object`, que están disponibles en [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)].  Vea <xref:Microsoft.VisualBasic.FileIO.FileSystem> para obtener más información.  Al final del tutorial, se proporciona un ejemplo equivalente que usa clases del espacio de nombres <xref:System.IO>.  
  
 [!INCLUDE[note_settings_general](../../../../csharp/language-reference/compiler-messages/includes/note_settings_general_md.md)]  
  
### Para crear el proyecto  
  
1.  En el menú **Archivo**, haga clic en **Nuevo proyecto**.  
  
     Aparecerá el cuadro de diálogo **Nuevo proyecto**.  
  
2.  En el panel **Plantillas instaladas**, expanda **Visual Basic** y, a continuación, haga clic en **Windows**.  En el panel central **Plantillas**, haga clic en **Aplicación de Windows Forms**.  
  
3.  En el cuadro **Nombre**, escriba `FileExplorer` para establecer el nombre del proyecto y, a continuación, haga clic en **Aceptar**.  
  
     [!INCLUDE[vsprvs](../../../../csharp/includes/vsprvs_md.md)] agregará el proyecto al **Explorador de soluciones** y se abrirá el Diseñador de Windows Forms.  
  
4.  Agregue los controles de la siguiente tabla al formulario y establezca los correspondientes valores para sus propiedades.  
  
    |Control|Propiedad.|Valor|  
    |-------------|----------------|-----------|  
    |**ListBox**|**Name**|`filesListBox`|  
    |**Button**|**Name**<br /><br /> **Text**|`browseButton`<br /><br /> Browse|  
    |**Button**|**Name**<br /><br /> **Text**|`examineButton`<br /><br /> Examine|  
    |**CheckBox**|**Name**<br /><br /> **Text**|`saveCheckBox`<br /><br /> Guardar resultados|  
    |**FolderBrowserDialog**|**Name**|`FolderBrowserDialog1`|  
  
### Seleccionar una carpeta y enumerar archivos en una carpeta  
  
1.  Cree un controlador de eventos `Click` para `browseButton` haciendo doble clic en el control del formulario.  Se abrirá el Editor de código.  
  
2.  Agregue el código siguiente al controlador de eventos `Click`.  
  
     [!code-vb[VbVbcnMyFileSystem#103](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/walkthrough-manipulating-files-and-directories_1.vb)]  
  
     La llamada `FolderBrowserDialog1.ShowDialog` abre el cuadro de diálogo **Buscar carpeta**.  Una vez que el usuario hace clic en **Aceptar**, la propiedad <xref:System.Windows.Forms.FolderBrowserDialog.SelectedPath%2A> se envía como un argumento al método `ListFiles`, que se agrega en el paso siguiente.  
  
3.  Agregue el siguiente método `ListFiles`.  
  
     [!code-vb[VbVbcnMyFileSystem#104](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/walkthrough-manipulating-files-and-directories_2.vb)]  
  
     Este código primero borra el control **ListBox**.  
  
     A continuación, el método <xref:Microsoft.VisualBasic.FileIO.FileSystem.GetFiles%2A> recupera una colección de cadenas, una para cada archivo del directorio.  El método `GetFiles` acepta un argumento de modelo de búsqueda para recuperar los archivos que coinciden con un modelo determinado.  En este ejemplo, únicamente se devuelven los archivos que tienen la extensión .txt.  
  
     A continuación, las cadenas que devuelve el método `GetFiles` se agregan al control **ListBox**.  
  
4.  Ejecute la aplicación.  Haga clic en el botón **Examinar**.  En el cuadro de diálogo **Buscar carpeta**, busque una carpeta con archivos .txt y, a continuación, seleccione la carpeta y haga clic en **Aceptar**.  
  
     `ListBox` contiene una lista de archivos .txt en la carpeta seleccionada.  
  
5.  Detenga la ejecución de la aplicación.  
  
### Obtener atributos de un archivo y contenido de un archivo de texto  
  
1.  Cree un controlador de eventos `Click` para `examineButton` haciendo doble clic en el control del formulario.  
  
2.  Agregue el código siguiente al controlador de eventos `Click`.  
  
     [!code-vb[VbVbcnMyFileSystem#105](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/walkthrough-manipulating-files-and-directories_3.vb)]  
  
     El código comprueba que un elemento está seleccionado en `ListBox`.  A continuación, obtiene la entrada de la ruta de acceso del archivo de `ListBox`.  El método <xref:Microsoft.VisualBasic.FileIO.FileSystem.FileExists%2A> se utiliza para comprobar si el archivo todavía existe.  
  
     La ruta de acceso del archivo se envía como un argumento al método `GetTextForOutput`, que se agrega en el paso siguiente.  Este método devuelve una cadena que contiene la información del archivos.  La información del archivo aparece en un **MessageBox**.  
  
3.  Agregue el siguiente método `GetTextForOutput`.  
  
     [!code-vb[VbVbcnMyFileSystem#107](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/walkthrough-manipulating-files-and-directories_4.vb)]  
  
     El código utiliza el método <xref:Microsoft.VisualBasic.FileIO.FileSystem.GetFileInfo%2A> para obtener los parámetros del archivo.  Los parámetros del archivo se agregan a <xref:System.Text.StringBuilder>.  
  
     El método <xref:Microsoft.VisualBasic.FileIO.FileSystem.OpenTextFileReader%2A> lee el contenido del archivo en <xref:System.IO.StreamReader>.  La primera línea del contenido se obtiene de `StreamReader` y se agrega a `StringBuilder`.  
  
4.  Ejecute la aplicación.  Haga clic en **Browse** y vaya a una carpeta que contiene archivos .txt.  Haga clic en **Aceptar**.  
  
     Seleccione un archivo en `ListBox` y, a continuación, haga clic en **Examine**.  `MessageBox` muestra la información del archivo.  
  
5.  Detenga la ejecución de la aplicación.  
  
### Agregar una entrada de registro  
  
1.  Agregue el siguiente código al final del controlador de eventos `examineButton_Click`.  
  
     [!code-vb[VbVbcnMyFileSystem#106](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/walkthrough-manipulating-files-and-directories_5.vb)]  
  
     El código establece la ruta del archivo de registro para colocar el archivo de registro en el mismo directorio que el archivo seleccionado.  El texto de la entrada de registro se establece en la fecha y hora actual seguido de la información del archivo.  
  
     El método <xref:Microsoft.VisualBasic.FileIO.FileSystem.WriteAllText%2A>, con el argumento `append` establecido en `True`, se utiliza para crear la entrada de registro.  
  
2.  Ejecute la aplicación.  Vaya a un archivo de texto, selecciónelo en `ListBox`, active la casilla **Guardar resultados** y, a continuación, haga clic en **Examine**.  Compruebe que la entrada de registro está escrita en el archivo `log.txt`.  
  
3.  Detenga la ejecución de la aplicación.  
  
### Utilizar el directorio actual  
  
1.  Haga doble clic en el formulario para crear un controlador de eventos para `Form1_Load`.  
  
2.  Agregue el siguiente código al controlador de eventos.  
  
     [!code-vb[VbVbcnMyFileSystem#102](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/walkthrough-manipulating-files-and-directories_6.vb)]  
  
     Este código establece el directorio predeterminado del explorador de la carpeta en el directorio actual.  
  
3.  Ejecute la aplicación.  Al hacer clic por primera vez en **Examinar**, se abre el cuadro de diálogo **Buscar carpeta** en el directorio actual.  
  
4.  Detenga la ejecución de la aplicación.  
  
### Habilitar controles de forma selectiva  
  
1.  Agregue el siguiente método `SetEnabled`.  
  
     [!code-vb[VbVbcnMyFileSystem#108](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/walkthrough-manipulating-files-and-directories_7.vb)]  
  
     El método `SetEnabled` habilita o deshabilita controles dependiendo de si un elemento se selecciona en `ListBox`.  
  
2.  Cree un controlador de eventos `SelectedIndexChanged` para `filesListBox` haciendo doble clic en el control `ListBox` del formulario.  
  
3.  Agregue una llamada a `SetEnabled` en el nuevo controlador de eventos `filesListBox_SelectedIndexChanged`.  
  
4.  Agregue una llamada a `SetEnabled` la final del controlador de eventos `browseButton_Click`.  
  
5.  Agregue una llamada a `SetEnabled` la final del controlador de eventos `Form1_Load`.  
  
6.  Ejecute la aplicación.  La casilla **Guardar resultados** y el botón **Examine** se deshabilitan deshabilitados si no se selecciona un elemento en `ListBox`.  
  
## Ejemplo completo utilizando My.Computer.FileSystem  
 El ejemplo completo aparece a continuación.  
  
 [!code-vb[VbVbcnMyFileSystem#101](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/walkthrough-manipulating-files-and-directories_8.vb)]  
  
## Ejemplo completo utilizando System.IO  
 El siguiente ejemplo equivalente utiliza las clases del espacio de nombres <xref:System.IO> en lugar de utilizar los objetos `My.Computer.FileSystem`.  
  
 [!code-vb[VbVbcnMyFileSystem#111](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/walkthrough-manipulating-files-and-directories_9.vb)]  
  
## Vea también  
 <xref:System.IO>   
 <xref:Microsoft.VisualBasic.FileIO.FileSystem>   
 <xref:Microsoft.VisualBasic.FileIO.FileSystem.CurrentDirectory%2A>   
 [Tutorial: Manipular archivos utilizando métodos de .NET Framework](../../../../visual-basic/developing-apps/programming/drives-directories-files/walkthrough-manipulating-files-by-using-net-framework-methods.md)