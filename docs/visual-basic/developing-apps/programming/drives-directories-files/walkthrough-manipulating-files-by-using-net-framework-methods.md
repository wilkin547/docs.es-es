---
title: "Tutorial: Manipular archivos utilizando m&#233;todos de .NET Framework (Visual Basic) | Microsoft Docs"
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
  - "archivos, obtener acceso"
  - "archivos, buscar"
  - "E/S [Visual Basic], leer texto de archivos"
  - "E/S [Visual Basic], tutoriales"
  - "E/S [Visual Basic], escribir texto en archivos"
  - "leer archivos de texto"
  - "StreamReader (clase), tutoriales"
  - "StreamWriter (clase), tutoriales"
  - "archivos de texto, leer"
  - "archivos de texto, escribir"
  - "texto, escribir en archivos"
  - "escribir en archivos, tutoriales"
ms.assetid: 7d2109eb-f98a-4389-b43d-30f384aaa7d5
caps.latest.revision: 18
caps.handback.revision: 18
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Tutorial: Manipular archivos utilizando m&#233;todos de .NET Framework (Visual Basic)
[!INCLUDE[vs2017banner](../../../../csharp/includes/vs2017banner.md)]

Este tutorial muestra cómo abrir y leer un archivo utilizando la clase <xref:System.IO.StreamReader>, comprobar si se está teniendo acceso a un archivo, buscar una cadena dentro de un archivo leído con una instancia de la clase <xref:System.IO.StreamReader> y escribir en un archivo utilizando la clase <xref:System.IO.StreamWriter>.  
  
 [!INCLUDE[note_settings_general](../../../../csharp/language-reference/compiler-messages/includes/note_settings_general_md.md)]  
  
## Crear la aplicación  
 Inicie [!INCLUDE[vsprvs](../../../../csharp/includes/vsprvs_md.md)] y comience el proyecto creando un formulario que el usuario pueda utilizar para escribir en el archivo designado.  
  
#### Para crear el proyecto  
  
1.  En el menú **Archivo**, seleccione **Nuevo proyecto**.  
  
2.  En el panel **Nuevo proyecto**, haga clic en **Aplicación para Windows**.  
  
3.  En el cuadro **Nombre**, escriba `MyDiary` y haga clic en **Aceptar**.  
  
     [!INCLUDE[vsprvs](../../../../csharp/includes/vsprvs_md.md)] agrega el proyecto al **Explorador de soluciones** y se abre el **Diseñador de Windows Forms**.  
  
4.  Agregue los controles de la siguiente tabla al formulario y establezca los correspondientes valores para sus propiedades.  
  
||||  
|-|-|-|  
|**Objeto.**|**Propiedades**|**Valor**|  
|<xref:System.Windows.Forms.Button>|**Name**<br /><br /> **Text**|`Submit`<br /><br /> Enviar entrada|  
|<xref:System.Windows.Forms.Button>|**Name**<br /><br /> **Text**|`Clear`<br /><br /> Borrar entrada|  
|<xref:System.Windows.Forms.TextBox>|**Name**<br /><br /> **Text**<br /><br /> **Multiline**|`Entry`<br /><br /> Escriba algo.<br /><br /> `False`|  
  
## Escribir en el archivo  
 Si desea agregar funcionalidad para escribir en un archivo a través de la aplicación, utilice la clase <xref:System.IO.StreamWriter>.  <xref:System.IO.StreamWriter> se ha diseñado para la salida de caracteres mediante una codificación determinada, mientras que la clase <xref:System.IO.Stream> se ha diseñado para la entrada y salida de bytes.  Utilice <xref:System.IO.StreamWriter> para escribir líneas de información en un archivo de texto estándar.  Para obtener más información sobre la clase <xref:System.IO.StreamWriter>, vea <xref:System.IO.StreamWriter>.  
  
#### Para agregar la funcionalidad de escritura  
  
1.  En el menú **Ver**, elija **Código** para abrir el Editor de código.  
  
