---
description: 'Más información acerca de: Tutorial: Manipular archivos utilizando métodos de .NET Framework (Visual Basic)'
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
ms.openlocfilehash: e59dca15660a981c487688234c864a818398af65
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99775375"
---
# <a name="walkthrough-manipulating-files-by-using-net-framework-methods-visual-basic"></a><span data-ttu-id="edd2c-103">Tutorial: Manipular archivos utilizando métodos de .NET Framework (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="edd2c-103">Walkthrough: Manipulating Files by Using .NET Framework Methods (Visual Basic)</span></span>

<span data-ttu-id="edd2c-104">En este tutorial se muestra cómo abrir y leer un archivo mediante la clase <xref:System.IO.StreamReader>, comprobar si se ha tenido acceso a un archivo, buscar una cadena dentro de un archivo leído con una instancia de la clase <xref:System.IO.StreamReader> y escribir en un archivo mediante la clase <xref:System.IO.StreamWriter>.</span><span class="sxs-lookup"><span data-stu-id="edd2c-104">This walkthrough demonstrates how to open and read a file using the <xref:System.IO.StreamReader> class, check to see if a file is being accessed, search for a string within a file read with an instance of the <xref:System.IO.StreamReader> class, and write to a file using the <xref:System.IO.StreamWriter> class.</span></span>

[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]

## <a name="creating-the-application"></a><span data-ttu-id="edd2c-105">Crear la aplicación</span><span class="sxs-lookup"><span data-stu-id="edd2c-105">Creating the Application</span></span>

<span data-ttu-id="edd2c-106">Inicie Visual Studio y comience el proyecto mediante la creación de un formulario que el usuario pueda usar para escribir en el archivo designado.</span><span class="sxs-lookup"><span data-stu-id="edd2c-106">Start Visual Studio and begin the project by creating a form that the user can use to write to the designated file.</span></span>

### <a name="to-create-the-project"></a><span data-ttu-id="edd2c-107">Para crear el proyecto</span><span class="sxs-lookup"><span data-stu-id="edd2c-107">To create the project</span></span>

1. <span data-ttu-id="edd2c-108">En el menú **Archivo**, seleccione **Nuevo proyecto**.</span><span class="sxs-lookup"><span data-stu-id="edd2c-108">On the **File** menu, select **New Project**.</span></span>

2. <span data-ttu-id="edd2c-109">En el panel **Nuevo proyecto**, haga clic en **Aplicación Windows**.</span><span class="sxs-lookup"><span data-stu-id="edd2c-109">In the **New Project** pane, click **Windows Application**.</span></span>

3. <span data-ttu-id="edd2c-110">En el cuadro **Nombre**, escriba `MyDiary` y haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="edd2c-110">In the **Name** box type `MyDiary` and click **OK**.</span></span>

     <span data-ttu-id="edd2c-111">Visual Studio agrega el proyecto al **Explorador de soluciones** y se abre el **Diseñador de Windows Forms**.</span><span class="sxs-lookup"><span data-stu-id="edd2c-111">Visual Studio adds the project to **Solution Explorer**, and the **Windows Forms Designer** opens.</span></span>

4. <span data-ttu-id="edd2c-112">Agregue los controles de la siguiente tabla al formulario y establezca los valores correspondientes para sus propiedades.</span><span class="sxs-lookup"><span data-stu-id="edd2c-112">Add the controls in the following table to the form and set the corresponding values for their properties.</span></span>

