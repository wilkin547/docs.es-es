---
title: Ejemplo de enlace de datos de LINQ to XML
ms.date: 10/22/2019
ms.topic: sample
helpviewer_keywords:
- linq to xml data binding sample
ms.openlocfilehash: aac814e4768a863a93e69e34cd18c941a9b35c89
ms.sourcegitcommit: 82f94a44ad5c64a399df2a03fa842db308185a76
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/25/2019
ms.locfileid: "72921225"
---
# <a name="linq-to-xml-data-binding-sample"></a><span data-ttu-id="552dd-102">Ejemplo de enlace de datos de LINQ to XML</span><span class="sxs-lookup"><span data-stu-id="552dd-102">LINQ to XML data binding sample</span></span>

<span data-ttu-id="552dd-103">En este artículo se describe el ejemplo LinqToXmlDataBinding, una aplicación Windows Presentation Foundation (WPF) que enlaza los componentes de la interfaz de usuario a un origen de datos XML incrustado.</span><span class="sxs-lookup"><span data-stu-id="552dd-103">This article describes the LinqToXmlDataBinding sample, a Windows Presentation Foundation (WPF) app that binds user interface components to an embedded XML data source.</span></span>

## <a name="overview"></a><span data-ttu-id="552dd-104">Información general</span><span class="sxs-lookup"><span data-stu-id="552dd-104">Overview</span></span>

<span data-ttu-id="552dd-105">El ejemplo LinqToXmlDataBinding es una aplicación Windows Presentation Foundation (WPF) que contiene C# archivos de código fuente XAML y.</span><span class="sxs-lookup"><span data-stu-id="552dd-105">The LinqToXmlDataBinding sample is a Windows Presentation Foundation (WPF) app that contains C# and XAML source files.</span></span> <span data-ttu-id="552dd-106">Un documento XML incrustado define una lista de libros.</span><span class="sxs-lookup"><span data-stu-id="552dd-106">An embedded XML document defines a list of books.</span></span> <span data-ttu-id="552dd-107">La aplicación permite al usuario ver, agregar, eliminar y editar las entradas del libro.</span><span class="sxs-lookup"><span data-stu-id="552dd-107">The app enables the user to view, add, delete, and edit the book entries.</span></span>

<span data-ttu-id="552dd-108">Hay dos archivos de origen principales:</span><span class="sxs-lookup"><span data-stu-id="552dd-108">There are two primary source files:</span></span>

- <span data-ttu-id="552dd-109">[L2DBForm.xaml](l2dbform-xaml-source-code.md) contiene el código de declaración XAML para la interfaz de usuario (IU) de la ventana principal.</span><span class="sxs-lookup"><span data-stu-id="552dd-109">[L2DBForm.xaml](l2dbform-xaml-source-code.md) contains the XAML declaration code for the user interface (UI) of the main window.</span></span> <span data-ttu-id="552dd-110">También contiene una sección de recursos de ventana que define un proveedor de datos y un documento XML incrustado para los listados de libros.</span><span class="sxs-lookup"><span data-stu-id="552dd-110">It also contains a window resource section that defines a data provider and an embedded XML document for the book listings.</span></span>

- <span data-ttu-id="552dd-111">[L2DBForm.xaml.cs](l2dbform-xaml-cs-source-code.md) contiene los métodos de control de eventos y de inicialización asociados a la IU.</span><span class="sxs-lookup"><span data-stu-id="552dd-111">[L2DBForm.xaml.cs](l2dbform-xaml-cs-source-code.md) contains the initialization and event-handling methods associated with the UI.</span></span>

<span data-ttu-id="552dd-112">La ventana principal se divide en las cuatro secciones de IU verticales siguientes:</span><span class="sxs-lookup"><span data-stu-id="552dd-112">The main window is divided into the following four vertical UI sections:</span></span>

- <span data-ttu-id="552dd-113">**XML** muestra el origen XML sin procesar de la lista de libros insertada.</span><span class="sxs-lookup"><span data-stu-id="552dd-113">**XML** displays the raw XML source of the embedded book listing.</span></span>

