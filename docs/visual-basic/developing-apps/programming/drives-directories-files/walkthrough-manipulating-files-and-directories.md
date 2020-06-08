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
# <a name="walkthrough-manipulating-files-and-directories-in-visual-basic"></a><span data-ttu-id="3f2d9-102">Tutorial: Manipular archivos y directorios en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="3f2d9-102">Walkthrough: Manipulating Files and Directories in Visual Basic</span></span>

<span data-ttu-id="3f2d9-103">En este tutorial se ofrece una introducción a los conceptos básicos de E/S de archivos en Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="3f2d9-103">This walkthrough provides an introduction to the fundamentals of file I/O in Visual Basic.</span></span> <span data-ttu-id="3f2d9-104">En él se describe cómo crear una pequeña aplicación que enumera y examina archivos de texto en un directorio.</span><span class="sxs-lookup"><span data-stu-id="3f2d9-104">It describes how to create a small application that lists and examines text files in a directory.</span></span> <span data-ttu-id="3f2d9-105">Para cada archivo de texto seleccionado, la aplicación proporciona atributos de archivo y la primera línea de contenido.</span><span class="sxs-lookup"><span data-stu-id="3f2d9-105">For each selected text file, the application provides file attributes and the first line of content.</span></span> <span data-ttu-id="3f2d9-106">Existe una opción para escribir información en un archivo de registro.</span><span class="sxs-lookup"><span data-stu-id="3f2d9-106">There is an option to write information to a log file.</span></span>  
  
 <span data-ttu-id="3f2d9-107">En este tutorial se usan los miembros del elemento `My.Computer.FileSystem Object`, que están disponibles en Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="3f2d9-107">This walkthrough uses members of the `My.Computer.FileSystem Object`, which are available in Visual Basic.</span></span> <span data-ttu-id="3f2d9-108">Vea <xref:Microsoft.VisualBasic.FileIO.FileSystem> para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="3f2d9-108">See <xref:Microsoft.VisualBasic.FileIO.FileSystem> for more information.</span></span> <span data-ttu-id="3f2d9-109">Al final del tutorial, se incluye un ejemplo equivalente que usa clases del espacio de nombres <xref:System.IO>.</span><span class="sxs-lookup"><span data-stu-id="3f2d9-109">At the end of the walkthrough, an equivalent example is provided that uses classes from the <xref:System.IO> namespace.</span></span>  
  
[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]  
  
### <a name="to-create-the-project"></a><span data-ttu-id="3f2d9-110">Para crear el proyecto</span><span class="sxs-lookup"><span data-stu-id="3f2d9-110">To create the project</span></span>  
  
1. <span data-ttu-id="3f2d9-111">En el menú **Archivo**, haga clic en **Nuevo proyecto**.</span><span class="sxs-lookup"><span data-stu-id="3f2d9-111">On the **File** menu, click **New Project**.</span></span>  
  
     <span data-ttu-id="3f2d9-112">Aparecerá el cuadro de diálogo **Nuevo proyecto** .</span><span class="sxs-lookup"><span data-stu-id="3f2d9-112">The **New Project** dialog box appears.</span></span>  
  
2. <span data-ttu-id="3f2d9-113">En el panel **Plantillas instaladas**, expanda **Visual Basic** y haga clic en **Windows**.</span><span class="sxs-lookup"><span data-stu-id="3f2d9-113">In the **Installed Templates** pane, expand **Visual Basic**, and then click **Windows**.</span></span> <span data-ttu-id="3f2d9-114">En el panel **Plantillas** situado en el medio, haga clic en **Aplicación de Windows Forms**.</span><span class="sxs-lookup"><span data-stu-id="3f2d9-114">In the **Templates** pane in the middle, click **Windows Forms Application**.</span></span>  
  
3. <span data-ttu-id="3f2d9-115">En la casilla **Nombre**, escriba `FileExplorer` para establecer el nombre del proyecto y, luego, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="3f2d9-115">In the **Name** box, type `FileExplorer` to set the project name, and then click **OK**.</span></span>  
  
     <span data-ttu-id="3f2d9-116">Visual Studio agrega el proyecto al **Explorador de soluciones** y se abre el Diseñador de Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="3f2d9-116">Visual Studio adds the project to **Solution Explorer**, and the Windows Forms Designer opens.</span></span>  
  