2.  Dado que la aplicación hace referencia al espacio de nombres <xref:System.IO>, agregue las siguientes instrucciones al principio del código, antes de la declaración de código del formulario, que empieza por `Public Class Form1`.  
  
     [!code-vb[VbVbcnMyFileSystem#35](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/walkthrough-manipulating-files-by-using-net-framework-methods_1.vb)]  
  
     Antes de escribir en el archivo, deberá crear una instancia de una clase <xref:System.IO.StreamWriter>.  
  
3.  En el menú **Ver**, elija **Diseñador** para volver al **Diseñador de Windows Forms**.  Haga doble clic en el botón `Submit` para crear un controlador de eventos <xref:System.Windows.Forms.Control.Click> para el botón y, a continuación, agréguele el código siguiente:  
  
     [!code-vb[VbVbcnMyFileSystem#36](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/walkthrough-manipulating-files-by-using-net-framework-methods_2.vb)]  
  
> [!NOTE]
>  El Entorno de desarrollo integrado \(IDE\) de Visual Studio volverá al Editor de código y colocará el punto de inserción dentro del controlador de eventos donde debe agregar el código.  
  
1.  Para escribir en el archivo, utilice el método <xref:System.IO.StreamWriter.Write%2A> de la clase <xref:System.IO.StreamWriter>.  Agregue el código siguiente directamente después de `Dim fw As StreamWriter`:  No debe preocuparse por que se produzca una excepción si el archivo no existe, porque se creará si no existe ya.  
  
     [!code-vb[VbVbcnMyFileSystem#37](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/walkthrough-manipulating-files-by-using-net-framework-methods_3.vb)]  
  
2.  Asegúrese de que el usuario no pueda enviar una entrada en blanco agregando el código siguiente inmediatamente después de `Dim ReadString As String`.  
  
     [!code-vb[VbVbcnMyFileSystem#38](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/walkthrough-manipulating-files-by-using-net-framework-methods_4.vb)]  
  
3.  Dado que se trata de un diario, el usuario deseará asignar una fecha a cada entrada.  Inserte el código siguiente después de `fw = New StreamWriter("C:\MyDiary.txt", True)` para establecer la variable `Today` en la fecha actual.  
  
     [!code-vb[VbVbcnMyFileSystem#39](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/walkthrough-manipulating-files-by-using-net-framework-methods_5.vb)]  
  
4.  Por último, anexe código para borrar el cuadro de texto <xref:System.Windows.Forms.TextBox>.  Agregue el código siguiente al evento <xref:System.Windows.Forms.Control.Click> del botón `Clear`.  
  
     [!code-vb[VbVbcnMyFileSystem#40](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/walkthrough-manipulating-files-by-using-net-framework-methods_6.vb)]  
  
## Agregar características de presentación al diario  
 En esta sección, debe agregar una característica que muestra la última entrada del <xref:System.Windows.Forms.TextBox> `DisplayEntry`.  También puede agregar un cuadro combinado <xref:System.Windows.Forms.ComboBox> que muestra varias entradas y desde el que un usuario puede seleccionar una entrada que mostrar en el <xref:System.Windows.Forms.TextBox> `DisplayEntry`.  Una instancia de la clase <xref:System.IO.StreamReader> lee de `MyDiary.txt`.  Al igual que la clase <xref:System.IO.StreamWriter>, <xref:System.IO.StreamReader> está pensado para su uso con archivos de texto.  
  
 Para esta sección del tutorial, agregue los controles de la siguiente tabla al formulario y establezca los correspondientes valores para sus propiedades.  
  
|Control|Propiedades|Valores|  
|-------------|-----------------|-------------|  
|<xref:System.Windows.Forms.TextBox>|**Name**<br /><br /> **Visible**<br /><br /> **Size**<br /><br /> **Multiline**|`DisplayEntry`<br /><br /> `False`<br /><br /> `120,60`<br /><br /> `True`|  
|<xref:System.Windows.Forms.Button>|**Name**<br /><br /> **Text**|`Display`<br /><br /> Display|  
|<xref:System.Windows.Forms.Button>|**Name**<br /><br /> **Text**|`GetEntries`<br /><br /> Obtener entradas|  
|<xref:System.Windows.Forms.ComboBox>|**Name**<br /><br /> **Text**<br /><br /> **Enabled**|`PickEntries`<br /><br /> Seleccionar una entrada<br /><br /> `False`|  
  
#### Para rellenar el cuadro combinado  
  
1.  El <xref:System.Windows.Forms.ComboBox> `PickEntries` se utiliza para mostrar las fechas en las que el usuario envía cada entrada, de modo que el usuario pueda seleccionar la entrada correspondiente a una fecha específica.  Cree un controlador de eventos <xref:System.Windows.Forms.Control.Click> para el botón `GetEntries` y agréguele el código siguiente.  
  
     [!code-vb[VbVbcnMyFileSystem#41](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/walkthrough-manipulating-files-by-using-net-framework-methods_7.vb)]  
  
2.  Para probar el código, presione F5 para compilar la aplicación y haga clic en **Obtener entradas**.  Haga clic en la flecha desplegable del <xref:System.Windows.Forms.ComboBox> para mostrar las fechas de entrada.  
  
#### Para elegir y mostrar entradas individuales  
  
1.  Cree un controlador de eventos <xref:System.Windows.Forms.Control.Click> para el botón `Display` y agréguele el código siguiente.  
  
     [!code-vb[VbVbcnMyFileSystem#42](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/walkthrough-manipulating-files-by-using-net-framework-methods_8.vb)]  
  
2.  Para probar el código, presione F5 para compilar la aplicación y envíe una entrada.  Haga clic en **Obtener entradas**, seleccione una entrada en el <xref:System.Windows.Forms.ComboBox> y haga clic en **Display**.  El contenido de la entrada seleccionada aparecerá en el <xref:System.Windows.Forms.TextBox> `DisplayEntry`.  
  
## Permitir a los usuarios a eliminar o modificar entradas  
 Finalmente, puede incluir funcionalidad adicional para permitir que los usuarios eliminen o modifiquen una entrada utilizando los botones `DeleteEntry` y `EditEntry`.  Ambos botones permanecen deshabilitados a menos que se esté mostrando una entrada.  
  
 Agregue los controles de la siguiente tabla al formulario y establezca los correspondientes valores para sus propiedades.  
  
|Control|Propiedades|Valores|  
|-------------|-----------------|-------------|  
|<xref:System.Windows.Forms.Button>|**Name**<br /><br /> **Text**<br /><br /> **Enabled**|`DeleteEntry`<br /><br /> Eliminar entrada<br /><br /> `False`|  
|<xref:System.Windows.Forms.Button>|**Name**<br /><br /> **Text**<br /><br /> **Enabled**|`EditEntry`<br /><br /> Editar entrada<br /><br /> `False`|  
|<xref:System.Windows.Forms.Button>|**Name**<br /><br /> **Text**<br /><br /> **Enabled**|`SubmitEdit`<br /><br /> Enviar edición<br /><br /> `False`|  
  
#### Para habilitar la eliminación y modificación de entradas  
  
1.  Agregue el código siguiente al evento <xref:System.Windows.Forms.Control.Click> del botón `Display`, a continuación de `DisplayEntry.Text = ReadString`.  
  
     [!code-vb[VbVbcnMyFileSystem#43](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/walkthrough-manipulating-files-by-using-net-framework-methods_9.vb)]  
  
2.  Cree un controlador de eventos <xref:System.Windows.Forms.Control.Click> para el botón `DeleteEntry` y agréguele el código siguiente.  
  
     [!code-vb[VbVbcnMyFileSystem#44](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/walkthrough-manipulating-files-by-using-net-framework-methods_10.vb)]  
  
3.  Cuando un usuario muestra una entrada, se habilita el botón `EditEntry`.  Agregue el código siguiente al controlador de eventos <xref:System.Windows.Forms.Control.Click> del botón `Display`, a continuación de `DisplayEntry.Text = ReadString`.  
  
     [!code-vb[VbVbcnMyFileSystem#45](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/walkthrough-manipulating-files-by-using-net-framework-methods_11.vb)]  
  
4.  Cree un controlador de eventos <xref:System.Windows.Forms.Control.Click> para el botón `EditEntry` y agréguele el código siguiente.  
  
     [!code-vb[VbVbcnMyFileSystem#46](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/walkthrough-manipulating-files-by-using-net-framework-methods_12.vb)]  
  
5.  Cree un controlador de eventos <xref:System.Windows.Forms.Control.Click> para el botón `SubmitEdit` y agréguele el código siguiente.  
  
     [!code-vb[VbVbcnMyFileSystem#47](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/walkthrough-manipulating-files-by-using-net-framework-methods_13.vb)]  
  
 Para probar el código, presione F5 para compilar la aplicación.  Haga clic en **Obtener entradas**, seleccione una entrada y, a continuación, haga clic en **Display**.  La entrada aparece en el <xref:System.Windows.Forms.TextBox> `DisplayEntry`.  Haga clic en **Editar entrada**.  La entrada aparece en el <xref:System.Windows.Forms.TextBox> `Entry`.  Edite la entrada del <xref:System.Windows.Forms.TextBox> `Entry` y haga clic en **Enviar edición**.  Abra el archivo `MyDiary.txt` para confirmar la corrección.  Seleccione una entrada y haga clic en **Eliminar entrada**.  Cuando el <xref:System.Windows.Forms.MessageBox> solicite confirmación, haga clic en **Aceptar**.  Cierre la aplicación y abra `MyDiary.txt` para confirmar la eliminación.  
  
## Vea también  
 <xref:System.IO.StreamReader>   
 <xref:System.IO.StreamWriter>   
 [Tutoriales](../../../../visual-basic/walkthroughs.md)