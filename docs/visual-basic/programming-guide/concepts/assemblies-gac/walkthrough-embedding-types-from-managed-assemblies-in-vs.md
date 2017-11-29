---
title: 'Tutorial: Incrustar los tipos de los ensamblados administrados en Visual Studio (Visual Basic)'
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 56ed12ba-adff-4e9c-a668-7fcba80c4795
caps.latest.revision: "3"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 4411b40d8ffbdf2b74c49152db675286d91b43ea
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="walkthrough-embedding-types-from-managed-assemblies-in-visual-studio-visual-basic"></a><span data-ttu-id="fb66c-102">Tutorial: Incrustar los tipos de los ensamblados administrados en Visual Studio (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="fb66c-102">Walkthrough: Embedding Types from Managed Assemblies in Visual Studio (Visual Basic)</span></span>
<span data-ttu-id="fb66c-103">Si inserta información de tipos de un ensamblado administrado con nombre seguro, puede acoplar tipos holgadamente en una aplicación para lograr independencia de versiones.</span><span class="sxs-lookup"><span data-stu-id="fb66c-103">If you embed type information from a strong-named managed assembly, you can loosely couple types in an application to achieve version independence.</span></span> <span data-ttu-id="fb66c-104">Es decir, el programa puede escribirse de modo que use tipos de varias versiones de una biblioteca administrada sin tener que volver a compilarse para cada versión.</span><span class="sxs-lookup"><span data-stu-id="fb66c-104">That is, your program can be written to use types from multiple versions of a managed library without having to be recompiled for each version.</span></span>  
  
 <span data-ttu-id="fb66c-105">La inserción de tipos se usa a menudo con interoperabilidad COM, como, por ejemplo, una aplicación que use objetos de automatización de Microsoft Office.</span><span class="sxs-lookup"><span data-stu-id="fb66c-105">Type embedding is frequently used with COM interop, such as an application that uses automation objects from Microsoft Office.</span></span> <span data-ttu-id="fb66c-106">La inserción de información de tipos permite que la misma versión de un programa funcione con distintas versiones de Microsoft Office en equipos diferentes.</span><span class="sxs-lookup"><span data-stu-id="fb66c-106">Embedding type information enables the same build of a program to work with different versions of Microsoft Office on different computers.</span></span> <span data-ttu-id="fb66c-107">Pero la inserción de tipos también se puede usar con una solución totalmente administrada.</span><span class="sxs-lookup"><span data-stu-id="fb66c-107">However, you can also use type embedding with a fully managed solution.</span></span>  
  
 <span data-ttu-id="fb66c-108">La información de tipos puede insertarse de un ensamblado que tenga las siguientes características:</span><span class="sxs-lookup"><span data-stu-id="fb66c-108">Type information can be embedded from an assembly that has the following characteristics:</span></span>  
  
-   <span data-ttu-id="fb66c-109">El ensamblado expone al menos una interfaz pública.</span><span class="sxs-lookup"><span data-stu-id="fb66c-109">The assembly exposes at least one public interface.</span></span>  
  
-   <span data-ttu-id="fb66c-110">Las interfaces insertadas se anotan con un atributo `ComImport` y un atributo `Guid` (y un GUID único).</span><span class="sxs-lookup"><span data-stu-id="fb66c-110">The embedded interfaces are annotated with a `ComImport` attribute and a `Guid` attribute (and a unique GUID).</span></span>  
  
-   <span data-ttu-id="fb66c-111">El ensamblado se anota con los atributos `ImportedFromTypeLib` o `PrimaryInteropAssembly` y un atributo `Guid` de nivel de ensamblado.</span><span class="sxs-lookup"><span data-stu-id="fb66c-111">The assembly is annotated with the `ImportedFromTypeLib` attribute or the `PrimaryInteropAssembly` attribute, and an assembly-level `Guid` attribute.</span></span> <span data-ttu-id="fb66c-112">(De forma predeterminada, las plantillas de proyecto de Visual Basic incluyen un nivel de ensamblado `Guid` atributo.)</span><span class="sxs-lookup"><span data-stu-id="fb66c-112">(By default, Visual Basic project templates include an assembly-level `Guid` attribute.)</span></span>  
  
 <span data-ttu-id="fb66c-113">Después de especificar las interfaces públicas que se pueden insertar, puede crear clases en tiempo de ejecución que implementen esas interfaces.</span><span class="sxs-lookup"><span data-stu-id="fb66c-113">After you have specified the public interfaces that can be embedded, you can create runtime classes that implement those interfaces.</span></span> <span data-ttu-id="fb66c-114">Un programa cliente puede luego incrustar la información de tipo de dichas interfaces en tiempo de diseño haciendo referencia al ensamblado que contiene la configuración y las interfaces públicas de la propiedad `Embed Interop Types` de la referencia a `True`.</span><span class="sxs-lookup"><span data-stu-id="fb66c-114">A client program can then embed the type information for those interfaces at design time by referencing the assembly that contains the public interfaces and setting the `Embed Interop Types` property of the reference to `True`.</span></span> <span data-ttu-id="fb66c-115">Esto equivale a usar el compilador de línea de comandos y hacer referencia al ensamblado mediante la opción `/link` del compilador.</span><span class="sxs-lookup"><span data-stu-id="fb66c-115">This is equivalent to using the command line compiler and referencing the assembly by using the `/link` compiler option.</span></span> <span data-ttu-id="fb66c-116">El programa cliente puede luego cargar instancias de los objetos en tiempo de ejecución escritos como esas interfaces.</span><span class="sxs-lookup"><span data-stu-id="fb66c-116">The client program can then load instances of your runtime objects typed as those interfaces.</span></span> <span data-ttu-id="fb66c-117">Si crea otra versión del ensamblado en tiempo de ejecución con nombre seguro, el programa cliente no tiene que volver a compilarse con el ensamblado en tiempo de ejecución actualizado.</span><span class="sxs-lookup"><span data-stu-id="fb66c-117">If you create a new version of your strong-named runtime assembly, the client program does not have to be recompiled with the updated runtime assembly.</span></span> <span data-ttu-id="fb66c-118">En su lugar, el programa cliente sigue usando cualquier versión del ensamblado en tiempo de ejecución que encuentre disponible y usa la información de tipo insertada para las interfaces públicas.</span><span class="sxs-lookup"><span data-stu-id="fb66c-118">Instead, the client program continues to use whichever version of the runtime assembly is available to it, using the embedded type information for the public interfaces.</span></span>  
  
 <span data-ttu-id="fb66c-119">Dado que la función principal de la inserción de tipos es admitir la inserción de información de tipos de ensamblados de interoperabilidad COM, cuando se inserta información de tipos en una solución totalmente administrada se aplican las siguientes limitaciones:</span><span class="sxs-lookup"><span data-stu-id="fb66c-119">Because the primary function of type embedding is to support embedding of type information from COM interop assemblies, the following limitations apply when you embed type information in a fully managed solution:</span></span>  
  
-   <span data-ttu-id="fb66c-120">Solo se insertan los atributos específicos de interoperabilidad COM; se omiten otros atributos.</span><span class="sxs-lookup"><span data-stu-id="fb66c-120">Only attributes specific to COM interop are embedded; other attributes are ignored.</span></span>  
  
-   <span data-ttu-id="fb66c-121">Si un tipo usa parámetros genéricos y el tipo del parámetro genérico es un tipo insertado, ese tipo no se puede usar más allá de un límite de ensamblado.</span><span class="sxs-lookup"><span data-stu-id="fb66c-121">If a type uses generic parameters and the type of the generic parameter is an embedded type, that type cannot be used across an assembly boundary.</span></span> <span data-ttu-id="fb66c-122">Entre los ejemplos de cruce de un límite de ensamblado se incluyen llamar a un método desde otro ensamblado o derivar un tipo de un tipo definido en otro ensamblado.</span><span class="sxs-lookup"><span data-stu-id="fb66c-122">Examples of crossing an assembly boundary include calling a method from another assembly or a deriving a type from a type defined in another assembly.</span></span>  
  
-   <span data-ttu-id="fb66c-123">Las constantes no se insertan.</span><span class="sxs-lookup"><span data-stu-id="fb66c-123">Constants are not embedded.</span></span>  
  
-   <span data-ttu-id="fb66c-124">La clase <xref:System.Collections.Generic.Dictionary%602?displayProperty=nameWithType> no admite un tipo insertado como clave.</span><span class="sxs-lookup"><span data-stu-id="fb66c-124">The <xref:System.Collections.Generic.Dictionary%602?displayProperty=nameWithType> class does not support an embedded type as a key.</span></span> <span data-ttu-id="fb66c-125">Puede implementar su propio tipo de diccionario que admita un tipo insertado como clave.</span><span class="sxs-lookup"><span data-stu-id="fb66c-125">You can implement your own dictionary type to support an embedded type as a key.</span></span>  
  
 <span data-ttu-id="fb66c-126">En este tutorial, se realizarán las siguientes tareas:</span><span class="sxs-lookup"><span data-stu-id="fb66c-126">In this walkthrough, you will do the following:</span></span>  
  
-   <span data-ttu-id="fb66c-127">Crear un ensamblado con nombre seguro que tenga una interfaz pública e incluya información de tipo que se puede insertar.</span><span class="sxs-lookup"><span data-stu-id="fb66c-127">Create a strong-named assembly that has a public interface that contains type information that can be embedded.</span></span>  
  
-   <span data-ttu-id="fb66c-128">Crear un ensamblado en tiempo de ejecución con nombre seguro que implemente esa interfaz pública.</span><span class="sxs-lookup"><span data-stu-id="fb66c-128">Create a strong-named runtime assembly that implements that public interface.</span></span>  
  
-   <span data-ttu-id="fb66c-129">Crear un programa cliente que inserte la información de tipo de la interfaz pública y cree una instancia de la clase del ensamblado en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="fb66c-129">Create a client program that embeds the type information from the public interface and creates an instance of the class from the runtime assembly.</span></span>  
  
-   <span data-ttu-id="fb66c-130">Modificar y recompilar el ensamblado en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="fb66c-130">Modify and rebuild the runtime assembly.</span></span>  
  
-   <span data-ttu-id="fb66c-131">Ejecute el programa cliente para ver que se usa la nueva versión del ensamblado en tiempo de ejecución sin tener que recompilar el programa cliente.</span><span class="sxs-lookup"><span data-stu-id="fb66c-131">Run the client program to see that the new version of the runtime assembly is being used without having to recompile the client program.</span></span>  
  
[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]  
  
## <a name="creating-an-interface"></a><span data-ttu-id="fb66c-132">Creación de una interfaz</span><span class="sxs-lookup"><span data-stu-id="fb66c-132">Creating an Interface</span></span>  
  
#### <a name="to-create-the-type-equivalence-interface-project"></a><span data-ttu-id="fb66c-133">Para crear el proyecto de interfaz de equivalencia de tipos</span><span class="sxs-lookup"><span data-stu-id="fb66c-133">To create the type equivalence interface project</span></span>  
  
1.  <span data-ttu-id="fb66c-134">En el menú **Archivo** de Visual Studio, apunte a **Nuevo** y haga clic en **Proyecto**.</span><span class="sxs-lookup"><span data-stu-id="fb66c-134">In Visual Studio, on the **File** menu, point to **New** and then click **Project**.</span></span>  
  
2.  <span data-ttu-id="fb66c-135">En el panel **Tipos de proyecto** del cuadro de diálogo **Nuevo proyecto**, asegúrese de que esté seleccionado **Windows**.</span><span class="sxs-lookup"><span data-stu-id="fb66c-135">In the **New Project** dialog box, in the **Project Types** pane, make sure that **Windows** is selected.</span></span> <span data-ttu-id="fb66c-136">Seleccione **Biblioteca de clases** en el panel **Plantillas**.</span><span class="sxs-lookup"><span data-stu-id="fb66c-136">Select **Class Library** in the **Templates** pane.</span></span> <span data-ttu-id="fb66c-137">En el cuadro **Nombre**, escriba `TypeEquivalenceInterface` y haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="fb66c-137">In the **Name** box, type `TypeEquivalenceInterface`, and then click **OK**.</span></span> <span data-ttu-id="fb66c-138">Se crea el proyecto.</span><span class="sxs-lookup"><span data-stu-id="fb66c-138">The new project is created.</span></span>  
  
3.  <span data-ttu-id="fb66c-139">En **el Explorador de soluciones**, haga clic en el archivo Class1.vb y haga clic en **cambiar el nombre de**.</span><span class="sxs-lookup"><span data-stu-id="fb66c-139">In **Solution Explorer**, right-click the Class1.vb file and click **Rename**.</span></span> <span data-ttu-id="fb66c-140">Cambie el nombre del archivo a `ISampleInterface.vb` y pulse ENTRAR.</span><span class="sxs-lookup"><span data-stu-id="fb66c-140">Rename the file to `ISampleInterface.vb` and press ENTER.</span></span> <span data-ttu-id="fb66c-141">Al cambiar el nombre del archivo también se cambiará el nombre de la clase a `ISampleInterface`.</span><span class="sxs-lookup"><span data-stu-id="fb66c-141">Renaming the file will also rename the class to `ISampleInterface`.</span></span> <span data-ttu-id="fb66c-142">Esta clase representará la interfaz pública de la clase.</span><span class="sxs-lookup"><span data-stu-id="fb66c-142">This class will represent the public interface for the class.</span></span>  
  
4.  <span data-ttu-id="fb66c-143">Haga clic con el botón derecho en el proyecto TypeEquivalenceInterface y haga clic en **Propiedades**.</span><span class="sxs-lookup"><span data-stu-id="fb66c-143">Right-click the TypeEquivalenceInterface project and click **Properties**.</span></span> <span data-ttu-id="fb66c-144">Haga clic en la pestaña **Compilar**. Establezca la ruta de acceso de salida en una ubicación válida en el equipo de desarrollo, como `C:\TypeEquivalenceSample`.</span><span class="sxs-lookup"><span data-stu-id="fb66c-144">Click the **Compile** tab. Set the output path to a valid location on your development computer, such as `C:\TypeEquivalenceSample`.</span></span> <span data-ttu-id="fb66c-145">Esta ubicación también se usará en un paso posterior en este tutorial.</span><span class="sxs-lookup"><span data-stu-id="fb66c-145">This location will also be used in a later step in this walkthrough.</span></span>  
  
5.  <span data-ttu-id="fb66c-146">Mientras sigue editando las propiedades del proyecto, haga clic en la pestaña **Firma**. Seleccione la opción **Firmar el ensamblado**.</span><span class="sxs-lookup"><span data-stu-id="fb66c-146">While still editing the project properties, click the **Signing** tab. Select the **Sign the assembly** option.</span></span> <span data-ttu-id="fb66c-147">En la lista **Elija un archivo de clave de nombre seguro**, haga clic en **<Nuevo...>**.</span><span class="sxs-lookup"><span data-stu-id="fb66c-147">In the **Choose a strong name key file** list, click **<New...>**.</span></span> <span data-ttu-id="fb66c-148">En el cuadro **Nombre del archivo de clave**, escriba `key.snk`.</span><span class="sxs-lookup"><span data-stu-id="fb66c-148">In the **Key file name** box, type `key.snk`.</span></span> <span data-ttu-id="fb66c-149">Desactive la casilla **Proteger mi archivo de clave mediante contraseña**.</span><span class="sxs-lookup"><span data-stu-id="fb66c-149">Clear the **Protect my key file with a password** check box.</span></span> <span data-ttu-id="fb66c-150">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="fb66c-150">Click **OK**.</span></span>  
  
6.  <span data-ttu-id="fb66c-151">Abra el archivo ISampleInterface.vb.</span><span class="sxs-lookup"><span data-stu-id="fb66c-151">Open the ISampleInterface.vb file.</span></span> <span data-ttu-id="fb66c-152">Agregue el código siguiente al archivo de clase ISampleInterface para crear la interfaz ISampleInterface.</span><span class="sxs-lookup"><span data-stu-id="fb66c-152">Add the following code to the ISampleInterface class file to create the ISampleInterface interface.</span></span>  
  
    ```vb  
    Imports System.Runtime.InteropServices  
  
    <ComImport()>  
    <Guid("8DA56996-A151-4136-B474-32784559F6DF")>  
    Public Interface ISampleInterface  
        Sub GetUserInput()  
        ReadOnly Property UserInput As String  
    End Interface  
    ```  
  
7.  <span data-ttu-id="fb66c-153">En el menú **Herramientas**, haga clic en **Crear GUID**.</span><span class="sxs-lookup"><span data-stu-id="fb66c-153">On the **Tools** menu, click **Create Guid**.</span></span> <span data-ttu-id="fb66c-154">En el cuadro de diálogo **Crear GUID**, haga clic en **Formato de Registro** y luego en **Copiar**.</span><span class="sxs-lookup"><span data-stu-id="fb66c-154">In the **Create GUID** dialog box, click **Registry Format** and then click **Copy**.</span></span> <span data-ttu-id="fb66c-155">Haga clic en **Salir**.</span><span class="sxs-lookup"><span data-stu-id="fb66c-155">Click **Exit**.</span></span>  
  
8.  <span data-ttu-id="fb66c-156">En el atributo `Guid`, elimine el GUID de ejemplo y pegue el GUID que ha copiado del cuadro de diálogo **Crear GUID**.</span><span class="sxs-lookup"><span data-stu-id="fb66c-156">In the `Guid` attribute, delete the sample GUID and paste in the GUID that you copied from the **Create GUID** dialog box.</span></span> <span data-ttu-id="fb66c-157">Quite las llaves ({}) del GUID copiado.</span><span class="sxs-lookup"><span data-stu-id="fb66c-157">Remove the braces ({}) from the copied GUID.</span></span>  
  
9. <span data-ttu-id="fb66c-158">En el menú **Proyecto**, haga clic en **Mostrar todos los archivos**.</span><span class="sxs-lookup"><span data-stu-id="fb66c-158">On the **Project** menu, click **Show All Files**.</span></span>  
  
10. <span data-ttu-id="fb66c-159">En **el Explorador de soluciones**, expanda la **mi proyecto** carpeta.</span><span class="sxs-lookup"><span data-stu-id="fb66c-159">In **Solution Explorer**, expand the **My Project** folder.</span></span> <span data-ttu-id="fb66c-160">Haga doble clic en el AssemblyInfo.vb.</span><span class="sxs-lookup"><span data-stu-id="fb66c-160">Double-click the AssemblyInfo.vb.</span></span> <span data-ttu-id="fb66c-161">Agregue el atributo siguiente al archivo.</span><span class="sxs-lookup"><span data-stu-id="fb66c-161">Add the following attribute to the file.</span></span>  
  
    ```vb  
    <Assembly: ImportedFromTypeLib("")>  
    ```  
  
     <span data-ttu-id="fb66c-162">Guarde el archivo.</span><span class="sxs-lookup"><span data-stu-id="fb66c-162">Save the file.</span></span>  
  
11. <span data-ttu-id="fb66c-163">Guarde el proyecto.</span><span class="sxs-lookup"><span data-stu-id="fb66c-163">Save the project.</span></span>  
  
12. <span data-ttu-id="fb66c-164">Haga clic con el botón derecho en el proyecto TypeEquivalenceInterface y haga clic en **Compilar**.</span><span class="sxs-lookup"><span data-stu-id="fb66c-164">Right-click the TypeEquivalenceInterface project and click **Build**.</span></span> <span data-ttu-id="fb66c-165">El archivo .dll de biblioteca de clases se compila y se guarda en la ruta de acceso de salida de la compilación especificada (por ejemplo, C:\TypeEquivalenceSample).</span><span class="sxs-lookup"><span data-stu-id="fb66c-165">The class library .dll file is compiled and saved to the specified build output path (for example, C:\TypeEquivalenceSample).</span></span>  
  
## <a name="creating-a-runtime-class"></a><span data-ttu-id="fb66c-166">Creación de una clase en tiempo de ejecución</span><span class="sxs-lookup"><span data-stu-id="fb66c-166">Creating a Runtime Class</span></span>  
  
#### <a name="to-create-the-type-equivalence-runtime-project"></a><span data-ttu-id="fb66c-167">Para crear el proyecto en tiempo de ejecución de equivalencia de tipos</span><span class="sxs-lookup"><span data-stu-id="fb66c-167">To create the type equivalence runtime project</span></span>  
  
1.  <span data-ttu-id="fb66c-168">En el menú **Archivo** de Visual Studio, apunte a **Nuevo** y haga clic en **Proyecto**.</span><span class="sxs-lookup"><span data-stu-id="fb66c-168">In Visual Studio, on the **File** menu, point to **New** and then click **Project**.</span></span>  
  
2.  <span data-ttu-id="fb66c-169">En el panel **Tipos de proyecto** del cuadro de diálogo **Nuevo proyecto**, asegúrese de que esté seleccionado **Windows**.</span><span class="sxs-lookup"><span data-stu-id="fb66c-169">In the **New Project** dialog box, in the **Project Types** pane, make sure that **Windows** is selected.</span></span> <span data-ttu-id="fb66c-170">Seleccione **Biblioteca de clases** en el panel **Plantillas**.</span><span class="sxs-lookup"><span data-stu-id="fb66c-170">Select **Class Library** in the **Templates** pane.</span></span> <span data-ttu-id="fb66c-171">En el cuadro **Nombre**, escriba `TypeEquivalenceRuntime` y haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="fb66c-171">In the **Name** box, type `TypeEquivalenceRuntime`, and then click **OK**.</span></span> <span data-ttu-id="fb66c-172">Se crea el proyecto.</span><span class="sxs-lookup"><span data-stu-id="fb66c-172">The new project is created.</span></span>  
  
3.  <span data-ttu-id="fb66c-173">En **el Explorador de soluciones**, haga clic en el archivo Class1.vb y haga clic en **cambiar el nombre de**.</span><span class="sxs-lookup"><span data-stu-id="fb66c-173">In **Solution Explorer**, right-click the Class1.vb file and click **Rename**.</span></span> <span data-ttu-id="fb66c-174">Cambie el nombre del archivo a `SampleClass.vb` y pulse ENTRAR.</span><span class="sxs-lookup"><span data-stu-id="fb66c-174">Rename the file to `SampleClass.vb` and press ENTER.</span></span> <span data-ttu-id="fb66c-175">Al cambiar el nombre del archivo también se cambiará el nombre de la clase a `SampleClass`.</span><span class="sxs-lookup"><span data-stu-id="fb66c-175">Renaming the file also renames the class to `SampleClass`.</span></span> <span data-ttu-id="fb66c-176">Esta clase implementará la interfaz `ISampleInterface`.</span><span class="sxs-lookup"><span data-stu-id="fb66c-176">This class will implement the `ISampleInterface` interface.</span></span>  
  
4.  <span data-ttu-id="fb66c-177">Haga clic con el botón derecho en el proyecto TypeEquivalenceRuntime y haga clic en **Propiedades**.</span><span class="sxs-lookup"><span data-stu-id="fb66c-177">Right-click the TypeEquivalenceRuntime project and click **Properties**.</span></span> <span data-ttu-id="fb66c-178">Haga clic en la pestaña **Compilar**. Establezca la ruta de acceso de salida en la misma ubicación que se usa en el proyecto TypeEquivalenceInterface, por ejemplo, `C:\TypeEquivalenceSample`.</span><span class="sxs-lookup"><span data-stu-id="fb66c-178">Click the **Compile** tab. Set the output path to the same location you used in the TypeEquivalenceInterface project, for example, `C:\TypeEquivalenceSample`.</span></span>  
  
5.  <span data-ttu-id="fb66c-179">Mientras sigue editando las propiedades del proyecto, haga clic en la pestaña **Firma**. Seleccione la opción **Firmar el ensamblado**.</span><span class="sxs-lookup"><span data-stu-id="fb66c-179">While still editing the project properties, click the **Signing** tab. Select the **Sign the assembly** option.</span></span> <span data-ttu-id="fb66c-180">En la lista **Elija un archivo de clave de nombre seguro**, haga clic en **<Nuevo...>**.</span><span class="sxs-lookup"><span data-stu-id="fb66c-180">In the **Choose a strong name key file** list, click **<New...>**.</span></span> <span data-ttu-id="fb66c-181">En el cuadro **Nombre del archivo de clave**, escriba `key.snk`.</span><span class="sxs-lookup"><span data-stu-id="fb66c-181">In the **Key file name** box, type `key.snk`.</span></span> <span data-ttu-id="fb66c-182">Desactive la casilla **Proteger mi archivo de clave mediante contraseña**.</span><span class="sxs-lookup"><span data-stu-id="fb66c-182">Clear the **Protect my key file with a password** check box.</span></span> <span data-ttu-id="fb66c-183">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="fb66c-183">Click **OK**.</span></span>  
  
6.  <span data-ttu-id="fb66c-184">Haga clic con el botón derecho en el proyecto TypeEquivalenceRuntime y haga clic en **Agregar referencia**.</span><span class="sxs-lookup"><span data-stu-id="fb66c-184">Right-click the TypeEquivalenceRuntime project and click **Add Reference**.</span></span> <span data-ttu-id="fb66c-185">Haga clic en la pestaña **Examinar** y vaya a la carpeta de la ruta de acceso de salida.</span><span class="sxs-lookup"><span data-stu-id="fb66c-185">Click the **Browse** tab and browse to the output path folder.</span></span> <span data-ttu-id="fb66c-186">Seleccione el archivo TypeEquivalenceInterface.dll y haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="fb66c-186">Select the TypeEquivalenceInterface.dll file and click **OK**.</span></span>  
  
7.  <span data-ttu-id="fb66c-187">En el menú **Proyecto**, haga clic en **Mostrar todos los archivos**.</span><span class="sxs-lookup"><span data-stu-id="fb66c-187">On the **Project** menu, click **Show All Files**.</span></span>  
  
8.  <span data-ttu-id="fb66c-188">En el **Explorador de soluciones**, expanda la carpeta **Referencias**.</span><span class="sxs-lookup"><span data-stu-id="fb66c-188">In **Solution Explorer**, expand the **References** folder.</span></span> <span data-ttu-id="fb66c-189">Seleccione la referencia TypeEquivalenceInterface.</span><span class="sxs-lookup"><span data-stu-id="fb66c-189">Select the TypeEquivalenceInterface reference.</span></span> <span data-ttu-id="fb66c-190">En la ventana Propiedades de la referencia TypeEquivalenceInterface, establezca la propiedad **Versión específica** en **False**.</span><span class="sxs-lookup"><span data-stu-id="fb66c-190">In the Properties window for the TypeEquivalenceInterface reference, set the **Specific Version** property to **False**.</span></span>  
  
9. <span data-ttu-id="fb66c-191">Agregue el código siguiente al archivo de clase SampleClass para crear la clase SampleClass.</span><span class="sxs-lookup"><span data-stu-id="fb66c-191">Add the following code to the SampleClass class file to create the SampleClass class.</span></span>  
  
    ```vb  
    Imports TypeEquivalenceInterface  
  
    Public Class SampleClass  
        Implements ISampleInterface  
  
        Private p_UserInput As String  
        Public ReadOnly Property UserInput() As String Implements ISampleInterface.UserInput  
            Get  
                Return p_UserInput  
            End Get  
        End Property  
  
        Public Sub GetUserInput() Implements ISampleInterface.GetUserInput  
            Console.WriteLine("Please enter a value:")  
            p_UserInput = Console.ReadLine()  
        End Sub  
    End Class  
    ```  
  
10. <span data-ttu-id="fb66c-192">Guarde el proyecto.</span><span class="sxs-lookup"><span data-stu-id="fb66c-192">Save the project.</span></span>  
  
11. <span data-ttu-id="fb66c-193">Haga clic con el botón derecho en el proyecto TypeEquivalenceRuntime y haga clic en **Compilar**.</span><span class="sxs-lookup"><span data-stu-id="fb66c-193">Right-click the TypeEquivalenceRuntime project and click **Build**.</span></span> <span data-ttu-id="fb66c-194">El archivo .dll de biblioteca de clases se compila y se guarda en la ruta de acceso de salida de la compilación especificada (por ejemplo, C:\TypeEquivalenceSample).</span><span class="sxs-lookup"><span data-stu-id="fb66c-194">The class library .dll file is compiled and saved to the specified build output path (for example, C:\TypeEquivalenceSample).</span></span>  
  
## <a name="creating-a-client-project"></a><span data-ttu-id="fb66c-195">Creación de un proyecto de cliente</span><span class="sxs-lookup"><span data-stu-id="fb66c-195">Creating a Client Project</span></span>  
  
#### <a name="to-create-the-type-equivalence-client-project"></a><span data-ttu-id="fb66c-196">Para crear el proyecto de cliente de equivalencia de tipos</span><span class="sxs-lookup"><span data-stu-id="fb66c-196">To create the type equivalence client project</span></span>  
  
1.  <span data-ttu-id="fb66c-197">En el menú **Archivo** de Visual Studio, apunte a **Nuevo** y haga clic en **Proyecto**.</span><span class="sxs-lookup"><span data-stu-id="fb66c-197">In Visual Studio, on the **File** menu, point to **New** and then click **Project**.</span></span>  
  
2.  <span data-ttu-id="fb66c-198">En el panel **Tipos de proyecto** del cuadro de diálogo **Nuevo proyecto**, asegúrese de que esté seleccionado **Windows**.</span><span class="sxs-lookup"><span data-stu-id="fb66c-198">In the **New Project** dialog box, in the **Project Types** pane, make sure that **Windows** is selected.</span></span> <span data-ttu-id="fb66c-199">Seleccione **Aplicación de consola** en el panel **Plantillas**.</span><span class="sxs-lookup"><span data-stu-id="fb66c-199">Select **Console Application** in the **Templates** pane.</span></span> <span data-ttu-id="fb66c-200">En el cuadro **Nombre**, escriba `TypeEquivalenceClient` y haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="fb66c-200">In the **Name** box, type `TypeEquivalenceClient`, and then click **OK**.</span></span> <span data-ttu-id="fb66c-201">Se crea el proyecto.</span><span class="sxs-lookup"><span data-stu-id="fb66c-201">The new project is created.</span></span>  
  
3.  <span data-ttu-id="fb66c-202">Haga clic con el botón derecho en el proyecto TypeEquivalenceClient y haga clic en **Propiedades**.</span><span class="sxs-lookup"><span data-stu-id="fb66c-202">Right-click the TypeEquivalenceClient project and click **Properties**.</span></span> <span data-ttu-id="fb66c-203">Haga clic en la pestaña **Compilar**. Establezca la ruta de acceso de salida en la misma ubicación que se usa en el proyecto TypeEquivalenceInterface, por ejemplo, `C:\TypeEquivalenceSample`.</span><span class="sxs-lookup"><span data-stu-id="fb66c-203">Click the **Compile** tab. Set the output path to the same location you used in the TypeEquivalenceInterface project, for example, `C:\TypeEquivalenceSample`.</span></span>  
  
4.  <span data-ttu-id="fb66c-204">Haga clic con el botón derecho en el proyecto TypeEquivalenceClient y haga clic en **Agregar referencia**.</span><span class="sxs-lookup"><span data-stu-id="fb66c-204">Right-click the TypeEquivalenceClient project and click **Add Reference**.</span></span> <span data-ttu-id="fb66c-205">Haga clic en la pestaña **Examinar** y vaya a la carpeta de la ruta de acceso de salida.</span><span class="sxs-lookup"><span data-stu-id="fb66c-205">Click the **Browse** tab and browse to the output path folder.</span></span> <span data-ttu-id="fb66c-206">Seleccione el archivo TypeEquivalenceInterface.dll file (no el TypeEquivalenceRuntime.dll) y haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="fb66c-206">Select the TypeEquivalenceInterface.dll file (not the TypeEquivalenceRuntime.dll) and click **OK**.</span></span>  
  
5.  <span data-ttu-id="fb66c-207">En el menú **Proyecto**, haga clic en **Mostrar todos los archivos**.</span><span class="sxs-lookup"><span data-stu-id="fb66c-207">On the **Project** menu, click **Show All Files**.</span></span>  
  
6.  <span data-ttu-id="fb66c-208">En el **Explorador de soluciones**, expanda la carpeta **Referencias**.</span><span class="sxs-lookup"><span data-stu-id="fb66c-208">In **Solution Explorer**, expand the **References** folder.</span></span> <span data-ttu-id="fb66c-209">Seleccione la referencia TypeEquivalenceInterface.</span><span class="sxs-lookup"><span data-stu-id="fb66c-209">Select the TypeEquivalenceInterface reference.</span></span> <span data-ttu-id="fb66c-210">En la ventana Propiedades de la referencia TypeEquivalenceInterface, establezca la propiedad **Incrustar tipos de interoperabilidad** en **True**.</span><span class="sxs-lookup"><span data-stu-id="fb66c-210">In the Properties window for the TypeEquivalenceInterface reference, set the **Embed Interop Types** property to **True**.</span></span>  
  
7.  <span data-ttu-id="fb66c-211">Agregue el código siguiente al archivo Module1.vb para crear el programa cliente.</span><span class="sxs-lookup"><span data-stu-id="fb66c-211">Add the following code to the Module1.vb file to create the client program.</span></span>  
  
    ```vb  
    Imports TypeEquivalenceInterface  
    Imports System.Reflection  
  
    Module Module1  
  
        Sub Main()  
            Dim sampleAssembly = Assembly.Load("TypeEquivalenceRuntime")  
            Dim sampleClass As ISampleInterface = CType( _  
                sampleAssembly.CreateInstance("TypeEquivalenceRuntime.SampleClass"), ISampleInterface)  
            sampleClass.GetUserInput()  
            Console.WriteLine(sampleClass.UserInput)  
            Console.WriteLine(sampleAssembly.GetName().Version)  
            Console.ReadLine()  
        End Sub  
  
    End Module  
    ```  
  
8.  <span data-ttu-id="fb66c-212">Pulse CTRL+F5 para compilar y ejecutar el programa.</span><span class="sxs-lookup"><span data-stu-id="fb66c-212">Press CTRL+F5 to build and run the program.</span></span>  
  
## <a name="modifying-the-interface"></a><span data-ttu-id="fb66c-213">Modificación de la interfaz</span><span class="sxs-lookup"><span data-stu-id="fb66c-213">Modifying the Interface</span></span>  
  
#### <a name="to-modify-the-interface"></a><span data-ttu-id="fb66c-214">Para modificar la interfaz</span><span class="sxs-lookup"><span data-stu-id="fb66c-214">To modify the interface</span></span>  
  
1.  <span data-ttu-id="fb66c-215">En el menú **Archivo** de Visual Studio, apunte a **Abrir** y haga clic en **Proyecto o solución**.</span><span class="sxs-lookup"><span data-stu-id="fb66c-215">In Visual Studio, on the **File** menu, point to **Open**, and then click **Project/Solution**.</span></span>  
  
2.  <span data-ttu-id="fb66c-216">En el cuadro de diálogo **Abrir proyecto**, haga clic con el botón derecho en el proyecto TypeEquivalenceInterface y haga clic en **Propiedades**.</span><span class="sxs-lookup"><span data-stu-id="fb66c-216">In the **Open Project** dialog box, right-click the TypeEquivalenceInterface project, and then click **Properties**.</span></span> <span data-ttu-id="fb66c-217">Haga clic en la pestaña **Aplicación** . Haga clic en el botón **Información de ensamblado**.</span><span class="sxs-lookup"><span data-stu-id="fb66c-217">Click the **Application** tab. Click the **Assembly Information** button.</span></span> <span data-ttu-id="fb66c-218">Cambie los valores de **Versión de ensamblado** y **Versión de archivo** a `2.0.0.0`.</span><span class="sxs-lookup"><span data-stu-id="fb66c-218">Change the **Assembly Version** and **File Version** values to `2.0.0.0`.</span></span>  
  
3.  <span data-ttu-id="fb66c-219">Abra el archivo ISampleInterface.vb.</span><span class="sxs-lookup"><span data-stu-id="fb66c-219">Open the ISampleInterface.vb file.</span></span> <span data-ttu-id="fb66c-220">Agregue la línea de código siguiente a la interfaz ISampleInterface.</span><span class="sxs-lookup"><span data-stu-id="fb66c-220">Add the following line of code to the ISampleInterface interface.</span></span>  
  
    ```vb  
    Function GetDate() As Date  
    ```  
  
     <span data-ttu-id="fb66c-221">Guarde el archivo.</span><span class="sxs-lookup"><span data-stu-id="fb66c-221">Save the file.</span></span>  
  
4.  <span data-ttu-id="fb66c-222">Guarde el proyecto.</span><span class="sxs-lookup"><span data-stu-id="fb66c-222">Save the project.</span></span>  
  
5.  <span data-ttu-id="fb66c-223">Haga clic con el botón derecho en el proyecto TypeEquivalenceInterface y haga clic en **Compilar**.</span><span class="sxs-lookup"><span data-stu-id="fb66c-223">Right-click the TypeEquivalenceInterface project and click **Build**.</span></span> <span data-ttu-id="fb66c-224">Una nueva versión del archivo .dll de biblioteca de clases se compila y se guarda en la ruta de acceso de salida de la compilación especificada (por ejemplo, C:\TypeEquivalenceSample).</span><span class="sxs-lookup"><span data-stu-id="fb66c-224">A new version of the class library .dll file is compiled and saved in the specified build output path (for example, C:\TypeEquivalenceSample).</span></span>  
  
## <a name="modifying-the-runtime-class"></a><span data-ttu-id="fb66c-225">Modificación de la clase en tiempo de ejecución</span><span class="sxs-lookup"><span data-stu-id="fb66c-225">Modifying the Runtime Class</span></span>  
  
#### <a name="to-modify-the-runtime-class"></a><span data-ttu-id="fb66c-226">Para modificar la clase en tiempo de ejecución</span><span class="sxs-lookup"><span data-stu-id="fb66c-226">To modify the runtime class</span></span>  
  
1.  <span data-ttu-id="fb66c-227">En el menú **Archivo** de Visual Studio, apunte a **Abrir** y haga clic en **Proyecto o solución**.</span><span class="sxs-lookup"><span data-stu-id="fb66c-227">In Visual Studio, on the **File** menu, point to **Open**, and then click **Project/Solution**.</span></span>  
  
2.  <span data-ttu-id="fb66c-228">En el cuadro de diálogo **Abrir proyecto**, haga clic con el botón derecho en el proyecto TypeEquivalenceRuntime y haga clic en **Propiedades**.</span><span class="sxs-lookup"><span data-stu-id="fb66c-228">In the **Open Project** dialog box, right-click the TypeEquivalenceRuntime project and click **Properties**.</span></span> <span data-ttu-id="fb66c-229">Haga clic en la pestaña **Aplicación** . Haga clic en el botón **Información de ensamblado**.</span><span class="sxs-lookup"><span data-stu-id="fb66c-229">Click the **Application** tab. Click the **Assembly Information** button.</span></span> <span data-ttu-id="fb66c-230">Cambie los valores de **Versión de ensamblado** y **Versión de archivo** a `2.0.0.0`.</span><span class="sxs-lookup"><span data-stu-id="fb66c-230">Change the **Assembly Version** and **File Version** values to `2.0.0.0`.</span></span>  
  
3.  <span data-ttu-id="fb66c-231">Abra el SampleClass.vbfile.</span><span class="sxs-lookup"><span data-stu-id="fb66c-231">Open the SampleClass.vbfile.</span></span> <span data-ttu-id="fb66c-232">Agregue las líneas de código siguientes a la clase SampleClass.</span><span class="sxs-lookup"><span data-stu-id="fb66c-232">Add the following lines of code to the SampleClass class.</span></span>  
  
```vb  
Public Function GetDate() As DateTime Implements ISampleInterface.GetDate  
    Return Now  
End Function  
```  
  
     Save the file.  
  
4.  <span data-ttu-id="fb66c-233">Guarde el proyecto.</span><span class="sxs-lookup"><span data-stu-id="fb66c-233">Save the project.</span></span>  
  
5.  <span data-ttu-id="fb66c-234">Haga clic con el botón derecho en el proyecto TypeEquivalenceRuntime y haga clic en **Compilar**.</span><span class="sxs-lookup"><span data-stu-id="fb66c-234">Right-click the TypeEquivalenceRuntime project and click **Build**.</span></span> <span data-ttu-id="fb66c-235">Una versión actualizada del archivo .dll de biblioteca de clases se compila y se guarda en la ruta de acceso de salida de la compilación especificada anteriormente (por ejemplo, C:\TypeEquivalenceSample).</span><span class="sxs-lookup"><span data-stu-id="fb66c-235">An updated version of the class library .dll file is compiled and saved in the previously specified build output path (for example, C:\TypeEquivalenceSample).</span></span>  
  
6.  <span data-ttu-id="fb66c-236">En el Explorador de archivos, abra la carpeta de la ruta de acceso de salida (por ejemplo, C:\TypeEquivalenceSample).</span><span class="sxs-lookup"><span data-stu-id="fb66c-236">In File Explorer, open the output path folder (for example, C:\TypeEquivalenceSample).</span></span> <span data-ttu-id="fb66c-237">Haga doble clic en el archivo TypeEquivalenceClient.exe para ejecutar el programa.</span><span class="sxs-lookup"><span data-stu-id="fb66c-237">Double-click the TypeEquivalenceClient.exe to run the program.</span></span> <span data-ttu-id="fb66c-238">El programa reflejará la nueva versión del ensamblado TypeEquivalenceRuntime sin tener que volver a compilarse de nuevo.</span><span class="sxs-lookup"><span data-stu-id="fb66c-238">The program will reflect the new version of the TypeEquivalenceRuntime assembly without having been recompiled.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fb66c-239">Vea también</span><span class="sxs-lookup"><span data-stu-id="fb66c-239">See Also</span></span>  
 [<span data-ttu-id="fb66c-240">/link (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="fb66c-240">/link (Visual Basic)</span></span>](../../../../visual-basic/reference/command-line-compiler/link.md)  
 [<span data-ttu-id="fb66c-241">Conceptos de programación</span><span class="sxs-lookup"><span data-stu-id="fb66c-241">Programming Concepts</span></span>](../../../../visual-basic/programming-guide/concepts/index.md)  
 [<span data-ttu-id="fb66c-242">Programar con ensamblados</span><span class="sxs-lookup"><span data-stu-id="fb66c-242">Programming with Assemblies</span></span>](../../../../framework/app-domains/programming-with-assemblies.md)  
 [<span data-ttu-id="fb66c-243">Ensamblados y caché global de ensamblados (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="fb66c-243">Assemblies and the Global Assembly Cache (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/assemblies-gac/index.md)