4. <span data-ttu-id="3f2d9-117">Agregue los controles de la siguiente tabla al formulario y establezca los valores correspondientes para sus propiedades.</span><span class="sxs-lookup"><span data-stu-id="3f2d9-117">Add the controls in the following table to the form, and set the corresponding values for their properties.</span></span>  
  
    |<span data-ttu-id="3f2d9-118">Control</span><span class="sxs-lookup"><span data-stu-id="3f2d9-118">Control</span></span>|<span data-ttu-id="3f2d9-119">Property</span><span class="sxs-lookup"><span data-stu-id="3f2d9-119">Property</span></span>|<span data-ttu-id="3f2d9-120">Valor</span><span class="sxs-lookup"><span data-stu-id="3f2d9-120">Value</span></span>|  
    |-------------|--------------|-----------|  
    |<span data-ttu-id="3f2d9-121">**ListBox**</span><span class="sxs-lookup"><span data-stu-id="3f2d9-121">**ListBox**</span></span>|<span data-ttu-id="3f2d9-122">**Name**</span><span class="sxs-lookup"><span data-stu-id="3f2d9-122">**Name**</span></span>|`filesListBox`|  
    |<span data-ttu-id="3f2d9-123">**Button**</span><span class="sxs-lookup"><span data-stu-id="3f2d9-123">**Button**</span></span>|<span data-ttu-id="3f2d9-124">**Name**</span><span class="sxs-lookup"><span data-stu-id="3f2d9-124">**Name**</span></span><br /><br /> <span data-ttu-id="3f2d9-125">**Text**</span><span class="sxs-lookup"><span data-stu-id="3f2d9-125">**Text**</span></span>|`browseButton`<br /><br /> <span data-ttu-id="3f2d9-126">**Examinar**</span><span class="sxs-lookup"><span data-stu-id="3f2d9-126">**Browse**</span></span>|  
    |<span data-ttu-id="3f2d9-127">**Button**</span><span class="sxs-lookup"><span data-stu-id="3f2d9-127">**Button**</span></span>|<span data-ttu-id="3f2d9-128">**Name**</span><span class="sxs-lookup"><span data-stu-id="3f2d9-128">**Name**</span></span><br /><br /> <span data-ttu-id="3f2d9-129">**Text**</span><span class="sxs-lookup"><span data-stu-id="3f2d9-129">**Text**</span></span>|`examineButton`<br /><br /> <span data-ttu-id="3f2d9-130">**Examine** (Examinar)</span><span class="sxs-lookup"><span data-stu-id="3f2d9-130">**Examine**</span></span>|  
    |<span data-ttu-id="3f2d9-131">**CheckBox**</span><span class="sxs-lookup"><span data-stu-id="3f2d9-131">**CheckBox**</span></span>|<span data-ttu-id="3f2d9-132">**Name**</span><span class="sxs-lookup"><span data-stu-id="3f2d9-132">**Name**</span></span><br /><br /> <span data-ttu-id="3f2d9-133">**Text**</span><span class="sxs-lookup"><span data-stu-id="3f2d9-133">**Text**</span></span>|`saveCheckBox`<br /><br /> <span data-ttu-id="3f2d9-134">**Guardar resultados**</span><span class="sxs-lookup"><span data-stu-id="3f2d9-134">**Save Results**</span></span>|  
    |<span data-ttu-id="3f2d9-135">**FolderBrowserDialog**</span><span class="sxs-lookup"><span data-stu-id="3f2d9-135">**FolderBrowserDialog**</span></span>|<span data-ttu-id="3f2d9-136">**Name**</span><span class="sxs-lookup"><span data-stu-id="3f2d9-136">**Name**</span></span>|`FolderBrowserDialog1`|  
  
### <a name="to-select-a-folder-and-list-files-in-a-folder"></a><span data-ttu-id="3f2d9-137">Para seleccionar una carpeta y enumerar archivos en una carpeta</span><span class="sxs-lookup"><span data-stu-id="3f2d9-137">To select a folder, and list files in a folder</span></span>  
  
