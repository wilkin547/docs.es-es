---
title: Manipulación de archivos y directorios
ms.date: 07/20/2015
helpviewer_keywords:
- files [Visual Basic], reading text
- reading files [Visual Basic], text
- I/O [Visual Basic], walkthroughs
- text, writing to files
- text, reading from files
- reading text from files [Visual Basic], walkthroughs
- Visual Basic code, file access
- files [Visual Basic], writing text
- I/O [Visual Basic], writing text to files
- file access, walkthroughs
- writing to files [Visual Basic], walkthroughs
- I/O [Visual Basic], reading text from files
ms.assetid: cae77565-9f78-4e46-8e42-eb2f9f8e1ffd
ms.openlocfilehash: 4b77618e5cd525cf3ad012405f402681aa5bb52c
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/04/2020
ms.locfileid: "84406669"
---
# <a name="walkthrough-manipulating-files-and-directories-in-visual-basic"></a>Tutorial: Manipular archivos y directorios en Visual Basic

En este tutorial se ofrece una introducción a los conceptos básicos de E/S de archivos en Visual Basic. En él se describe cómo crear una pequeña aplicación que enumera y examina archivos de texto en un directorio. Para cada archivo de texto seleccionado, la aplicación proporciona atributos de archivo y la primera línea de contenido. Existe una opción para escribir información en un archivo de registro.  
  
 En este tutorial se usan los miembros del elemento `My.Computer.FileSystem Object`, que están disponibles en Visual Basic. Vea <xref:Microsoft.VisualBasic.FileIO.FileSystem> para obtener más información. Al final del tutorial, se incluye un ejemplo equivalente que usa clases del espacio de nombres <xref:System.IO>.  
  
[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]  
  
### <a name="to-create-the-project"></a>Para crear el proyecto  
  
1. En el menú **Archivo**, haga clic en **Nuevo proyecto**.  
  
     Aparecerá el cuadro de diálogo **Nuevo proyecto** .  
  
2. En el panel **Plantillas instaladas**, expanda **Visual Basic** y haga clic en **Windows**. En el panel **Plantillas** situado en el medio, haga clic en **Aplicación de Windows Forms**.  
  
3. En la casilla **Nombre**, escriba `FileExplorer` para establecer el nombre del proyecto y, luego, haga clic en **Aceptar**.  
  
     Visual Studio agrega el proyecto al **Explorador de soluciones** y se abre el Diseñador de Windows Forms.  
  
4. Agregue los controles de la siguiente tabla al formulario y establezca los valores correspondientes para sus propiedades.  
  
    |Control|Property|Valor|  
    |-------------|--------------|-----------|  
    |**ListBox**|**Name**|`filesListBox`|  
    |**Button**|**Name**<br /><br /> **Text**|`browseButton`<br /><br /> **Examinar**|  
    |**Button**|**Name**<br /><br /> **Text**|`examineButton`<br /><br /> **Examine** (Examinar)|  
    |**CheckBox**|**Name**<br /><br /> **Text**|`saveCheckBox`<br /><br /> **Guardar resultados**|  
    |**FolderBrowserDialog**|**Name**|`FolderBrowserDialog1`|  
  
### <a name="to-select-a-folder-and-list-files-in-a-folder"></a>Para seleccionar una carpeta y enumerar archivos en una carpeta  
  
1. Cree un controlador de eventos `Click` para `browseButton` haciendo doble clic en el control del formulario. Se abrirá el Editor de código.  
  
