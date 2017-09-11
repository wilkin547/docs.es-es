---
title: 'Tutorial: Insertar tipos de ensamblados administrados en Visual Studio (C#)'
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
ms.assetid: 55ed13c9-c5bb-4bc2-bcd8-0587eb568864
caps.latest.revision: 3
author: BillWagner
ms.author: wiwagn
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 7b003e76229a06883adc22f933f08663330f0c9d
ms.contentlocale: es-es
ms.lasthandoff: 07/28/2017

---
# <a name="walkthrough-embedding-types-from-managed-assemblies-in-visual-studio-c"></a><span data-ttu-id="7ea6c-102">Tutorial: Insertar tipos de ensamblados administrados en Visual Studio (C#)</span><span class="sxs-lookup"><span data-stu-id="7ea6c-102">Walkthrough: Embedding Types from Managed Assemblies in Visual Studio (C#)</span></span>
<span data-ttu-id="7ea6c-103">Si inserta información de tipos de un ensamblado administrado con nombre seguro, puede acoplar tipos holgadamente en una aplicación para lograr independencia de versiones.</span><span class="sxs-lookup"><span data-stu-id="7ea6c-103">If you embed type information from a strong-named managed assembly, you can loosely couple types in an application to achieve version independence.</span></span> <span data-ttu-id="7ea6c-104">Es decir, el programa puede escribirse de modo que use tipos de varias versiones de una biblioteca administrada sin tener que volver a compilarse para cada versión.</span><span class="sxs-lookup"><span data-stu-id="7ea6c-104">That is, your program can be written to use types from multiple versions of a managed library without having to be recompiled for each version.</span></span>  
  
 <span data-ttu-id="7ea6c-105">La inserción de tipos se usa a menudo con interoperabilidad COM, como, por ejemplo, una aplicación que use objetos de automatización de Microsoft Office.</span><span class="sxs-lookup"><span data-stu-id="7ea6c-105">Type embedding is frequently used with COM interop, such as an application that uses automation objects from Microsoft Office.</span></span> <span data-ttu-id="7ea6c-106">La inserción de información de tipos permite que la misma versión de un programa funcione con distintas versiones de Microsoft Office en equipos diferentes.</span><span class="sxs-lookup"><span data-stu-id="7ea6c-106">Embedding type information enables the same build of a program to work with different versions of Microsoft Office on different computers.</span></span> <span data-ttu-id="7ea6c-107">Pero la inserción de tipos también se puede usar con una solución totalmente administrada.</span><span class="sxs-lookup"><span data-stu-id="7ea6c-107">However, you can also use type embedding with a fully managed solution.</span></span>  
  
 <span data-ttu-id="7ea6c-108">La información de tipos puede insertarse de un ensamblado que tenga las siguientes características:</span><span class="sxs-lookup"><span data-stu-id="7ea6c-108">Type information can be embedded from an assembly that has the following characteristics:</span></span>  
  
-   <span data-ttu-id="7ea6c-109">El ensamblado expone al menos una interfaz pública.</span><span class="sxs-lookup"><span data-stu-id="7ea6c-109">The assembly exposes at least one public interface.</span></span>  
  
-   <span data-ttu-id="7ea6c-110">Las interfaces insertadas se anotan con un atributo `ComImport` y un atributo `Guid` (y un GUID único).</span><span class="sxs-lookup"><span data-stu-id="7ea6c-110">The embedded interfaces are annotated with a `ComImport` attribute and a `Guid` attribute (and a unique GUID).</span></span>  
  