1. <span data-ttu-id="3f2d9-138">Cree un controlador de eventos `Click` para `browseButton` haciendo doble clic en el control del formulario.</span><span class="sxs-lookup"><span data-stu-id="3f2d9-138">Create a `Click` event handler for `browseButton` by double-clicking the control on the form.</span></span> <span data-ttu-id="3f2d9-139">Se abrirá el Editor de código.</span><span class="sxs-lookup"><span data-stu-id="3f2d9-139">The Code Editor opens.</span></span>  
  
2. <span data-ttu-id="3f2d9-140">Agregue el código siguiente al controlador de eventos `Click`.</span><span class="sxs-lookup"><span data-stu-id="3f2d9-140">Add the following code to the `Click` event handler.</span></span>  
  
     [!code-vb[VbVbcnMyFileSystem#103](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnMyFileSystem/VB/class2.vb#103)]  
  
     <span data-ttu-id="3f2d9-141">La llamada `FolderBrowserDialog1.ShowDialog` abre el cuadro de diálogo **Buscar carpeta**.</span><span class="sxs-lookup"><span data-stu-id="3f2d9-141">The `FolderBrowserDialog1.ShowDialog` call opens the **Browse For Folder** dialog box.</span></span> <span data-ttu-id="3f2d9-142">Después de que el usuario hace clic en **Aceptar**, la propiedad <xref:System.Windows.Forms.FolderBrowserDialog.SelectedPath%2A> se envía como un argumento al método `ListFiles`, que se agrega en el paso siguiente.</span><span class="sxs-lookup"><span data-stu-id="3f2d9-142">After the user clicks **OK**, the <xref:System.Windows.Forms.FolderBrowserDialog.SelectedPath%2A> property is sent as an argument to the `ListFiles` method, which is added in the next step.</span></span>  
  
3. <span data-ttu-id="3f2d9-143">Agregue el siguiente método `ListFiles`.</span><span class="sxs-lookup"><span data-stu-id="3f2d9-143">Add the following `ListFiles` method.</span></span>  
  
     [!code-vb[VbVbcnMyFileSystem#104](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnMyFileSystem/VB/class2.vb#104)]  
  
     <span data-ttu-id="3f2d9-144">Este código primero elimina el elemento **ListBox**.</span><span class="sxs-lookup"><span data-stu-id="3f2d9-144">This code first clears the **ListBox**.</span></span>  
  
     <span data-ttu-id="3f2d9-145">El método <xref:Microsoft.VisualBasic.FileIO.FileSystem.GetFiles%2A> recupera entonces una colección de cadenas, una para cada archivo del directorio.</span><span class="sxs-lookup"><span data-stu-id="3f2d9-145">The <xref:Microsoft.VisualBasic.FileIO.FileSystem.GetFiles%2A> method then retrieves a collection of strings, one for each file in the directory.</span></span> <span data-ttu-id="3f2d9-146">El método `GetFiles` acepta un argumento de patrón de búsqueda para recuperar los archivos que coinciden con un patrón determinado.</span><span class="sxs-lookup"><span data-stu-id="3f2d9-146">The `GetFiles` method accepts a search pattern argument to retrieve files that match a particular pattern.</span></span> <span data-ttu-id="3f2d9-147">En este ejemplo, se devuelven solo los archivos que tengan la extensión .txt.</span><span class="sxs-lookup"><span data-stu-id="3f2d9-147">In this example, only files that have the extension .txt are returned.</span></span>  
  
     <span data-ttu-id="3f2d9-148">Las cadenas devueltas por el método `GetFiles` se agregan luego al elemento **ListBox**.</span><span class="sxs-lookup"><span data-stu-id="3f2d9-148">The strings that are returned by the `GetFiles` method are then added to the **ListBox**.</span></span>  
  
4. <span data-ttu-id="3f2d9-149">Ejecute la aplicación.</span><span class="sxs-lookup"><span data-stu-id="3f2d9-149">Run the application.</span></span> <span data-ttu-id="3f2d9-150">Haga clic en el botón **Examinar**.</span><span class="sxs-lookup"><span data-stu-id="3f2d9-150">Click the **Browse** button.</span></span> <span data-ttu-id="3f2d9-151">En el cuadro de diálogo **Buscar carpeta**, busque una carpeta que contenga archivos .txt y, luego, selecciónela y haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="3f2d9-151">In the **Browse For Folder** dialog box, browse to a folder that contains .txt files, and then select the folder and click **OK**.</span></span>  
  
     <span data-ttu-id="3f2d9-152">El elemento `ListBox` contiene una lista de archivos .txt de la carpeta seleccionada.</span><span class="sxs-lookup"><span data-stu-id="3f2d9-152">The `ListBox` contains a list of .txt files in the selected folder.</span></span>  
  
5. <span data-ttu-id="3f2d9-153">Deje de ejecutar la aplicación.</span><span class="sxs-lookup"><span data-stu-id="3f2d9-153">Stop running the application.</span></span>  
  
### <a name="to-obtain-attributes-of-a-file-and-content-from-a-text-file"></a><span data-ttu-id="3f2d9-154">Para obtener los atributos de un archivo y contenido de un archivo de texto</span><span class="sxs-lookup"><span data-stu-id="3f2d9-154">To obtain attributes of a file, and content from a text file</span></span>  
  
1. <span data-ttu-id="3f2d9-155">Cree un controlador de eventos `Click` para `examineButton` haciendo doble clic en el control del formulario.</span><span class="sxs-lookup"><span data-stu-id="3f2d9-155">Create a `Click` event handler for `examineButton` by double-clicking the control on the form.</span></span>  
  
2. <span data-ttu-id="3f2d9-156">Agregue el código siguiente al controlador de eventos `Click`.</span><span class="sxs-lookup"><span data-stu-id="3f2d9-156">Add the following code to the `Click` event handler.</span></span>  
  
     [!code-vb[VbVbcnMyFileSystem#105](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnMyFileSystem/VB/class2.vb#105)]  
  
     <span data-ttu-id="3f2d9-157">El código comprueba que hay un elemento seleccionado en `ListBox`.</span><span class="sxs-lookup"><span data-stu-id="3f2d9-157">The code verifies that an item is selected in the `ListBox`.</span></span> <span data-ttu-id="3f2d9-158">Después, obtiene la entrada de ruta de archivo de `ListBox`.</span><span class="sxs-lookup"><span data-stu-id="3f2d9-158">It then obtains the file path entry from the `ListBox`.</span></span> <span data-ttu-id="3f2d9-159">El método <xref:Microsoft.VisualBasic.FileIO.FileSystem.FileExists%2A> se usa para comprobar si el archivo todavía existe.</span><span class="sxs-lookup"><span data-stu-id="3f2d9-159">The <xref:Microsoft.VisualBasic.FileIO.FileSystem.FileExists%2A> method is used to check whether the file still exists.</span></span>  
  
     <span data-ttu-id="3f2d9-160">La ruta del archivo se envía como argumento al método `GetTextForOutput`, que se agrega en el paso siguiente.</span><span class="sxs-lookup"><span data-stu-id="3f2d9-160">The file path is sent as an argument to the `GetTextForOutput` method, which is added in the next step.</span></span> <span data-ttu-id="3f2d9-161">Este método devuelve una cadena que contiene información del archivo.</span><span class="sxs-lookup"><span data-stu-id="3f2d9-161">This method returns a string that contains file information.</span></span> <span data-ttu-id="3f2d9-162">La información del archivo aparece en un elemento **MessageBox**.</span><span class="sxs-lookup"><span data-stu-id="3f2d9-162">The file information appears in a **MessageBox**.</span></span>  
  
3. <span data-ttu-id="3f2d9-163">Agregue el siguiente método `GetTextForOutput`.</span><span class="sxs-lookup"><span data-stu-id="3f2d9-163">Add the following `GetTextForOutput` method.</span></span>  
  
     [!code-vb[VbVbcnMyFileSystem#107](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnMyFileSystem/VB/class2.vb#107)]  
  
     <span data-ttu-id="3f2d9-164">El código usa el método <xref:Microsoft.VisualBasic.FileIO.FileSystem.GetFileInfo%2A> para obtener los parámetros del archivo.</span><span class="sxs-lookup"><span data-stu-id="3f2d9-164">The code uses the <xref:Microsoft.VisualBasic.FileIO.FileSystem.GetFileInfo%2A> method to obtain file parameters.</span></span> <span data-ttu-id="3f2d9-165">Los parámetros del archivo se agregan a <xref:System.Text.StringBuilder>.</span><span class="sxs-lookup"><span data-stu-id="3f2d9-165">The file parameters are added to a <xref:System.Text.StringBuilder>.</span></span>  
  
     <span data-ttu-id="3f2d9-166">El método <xref:Microsoft.VisualBasic.FileIO.FileSystem.OpenTextFileReader%2A> lee el contenido del archivo en <xref:System.IO.StreamReader>.</span><span class="sxs-lookup"><span data-stu-id="3f2d9-166">The <xref:Microsoft.VisualBasic.FileIO.FileSystem.OpenTextFileReader%2A> method reads the file contents into a <xref:System.IO.StreamReader>.</span></span> <span data-ttu-id="3f2d9-167">La primera línea del contenido se obtiene de `StreamReader` y se agrega a `StringBuilder`.</span><span class="sxs-lookup"><span data-stu-id="3f2d9-167">The first line of the contents is obtained from the `StreamReader` and is added to the `StringBuilder`.</span></span>  
  
4. <span data-ttu-id="3f2d9-168">Ejecute la aplicación.</span><span class="sxs-lookup"><span data-stu-id="3f2d9-168">Run the application.</span></span> <span data-ttu-id="3f2d9-169">Haga clic en **Examinar** y busque una carpeta que contenga archivos .txt.</span><span class="sxs-lookup"><span data-stu-id="3f2d9-169">Click **Browse**, and browse to a folder that contains .txt files.</span></span> <span data-ttu-id="3f2d9-170">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="3f2d9-170">Click **OK**.</span></span>  
  
     <span data-ttu-id="3f2d9-171">Seleccione un archivo en `ListBox` y, luego, haga clic en **Examine** (Examinar).</span><span class="sxs-lookup"><span data-stu-id="3f2d9-171">Select a file in the `ListBox`, and then click **Examine**.</span></span> <span data-ttu-id="3f2d9-172">La información del archivo se muestra en un `MessageBox`.</span><span class="sxs-lookup"><span data-stu-id="3f2d9-172">A `MessageBox` shows the file information.</span></span>  
  
5. <span data-ttu-id="3f2d9-173">Deje de ejecutar la aplicación.</span><span class="sxs-lookup"><span data-stu-id="3f2d9-173">Stop running the application.</span></span>  
  
### <a name="to-add-a-log-entry"></a><span data-ttu-id="3f2d9-174">Para agregar una entrada de registro</span><span class="sxs-lookup"><span data-stu-id="3f2d9-174">To add a log entry</span></span>  
  
1. <span data-ttu-id="3f2d9-175">Agregue el siguiente código al final del controlador de eventos `examineButton_Click`.</span><span class="sxs-lookup"><span data-stu-id="3f2d9-175">Add the following code to the end of the `examineButton_Click` event handler.</span></span>  
  
     [!code-vb[VbVbcnMyFileSystem#106](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnMyFileSystem/VB/class2.vb#106)]  
  
     <span data-ttu-id="3f2d9-176">El código establece la ruta del archivo de registro para colocarlo en el mismo directorio que el archivo seleccionado.</span><span class="sxs-lookup"><span data-stu-id="3f2d9-176">The code sets the log file path to put the log file in the same directory as that of the selected file.</span></span> <span data-ttu-id="3f2d9-177">El texto de la entrada de registro se establece en la fecha y hora actuales, seguido de la información del archivo.</span><span class="sxs-lookup"><span data-stu-id="3f2d9-177">The text of the log entry is set to the current date and time followed by the file information.</span></span>  
  
     <span data-ttu-id="3f2d9-178">El método <xref:Microsoft.VisualBasic.FileIO.FileSystem.WriteAllText%2A>, con el argumento `append` establecido en `True`, se usa para crear la entrada de registro.</span><span class="sxs-lookup"><span data-stu-id="3f2d9-178">The <xref:Microsoft.VisualBasic.FileIO.FileSystem.WriteAllText%2A> method, with the `append` argument set to `True`, is used to create the log entry.</span></span>  
  
2. <span data-ttu-id="3f2d9-179">Ejecute la aplicación.</span><span class="sxs-lookup"><span data-stu-id="3f2d9-179">Run the application.</span></span> <span data-ttu-id="3f2d9-180">Busque un archivo de texto, selecciónelo en `ListBox`, seleccione la casilla **Guardar resultados** y, luego, haga clic en **Examine** (Examinar).</span><span class="sxs-lookup"><span data-stu-id="3f2d9-180">Browse to a text file, select it in the `ListBox`, select the **Save Results** check box, and then click **Examine**.</span></span> <span data-ttu-id="3f2d9-181">Compruebe que la entrada de registro se ha escrito en el archivo `log.txt`.</span><span class="sxs-lookup"><span data-stu-id="3f2d9-181">Verify that the log entry is written to the `log.txt` file.</span></span>  
  
3. <span data-ttu-id="3f2d9-182">Deje de ejecutar la aplicación.</span><span class="sxs-lookup"><span data-stu-id="3f2d9-182">Stop running the application.</span></span>  
  
### <a name="to-use-the-current-directory"></a><span data-ttu-id="3f2d9-183">Para usar el directorio actual</span><span class="sxs-lookup"><span data-stu-id="3f2d9-183">To use the current directory</span></span>  
  
1. <span data-ttu-id="3f2d9-184">Cree un controlador de eventos para `Form1_Load` haciendo doble clic en el formulario.</span><span class="sxs-lookup"><span data-stu-id="3f2d9-184">Create an event handler for `Form1_Load` by double-clicking the form.</span></span>  
  
2. <span data-ttu-id="3f2d9-185">Agregue el siguiente código al controlador de eventos.</span><span class="sxs-lookup"><span data-stu-id="3f2d9-185">Add the following code to the event handler.</span></span>  
  
     [!code-vb[VbVbcnMyFileSystem#102](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnMyFileSystem/VB/class2.vb#102)]  
  
     <span data-ttu-id="3f2d9-186">Este código establece el directorio predeterminado del explorador de carpetas en el directorio actual.</span><span class="sxs-lookup"><span data-stu-id="3f2d9-186">This code sets the default directory of the folder browser to the current directory.</span></span>  
  
3. <span data-ttu-id="3f2d9-187">Ejecute la aplicación.</span><span class="sxs-lookup"><span data-stu-id="3f2d9-187">Run the application.</span></span> <span data-ttu-id="3f2d9-188">Al hacer clic en **Examinar** la primera vez, se abre el cuadro de diálogo **Buscar carpeta** en el directorio actual.</span><span class="sxs-lookup"><span data-stu-id="3f2d9-188">When you click **Browse** the first time, the **Browse For Folder** dialog box opens to the current directory.</span></span>  
  
4. <span data-ttu-id="3f2d9-189">Deje de ejecutar la aplicación.</span><span class="sxs-lookup"><span data-stu-id="3f2d9-189">Stop running the application.</span></span>  
  
### <a name="to-selectively-enable-controls"></a><span data-ttu-id="3f2d9-190">Para habilitar los controles de forma selectiva</span><span class="sxs-lookup"><span data-stu-id="3f2d9-190">To selectively enable controls</span></span>  
  
1. <span data-ttu-id="3f2d9-191">Agregue el siguiente método `SetEnabled`.</span><span class="sxs-lookup"><span data-stu-id="3f2d9-191">Add the following `SetEnabled` method.</span></span>  
  
     [!code-vb[VbVbcnMyFileSystem#108](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnMyFileSystem/VB/class2.vb#108)]  
  
     <span data-ttu-id="3f2d9-192">El método `SetEnabled` habilita o deshabilita los controles dependiendo de si hay un elemento seleccionado en `ListBox`.</span><span class="sxs-lookup"><span data-stu-id="3f2d9-192">The `SetEnabled` method enables or disables controls depending on whether an item is selected in the `ListBox`.</span></span>  
  
2. <span data-ttu-id="3f2d9-193">Cree un controlador de eventos `SelectedIndexChanged` para `filesListBox` haciendo doble clic en el control `ListBox` del formulario.</span><span class="sxs-lookup"><span data-stu-id="3f2d9-193">Create a `SelectedIndexChanged` event handler for `filesListBox` by double-clicking the `ListBox` control on the form.</span></span>  
  
3. <span data-ttu-id="3f2d9-194">Agregue una llamada a `SetEnabled` en el nuevo controlador de eventos `filesListBox_SelectedIndexChanged`.</span><span class="sxs-lookup"><span data-stu-id="3f2d9-194">Add a call to `SetEnabled` in the new `filesListBox_SelectedIndexChanged` event handler.</span></span>  
  
4. <span data-ttu-id="3f2d9-195">Agregue una llamada a `SetEnabled` al final del controlador de eventos `browseButton_Click`.</span><span class="sxs-lookup"><span data-stu-id="3f2d9-195">Add a call to `SetEnabled` at the end of the `browseButton_Click` event handler.</span></span>  
  
5. <span data-ttu-id="3f2d9-196">Agregue una llamada a `SetEnabled` al final del controlador de eventos `Form1_Load`.</span><span class="sxs-lookup"><span data-stu-id="3f2d9-196">Add a call to `SetEnabled` at the end of the `Form1_Load` event handler.</span></span>  
  
6. <span data-ttu-id="3f2d9-197">Ejecute la aplicación.</span><span class="sxs-lookup"><span data-stu-id="3f2d9-197">Run the application.</span></span> <span data-ttu-id="3f2d9-198">La casilla **Guardar resultados** y el botón **Examine** (Examinar) se deshabilitan si no hay ningún elemento seleccionado en `ListBox`.</span><span class="sxs-lookup"><span data-stu-id="3f2d9-198">The **Save Results** check box and the **Examine** button are disabled if an item is not selected in the `ListBox`.</span></span>  
  
## <a name="full-example-using-mycomputerfilesystem"></a><span data-ttu-id="3f2d9-199">Ejemplo completo usando My.Computer.FileSystem</span><span class="sxs-lookup"><span data-stu-id="3f2d9-199">Full example using My.Computer.FileSystem</span></span>  

 <span data-ttu-id="3f2d9-200">A continuación, se muestra el ejemplo completo.</span><span class="sxs-lookup"><span data-stu-id="3f2d9-200">Following is the complete example.</span></span>  
  
 [!code-vb[VbVbcnMyFileSystem#101](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnMyFileSystem/VB/class2.vb#101)]  
  
## <a name="full-example-using-systemio"></a><span data-ttu-id="3f2d9-201">Ejemplo completo usando System.IO</span><span class="sxs-lookup"><span data-stu-id="3f2d9-201">Full example using System.IO</span></span>  

 <span data-ttu-id="3f2d9-202">En el siguiente ejemplo equivalente se usan clases del espacio de nombres <xref:System.IO> en lugar de usar objetos `My.Computer.FileSystem`.</span><span class="sxs-lookup"><span data-stu-id="3f2d9-202">The following equivalent example uses classes from the <xref:System.IO> namespace instead of using `My.Computer.FileSystem` objects.</span></span>  
  
 [!code-vb[VbVbcnMyFileSystem#111](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnMyFileSystem/VB/class3.vb#111)]  
  
## <a name="see-also"></a><span data-ttu-id="3f2d9-203">Vea también</span><span class="sxs-lookup"><span data-stu-id="3f2d9-203">See also</span></span>

- <xref:System.IO>
- <xref:Microsoft.VisualBasic.FileIO.FileSystem>
- <xref:Microsoft.VisualBasic.FileIO.FileSystem.CurrentDirectory%2A>
- [<span data-ttu-id="3f2d9-204">Tutorial: Manipulación de archivos utilizando métodos de .NET Framework</span><span class="sxs-lookup"><span data-stu-id="3f2d9-204">Walkthrough: Manipulating Files by Using .NET Framework Methods</span></span>](walkthrough-manipulating-files-by-using-net-framework-methods.md)