2. Agregue el código siguiente al controlador de eventos `Click`.  
  
     [!code-vb[VbVbcnMyFileSystem#103](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnMyFileSystem/VB/class2.vb#103)]  
  
     La llamada `FolderBrowserDialog1.ShowDialog` abre el cuadro de diálogo **Buscar carpeta**. Después de que el usuario hace clic en **Aceptar**, la propiedad <xref:System.Windows.Forms.FolderBrowserDialog.SelectedPath%2A> se envía como un argumento al método `ListFiles`, que se agrega en el paso siguiente.  
  
3. Agregue el siguiente método `ListFiles`.  
  
     [!code-vb[VbVbcnMyFileSystem#104](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnMyFileSystem/VB/class2.vb#104)]  
  
     Este código primero elimina el elemento **ListBox**.  
  
     El método <xref:Microsoft.VisualBasic.FileIO.FileSystem.GetFiles%2A> recupera entonces una colección de cadenas, una para cada archivo del directorio. El método `GetFiles` acepta un argumento de patrón de búsqueda para recuperar los archivos que coinciden con un patrón determinado. En este ejemplo, se devuelven solo los archivos que tengan la extensión .txt.  
  
     Las cadenas devueltas por el método `GetFiles` se agregan luego al elemento **ListBox**.  
  
4. Ejecute la aplicación. Haga clic en el botón **Examinar**. En el cuadro de diálogo **Buscar carpeta**, busque una carpeta que contenga archivos .txt y, luego, selecciónela y haga clic en **Aceptar**.  
  
     El elemento `ListBox` contiene una lista de archivos .txt de la carpeta seleccionada.  
  
5. Deje de ejecutar la aplicación.  
  
### <a name="to-obtain-attributes-of-a-file-and-content-from-a-text-file"></a>Para obtener los atributos de un archivo y contenido de un archivo de texto  
  
1. Cree un controlador de eventos `Click` para `examineButton` haciendo doble clic en el control del formulario.  
  
2. Agregue el código siguiente al controlador de eventos `Click`.  
  
     [!code-vb[VbVbcnMyFileSystem#105](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnMyFileSystem/VB/class2.vb#105)]  
  
     El código comprueba que hay un elemento seleccionado en `ListBox`. Después, obtiene la entrada de ruta de archivo de `ListBox`. El método <xref:Microsoft.VisualBasic.FileIO.FileSystem.FileExists%2A> se usa para comprobar si el archivo todavía existe.  
  
     La ruta del archivo se envía como argumento al método `GetTextForOutput`, que se agrega en el paso siguiente. Este método devuelve una cadena que contiene información del archivo. La información del archivo aparece en un elemento **MessageBox**.  
  
3. Agregue el siguiente método `GetTextForOutput`.  
  
     [!code-vb[VbVbcnMyFileSystem#107](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnMyFileSystem/VB/class2.vb#107)]  
  
     El código usa el método <xref:Microsoft.VisualBasic.FileIO.FileSystem.GetFileInfo%2A> para obtener los parámetros del archivo. Los parámetros del archivo se agregan a <xref:System.Text.StringBuilder>.  
  
     El método <xref:Microsoft.VisualBasic.FileIO.FileSystem.OpenTextFileReader%2A> lee el contenido del archivo en <xref:System.IO.StreamReader>. La primera línea del contenido se obtiene de `StreamReader` y se agrega a `StringBuilder`.  
  
4. Ejecute la aplicación. Haga clic en **Examinar** y busque una carpeta que contenga archivos .txt. Haga clic en **Aceptar**.  
  
     Seleccione un archivo en `ListBox` y, luego, haga clic en **Examine** (Examinar). La información del archivo se muestra en un `MessageBox`.  
  
5. Deje de ejecutar la aplicación.  
  
### <a name="to-add-a-log-entry"></a>Para agregar una entrada de registro  
  
1. Agregue el siguiente código al final del controlador de eventos `examineButton_Click`.  
  
     [!code-vb[VbVbcnMyFileSystem#106](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnMyFileSystem/VB/class2.vb#106)]  
  
     El código establece la ruta del archivo de registro para colocarlo en el mismo directorio que el archivo seleccionado. El texto de la entrada de registro se establece en la fecha y hora actuales, seguido de la información del archivo.  
  
     El método <xref:Microsoft.VisualBasic.FileIO.FileSystem.WriteAllText%2A>, con el argumento `append` establecido en `True`, se usa para crear la entrada de registro.  
  
2. Ejecute la aplicación. Busque un archivo de texto, selecciónelo en `ListBox`, seleccione la casilla **Guardar resultados** y, luego, haga clic en **Examine** (Examinar). Compruebe que la entrada de registro se ha escrito en el archivo `log.txt`.  
  
3. Deje de ejecutar la aplicación.  
  
### <a name="to-use-the-current-directory"></a>Para usar el directorio actual  
  
1. Cree un controlador de eventos para `Form1_Load` haciendo doble clic en el formulario.  
  
2. Agregue el siguiente código al controlador de eventos.  
  
     [!code-vb[VbVbcnMyFileSystem#102](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnMyFileSystem/VB/class2.vb#102)]  
  
     Este código establece el directorio predeterminado del explorador de carpetas en el directorio actual.  
  
3. Ejecute la aplicación. Al hacer clic en **Examinar** la primera vez, se abre el cuadro de diálogo **Buscar carpeta** en el directorio actual.  
  
4. Deje de ejecutar la aplicación.  
  
### <a name="to-selectively-enable-controls"></a>Para habilitar los controles de forma selectiva  
  
1. Agregue el siguiente método `SetEnabled`.  
  
     [!code-vb[VbVbcnMyFileSystem#108](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnMyFileSystem/VB/class2.vb#108)]  
  
     El método `SetEnabled` habilita o deshabilita los controles dependiendo de si hay un elemento seleccionado en `ListBox`.  
  
2. Cree un controlador de eventos `SelectedIndexChanged` para `filesListBox` haciendo doble clic en el control `ListBox` del formulario.  
  
3. Agregue una llamada a `SetEnabled` en el nuevo controlador de eventos `filesListBox_SelectedIndexChanged`.  
  
4. Agregue una llamada a `SetEnabled` al final del controlador de eventos `browseButton_Click`.  
  
5. Agregue una llamada a `SetEnabled` al final del controlador de eventos `Form1_Load`.  
  
6. Ejecute la aplicación. La casilla **Guardar resultados** y el botón **Examine** (Examinar) se deshabilitan si no hay ningún elemento seleccionado en `ListBox`.  
  
## <a name="full-example-using-mycomputerfilesystem"></a>Ejemplo completo usando My.Computer.FileSystem  

 A continuación, se muestra el ejemplo completo.  
  
 [!code-vb[VbVbcnMyFileSystem#101](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnMyFileSystem/VB/class2.vb#101)]  
  
## <a name="full-example-using-systemio"></a>Ejemplo completo usando System.IO  

 En el siguiente ejemplo equivalente se usan clases del espacio de nombres <xref:System.IO> en lugar de usar objetos `My.Computer.FileSystem`.  
  
 [!code-vb[VbVbcnMyFileSystem#111](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnMyFileSystem/VB/class3.vb#111)]  
  
## <a name="see-also"></a>Vea también

- <xref:System.IO>
- <xref:Microsoft.VisualBasic.FileIO.FileSystem>
- <xref:Microsoft.VisualBasic.FileIO.FileSystem.CurrentDirectory%2A>
- [Tutorial: Manipulación de archivos utilizando métodos de .NET Framework](walkthrough-manipulating-files-by-using-net-framework-methods.md)