|<span data-ttu-id="edd2c-113">**Object**</span><span class="sxs-lookup"><span data-stu-id="edd2c-113">**Object**</span></span>|<span data-ttu-id="edd2c-114">**Propiedades**</span><span class="sxs-lookup"><span data-stu-id="edd2c-114">**Properties**</span></span>|<span data-ttu-id="edd2c-115">**Valor**</span><span class="sxs-lookup"><span data-stu-id="edd2c-115">**Value**</span></span>|
|---|---|---|
|<xref:System.Windows.Forms.Button>|<span data-ttu-id="edd2c-116">**Nombre**</span><span class="sxs-lookup"><span data-stu-id="edd2c-116">**Name**</span></span><br /><br /> <span data-ttu-id="edd2c-117">**Texto**</span><span class="sxs-lookup"><span data-stu-id="edd2c-117">**Text**</span></span>|`Submit`<br /><br /> <span data-ttu-id="edd2c-118">**Enviar entrada**</span><span class="sxs-lookup"><span data-stu-id="edd2c-118">**Submit Entry**</span></span>|
|<xref:System.Windows.Forms.Button>|<span data-ttu-id="edd2c-119">**Nombre**</span><span class="sxs-lookup"><span data-stu-id="edd2c-119">**Name**</span></span><br /><br /> <span data-ttu-id="edd2c-120">**Texto**</span><span class="sxs-lookup"><span data-stu-id="edd2c-120">**Text**</span></span>|`Clear`<br /><br /> <span data-ttu-id="edd2c-121">**Borrar entrada**</span><span class="sxs-lookup"><span data-stu-id="edd2c-121">**Clear Entry**</span></span>|
|<xref:System.Windows.Forms.TextBox>|<span data-ttu-id="edd2c-122">**Nombre**</span><span class="sxs-lookup"><span data-stu-id="edd2c-122">**Name**</span></span><br /><br /> <span data-ttu-id="edd2c-123">**Texto**</span><span class="sxs-lookup"><span data-stu-id="edd2c-123">**Text**</span></span><br /><br /> <span data-ttu-id="edd2c-124">**Multiline**</span><span class="sxs-lookup"><span data-stu-id="edd2c-124">**Multiline**</span></span>|`Entry`<br /><br /> <span data-ttu-id="edd2c-125">**Escriba algo.**</span><span class="sxs-lookup"><span data-stu-id="edd2c-125">**Please enter something.**</span></span><br /><br /> `False`|

## <a name="writing-to-the-file"></a><span data-ttu-id="edd2c-126">Escribir en el archivo</span><span class="sxs-lookup"><span data-stu-id="edd2c-126">Writing to the File</span></span>

<span data-ttu-id="edd2c-127">Para agregar la capacidad de escribir en un archivo a través de la aplicación, use la clase <xref:System.IO.StreamWriter>.</span><span class="sxs-lookup"><span data-stu-id="edd2c-127">To add the ability to write to a file via the application, use the <xref:System.IO.StreamWriter> class.</span></span> <span data-ttu-id="edd2c-128">La clase <xref:System.IO.StreamWriter> está diseñada para la salida de caracteres en una codificación determinada, mientras que la clase <xref:System.IO.Stream> está diseñada para la entrada y la salida de bytes.</span><span class="sxs-lookup"><span data-stu-id="edd2c-128"><xref:System.IO.StreamWriter> is designed for character output in a particular encoding, whereas the <xref:System.IO.Stream> class is designed for byte input and output.</span></span> <span data-ttu-id="edd2c-129">Use la clase <xref:System.IO.StreamWriter> para escribir líneas de información en un archivo de texto estándar.</span><span class="sxs-lookup"><span data-stu-id="edd2c-129">Use <xref:System.IO.StreamWriter> for writing lines of information to a standard text file.</span></span> <span data-ttu-id="edd2c-130">Para más información sobre la clase <xref:System.IO.StreamWriter>, vea <xref:System.IO.StreamWriter>.</span><span class="sxs-lookup"><span data-stu-id="edd2c-130">For more information on the <xref:System.IO.StreamWriter> class, see <xref:System.IO.StreamWriter>.</span></span>

### <a name="to-add-writing-functionality"></a><span data-ttu-id="edd2c-131">Para agregar funcionalidad de escritura</span><span class="sxs-lookup"><span data-stu-id="edd2c-131">To add writing functionality</span></span>

1. <span data-ttu-id="edd2c-132">En el menú **Vista**, seleccione **Código** para abrir el Editor de código.</span><span class="sxs-lookup"><span data-stu-id="edd2c-132">From the **View** menu, choose **Code** to open the Code Editor.</span></span>

