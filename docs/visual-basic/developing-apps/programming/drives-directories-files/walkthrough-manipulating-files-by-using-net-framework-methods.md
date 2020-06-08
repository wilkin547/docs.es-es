---
title: Manipulación de archivos mediante métodos de .NET Framework
ms.date: 07/20/2015
helpviewer_keywords:
- I/O [Visual Basic], walkthroughs
- text files [Visual Basic], writing to
- reading text files [Visual Basic]
- text, writing to files
- files [Visual Basic], searching
- StreamReader class, walkthroughs
- files [Visual Basic], accessing
- I/O [Visual Basic], writing text to files
- writing to files [Visual Basic], walkthroughs
- StreamWriter class, walkthroughs
- text files [Visual Basic], reading
- I/O [Visual Basic], reading text from files
ms.assetid: 7d2109eb-f98a-4389-b43d-30f384aaa7d5
ms.openlocfilehash: 9abb87f3f6cdefefef29eb37c2c2d4d15155e93d
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/04/2020
ms.locfileid: "84406656"
---
# <a name="walkthrough-manipulating-files-by-using-net-framework-methods-visual-basic"></a>Tutorial: Manipular archivos utilizando métodos de .NET Framework (Visual Basic)

En este tutorial se muestra cómo abrir y leer un archivo mediante la clase <xref:System.IO.StreamReader>, comprobar si se ha tenido acceso a un archivo, buscar una cadena dentro de un archivo leído con una instancia de la clase <xref:System.IO.StreamReader> y escribir en un archivo mediante la clase <xref:System.IO.StreamWriter>.

[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]

## <a name="creating-the-application"></a>Crear la aplicación

Inicie Visual Studio y comience el proyecto mediante la creación de un formulario que el usuario pueda usar para escribir en el archivo designado.

### <a name="to-create-the-project"></a>Para crear el proyecto

1. En el menú **Archivo**, seleccione **Nuevo proyecto**.

2. En el panel **Nuevo proyecto**, haga clic en **Aplicación Windows**.

3. En el cuadro **Nombre**, escriba `MyDiary` y haga clic en **Aceptar**.

     Visual Studio agrega el proyecto al **Explorador de soluciones** y se abre el **Diseñador de Windows Forms**.

4. Agregue los controles de la siguiente tabla al formulario y establezca los valores correspondientes para sus propiedades.

|**Objeto**|**Propiedades**|**Valor**|
|---|---|---|
|<xref:System.Windows.Forms.Button>|**Name**<br /><br /> **Text**|`Submit`<br /><br /> **Enviar entrada**|
|<xref:System.Windows.Forms.Button>|**Name**<br /><br /> **Text**|`Clear`<br /><br /> **Borrar entrada**|
|<xref:System.Windows.Forms.TextBox>|**Name**<br /><br /> **Text**<br /><br /> **Multiline**|`Entry`<br /><br /> **Escriba algo.**<br /><br /> `False`|

## <a name="writing-to-the-file"></a>Escribir en el archivo

Para agregar la capacidad de escribir en un archivo a través de la aplicación, use la clase <xref:System.IO.StreamWriter>. La clase <xref:System.IO.StreamWriter> está diseñada para la salida de caracteres en una codificación determinada, mientras que la clase <xref:System.IO.Stream> está diseñada para la entrada y la salida de bytes. Use la clase <xref:System.IO.StreamWriter> para escribir líneas de información en un archivo de texto estándar. Para más información sobre la clase <xref:System.IO.StreamWriter>, vea <xref:System.IO.StreamWriter>.

### <a name="to-add-writing-functionality"></a>Para agregar funcionalidad de escritura

1. En el menú **Vista**, seleccione **Código** para abrir el Editor de código.