- <span data-ttu-id="552dd-114">**Lista de libros** muestra las entradas de libro como texto estándar y permite que el usuario seleccione y elimine entradas individuales.</span><span class="sxs-lookup"><span data-stu-id="552dd-114">**Book List** displays the book entries as standard text and enables the user to select and delete individual entries.</span></span>

- <span data-ttu-id="552dd-115">**Edit Selected Book** (Editar libro seleccionado) permite que el usuario edite los valores asociados a la entrada de libro seleccionada actualmente.</span><span class="sxs-lookup"><span data-stu-id="552dd-115">**Edit Selected Book** enables the user to edit the values associated with the currently selected book entry.</span></span>

- <span data-ttu-id="552dd-116">**Add New Book** (Agregar nuevo libro) permite la creación de una entrada de libro según los valores especificados por el usuario.</span><span class="sxs-lookup"><span data-stu-id="552dd-116">**Add New Book** enables the creation of a new book entry based on values entered by the user.</span></span>

## <a name="run-the-sample"></a><span data-ttu-id="552dd-117">Ejecutar el ejemplo</span><span class="sxs-lookup"><span data-stu-id="552dd-117">Run the sample</span></span>

<span data-ttu-id="552dd-118">En esta sección se muestra cómo crear y compilar el proyecto LinqToXmlDataBinding en Visual Studio y cómo ejecutar la aplicación LinqToXmlDataBinding Windows Presentation Foundation (WPF) resultante.</span><span class="sxs-lookup"><span data-stu-id="552dd-118">This section shows how to create and build the LinqToXmlDataBinding project in Visual Studio, and how to run the resulting LinqToXmlDataBinding Windows Presentation Foundation (WPF) app.</span></span>

### <a name="create-the-project"></a><span data-ttu-id="552dd-119">Crear el proyecto</span><span class="sxs-lookup"><span data-stu-id="552dd-119">Create the project</span></span>

1. <span data-ttu-id="552dd-120">Abra Visual Studio y cree una **aplicación WPF** de C# con el nombre **LinqToXmlDataBinding**.</span><span class="sxs-lookup"><span data-stu-id="552dd-120">Open Visual Studio and create a C# **WPF App** named **LinqToXmlDataBinding**.</span></span>

   <span data-ttu-id="552dd-121">El proyecto debe tener como destino .NET Framework3.5 (o posterior).</span><span class="sxs-lookup"><span data-stu-id="552dd-121">The project should target the .NET Framework 3.5 (or later).</span></span>

1. <span data-ttu-id="552dd-122">Si aún no están presentes, agregue referencias al proyecto para los siguientes ensamblados de .NET:</span><span class="sxs-lookup"><span data-stu-id="552dd-122">If not already present, add project references for the following .NET assemblies:</span></span>

    - <span data-ttu-id="552dd-123">System.Data</span><span class="sxs-lookup"><span data-stu-id="552dd-123">System.Data</span></span>
    - <span data-ttu-id="552dd-124">System.Data.DataSetExtensions</span><span class="sxs-lookup"><span data-stu-id="552dd-124">System.Data.DataSetExtensions</span></span>
    - <span data-ttu-id="552dd-125">System.Xml</span><span class="sxs-lookup"><span data-stu-id="552dd-125">System.Xml</span></span>
    - <span data-ttu-id="552dd-126">System.Xml</span><span class="sxs-lookup"><span data-stu-id="552dd-126">System.Xml</span></span>

1. <span data-ttu-id="552dd-127">Compile la solución presionando **Ctrl**+**Mayús**+**B** y después presione **F5** para ejecutarla.</span><span class="sxs-lookup"><span data-stu-id="552dd-127">Build the solution by pressing **Ctrl**+**Shift**+**B**, then run it by pressing **F5**.</span></span>

   <span data-ttu-id="552dd-128">El proyecto debería compilarse sin errores y ejecutarse como una aplicación WPF genérica.</span><span class="sxs-lookup"><span data-stu-id="552dd-128">The project should compile without errors and run as a generic WPF application.</span></span>

### <a name="add-code"></a><span data-ttu-id="552dd-129">Agregar código</span><span class="sxs-lookup"><span data-stu-id="552dd-129">Add code</span></span>