2. <span data-ttu-id="edd2c-133">Dado que la aplicación hace referencia al espacio de nombres <xref:System.IO>, agregue las instrucciones siguientes al principio del código, antes de la declaración de clase del formulario, que empieza con `Public Class Form1`.</span><span class="sxs-lookup"><span data-stu-id="edd2c-133">Because the application references the <xref:System.IO> namespace, add the following statements at the very beginning of your code, before the class declaration for the form, which begins `Public Class Form1`.</span></span>

     [!code-vb[VbVbcnMyFileSystem#35](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnMyFileSystem/VB/Class1.vb#35)]

     <span data-ttu-id="edd2c-134">Antes de escribir en el archivo, debe crear una instancia de una clase <xref:System.IO.StreamWriter>.</span><span class="sxs-lookup"><span data-stu-id="edd2c-134">Before writing to the file, you must create an instance of a <xref:System.IO.StreamWriter> class.</span></span>

3. <span data-ttu-id="edd2c-135">En el menú **Vista**, seleccione **Diseñador** para volver al **Diseñador de Windows Forms**.</span><span class="sxs-lookup"><span data-stu-id="edd2c-135">From the **View** menu, choose **Designer** to return to the **Windows Forms Designer**.</span></span> <span data-ttu-id="edd2c-136">Haga doble clic en el botón `Submit` para crear un controlador de eventos <xref:System.Windows.Forms.Control.Click> para el botón y, después, agregue el código siguiente.</span><span class="sxs-lookup"><span data-stu-id="edd2c-136">Double-click the `Submit` button to create a <xref:System.Windows.Forms.Control.Click> event handler for the button, and then add the following code.</span></span>

     [!code-vb[VbVbcnMyFileSystem#36](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnMyFileSystem/VB/Class1.vb#36)]

> [!NOTE]
> <span data-ttu-id="edd2c-137">El entorno de desarrollo integrado (IDE) de Visual Studio volverá al Editor de código y colocará el punto de inserción en el controlador de eventos donde debe agregar el código.</span><span class="sxs-lookup"><span data-stu-id="edd2c-137">The Visual Studio Integrated Development Environment (IDE) will return to the Code Editor and position the insertion point within the event handler where you should add the code.</span></span>

1. <span data-ttu-id="edd2c-138">Para escribir en el archivo, use el método <xref:System.IO.StreamWriter.Write%2A> de la clase <xref:System.IO.StreamWriter>.</span><span class="sxs-lookup"><span data-stu-id="edd2c-138">To write to the file, use the <xref:System.IO.StreamWriter.Write%2A> method of the <xref:System.IO.StreamWriter> class.</span></span> <span data-ttu-id="edd2c-139">Agregue el código siguiente justo después de `Dim fw As StreamWriter`.</span><span class="sxs-lookup"><span data-stu-id="edd2c-139">Add the following code directly after `Dim fw As StreamWriter`.</span></span> <span data-ttu-id="edd2c-140">No se preocupe si se produce una excepción porque no se encuentra el archivo, ya que se creará en caso de que todavía no exista.</span><span class="sxs-lookup"><span data-stu-id="edd2c-140">You do not need to worry that an exception will be thrown if the file is not found, because it will be created if it does not already exist.</span></span>

     [!code-vb[VbVbcnMyFileSystem#37](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnMyFileSystem/VB/Class1.vb#37)]

2. <span data-ttu-id="edd2c-141">Asegúrese de que el usuario no puede enviar una entrada en blanco mediante la adición del código siguiente justo después de `Dim ReadString As String`.</span><span class="sxs-lookup"><span data-stu-id="edd2c-141">Make sure that the user cannot submit a blank entry by adding the following code directly after `Dim ReadString As String`.</span></span>

     [!code-vb[VbVbcnMyFileSystem#38](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnMyFileSystem/VB/Class1.vb#38)]

3. <span data-ttu-id="edd2c-142">Como se trata de una agenda, el usuario querrá asignar una fecha a cada entrada.</span><span class="sxs-lookup"><span data-stu-id="edd2c-142">Because this is a diary, the user will want to assign a date to each entry.</span></span> <span data-ttu-id="edd2c-143">Inserte el siguiente código después de `fw = New StreamWriter("C:\MyDiary.txt", True)` para establecer la variable `Today` en la fecha actual.</span><span class="sxs-lookup"><span data-stu-id="edd2c-143">Insert the following code after `fw = New StreamWriter("C:\MyDiary.txt", True)` to set the variable `Today` to the current date.</span></span>

     [!code-vb[VbVbcnMyFileSystem#39](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnMyFileSystem/VB/Class1.vb#39)]

4. <span data-ttu-id="edd2c-144">Por último, adjunte el código para borrar <xref:System.Windows.Forms.TextBox>.</span><span class="sxs-lookup"><span data-stu-id="edd2c-144">Finally, attach code to clear the <xref:System.Windows.Forms.TextBox>.</span></span> <span data-ttu-id="edd2c-145">Agregue el código siguiente al evento <xref:System.Windows.Forms.Control.Click> del botón `Clear`.</span><span class="sxs-lookup"><span data-stu-id="edd2c-145">Add the following code to the `Clear` button's <xref:System.Windows.Forms.Control.Click> event.</span></span>

     [!code-vb[VbVbcnMyFileSystem#40](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnMyFileSystem/VB/Class1.vb#40)]

## <a name="adding-display-features-to-the-diary"></a><span data-ttu-id="edd2c-146">Agregar características de visualización a la agenda</span><span class="sxs-lookup"><span data-stu-id="edd2c-146">Adding Display Features to the Diary</span></span>

<span data-ttu-id="edd2c-147">En esta sección, agregará una característica que muestra la entrada más reciente de `DisplayEntry`<xref:System.Windows.Forms.TextBox>.</span><span class="sxs-lookup"><span data-stu-id="edd2c-147">In this section, you add a feature that displays the latest entry in the `DisplayEntry`<xref:System.Windows.Forms.TextBox>.</span></span> <span data-ttu-id="edd2c-148">También puede agregar una clase <xref:System.Windows.Forms.ComboBox> que muestra varias entradas, de entre las cuales un usuario puede seleccionar una entrada para mostrarla en `DisplayEntry`<xref:System.Windows.Forms.TextBox>.</span><span class="sxs-lookup"><span data-stu-id="edd2c-148">You can also add a <xref:System.Windows.Forms.ComboBox> that displays various entries and from which a user can select an entry to display in the `DisplayEntry`<xref:System.Windows.Forms.TextBox>.</span></span> <span data-ttu-id="edd2c-149">Una instancia de la clase <xref:System.IO.StreamReader> lee de `MyDiary.txt`.</span><span class="sxs-lookup"><span data-stu-id="edd2c-149">An instance of the <xref:System.IO.StreamReader> class reads from `MyDiary.txt`.</span></span> <span data-ttu-id="edd2c-150">Como la clase <xref:System.IO.StreamWriter>, <xref:System.IO.StreamReader> está diseñado para usarlo con archivos de texto.</span><span class="sxs-lookup"><span data-stu-id="edd2c-150">Like the <xref:System.IO.StreamWriter> class, <xref:System.IO.StreamReader> is intended for use with text files.</span></span>

<span data-ttu-id="edd2c-151">Para esta sección del tutorial, agregue los controles de la siguiente tabla al formulario y establezca los valores correspondientes para sus propiedades.</span><span class="sxs-lookup"><span data-stu-id="edd2c-151">For this section of the walkthrough, add the controls in the following table to the form and set the corresponding values for their properties.</span></span>

|<span data-ttu-id="edd2c-152">Control</span><span class="sxs-lookup"><span data-stu-id="edd2c-152">Control</span></span>|<span data-ttu-id="edd2c-153">Propiedades</span><span class="sxs-lookup"><span data-stu-id="edd2c-153">Properties</span></span>|<span data-ttu-id="edd2c-154">Valores</span><span class="sxs-lookup"><span data-stu-id="edd2c-154">Values</span></span>|
|-------------|----------------|------------|
|<xref:System.Windows.Forms.TextBox>|<span data-ttu-id="edd2c-155">**Nombre**</span><span class="sxs-lookup"><span data-stu-id="edd2c-155">**Name**</span></span><br /><br /> <span data-ttu-id="edd2c-156">**Visible**</span><span class="sxs-lookup"><span data-stu-id="edd2c-156">**Visible**</span></span><br /><br /> <span data-ttu-id="edd2c-157">**Tamaño**</span><span class="sxs-lookup"><span data-stu-id="edd2c-157">**Size**</span></span><br /><br /> <span data-ttu-id="edd2c-158">**Multiline**</span><span class="sxs-lookup"><span data-stu-id="edd2c-158">**Multiline**</span></span>|`DisplayEntry`<br /><br /> `False`<br /><br /> `120,60`<br /><br /> `True`|
|<xref:System.Windows.Forms.Button>|<span data-ttu-id="edd2c-159">**Nombre**</span><span class="sxs-lookup"><span data-stu-id="edd2c-159">**Name**</span></span><br /><br /> <span data-ttu-id="edd2c-160">**Texto**</span><span class="sxs-lookup"><span data-stu-id="edd2c-160">**Text**</span></span>|`Display`<br /><br /> <span data-ttu-id="edd2c-161">**Pantalla**</span><span class="sxs-lookup"><span data-stu-id="edd2c-161">**Display**</span></span>|
|<xref:System.Windows.Forms.Button>|<span data-ttu-id="edd2c-162">**Nombre**</span><span class="sxs-lookup"><span data-stu-id="edd2c-162">**Name**</span></span><br /><br /> <span data-ttu-id="edd2c-163">**Texto**</span><span class="sxs-lookup"><span data-stu-id="edd2c-163">**Text**</span></span>|`GetEntries`<br /><br /> <span data-ttu-id="edd2c-164">**Obtener entradas**</span><span class="sxs-lookup"><span data-stu-id="edd2c-164">**Get Entries**</span></span>|
|<xref:System.Windows.Forms.ComboBox>|<span data-ttu-id="edd2c-165">**Nombre**</span><span class="sxs-lookup"><span data-stu-id="edd2c-165">**Name**</span></span><br /><br /> <span data-ttu-id="edd2c-166">**Texto**</span><span class="sxs-lookup"><span data-stu-id="edd2c-166">**Text**</span></span><br /><br /> <span data-ttu-id="edd2c-167">**Habilitado**</span><span class="sxs-lookup"><span data-stu-id="edd2c-167">**Enabled**</span></span>|`PickEntries`<br /><br /> <span data-ttu-id="edd2c-168">**Seleccione una entrada**</span><span class="sxs-lookup"><span data-stu-id="edd2c-168">**Select an Entry**</span></span><br /><br /> `False`|

### <a name="to-populate-the-combo-box"></a><span data-ttu-id="edd2c-169">Para rellenar el cuadro combinado</span><span class="sxs-lookup"><span data-stu-id="edd2c-169">To populate the combo box</span></span>

1. <span data-ttu-id="edd2c-170">El control `PickEntries`<xref:System.Windows.Forms.ComboBox> se usa para mostrar las fechas en las que el usuario envía cada entrada, de modo que el usuario pueda seleccionar una entrada de una fecha concreta.</span><span class="sxs-lookup"><span data-stu-id="edd2c-170">The `PickEntries`<xref:System.Windows.Forms.ComboBox> is used to display the dates on which a user submits each entry, so the user can select an entry from a specific date.</span></span> <span data-ttu-id="edd2c-171">Cree un controlador de eventos <xref:System.Windows.Forms.Control.Click> para el botón `GetEntries` y agréguele el siguiente código.</span><span class="sxs-lookup"><span data-stu-id="edd2c-171">Create a <xref:System.Windows.Forms.Control.Click> event handler to the `GetEntries` button and add the following code.</span></span>

     [!code-vb[VbVbcnMyFileSystem#41](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnMyFileSystem/VB/Class1.vb#41)]

2. <span data-ttu-id="edd2c-172">Para probar el código, presione F5 para compilar la aplicación y, después, haga clic en **Obtener entradas**.</span><span class="sxs-lookup"><span data-stu-id="edd2c-172">To test your code, press F5 to compile the application, and then click **Get Entries**.</span></span> <span data-ttu-id="edd2c-173">Haga clic en la flecha desplegable en <xref:System.Windows.Forms.ComboBox> para mostrar las flechas de entrada.</span><span class="sxs-lookup"><span data-stu-id="edd2c-173">Click the drop-down arrow in the <xref:System.Windows.Forms.ComboBox> to display the entry dates.</span></span>

### <a name="to-choose-and-display-individual-entries"></a><span data-ttu-id="edd2c-174">Para seleccionar y mostrar entradas individuales</span><span class="sxs-lookup"><span data-stu-id="edd2c-174">To choose and display individual entries</span></span>

1. <span data-ttu-id="edd2c-175">Cree un controlador de eventos <xref:System.Windows.Forms.Control.Click> para el botón `Display` y agregue el código siguiente.</span><span class="sxs-lookup"><span data-stu-id="edd2c-175">Create a <xref:System.Windows.Forms.Control.Click> event handler for the `Display` button and add the following code.</span></span>

     [!code-vb[VbVbcnMyFileSystem#42](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnMyFileSystem/VB/Class1.vb#42)]

2. <span data-ttu-id="edd2c-176">Para probar el código, pulse F5 para compilar la aplicación y, después, envíe una entrada.</span><span class="sxs-lookup"><span data-stu-id="edd2c-176">To test your code, press F5 to compile the application, and then submit an entry.</span></span> <span data-ttu-id="edd2c-177">Haga clic en **Obtener entradas**, seleccione una entrada de <xref:System.Windows.Forms.ComboBox> y, después, haga clic en **Mostrar**.</span><span class="sxs-lookup"><span data-stu-id="edd2c-177">Click **Get Entries**, select an entry from the <xref:System.Windows.Forms.ComboBox>, and then click **Display**.</span></span> <span data-ttu-id="edd2c-178">El contenido de la entrada seleccionada aparece en `DisplayEntry`<xref:System.Windows.Forms.TextBox>.</span><span class="sxs-lookup"><span data-stu-id="edd2c-178">The contents of the selected entry appear in the `DisplayEntry`<xref:System.Windows.Forms.TextBox>.</span></span>

## <a name="enabling-users-to-delete-or-modify-entries"></a><span data-ttu-id="edd2c-179">Permitir que los usuarios eliminen o modifiquen entradas</span><span class="sxs-lookup"><span data-stu-id="edd2c-179">Enabling Users to Delete or Modify Entries</span></span>

<span data-ttu-id="edd2c-180">Por último, puede incluir funcionalidad adicional para permitir que los usuarios eliminen o modifiquen una entrada mediante los botones `DeleteEntry` y `EditEntry`.</span><span class="sxs-lookup"><span data-stu-id="edd2c-180">Finally, you can include additional functionality enables users to delete or modify an entry by using `DeleteEntry` and `EditEntry` buttons.</span></span> <span data-ttu-id="edd2c-181">Ambos botones permanecen deshabilitados a menos que se muestre una entrada.</span><span class="sxs-lookup"><span data-stu-id="edd2c-181">Both buttons remain disabled unless an entry is displayed.</span></span>

<span data-ttu-id="edd2c-182">Agregue los controles de la siguiente tabla al formulario y establezca los valores correspondientes para sus propiedades.</span><span class="sxs-lookup"><span data-stu-id="edd2c-182">Add the controls in the following table to the form and set the corresponding values for their properties.</span></span>

|<span data-ttu-id="edd2c-183">Control</span><span class="sxs-lookup"><span data-stu-id="edd2c-183">Control</span></span>|<span data-ttu-id="edd2c-184">Propiedades</span><span class="sxs-lookup"><span data-stu-id="edd2c-184">Properties</span></span>|<span data-ttu-id="edd2c-185">Valores</span><span class="sxs-lookup"><span data-stu-id="edd2c-185">Values</span></span>|
|-------------|----------------|------------|
|<xref:System.Windows.Forms.Button>|<span data-ttu-id="edd2c-186">**Nombre**</span><span class="sxs-lookup"><span data-stu-id="edd2c-186">**Name**</span></span><br /><br /> <span data-ttu-id="edd2c-187">**Texto**</span><span class="sxs-lookup"><span data-stu-id="edd2c-187">**Text**</span></span><br /><br /> <span data-ttu-id="edd2c-188">**Habilitado**</span><span class="sxs-lookup"><span data-stu-id="edd2c-188">**Enabled**</span></span>|`DeleteEntry`<br /><br /> <span data-ttu-id="edd2c-189">**Eliminar entrada**</span><span class="sxs-lookup"><span data-stu-id="edd2c-189">**Delete Entry**</span></span><br /><br /> `False`|
|<xref:System.Windows.Forms.Button>|<span data-ttu-id="edd2c-190">**Nombre**</span><span class="sxs-lookup"><span data-stu-id="edd2c-190">**Name**</span></span><br /><br /> <span data-ttu-id="edd2c-191">**Texto**</span><span class="sxs-lookup"><span data-stu-id="edd2c-191">**Text**</span></span><br /><br /> <span data-ttu-id="edd2c-192">**Habilitado**</span><span class="sxs-lookup"><span data-stu-id="edd2c-192">**Enabled**</span></span>|`EditEntry`<br /><br /> <span data-ttu-id="edd2c-193">**Editar entrada**</span><span class="sxs-lookup"><span data-stu-id="edd2c-193">**Edit Entry**</span></span><br /><br /> `False`|
|<xref:System.Windows.Forms.Button>|<span data-ttu-id="edd2c-194">**Nombre**</span><span class="sxs-lookup"><span data-stu-id="edd2c-194">**Name**</span></span><br /><br /> <span data-ttu-id="edd2c-195">**Texto**</span><span class="sxs-lookup"><span data-stu-id="edd2c-195">**Text**</span></span><br /><br /> <span data-ttu-id="edd2c-196">**Habilitado**</span><span class="sxs-lookup"><span data-stu-id="edd2c-196">**Enabled**</span></span>|`SubmitEdit`<br /><br /> <span data-ttu-id="edd2c-197">**Enviar edición**</span><span class="sxs-lookup"><span data-stu-id="edd2c-197">**Submit Edit**</span></span><br /><br /> `False`|

### <a name="to-enable-deletion-and-modification-of-entries"></a><span data-ttu-id="edd2c-198">Para habilitar la eliminación y la modificación de entradas</span><span class="sxs-lookup"><span data-stu-id="edd2c-198">To enable deletion and modification of entries</span></span>

1. <span data-ttu-id="edd2c-199">Agregue el código siguiente al evento <xref:System.Windows.Forms.Control.Click> del botón `Display`, después de `DisplayEntry.Text = ReadString`.</span><span class="sxs-lookup"><span data-stu-id="edd2c-199">Add the following code to the `Display` button's <xref:System.Windows.Forms.Control.Click> event, after `DisplayEntry.Text = ReadString`.</span></span>

     [!code-vb[VbVbcnMyFileSystem#43](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnMyFileSystem/VB/Class1.vb#43)]

2. <span data-ttu-id="edd2c-200">Cree un controlador de eventos <xref:System.Windows.Forms.Control.Click> para el botón `DeleteEntry` y agregue el código siguiente.</span><span class="sxs-lookup"><span data-stu-id="edd2c-200">Create a <xref:System.Windows.Forms.Control.Click> event handler for the `DeleteEntry` button and add the following code.</span></span>

     [!code-vb[VbVbcnMyFileSystem#44](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnMyFileSystem/VB/Class1.vb#44)]

3. <span data-ttu-id="edd2c-201">Cuando un usuario muestra una entrada, se habilita el botón `EditEntry`.</span><span class="sxs-lookup"><span data-stu-id="edd2c-201">When a user displays an entry, the `EditEntry` button becomes enabled.</span></span> <span data-ttu-id="edd2c-202">Agregue el código siguiente al evento <xref:System.Windows.Forms.Control.Click> del botón `Display` después de `DisplayEntry.Text = ReadString`.</span><span class="sxs-lookup"><span data-stu-id="edd2c-202">Add the following code to the <xref:System.Windows.Forms.Control.Click> event of the `Display` button after `DisplayEntry.Text = ReadString`.</span></span>

     [!code-vb[VbVbcnMyFileSystem#45](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnMyFileSystem/VB/Class1.vb#45)]

4. <span data-ttu-id="edd2c-203">Cree un controlador de eventos <xref:System.Windows.Forms.Control.Click> para el botón `EditEntry` y agregue el código siguiente.</span><span class="sxs-lookup"><span data-stu-id="edd2c-203">Create a <xref:System.Windows.Forms.Control.Click> event handler for the `EditEntry` button and add the following code.</span></span>

     [!code-vb[VbVbcnMyFileSystem#46](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnMyFileSystem/VB/Class1.vb#46)]

5. <span data-ttu-id="edd2c-204">Cree un controlador de eventos <xref:System.Windows.Forms.Control.Click> para el botón `SubmitEdit` y agregue el código siguiente.</span><span class="sxs-lookup"><span data-stu-id="edd2c-204">Create a <xref:System.Windows.Forms.Control.Click> event handler for the `SubmitEdit` button and add the following code</span></span>

     [!code-vb[VbVbcnMyFileSystem#47](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnMyFileSystem/VB/Class1.vb#47)]

<span data-ttu-id="edd2c-205">Para probar el código, pulse F5 para compilar la aplicación.</span><span class="sxs-lookup"><span data-stu-id="edd2c-205">To test your code, press F5 to compile the application.</span></span> <span data-ttu-id="edd2c-206">Haga clic en **Obtener entradas**, seleccione una entrada y, después, haga clic en **Mostrar**.</span><span class="sxs-lookup"><span data-stu-id="edd2c-206">Click **Get Entries**, select an entry, and then click **Display**.</span></span> <span data-ttu-id="edd2c-207">La entrada aparece en `DisplayEntry`<xref:System.Windows.Forms.TextBox>.</span><span class="sxs-lookup"><span data-stu-id="edd2c-207">The entry appears in the `DisplayEntry`<xref:System.Windows.Forms.TextBox>.</span></span> <span data-ttu-id="edd2c-208">Haga clic en **Editar entrada**.</span><span class="sxs-lookup"><span data-stu-id="edd2c-208">Click **Edit Entry**.</span></span> <span data-ttu-id="edd2c-209">La entrada aparece en `Entry`<xref:System.Windows.Forms.TextBox>.</span><span class="sxs-lookup"><span data-stu-id="edd2c-209">The entry appears in the `Entry`<xref:System.Windows.Forms.TextBox>.</span></span> <span data-ttu-id="edd2c-210">Edite la entrada de `Entry`<xref:System.Windows.Forms.TextBox> y haga clic en **Submit Edit** (Enviar edición).</span><span class="sxs-lookup"><span data-stu-id="edd2c-210">Edit the entry in the `Entry`<xref:System.Windows.Forms.TextBox> and click **Submit Edit**.</span></span> <span data-ttu-id="edd2c-211">Abra el archivo `MyDiary.txt` para confirmar la corrección.</span><span class="sxs-lookup"><span data-stu-id="edd2c-211">Open the `MyDiary.txt` file to confirm your correction.</span></span> <span data-ttu-id="edd2c-212">Seleccione una entrada y haga clic en **Eliminar entrada**.</span><span class="sxs-lookup"><span data-stu-id="edd2c-212">Now select an entry and click **Delete Entry**.</span></span> <span data-ttu-id="edd2c-213">Cuando <xref:System.Windows.Forms.MessageBox> solicite confirmación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="edd2c-213">When the <xref:System.Windows.Forms.MessageBox> requests confirmation, click **OK**.</span></span> <span data-ttu-id="edd2c-214">Cierre la aplicación y abra `MyDiary.txt` para confirmar la eliminación.</span><span class="sxs-lookup"><span data-stu-id="edd2c-214">Close the application and open `MyDiary.txt` to confirm the deletion.</span></span>

## <a name="see-also"></a><span data-ttu-id="edd2c-215">Vea también</span><span class="sxs-lookup"><span data-stu-id="edd2c-215">See also</span></span>

- <xref:System.IO.StreamReader>
- <xref:System.IO.StreamWriter>
- [<span data-ttu-id="edd2c-216">Tutoriales</span><span class="sxs-lookup"><span data-stu-id="edd2c-216">Walkthroughs</span></span>](../../../walkthroughs.md)