2. Dado que la aplicación hace referencia al espacio de nombres <xref:System.IO>, agregue las instrucciones siguientes al principio del código, antes de la declaración de clase del formulario, que empieza con `Public Class Form1`.

     [!code-vb[VbVbcnMyFileSystem#35](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnMyFileSystem/VB/Class1.vb#35)]

     Antes de escribir en el archivo, debe crear una instancia de una clase <xref:System.IO.StreamWriter>.

3. En el menú **Vista**, seleccione **Diseñador** para volver al **Diseñador de Windows Forms**. Haga doble clic en el botón `Submit` para crear un controlador de eventos <xref:System.Windows.Forms.Control.Click> para el botón y, después, agregue el código siguiente.

     [!code-vb[VbVbcnMyFileSystem#36](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnMyFileSystem/VB/Class1.vb#36)]

> [!NOTE]
> El entorno de desarrollo integrado (IDE) de Visual Studio volverá al Editor de código y colocará el punto de inserción en el controlador de eventos donde debe agregar el código.

1. Para escribir en el archivo, use el método <xref:System.IO.StreamWriter.Write%2A> de la clase <xref:System.IO.StreamWriter>. Agregue el código siguiente justo después de `Dim fw As StreamWriter`. No se preocupe si se produce una excepción porque no se encuentra el archivo, ya que se creará en caso de que todavía no exista.

     [!code-vb[VbVbcnMyFileSystem#37](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnMyFileSystem/VB/Class1.vb#37)]

2. Asegúrese de que el usuario no puede enviar una entrada en blanco mediante la adición del código siguiente justo después de `Dim ReadString As String`.

     [!code-vb[VbVbcnMyFileSystem#38](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnMyFileSystem/VB/Class1.vb#38)]

3. Como se trata de una agenda, el usuario querrá asignar una fecha a cada entrada. Inserte el siguiente código después de `fw = New StreamWriter("C:\MyDiary.txt", True)` para establecer la variable `Today` en la fecha actual.

     [!code-vb[VbVbcnMyFileSystem#39](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnMyFileSystem/VB/Class1.vb#39)]

4. Por último, adjunte el código para borrar <xref:System.Windows.Forms.TextBox>. Agregue el código siguiente al evento <xref:System.Windows.Forms.Control.Click> del botón `Clear`.

     [!code-vb[VbVbcnMyFileSystem#40](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnMyFileSystem/VB/Class1.vb#40)]

## <a name="adding-display-features-to-the-diary"></a>Agregar características de visualización a la agenda

En esta sección, agregará una característica que muestra la entrada más reciente de `DisplayEntry`<xref:System.Windows.Forms.TextBox>. También puede agregar una clase <xref:System.Windows.Forms.ComboBox> que muestra varias entradas, de entre las cuales un usuario puede seleccionar una entrada para mostrarla en `DisplayEntry`<xref:System.Windows.Forms.TextBox>. Una instancia de la clase <xref:System.IO.StreamReader> lee de `MyDiary.txt`. Como la clase <xref:System.IO.StreamWriter>, <xref:System.IO.StreamReader> está diseñado para usarlo con archivos de texto.

Para esta sección del tutorial, agregue los controles de la siguiente tabla al formulario y establezca los valores correspondientes para sus propiedades.

|Control|Propiedades|Valores|
|-------------|----------------|------------|
|<xref:System.Windows.Forms.TextBox>|**Name**<br /><br /> **Visible**<br /><br /> **Size**<br /><br /> **Multiline**|`DisplayEntry`<br /><br /> `False`<br /><br /> `120,60`<br /><br /> `True`|
|<xref:System.Windows.Forms.Button>|**Name**<br /><br /> **Text**|`Display`<br /><br /> **Pantalla**|
|<xref:System.Windows.Forms.Button>|**Name**<br /><br /> **Text**|`GetEntries`<br /><br /> **Obtener entradas**|
|<xref:System.Windows.Forms.ComboBox>|**Name**<br /><br /> **Text**<br /><br /> **Enabled**|`PickEntries`<br /><br /> **Seleccione una entrada**<br /><br /> `False`|

### <a name="to-populate-the-combo-box"></a>Para rellenar el cuadro combinado

1. El control `PickEntries`<xref:System.Windows.Forms.ComboBox> se usa para mostrar las fechas en las que el usuario envía cada entrada, de modo que el usuario pueda seleccionar una entrada de una fecha concreta. Cree un controlador de eventos <xref:System.Windows.Forms.Control.Click> para el botón `GetEntries` y agréguele el siguiente código.

     [!code-vb[VbVbcnMyFileSystem#41](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnMyFileSystem/VB/Class1.vb#41)]

2. Para probar el código, presione F5 para compilar la aplicación y, después, haga clic en **Obtener entradas**. Haga clic en la flecha desplegable en <xref:System.Windows.Forms.ComboBox> para mostrar las flechas de entrada.

### <a name="to-choose-and-display-individual-entries"></a>Para seleccionar y mostrar entradas individuales

1. Cree un controlador de eventos <xref:System.Windows.Forms.Control.Click> para el botón `Display` y agregue el código siguiente.

     [!code-vb[VbVbcnMyFileSystem#42](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnMyFileSystem/VB/Class1.vb#42)]

2. Para probar el código, pulse F5 para compilar la aplicación y, después, envíe una entrada. Haga clic en **Obtener entradas**, seleccione una entrada de <xref:System.Windows.Forms.ComboBox> y, después, haga clic en **Mostrar**. El contenido de la entrada seleccionada aparece en `DisplayEntry`<xref:System.Windows.Forms.TextBox>.

## <a name="enabling-users-to-delete-or-modify-entries"></a>Permitir que los usuarios eliminen o modifiquen entradas

Por último, puede incluir funcionalidad adicional para permitir que los usuarios eliminen o modifiquen una entrada mediante los botones `DeleteEntry` y `EditEntry`. Ambos botones permanecen deshabilitados a menos que se muestre una entrada.

Agregue los controles de la siguiente tabla al formulario y establezca los valores correspondientes para sus propiedades.

|Control|Propiedades|Valores|
|-------------|----------------|------------|
|<xref:System.Windows.Forms.Button>|**Name**<br /><br /> **Text**<br /><br /> **Enabled**|`DeleteEntry`<br /><br /> **Eliminar entrada**<br /><br /> `False`|
|<xref:System.Windows.Forms.Button>|**Name**<br /><br /> **Text**<br /><br /> **Enabled**|`EditEntry`<br /><br /> **Editar entrada**<br /><br /> `False`|
|<xref:System.Windows.Forms.Button>|**Name**<br /><br /> **Text**<br /><br /> **Enabled**|`SubmitEdit`<br /><br /> **Enviar edición**<br /><br /> `False`|

### <a name="to-enable-deletion-and-modification-of-entries"></a>Para habilitar la eliminación y la modificación de entradas

1. Agregue el código siguiente al evento <xref:System.Windows.Forms.Control.Click> del botón `Display`, después de `DisplayEntry.Text = ReadString`.

     [!code-vb[VbVbcnMyFileSystem#43](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnMyFileSystem/VB/Class1.vb#43)]

2. Cree un controlador de eventos <xref:System.Windows.Forms.Control.Click> para el botón `DeleteEntry` y agregue el código siguiente.

     [!code-vb[VbVbcnMyFileSystem#44](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnMyFileSystem/VB/Class1.vb#44)]

3. Cuando un usuario muestra una entrada, se habilita el botón `EditEntry`. Agregue el código siguiente al evento <xref:System.Windows.Forms.Control.Click> del botón `Display` después de `DisplayEntry.Text = ReadString`.

     [!code-vb[VbVbcnMyFileSystem#45](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnMyFileSystem/VB/Class1.vb#45)]

4. Cree un controlador de eventos <xref:System.Windows.Forms.Control.Click> para el botón `EditEntry` y agregue el código siguiente.

     [!code-vb[VbVbcnMyFileSystem#46](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnMyFileSystem/VB/Class1.vb#46)]

5. Cree un controlador de eventos <xref:System.Windows.Forms.Control.Click> para el botón `SubmitEdit` y agregue el código siguiente.

     [!code-vb[VbVbcnMyFileSystem#47](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnMyFileSystem/VB/Class1.vb#47)]

Para probar el código, pulse F5 para compilar la aplicación. Haga clic en **Obtener entradas**, seleccione una entrada y, después, haga clic en **Mostrar**. La entrada aparece en `DisplayEntry`<xref:System.Windows.Forms.TextBox>. Haga clic en **Editar entrada**. La entrada aparece en `Entry`<xref:System.Windows.Forms.TextBox>. Edite la entrada de `Entry`<xref:System.Windows.Forms.TextBox> y haga clic en **Submit Edit** (Enviar edición). Abra el archivo `MyDiary.txt` para confirmar la corrección. Seleccione una entrada y haga clic en **Eliminar entrada**. Cuando <xref:System.Windows.Forms.MessageBox> solicite confirmación, haga clic en **Aceptar**. Cierre la aplicación y abra `MyDiary.txt` para confirmar la eliminación.

## <a name="see-also"></a>Vea también

- <xref:System.IO.StreamReader>
- <xref:System.IO.StreamWriter>
- [Tutoriales](../../../walkthroughs.md)