1. <span data-ttu-id="552dd-130">En el **Explorador de soluciones**, cambie el nombre del archivo de origen **Window1.xaml** a **L2XDBForm.xaml**.</span><span class="sxs-lookup"><span data-stu-id="552dd-130">In **Solution Explorer**, rename the source file **Window1.xaml** to **L2XDBForm.xaml**.</span></span>

   <span data-ttu-id="552dd-131">El nombre del archivo de código fuente dependiente Window1.xaml.cs se cambia automáticamente a L2XDBForm.xaml.cs.</span><span class="sxs-lookup"><span data-stu-id="552dd-131">The dependent source file Window1.xaml.cs is automatically renamed to L2XDBForm.xaml.cs.</span></span>

1. <span data-ttu-id="552dd-132">Reemplace el código fuente que se encuentra en el archivo **L2XDBForm. Xaml** por el [código fuente L2DBForm. Xaml](l2dbform-xaml-source-code.md).</span><span class="sxs-lookup"><span data-stu-id="552dd-132">Replace the source code found in the file **L2XDBForm.xaml** with the [L2DBForm.xaml source code](l2dbform-xaml-source-code.md).</span></span> <span data-ttu-id="552dd-133">(Use la vista de origen de XAML para trabajar con este archivo).</span><span class="sxs-lookup"><span data-stu-id="552dd-133">Use the XAML source view to work with this file.</span></span>

1. <span data-ttu-id="552dd-134">Del mismo modo, reemplace el código fuente de **L2XDBForm.Xaml.CS** por el [código fuente de L2DBForm.Xaml.CS](l2dbform-xaml-cs-source-code.md).</span><span class="sxs-lookup"><span data-stu-id="552dd-134">Similarly, replace the source in **L2XDBForm.xaml.cs** with the [L2DBForm.xaml.cs source code](l2dbform-xaml-cs-source-code.md).</span></span>

1. <span data-ttu-id="552dd-135">En el archivo **app. Xaml**, reemplace todas las apariciones de la cadena **Window1. Xaml** por **L2XDBForm. Xaml**.</span><span class="sxs-lookup"><span data-stu-id="552dd-135">In the file **App.xaml**, replace all occurrences of the string **Window1.xaml** with **L2XDBForm.xaml**.</span></span>

1. <span data-ttu-id="552dd-136">Compile la solución presionando **Ctrl**+**Mayús**+**B**.</span><span class="sxs-lookup"><span data-stu-id="552dd-136">Build the solution by pressing **Ctrl**+**Shift**+**B**.</span></span>

### <a name="run-the-app"></a><span data-ttu-id="552dd-137">Ejecutar la aplicación</span><span class="sxs-lookup"><span data-stu-id="552dd-137">Run the app</span></span>

<span data-ttu-id="552dd-138">La aplicación LinqToXmlDataBinding permite al usuario ver y manipular una lista de libros que se almacenan como un elemento XML incrustado.</span><span class="sxs-lookup"><span data-stu-id="552dd-138">The LinqToXmlDataBinding app enables the user to view and manipulate a list of books that's stored as an embedded XML element.</span></span> <span data-ttu-id="552dd-139">Ejecute la aplicación presionando **F5** (iniciar depuración) o **Ctrl**+**F5** (iniciar sin depurar).</span><span class="sxs-lookup"><span data-stu-id="552dd-139">Run the app by pressing **F5** (Start Debugging) or **Ctrl**+**F5** (Start Without Debugging).</span></span>

<span data-ttu-id="552dd-140">Se muestra una ventana de programa con el título **Enlace de datos de WPF con LINQ to XML**.</span><span class="sxs-lookup"><span data-stu-id="552dd-140">A program window with the title **WPF Data Binding using LINQ to XML** appears.</span></span>