-   <span data-ttu-id="7ea6c-111">El ensamblado se anota con los atributos `ImportedFromTypeLib` o `PrimaryInteropAssembly` y un atributo `Guid` de nivel de ensamblado.</span><span class="sxs-lookup"><span data-stu-id="7ea6c-111">The assembly is annotated with the `ImportedFromTypeLib` attribute or the `PrimaryInteropAssembly` attribute, and an assembly-level `Guid` attribute.</span></span> <span data-ttu-id="7ea6c-112">(De forma predeterminada, las plantillas de proyecto de Visual C# incluyen un atributo `Guid` de nivel de ensamblado).</span><span class="sxs-lookup"><span data-stu-id="7ea6c-112">(By default, Visual C# project templates include an assembly-level `Guid` attribute.)</span></span>  
  
 <span data-ttu-id="7ea6c-113">Después de especificar las interfaces públicas que se pueden insertar, puede crear clases en tiempo de ejecución que implementen esas interfaces.</span><span class="sxs-lookup"><span data-stu-id="7ea6c-113">After you have specified the public interfaces that can be embedded, you can create runtime classes that implement those interfaces.</span></span> <span data-ttu-id="7ea6c-114">Un programa cliente puede luego incrustar la información de tipo de dichas interfaces en tiempo de diseño haciendo referencia al ensamblado que contiene la configuración y las interfaces públicas de la propiedad `Embed Interop Types` de la referencia a `True`.</span><span class="sxs-lookup"><span data-stu-id="7ea6c-114">A client program can then embed the type information for those interfaces at design time by referencing the assembly that contains the public interfaces and setting the `Embed Interop Types` property of the reference to `True`.</span></span> <span data-ttu-id="7ea6c-115">Esto equivale a usar el compilador de línea de comandos y hacer referencia al ensamblado mediante la opción `/link` del compilador.</span><span class="sxs-lookup"><span data-stu-id="7ea6c-115">This is equivalent to using the command line compiler and referencing the assembly by using the `/link` compiler option.</span></span> <span data-ttu-id="7ea6c-116">El programa cliente puede luego cargar instancias de los objetos en tiempo de ejecución escritos como esas interfaces.</span><span class="sxs-lookup"><span data-stu-id="7ea6c-116">The client program can then load instances of your runtime objects typed as those interfaces.</span></span> <span data-ttu-id="7ea6c-117">Si crea otra versión del ensamblado en tiempo de ejecución con nombre seguro, el programa cliente no tiene que volver a compilarse con el ensamblado en tiempo de ejecución actualizado.</span><span class="sxs-lookup"><span data-stu-id="7ea6c-117">If you create a new version of your strong-named runtime assembly, the client program does not have to be recompiled with the updated runtime assembly.</span></span> <span data-ttu-id="7ea6c-118">En su lugar, el programa cliente sigue usando cualquier versión del ensamblado en tiempo de ejecución que encuentre disponible y usa la información de tipo insertada para las interfaces públicas.</span><span class="sxs-lookup"><span data-stu-id="7ea6c-118">Instead, the client program continues to use whichever version of the runtime assembly is available to it, using the embedded type information for the public interfaces.</span></span>  
  
 <span data-ttu-id="7ea6c-119">Dado que la función principal de la inserción de tipos es admitir la inserción de información de tipos de ensamblados de interoperabilidad COM, cuando se inserta información de tipos en una solución totalmente administrada se aplican las siguientes limitaciones:</span><span class="sxs-lookup"><span data-stu-id="7ea6c-119">Because the primary function of type embedding is to support embedding of type information from COM interop assemblies, the following limitations apply when you embed type information in a fully managed solution:</span></span>  
  
-   <span data-ttu-id="7ea6c-120">Solo se insertan los atributos específicos de interoperabilidad COM; se omiten otros atributos.</span><span class="sxs-lookup"><span data-stu-id="7ea6c-120">Only attributes specific to COM interop are embedded; other attributes are ignored.</span></span>  
  
-   <span data-ttu-id="7ea6c-121">Si un tipo usa parámetros genéricos y el tipo del parámetro genérico es un tipo insertado, ese tipo no se puede usar más allá de un límite de ensamblado.</span><span class="sxs-lookup"><span data-stu-id="7ea6c-121">If a type uses generic parameters and the type of the generic parameter is an embedded type, that type cannot be used across an assembly boundary.</span></span> <span data-ttu-id="7ea6c-122">Entre los ejemplos de cruce de un límite de ensamblado se incluyen llamar a un método desde otro ensamblado o derivar un tipo de un tipo definido en otro ensamblado.</span><span class="sxs-lookup"><span data-stu-id="7ea6c-122">Examples of crossing an assembly boundary include calling a method from another assembly or a deriving a type from a type defined in another assembly.</span></span>  
  
-   <span data-ttu-id="7ea6c-123">Las constantes no se insertan.</span><span class="sxs-lookup"><span data-stu-id="7ea6c-123">Constants are not embedded.</span></span>  
  
-   <span data-ttu-id="7ea6c-124">La clase <xref:System.Collections.Generic.Dictionary%602?displayProperty=fullName> no admite un tipo insertado como clave.</span><span class="sxs-lookup"><span data-stu-id="7ea6c-124">The <xref:System.Collections.Generic.Dictionary%602?displayProperty=fullName> class does not support an embedded type as a key.</span></span> <span data-ttu-id="7ea6c-125">Puede implementar su propio tipo de diccionario que admita un tipo insertado como clave.</span><span class="sxs-lookup"><span data-stu-id="7ea6c-125">You can implement your own dictionary type to support an embedded type as a key.</span></span>  
  
 <span data-ttu-id="7ea6c-126">En este tutorial, se realizarán las siguientes tareas:</span><span class="sxs-lookup"><span data-stu-id="7ea6c-126">In this walkthrough, you will do the following:</span></span>  
  
-   <span data-ttu-id="7ea6c-127">Crear un ensamblado con nombre seguro que tenga una interfaz pública e incluya información de tipo que se puede insertar.</span><span class="sxs-lookup"><span data-stu-id="7ea6c-127">Create a strong-named assembly that has a public interface that contains type information that can be embedded.</span></span>  
  
-   <span data-ttu-id="7ea6c-128">Crear un ensamblado en tiempo de ejecución con nombre seguro que implemente esa interfaz pública.</span><span class="sxs-lookup"><span data-stu-id="7ea6c-128">Create a strong-named runtime assembly that implements that public interface.</span></span>  
  
-   <span data-ttu-id="7ea6c-129">Crear un programa cliente que inserte la información de tipo de la interfaz pública y cree una instancia de la clase del ensamblado en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="7ea6c-129">Create a client program that embeds the type information from the public interface and creates an instance of the class from the runtime assembly.</span></span>  
  
-   <span data-ttu-id="7ea6c-130">Modificar y recompilar el ensamblado en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="7ea6c-130">Modify and rebuild the runtime assembly.</span></span>  
  
-   <span data-ttu-id="7ea6c-131">Ejecute el programa cliente para ver que se usa la nueva versión del ensamblado en tiempo de ejecución sin tener que recompilar el programa cliente.</span><span class="sxs-lookup"><span data-stu-id="7ea6c-131">Run the client program to see that the new version of the runtime assembly is being used without having to recompile the client program.</span></span>  
  
[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]  
  
## <a name="creating-an-interface"></a><span data-ttu-id="7ea6c-132">Creación de una interfaz</span><span class="sxs-lookup"><span data-stu-id="7ea6c-132">Creating an Interface</span></span>  
  
#### <a name="to-create-the-type-equivalence-interface-project"></a><span data-ttu-id="7ea6c-133">Para crear el proyecto de interfaz de equivalencia de tipos</span><span class="sxs-lookup"><span data-stu-id="7ea6c-133">To create the type equivalence interface project</span></span>  
  
1.  <span data-ttu-id="7ea6c-134">En el menú **Archivo** de Visual Studio, elija **Nuevo** y haga clic en **Proyecto**.</span><span class="sxs-lookup"><span data-stu-id="7ea6c-134">In Visual Studio, on the **File** menu, choose **New** and then click **Project**.</span></span>  
  
2.  <span data-ttu-id="7ea6c-135">En el panel **Tipos de proyecto** del cuadro de diálogo **Nuevo proyecto**, asegúrese de que esté seleccionado **Windows**.</span><span class="sxs-lookup"><span data-stu-id="7ea6c-135">In the **New Project** dialog box, in the **Project Types** pane, make sure that **Windows** is selected.</span></span> <span data-ttu-id="7ea6c-136">Seleccione **Biblioteca de clases** en el panel **Plantillas**.</span><span class="sxs-lookup"><span data-stu-id="7ea6c-136">Select **Class Library** in the **Templates** pane.</span></span> <span data-ttu-id="7ea6c-137">En el cuadro **Nombre**, escriba `TypeEquivalenceInterface` y haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="7ea6c-137">In the **Name** box, type `TypeEquivalenceInterface`, and then click **OK**.</span></span> <span data-ttu-id="7ea6c-138">Se crea el proyecto.</span><span class="sxs-lookup"><span data-stu-id="7ea6c-138">The new project is created.</span></span>  
  
3.  <span data-ttu-id="7ea6c-139">En el **Explorador de soluciones**, haga clic con el botón derecho en el archivo Class1.cs y haga clic en **Cambiar nombre**.</span><span class="sxs-lookup"><span data-stu-id="7ea6c-139">In **Solution Explorer**, right-click the Class1.cs file and click **Rename**.</span></span> <span data-ttu-id="7ea6c-140">Cambie el nombre del archivo a `ISampleInterface.cs` y pulse ENTRAR.</span><span class="sxs-lookup"><span data-stu-id="7ea6c-140">Rename the file to `ISampleInterface.cs` and press ENTER.</span></span> <span data-ttu-id="7ea6c-141">Al cambiar el nombre del archivo también se cambiará el nombre de la clase a `ISampleInterface`.</span><span class="sxs-lookup"><span data-stu-id="7ea6c-141">Renaming the file will also rename the class to `ISampleInterface`.</span></span> <span data-ttu-id="7ea6c-142">Esta clase representará la interfaz pública de la clase.</span><span class="sxs-lookup"><span data-stu-id="7ea6c-142">This class will represent the public interface for the class.</span></span>  
  
4.  <span data-ttu-id="7ea6c-143">Haga clic con el botón derecho en el proyecto TypeEquivalenceInterface y haga clic en **Propiedades**.</span><span class="sxs-lookup"><span data-stu-id="7ea6c-143">Right-click the TypeEquivalenceInterface project and click **Properties**.</span></span> <span data-ttu-id="7ea6c-144">Haga clic en la pestaña **Compilar**.</span><span class="sxs-lookup"><span data-stu-id="7ea6c-144">Click the the **Build** tab.</span></span> <span data-ttu-id="7ea6c-145">Establezca la ruta de acceso de salida en una ubicación válida en el equipo de desarrollo, como `C:\TypeEquivalenceSample`.</span><span class="sxs-lookup"><span data-stu-id="7ea6c-145">Set the output path to a valid location on your development computer, such as `C:\TypeEquivalenceSample`.</span></span> <span data-ttu-id="7ea6c-146">Esta ubicación también se usará en un paso posterior en este tutorial.</span><span class="sxs-lookup"><span data-stu-id="7ea6c-146">This location will also be used in a later step in this walkthrough.</span></span>  
  
5.  <span data-ttu-id="7ea6c-147">Mientras sigue editando las propiedades del proyecto, haga clic en la pestaña **Firma**.</span><span class="sxs-lookup"><span data-stu-id="7ea6c-147">While still editing the project properties, click the **Signing** tab.</span></span> <span data-ttu-id="7ea6c-148">Seleccione la opción **Firmar el ensamblado**.</span><span class="sxs-lookup"><span data-stu-id="7ea6c-148">Select the **Sign the assembly** option.</span></span> <span data-ttu-id="7ea6c-149">En la lista **Elija un archivo de clave de nombre seguro**, haga clic en **<Nuevo...>**.</span><span class="sxs-lookup"><span data-stu-id="7ea6c-149">In the **Choose a strong name key file** list, click **<New...>**.</span></span> <span data-ttu-id="7ea6c-150">En el cuadro **Nombre del archivo de clave**, escriba `key.snk`.</span><span class="sxs-lookup"><span data-stu-id="7ea6c-150">In the **Key file name** box, type `key.snk`.</span></span> <span data-ttu-id="7ea6c-151">Desactive la casilla **Proteger mi archivo de clave mediante contraseña**.</span><span class="sxs-lookup"><span data-stu-id="7ea6c-151">Clear the **Protect my key file with a password** check box.</span></span> <span data-ttu-id="7ea6c-152">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="7ea6c-152">Click **OK**.</span></span>  
  
6.  <span data-ttu-id="7ea6c-153">Abra el archivo ISampleInterface.cs.</span><span class="sxs-lookup"><span data-stu-id="7ea6c-153">Open the ISampleInterface.cs file.</span></span> <span data-ttu-id="7ea6c-154">Agregue el código siguiente al archivo de clase ISampleInterface para crear la interfaz ISampleInterface.</span><span class="sxs-lookup"><span data-stu-id="7ea6c-154">Add the following code to the ISampleInterface class file to create the ISampleInterface interface.</span></span>  
  
    ```csharp  
    using System;  
    using System.Runtime.InteropServices;  
  
    namespace TypeEquivalenceInterface  
    {  
        [ComImport]  
        [Guid("8DA56996-A151-4136-B474-32784559F6DF")]  
        public interface ISampleInterface  
        {  
            void GetUserInput();  
            string UserInput { get; }  
        }  
    }  
    ```  
  
7.  <span data-ttu-id="7ea6c-155">En el menú **Herramientas**, haga clic en **Crear GUID**.</span><span class="sxs-lookup"><span data-stu-id="7ea6c-155">On the **Tools** menu, click **Create Guid**.</span></span> <span data-ttu-id="7ea6c-156">En el cuadro de diálogo **Crear GUID**, haga clic en **Formato de Registro** y luego en **Copiar**.</span><span class="sxs-lookup"><span data-stu-id="7ea6c-156">In the **Create GUID** dialog box, click **Registry Format** and then click **Copy**.</span></span> <span data-ttu-id="7ea6c-157">Haga clic en **Salir**.</span><span class="sxs-lookup"><span data-stu-id="7ea6c-157">Click **Exit**.</span></span>  
  
8.  <span data-ttu-id="7ea6c-158">En el atributo `Guid`, elimine el GUID de ejemplo y pegue el GUID que ha copiado del cuadro de diálogo **Crear GUID**.</span><span class="sxs-lookup"><span data-stu-id="7ea6c-158">In the `Guid` attribute, delete the sample GUID and paste in the GUID that you copied from the **Create GUID** dialog box.</span></span> <span data-ttu-id="7ea6c-159">Quite las llaves ({}) del GUID copiado.</span><span class="sxs-lookup"><span data-stu-id="7ea6c-159">Remove the braces ({}) from the copied GUID.</span></span>  
  
9. <span data-ttu-id="7ea6c-160">En el **Explorador de soluciones**, expanda la carpeta **Propiedades**.</span><span class="sxs-lookup"><span data-stu-id="7ea6c-160">In **Solution Explorer**, expand the **Properties** folder.</span></span> <span data-ttu-id="7ea6c-161">Haga doble clic en el archivo AssemblyInfo.cs.</span><span class="sxs-lookup"><span data-stu-id="7ea6c-161">Double-click the AssemblyInfo.cs file.</span></span> <span data-ttu-id="7ea6c-162">Agregue el atributo siguiente al archivo.</span><span class="sxs-lookup"><span data-stu-id="7ea6c-162">Add the following attribute to the file.</span></span>  
  
    ```csharp  
    [assembly: ImportedFromTypeLib("")]  
    ```  
  
     <span data-ttu-id="7ea6c-163">Guarde el archivo.</span><span class="sxs-lookup"><span data-stu-id="7ea6c-163">Save the file.</span></span>  
  
10. <span data-ttu-id="7ea6c-164">Guarde el proyecto.</span><span class="sxs-lookup"><span data-stu-id="7ea6c-164">Save the project.</span></span>  
  
11. <span data-ttu-id="7ea6c-165">Haga clic con el botón derecho en el proyecto TypeEquivalenceInterface y haga clic en **Compilar**.</span><span class="sxs-lookup"><span data-stu-id="7ea6c-165">Right-click the TypeEquivalenceInterface project and click **Build**.</span></span> <span data-ttu-id="7ea6c-166">El archivo .dll de biblioteca de clases se compila y se guarda en la ruta de acceso de salida de la compilación especificada (por ejemplo, C:\TypeEquivalenceSample).</span><span class="sxs-lookup"><span data-stu-id="7ea6c-166">The class library .dll file is compiled and saved to the specified build output path (for example, C:\TypeEquivalenceSample).</span></span>  
  
## <a name="creating-a-runtime-class"></a><span data-ttu-id="7ea6c-167">Creación de una clase en tiempo de ejecución</span><span class="sxs-lookup"><span data-stu-id="7ea6c-167">Creating a Runtime Class</span></span>  
  
#### <a name="to-create-the-type-equivalence-runtime-project"></a><span data-ttu-id="7ea6c-168">Para crear el proyecto en tiempo de ejecución de equivalencia de tipos</span><span class="sxs-lookup"><span data-stu-id="7ea6c-168">To create the type equivalence runtime project</span></span>  
  
1.  <span data-ttu-id="7ea6c-169">En el menú **Archivo** de Visual Studio, apunte a **Nuevo** y haga clic en **Proyecto**.</span><span class="sxs-lookup"><span data-stu-id="7ea6c-169">In Visual Studio, on the **File** menu, point to **New** and then click **Project**.</span></span>  
  
2.  <span data-ttu-id="7ea6c-170">En el panel **Tipos de proyecto** del cuadro de diálogo **Nuevo proyecto**, asegúrese de que esté seleccionado **Windows**.</span><span class="sxs-lookup"><span data-stu-id="7ea6c-170">In the **New Project** dialog box, in the **Project Types** pane, make sure that **Windows** is selected.</span></span> <span data-ttu-id="7ea6c-171">Seleccione **Biblioteca de clases** en el panel **Plantillas**.</span><span class="sxs-lookup"><span data-stu-id="7ea6c-171">Select **Class Library** in the **Templates** pane.</span></span> <span data-ttu-id="7ea6c-172">En el cuadro **Nombre**, escriba `TypeEquivalenceRuntime` y haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="7ea6c-172">In the **Name** box, type `TypeEquivalenceRuntime`, and then click **OK**.</span></span> <span data-ttu-id="7ea6c-173">Se crea el proyecto.</span><span class="sxs-lookup"><span data-stu-id="7ea6c-173">The new project is created.</span></span>  
  
3.  <span data-ttu-id="7ea6c-174">En el **Explorador de soluciones**, haga clic con el botón derecho en el archivo Class1.cs y haga clic en **Cambiar nombre**.</span><span class="sxs-lookup"><span data-stu-id="7ea6c-174">In **Solution Explorer**, right-click the Class1.cs file and click **Rename**.</span></span> <span data-ttu-id="7ea6c-175">Cambie el nombre del archivo a `SampleClass.cs` y pulse ENTRAR.</span><span class="sxs-lookup"><span data-stu-id="7ea6c-175">Rename the file to `SampleClass.cs` and press ENTER.</span></span> <span data-ttu-id="7ea6c-176">Al cambiar el nombre del archivo también se cambiará el nombre de la clase a `SampleClass`.</span><span class="sxs-lookup"><span data-stu-id="7ea6c-176">Renaming the file also renames the class to `SampleClass`.</span></span> <span data-ttu-id="7ea6c-177">Esta clase implementará la interfaz `ISampleInterface`.</span><span class="sxs-lookup"><span data-stu-id="7ea6c-177">This class will implement the `ISampleInterface` interface.</span></span>  
  
4.  <span data-ttu-id="7ea6c-178">Haga clic con el botón derecho en el proyecto TypeEquivalenceRuntime y haga clic en **Propiedades**.</span><span class="sxs-lookup"><span data-stu-id="7ea6c-178">Right-click the TypeEquivalenceRuntime project and click **Properties**.</span></span> <span data-ttu-id="7ea6c-179">Haga clic en la pestaña **Compilar**.</span><span class="sxs-lookup"><span data-stu-id="7ea6c-179">Click the **Build** tab.</span></span> <span data-ttu-id="7ea6c-180">Establezca la ruta de acceso de salida en la misma ubicación que se usa en el proyecto TypeEquivalenceInterface, por ejemplo, `C:\TypeEquivalenceSample`.</span><span class="sxs-lookup"><span data-stu-id="7ea6c-180">Set the output path to the same location you used in the TypeEquivalenceInterface project, for example, `C:\TypeEquivalenceSample`.</span></span>  
  
5.  <span data-ttu-id="7ea6c-181">Mientras sigue editando las propiedades del proyecto, haga clic en la pestaña **Firma**.</span><span class="sxs-lookup"><span data-stu-id="7ea6c-181">While still editing the project properties, click the **Signing** tab.</span></span> <span data-ttu-id="7ea6c-182">Seleccione la opción **Firmar el ensamblado**.</span><span class="sxs-lookup"><span data-stu-id="7ea6c-182">Select the **Sign the assembly** option.</span></span> <span data-ttu-id="7ea6c-183">En la lista **Elija un archivo de clave de nombre seguro**, haga clic en **<Nuevo...>**.</span><span class="sxs-lookup"><span data-stu-id="7ea6c-183">In the **Choose a strong name key file** list, click **<New...>**.</span></span> <span data-ttu-id="7ea6c-184">En el cuadro **Nombre del archivo de clave**, escriba `key.snk`.</span><span class="sxs-lookup"><span data-stu-id="7ea6c-184">In the **Key file name** box, type `key.snk`.</span></span> <span data-ttu-id="7ea6c-185">Desactive la casilla **Proteger mi archivo de clave mediante contraseña**.</span><span class="sxs-lookup"><span data-stu-id="7ea6c-185">Clear the **Protect my key file with a password** check box.</span></span> <span data-ttu-id="7ea6c-186">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="7ea6c-186">Click **OK**.</span></span>  
  
6.  <span data-ttu-id="7ea6c-187">Haga clic con el botón derecho en el proyecto TypeEquivalenceRuntime y haga clic en **Agregar referencia**.</span><span class="sxs-lookup"><span data-stu-id="7ea6c-187">Right-click the TypeEquivalenceRuntime project and click **Add Reference**.</span></span> <span data-ttu-id="7ea6c-188">Haga clic en la pestaña **Examinar** y vaya a la carpeta de la ruta de acceso de salida.</span><span class="sxs-lookup"><span data-stu-id="7ea6c-188">Click the **Browse** tab and browse to the output path folder.</span></span> <span data-ttu-id="7ea6c-189">Seleccione el archivo TypeEquivalenceInterface.dll y haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="7ea6c-189">Select the TypeEquivalenceInterface.dll file and click **OK**.</span></span>  
  
7.  <span data-ttu-id="7ea6c-190">En el **Explorador de soluciones**, expanda la carpeta **Referencias**.</span><span class="sxs-lookup"><span data-stu-id="7ea6c-190">In **Solution Explorer**, expand the **References** folder.</span></span> <span data-ttu-id="7ea6c-191">Seleccione la referencia TypeEquivalenceInterface.</span><span class="sxs-lookup"><span data-stu-id="7ea6c-191">Select the TypeEquivalenceInterface reference.</span></span> <span data-ttu-id="7ea6c-192">En la ventana Propiedades de la referencia TypeEquivalenceInterface, establezca la propiedad **Versión específica** en **False**.</span><span class="sxs-lookup"><span data-stu-id="7ea6c-192">In the Properties window for the TypeEquivalenceInterface reference, set the **Specific Version** property to **False**.</span></span>  
  
8.  <span data-ttu-id="7ea6c-193">Agregue el código siguiente al archivo de clase SampleClass para crear la clase SampleClass.</span><span class="sxs-lookup"><span data-stu-id="7ea6c-193">Add the following code to the SampleClass class file to create the SampleClass class.</span></span>  
  
    ```csharp  
    using System;  
    using System.Collections.Generic;  
    using System.Linq;  
    using System.Text;  
    using TypeEquivalenceInterface;  
  
    namespace TypeEquivalenceRuntime  
    {  
        public class SampleClass : ISampleInterface  
        {  
            private string p_UserInput;  
            public string UserInput { get { return p_UserInput; } }  
  
            public void GetUserInput()  
            {  
                Console.WriteLine("Please enter a value:");  
                p_UserInput = Console.ReadLine();  
            }  
        }  
    )  
    ```  
  
9. <span data-ttu-id="7ea6c-194">Guarde el proyecto.</span><span class="sxs-lookup"><span data-stu-id="7ea6c-194">Save the project.</span></span>  
  
10. <span data-ttu-id="7ea6c-195">Haga clic con el botón derecho en el proyecto TypeEquivalenceRuntime y haga clic en **Compilar**.</span><span class="sxs-lookup"><span data-stu-id="7ea6c-195">Right-click the TypeEquivalenceRuntime project and click **Build**.</span></span> <span data-ttu-id="7ea6c-196">El archivo .dll de biblioteca de clases se compila y se guarda en la ruta de acceso de salida de la compilación especificada (por ejemplo, C:\TypeEquivalenceSample).</span><span class="sxs-lookup"><span data-stu-id="7ea6c-196">The class library .dll file is compiled and saved to the specified build output path (for example, C:\TypeEquivalenceSample).</span></span>  
  
## <a name="creating-a-client-project"></a><span data-ttu-id="7ea6c-197">Creación de un proyecto de cliente</span><span class="sxs-lookup"><span data-stu-id="7ea6c-197">Creating a Client Project</span></span>  
  
#### <a name="to-create-the-type-equivalence-client-project"></a><span data-ttu-id="7ea6c-198">Para crear el proyecto de cliente de equivalencia de tipos</span><span class="sxs-lookup"><span data-stu-id="7ea6c-198">To create the type equivalence client project</span></span>  
  
1.  <span data-ttu-id="7ea6c-199">En el menú **Archivo** de Visual Studio, apunte a **Nuevo** y haga clic en **Proyecto**.</span><span class="sxs-lookup"><span data-stu-id="7ea6c-199">In Visual Studio, on the **File** menu, point to **New** and then click **Project**.</span></span>  
  
2.  <span data-ttu-id="7ea6c-200">En el panel **Tipos de proyecto** del cuadro de diálogo **Nuevo proyecto**, asegúrese de que esté seleccionado **Windows**.</span><span class="sxs-lookup"><span data-stu-id="7ea6c-200">In the **New Project** dialog box, in the **Project Types** pane, make sure that **Windows** is selected.</span></span> <span data-ttu-id="7ea6c-201">Seleccione **Aplicación de consola** en el panel **Plantillas**.</span><span class="sxs-lookup"><span data-stu-id="7ea6c-201">Select **Console Application** in the **Templates** pane.</span></span> <span data-ttu-id="7ea6c-202">En el cuadro **Nombre**, escriba `TypeEquivalenceClient` y haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="7ea6c-202">In the **Name** box, type `TypeEquivalenceClient`, and then click **OK**.</span></span> <span data-ttu-id="7ea6c-203">Se crea el proyecto.</span><span class="sxs-lookup"><span data-stu-id="7ea6c-203">The new project is created.</span></span>  
  
3.  <span data-ttu-id="7ea6c-204">Haga clic con el botón derecho en el proyecto TypeEquivalenceClient y haga clic en **Propiedades**.</span><span class="sxs-lookup"><span data-stu-id="7ea6c-204">Right-click the TypeEquivalenceClient project and click **Properties**.</span></span> <span data-ttu-id="7ea6c-205">Haga clic en la pestaña **Compilar**.</span><span class="sxs-lookup"><span data-stu-id="7ea6c-205">Click the **Build** tab.</span></span> <span data-ttu-id="7ea6c-206">Establezca la ruta de acceso de salida en la misma ubicación que se usa en el proyecto TypeEquivalenceInterface, por ejemplo, `C:\TypeEquivalenceSample`.</span><span class="sxs-lookup"><span data-stu-id="7ea6c-206">Set the output path to the same location you used in the TypeEquivalenceInterface project, for example, `C:\TypeEquivalenceSample`.</span></span>  
  
4.  <span data-ttu-id="7ea6c-207">Haga clic con el botón derecho en el proyecto TypeEquivalenceClient y haga clic en **Agregar referencia**.</span><span class="sxs-lookup"><span data-stu-id="7ea6c-207">Right-click the TypeEquivalenceClient project and click **Add Reference**.</span></span> <span data-ttu-id="7ea6c-208">Haga clic en la pestaña **Examinar** y vaya a la carpeta de la ruta de acceso de salida.</span><span class="sxs-lookup"><span data-stu-id="7ea6c-208">Click the **Browse** tab and browse to the output path folder.</span></span> <span data-ttu-id="7ea6c-209">Seleccione el archivo TypeEquivalenceInterface.dll file (no el TypeEquivalenceRuntime.dll) y haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="7ea6c-209">Select the TypeEquivalenceInterface.dll file (not the TypeEquivalenceRuntime.dll) and click **OK**.</span></span>  
  
5.  <span data-ttu-id="7ea6c-210">En el **Explorador de soluciones**, expanda la carpeta **Referencias**.</span><span class="sxs-lookup"><span data-stu-id="7ea6c-210">In **Solution Explorer**, expand the **References** folder.</span></span> <span data-ttu-id="7ea6c-211">Seleccione la referencia TypeEquivalenceInterface.</span><span class="sxs-lookup"><span data-stu-id="7ea6c-211">Select the TypeEquivalenceInterface reference.</span></span> <span data-ttu-id="7ea6c-212">En la ventana Propiedades de la referencia TypeEquivalenceInterface, establezca la propiedad **Incrustar tipos de interoperabilidad** en **True**.</span><span class="sxs-lookup"><span data-stu-id="7ea6c-212">In the Properties window for the TypeEquivalenceInterface reference, set the **Embed Interop Types** property to **True**.</span></span>  
  
6.  <span data-ttu-id="7ea6c-213">Agregue el código siguiente al archivo Program.cs para crear el programa cliente.</span><span class="sxs-lookup"><span data-stu-id="7ea6c-213">Add the following code to the Program.cs file to create the client program.</span></span>  
  
    ```csharp  
    using System;  
    using System.Collections.Generic;  
    using System.Linq;  
    using System.Text;  
    using TypeEquivalenceInterface;  
    using System.Reflection;  
  
    namespace TypeEquivalenceClient  
    {  
        class Program  
        {  
            static void Main(string[] args)  
            {  
                Assembly sampleAssembly = Assembly.Load("TypeEquivalenceRuntime");  
                ISampleInterface sampleClass =   
                    (ISampleInterface)sampleAssembly.CreateInstance("TypeEquivalenceRuntime.SampleClass");  
                sampleClass.GetUserInput();  
                Console.WriteLine(sampleClass.UserInput);  
                Console.WriteLine(sampleAssembly.GetName().Version.ToString());  
                Console.ReadLine();  
            }  
        }  
    }  
    ```  
  
7.  <span data-ttu-id="7ea6c-214">Pulse CTRL+F5 para compilar y ejecutar el programa.</span><span class="sxs-lookup"><span data-stu-id="7ea6c-214">Press CTRL+F5 to build and run the program.</span></span>  
  
## <a name="modifying-the-interface"></a><span data-ttu-id="7ea6c-215">Modificación de la interfaz</span><span class="sxs-lookup"><span data-stu-id="7ea6c-215">Modifying the Interface</span></span>  
  
#### <a name="to-modify-the-interface"></a><span data-ttu-id="7ea6c-216">Para modificar la interfaz</span><span class="sxs-lookup"><span data-stu-id="7ea6c-216">To modify the interface</span></span>  
  
1.  <span data-ttu-id="7ea6c-217">En el menú **Archivo** de Visual Studio, apunte a **Abrir** y haga clic en **Proyecto o solución**.</span><span class="sxs-lookup"><span data-stu-id="7ea6c-217">In Visual Studio, on the **File** menu, point to **Open**, and then click **Project/Solution**.</span></span>  
  
2.  <span data-ttu-id="7ea6c-218">En el cuadro de diálogo **Abrir proyecto**, haga clic con el botón derecho en el proyecto TypeEquivalenceInterface y haga clic en **Propiedades**.</span><span class="sxs-lookup"><span data-stu-id="7ea6c-218">In the **Open Project** dialog box, right-click the TypeEquivalenceInterface project, and then click **Properties**.</span></span> <span data-ttu-id="7ea6c-219">Haga clic en la pestaña **Aplicación** .</span><span class="sxs-lookup"><span data-stu-id="7ea6c-219">Click the **Application** tab.</span></span> <span data-ttu-id="7ea6c-220">Haga clic en el botón **Información de ensamblado**.</span><span class="sxs-lookup"><span data-stu-id="7ea6c-220">Click the **Assembly Information** button.</span></span> <span data-ttu-id="7ea6c-221">Cambie los valores de **Versión de ensamblado** y **Versión de archivo** a `2.0.0.0`.</span><span class="sxs-lookup"><span data-stu-id="7ea6c-221">Change the **Assembly Version** and **File Version** values to `2.0.0.0`.</span></span>  
  
3.  <span data-ttu-id="7ea6c-222">Abra el archivo SampleInterface.cs.</span><span class="sxs-lookup"><span data-stu-id="7ea6c-222">Open the SampleInterface.cs file.</span></span> <span data-ttu-id="7ea6c-223">Agregue la línea de código siguiente a la interfaz ISampleInterface.</span><span class="sxs-lookup"><span data-stu-id="7ea6c-223">Add the following line of code to the ISampleInterface interface.</span></span>  
  
    ```csharp  
    DateTime GetDate();  
    ```  
  
     <span data-ttu-id="7ea6c-224">Guarde el archivo.</span><span class="sxs-lookup"><span data-stu-id="7ea6c-224">Save the file.</span></span>  
  
4.  <span data-ttu-id="7ea6c-225">Guarde el proyecto.</span><span class="sxs-lookup"><span data-stu-id="7ea6c-225">Save the project.</span></span>  
  
5.  <span data-ttu-id="7ea6c-226">Haga clic con el botón derecho en el proyecto TypeEquivalenceInterface y haga clic en **Compilar**.</span><span class="sxs-lookup"><span data-stu-id="7ea6c-226">Right-click the TypeEquivalenceInterface project and click **Build**.</span></span> <span data-ttu-id="7ea6c-227">Una nueva versión del archivo .dll de biblioteca de clases se compila y se guarda en la ruta de acceso de salida de la compilación especificada (por ejemplo, C:\TypeEquivalenceSample).</span><span class="sxs-lookup"><span data-stu-id="7ea6c-227">A new version of the class library .dll file is compiled and saved in the specified build output path (for example, C:\TypeEquivalenceSample).</span></span>  
  
## <a name="modifying-the-runtime-class"></a><span data-ttu-id="7ea6c-228">Modificación de la clase en tiempo de ejecución</span><span class="sxs-lookup"><span data-stu-id="7ea6c-228">Modifying the Runtime Class</span></span>  
  
#### <a name="to-modify-the-runtime-class"></a><span data-ttu-id="7ea6c-229">Para modificar la clase en tiempo de ejecución</span><span class="sxs-lookup"><span data-stu-id="7ea6c-229">To modify the runtime class</span></span>  
  
1.  <span data-ttu-id="7ea6c-230">En el menú **Archivo** de Visual Studio, apunte a **Abrir** y haga clic en **Proyecto o solución**.</span><span class="sxs-lookup"><span data-stu-id="7ea6c-230">In Visual Studio, on the **File** menu, point to **Open**, and then click **Project/Solution**.</span></span>  
  
2.  <span data-ttu-id="7ea6c-231">En el cuadro de diálogo **Abrir proyecto**, haga clic con el botón derecho en el proyecto TypeEquivalenceRuntime y haga clic en **Propiedades**.</span><span class="sxs-lookup"><span data-stu-id="7ea6c-231">In the **Open Project** dialog box, right-click the TypeEquivalenceRuntime project and click **Properties**.</span></span> <span data-ttu-id="7ea6c-232">Haga clic en la pestaña **Aplicación** .</span><span class="sxs-lookup"><span data-stu-id="7ea6c-232">Click the **Application** tab.</span></span> <span data-ttu-id="7ea6c-233">Haga clic en el botón **Información de ensamblado**.</span><span class="sxs-lookup"><span data-stu-id="7ea6c-233">Click the **Assembly Information** button.</span></span> <span data-ttu-id="7ea6c-234">Cambie los valores de **Versión de ensamblado** y **Versión de archivo** a `2.0.0.0`.</span><span class="sxs-lookup"><span data-stu-id="7ea6c-234">Change the **Assembly Version** and **File Version** values to `2.0.0.0`.</span></span>  
  
3.  <span data-ttu-id="7ea6c-235">Abra el archivo SampleClass.cs.</span><span class="sxs-lookup"><span data-stu-id="7ea6c-235">Open the SampleClass.cs file.</span></span> <span data-ttu-id="7ea6c-236">Agregue las líneas de código siguientes a la clase SampleClass.</span><span class="sxs-lookup"><span data-stu-id="7ea6c-236">Add the following lines of code to the SampleClass class.</span></span>  
  
    ```csharp  
    public DateTime GetDate()  
    {  
        return DateTime.Now;  
    }  
    ```  
  
     <span data-ttu-id="7ea6c-237">Guarde el archivo.</span><span class="sxs-lookup"><span data-stu-id="7ea6c-237">Save the file.</span></span>  
  
4.  <span data-ttu-id="7ea6c-238">Guarde el proyecto.</span><span class="sxs-lookup"><span data-stu-id="7ea6c-238">Save the project.</span></span>  
  
5.  <span data-ttu-id="7ea6c-239">Haga clic con el botón derecho en el proyecto TypeEquivalenceRuntime y haga clic en **Compilar**.</span><span class="sxs-lookup"><span data-stu-id="7ea6c-239">Right-click the TypeEquivalenceRuntime project and click **Build**.</span></span> <span data-ttu-id="7ea6c-240">Una versión actualizada del archivo .dll de biblioteca de clases se compila y se guarda en la ruta de acceso de salida de la compilación especificada anteriormente (por ejemplo, C:\TypeEquivalenceSample).</span><span class="sxs-lookup"><span data-stu-id="7ea6c-240">An updated version of the class library .dll file is compiled and saved in the previously specified build output path (for example, C:\TypeEquivalenceSample).</span></span>  
  
6.  <span data-ttu-id="7ea6c-241">En el Explorador de archivos, abra la carpeta de la ruta de acceso de salida (por ejemplo, C:\TypeEquivalenceSample).</span><span class="sxs-lookup"><span data-stu-id="7ea6c-241">In File Explorer, open the output path folder (for example, C:\TypeEquivalenceSample).</span></span> <span data-ttu-id="7ea6c-242">Haga doble clic en el archivo TypeEquivalenceClient.exe para ejecutar el programa.</span><span class="sxs-lookup"><span data-stu-id="7ea6c-242">Double-click the TypeEquivalenceClient.exe to run the program.</span></span> <span data-ttu-id="7ea6c-243">El programa reflejará la nueva versión del ensamblado TypeEquivalenceRuntime sin tener que volver a compilarse de nuevo.</span><span class="sxs-lookup"><span data-stu-id="7ea6c-243">The program will reflect the new version of the TypeEquivalenceRuntime assembly without having been recompiled.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7ea6c-244">Vea también</span><span class="sxs-lookup"><span data-stu-id="7ea6c-244">See Also</span></span>  
 <span data-ttu-id="7ea6c-245">[/link (Opciones del compilador de C#)](../../../../csharp/language-reference/compiler-options/link-compiler-option.md) </span><span class="sxs-lookup"><span data-stu-id="7ea6c-245">[/link (C# Compiler Options)](../../../../csharp/language-reference/compiler-options/link-compiler-option.md) </span></span>  
 <span data-ttu-id="7ea6c-246">[Guía de programación de C#](../../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="7ea6c-246">[C# Programming Guide](../../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="7ea6c-247">[Programar con ensamblados](../../../../framework/app-domains/programming-with-assemblies.md) </span><span class="sxs-lookup"><span data-stu-id="7ea6c-247">[Programming with Assemblies](../../../../framework/app-domains/programming-with-assemblies.md) </span></span>  
 <span data-ttu-id="7ea6c-248">[Assemblies and the Global Assembly Cache (C#)](../../../../csharp/programming-guide/concepts/assemblies-gac/index.md) (Ensamblados y caché global de ensamblados [C#])</span><span class="sxs-lookup"><span data-stu-id="7ea6c-248">[Assemblies and the Global Assembly Cache (C#)](../../../../csharp/programming-guide/concepts/assemblies-gac/index.md)</span></span>