<span data-ttu-id="552dd-141">La sección superior de la interfaz de usuario muestra el **XML** sin formato que representa la lista de libros.</span><span class="sxs-lookup"><span data-stu-id="552dd-141">The top section of the UI displays the raw **XML** that represents the book list.</span></span> <span data-ttu-id="552dd-142">Se muestra mediante un control <xref:System.Windows.Controls.TextBlock> de WPF, que no permite la interacción a través del mouse o del teclado.</span><span class="sxs-lookup"><span data-stu-id="552dd-142">It is displayed using a WPF <xref:System.Windows.Controls.TextBlock> control, which does not enable interaction through the mouse or keyboard.</span></span>

<span data-ttu-id="552dd-143">En la segunda sección vertical, con la etiqueta **Lista de libros**, se muestran los libros como una lista ordenada de texto sin formato.</span><span class="sxs-lookup"><span data-stu-id="552dd-143">The second vertical section, labeled **Book List**, displays the books as a plain text ordered list.</span></span> <span data-ttu-id="552dd-144">Utiliza un control <xref:System.Windows.Controls.ListBox> que permite la selección a través del mouse o del teclado.</span><span class="sxs-lookup"><span data-stu-id="552dd-144">It uses a <xref:System.Windows.Controls.ListBox> control that enables selection though the mouse or keyboard.</span></span>

### <a name="add-and-delete-books"></a><span data-ttu-id="552dd-145">Agregar y eliminar libros</span><span class="sxs-lookup"><span data-stu-id="552dd-145">Add and delete books</span></span>

<span data-ttu-id="552dd-146">Para agregar un nuevo libro a la lista, escriba los valores en los controles **ID.** y **valor** <xref:System.Windows.Controls.TextBox> de la última sección, **Agregar nuevo libro**y, a continuación, seleccione **Agregar libro**.</span><span class="sxs-lookup"><span data-stu-id="552dd-146">To add a new book to the list, enter values into the **ID** and **Value** <xref:System.Windows.Controls.TextBox> controls in the last section, **Add New Book**, and then select **Add Book**.</span></span> <span data-ttu-id="552dd-147">El libro se anexa a la lista en los listados de libros y XML.</span><span class="sxs-lookup"><span data-stu-id="552dd-147">The book is appended to the list in both the book and XML listings.</span></span> <span data-ttu-id="552dd-148">Este programa no valida los valores de entrada.</span><span class="sxs-lookup"><span data-stu-id="552dd-148">This program does not validate input values.</span></span>

<span data-ttu-id="552dd-149">Para eliminar un libro existente de la lista, selecciónelo en la sección **lista de libros** y, a continuación, seleccione quitar el **libro seleccionado**.</span><span class="sxs-lookup"><span data-stu-id="552dd-149">To delete an existing book from the list, select it in the **Book List** section, and then select **Remove Selected Book**.</span></span> <span data-ttu-id="552dd-150">La entrada del libro se quita del libro y de las listas de origen XML sin formato.</span><span class="sxs-lookup"><span data-stu-id="552dd-150">The book entry is removed from both the book and the raw XML source listings.</span></span>

### <a name="edit-a-book-entry"></a><span data-ttu-id="552dd-151">Editar una entrada de libro</span><span class="sxs-lookup"><span data-stu-id="552dd-151">Edit a book entry</span></span>

1. <span data-ttu-id="552dd-152">Seleccione la entrada del libro en la segunda sección **Lista de libros**.</span><span class="sxs-lookup"><span data-stu-id="552dd-152">Select the book entry in the second **Book List** section.</span></span>

   <span data-ttu-id="552dd-153">Sus valores actuales se muestran en la sección **editar el libro seleccionado** .</span><span class="sxs-lookup"><span data-stu-id="552dd-153">Its current values are displayed in the **Edit Selected Book** section.</span></span>

1. <span data-ttu-id="552dd-154">Edite los valores usando el teclado.</span><span class="sxs-lookup"><span data-stu-id="552dd-154">Edit the values using the keyboard.</span></span> <span data-ttu-id="552dd-155">Tan pronto como el control <xref:System.Windows.Controls.TextBox> pierde el foco, los cambios se propagan automáticamente a la lista de orígenes y libros de origen XML.</span><span class="sxs-lookup"><span data-stu-id="552dd-155">As soon as either <xref:System.Windows.Controls.TextBox> control loses focus, changes are automatically propagated to the XML source and book listings.</span></span>
