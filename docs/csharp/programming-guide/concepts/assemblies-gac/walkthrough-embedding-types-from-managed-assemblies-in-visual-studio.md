---
title: 'Tutorial: Incrustar los tipos de los ensamblados administrados en Visual Studio (C#)'
ms.date: 07/20/2015
ms.assetid: 55ed13c9-c5bb-4bc2-bcd8-0587eb568864
ms.openlocfilehash: 39452702a3e757456ff00ee22e6eb1f90160ef38
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54500634"
---
# <a name="walkthrough-embedding-types-from-managed-assemblies-in-visual-studio-c"></a><span data-ttu-id="d1199-102">Tutorial: Incrustar los tipos de los ensamblados administrados en Visual Studio (C#)</span><span class="sxs-lookup"><span data-stu-id="d1199-102">Walkthrough: Embedding Types from Managed Assemblies in Visual Studio (C#)</span></span>
<span data-ttu-id="d1199-103">Si inserta información de tipos de un ensamblado administrado con nombre seguro, puede acoplar tipos holgadamente en una aplicación para lograr independencia de versiones.</span><span class="sxs-lookup"><span data-stu-id="d1199-103">If you embed type information from a strong-named managed assembly, you can loosely couple types in an application to achieve version independence.</span></span> <span data-ttu-id="d1199-104">Es decir, el programa puede escribirse de modo que use tipos de varias versiones de una biblioteca administrada sin tener que volver a compilarse para cada versión.</span><span class="sxs-lookup"><span data-stu-id="d1199-104">That is, your program can be written to use types from multiple versions of a managed library without having to be recompiled for each version.</span></span>  
  
 <span data-ttu-id="d1199-105">La inserción de tipos se usa a menudo con interoperabilidad COM, como, por ejemplo, una aplicación que use objetos de automatización de Microsoft Office.</span><span class="sxs-lookup"><span data-stu-id="d1199-105">Type embedding is frequently used with COM interop, such as an application that uses automation objects from Microsoft Office.</span></span> <span data-ttu-id="d1199-106">La inserción de información de tipos permite que la misma versión de un programa funcione con distintas versiones de Microsoft Office en equipos diferentes.</span><span class="sxs-lookup"><span data-stu-id="d1199-106">Embedding type information enables the same build of a program to work with different versions of Microsoft Office on different computers.</span></span> <span data-ttu-id="d1199-107">Pero la inserción de tipos también se puede usar con una solución totalmente administrada.</span><span class="sxs-lookup"><span data-stu-id="d1199-107">However, you can also use type embedding with a fully managed solution.</span></span>  
  
 <span data-ttu-id="d1199-108">La información de tipos puede insertarse de un ensamblado que tenga las siguientes características:</span><span class="sxs-lookup"><span data-stu-id="d1199-108">Type information can be embedded from an assembly that has the following characteristics:</span></span>  
  
-   <span data-ttu-id="d1199-109">El ensamblado expone al menos una interfaz pública.</span><span class="sxs-lookup"><span data-stu-id="d1199-109">The assembly exposes at least one public interface.</span></span>  
  
-   <span data-ttu-id="d1199-110">Las interfaces insertadas se anotan con un atributo `ComImport` y un atributo `Guid` (y un GUID único).</span><span class="sxs-lookup"><span data-stu-id="d1199-110">The embedded interfaces are annotated with a `ComImport` attribute and a `Guid` attribute (and a unique GUID).</span></span>  
  
-   <span data-ttu-id="d1199-111">El ensamblado se anota con los atributos `ImportedFromTypeLib` o `PrimaryInteropAssembly` y un atributo `Guid` de nivel de ensamblado.</span><span class="sxs-lookup"><span data-stu-id="d1199-111">The assembly is annotated with the `ImportedFromTypeLib` attribute or the `PrimaryInteropAssembly` attribute, and an assembly-level `Guid` attribute.</span></span> <span data-ttu-id="d1199-112">(De forma predeterminada, las plantillas de proyecto de Visual C# incluyen un atributo `Guid` de nivel de ensamblado).</span><span class="sxs-lookup"><span data-stu-id="d1199-112">(By default, Visual C# project templates include an assembly-level `Guid` attribute.)</span></span>  
  
 <span data-ttu-id="d1199-113">Después de especificar las interfaces públicas que se pueden insertar, puede crear clases en tiempo de ejecución que implementen esas interfaces.</span><span class="sxs-lookup"><span data-stu-id="d1199-113">After you have specified the public interfaces that can be embedded, you can create runtime classes that implement those interfaces.</span></span> <span data-ttu-id="d1199-114">Un programa cliente puede luego incrustar la información de tipo de dichas interfaces en tiempo de diseño haciendo referencia al ensamblado que contiene la configuración y las interfaces públicas de la propiedad `Embed Interop Types` de la referencia a `True`.</span><span class="sxs-lookup"><span data-stu-id="d1199-114">A client program can then embed the type information for those interfaces at design time by referencing the assembly that contains the public interfaces and setting the `Embed Interop Types` property of the reference to `True`.</span></span> <span data-ttu-id="d1199-115">Esto equivale a usar el compilador de línea de comandos y hacer referencia al ensamblado mediante la opción `/link` del compilador.</span><span class="sxs-lookup"><span data-stu-id="d1199-115">This is equivalent to using the command line compiler and referencing the assembly by using the `/link` compiler option.</span></span> <span data-ttu-id="d1199-116">El programa cliente puede luego cargar instancias de los objetos en tiempo de ejecución escritos como esas interfaces.</span><span class="sxs-lookup"><span data-stu-id="d1199-116">The client program can then load instances of your runtime objects typed as those interfaces.</span></span> <span data-ttu-id="d1199-117">Si crea otra versión del ensamblado en tiempo de ejecución con nombre seguro, el programa cliente no tiene que volver a compilarse con el ensamblado en tiempo de ejecución actualizado.</span><span class="sxs-lookup"><span data-stu-id="d1199-117">If you create a new version of your strong-named runtime assembly, the client program does not have to be recompiled with the updated runtime assembly.</span></span> <span data-ttu-id="d1199-118">En su lugar, el programa cliente sigue usando cualquier versión del ensamblado en tiempo de ejecución que encuentre disponible y usa la información de tipo insertada para las interfaces públicas.</span><span class="sxs-lookup"><span data-stu-id="d1199-118">Instead, the client program continues to use whichever version of the runtime assembly is available to it, using the embedded type information for the public interfaces.</span></span>  
  
 <span data-ttu-id="d1199-119">Dado que la función principal de la inserción de tipos es admitir la inserción de información de tipos de ensamblados de interoperabilidad COM, cuando se inserta información de tipos en una solución totalmente administrada se aplican las siguientes limitaciones:</span><span class="sxs-lookup"><span data-stu-id="d1199-119">Because the primary function of type embedding is to support embedding of type information from COM interop assemblies, the following limitations apply when you embed type information in a fully managed solution:</span></span>  
  
-   <span data-ttu-id="d1199-120">Solo se insertan los atributos específicos de interoperabilidad COM; se omiten otros atributos.</span><span class="sxs-lookup"><span data-stu-id="d1199-120">Only attributes specific to COM interop are embedded; other attributes are ignored.</span></span>  
  
-   <span data-ttu-id="d1199-121">Si un tipo usa parámetros genéricos y el tipo del parámetro genérico es un tipo insertado, ese tipo no se puede usar más allá de un límite de ensamblado.</span><span class="sxs-lookup"><span data-stu-id="d1199-121">If a type uses generic parameters and the type of the generic parameter is an embedded type, that type cannot be used across an assembly boundary.</span></span> <span data-ttu-id="d1199-122">Entre los ejemplos de cruce de un límite de ensamblado se incluyen llamar a un método desde otro ensamblado o derivar un tipo de un tipo definido en otro ensamblado.</span><span class="sxs-lookup"><span data-stu-id="d1199-122">Examples of crossing an assembly boundary include calling a method from another assembly or a deriving a type from a type defined in another assembly.</span></span>  
  
-   <span data-ttu-id="d1199-123">Las constantes no se insertan.</span><span class="sxs-lookup"><span data-stu-id="d1199-123">Constants are not embedded.</span></span>  
  
-   <span data-ttu-id="d1199-124">La clase <xref:System.Collections.Generic.Dictionary%602?displayProperty=nameWithType> no admite un tipo insertado como clave.</span><span class="sxs-lookup"><span data-stu-id="d1199-124">The <xref:System.Collections.Generic.Dictionary%602?displayProperty=nameWithType> class does not support an embedded type as a key.</span></span> <span data-ttu-id="d1199-125">Puede implementar su propio tipo de diccionario que admita un tipo insertado como clave.</span><span class="sxs-lookup"><span data-stu-id="d1199-125">You can implement your own dictionary type to support an embedded type as a key.</span></span>  
  
 <span data-ttu-id="d1199-126">En este tutorial, se realizarán las siguientes tareas:</span><span class="sxs-lookup"><span data-stu-id="d1199-126">In this walkthrough, you will do the following:</span></span>  
  
-   <span data-ttu-id="d1199-127">Crear un ensamblado con nombre seguro que tenga una interfaz pública e incluya información de tipo que se puede insertar.</span><span class="sxs-lookup"><span data-stu-id="d1199-127">Create a strong-named assembly that has a public interface that contains type information that can be embedded.</span></span>  
  
-   <span data-ttu-id="d1199-128">Crear un ensamblado en tiempo de ejecución con nombre seguro que implemente esa interfaz pública.</span><span class="sxs-lookup"><span data-stu-id="d1199-128">Create a strong-named runtime assembly that implements that public interface.</span></span>  
  
-   <span data-ttu-id="d1199-129">Crear un programa cliente que inserte la información de tipo de la interfaz pública y cree una instancia de la clase del ensamblado en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="d1199-129">Create a client program that embeds the type information from the public interface and creates an instance of the class from the runtime assembly.</span></span>  
  
-   <span data-ttu-id="d1199-130">Modificar y recompilar el ensamblado en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="d1199-130">Modify and rebuild the runtime assembly.</span></span>  
  
-   <span data-ttu-id="d1199-131">Ejecute el programa cliente para ver que se usa la nueva versión del ensamblado en tiempo de ejecución sin tener que recompilar el programa cliente.</span><span class="sxs-lookup"><span data-stu-id="d1199-131">Run the client program to see that the new version of the runtime assembly is being used without having to recompile the client program.</span></span>  
  
[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]  
  
## <a name="creating-an-interface"></a><span data-ttu-id="d1199-132">Creación de una interfaz</span><span class="sxs-lookup"><span data-stu-id="d1199-132">Creating an Interface</span></span>  
  
#### <a name="to-create-the-type-equivalence-interface-project"></a><span data-ttu-id="d1199-133">Para crear el proyecto de interfaz de equivalencia de tipos</span><span class="sxs-lookup"><span data-stu-id="d1199-133">To create the type equivalence interface project</span></span>  
  
1.  <span data-ttu-id="d1199-134">En el menú **Archivo** de Visual Studio, elija **Nuevo** y haga clic en **Proyecto**.</span><span class="sxs-lookup"><span data-stu-id="d1199-134">In Visual Studio, on the **File** menu, choose **New** and then click **Project**.</span></span>  
  
2.  <span data-ttu-id="d1199-135">En el panel **Tipos de proyecto** del cuadro de diálogo **Nuevo proyecto**, asegúrese de que esté seleccionado **Windows**.</span><span class="sxs-lookup"><span data-stu-id="d1199-135">In the **New Project** dialog box, in the **Project Types** pane, make sure that **Windows** is selected.</span></span> <span data-ttu-id="d1199-136">Seleccione **Biblioteca de clases** en el panel **Plantillas**.</span><span class="sxs-lookup"><span data-stu-id="d1199-136">Select **Class Library** in the **Templates** pane.</span></span> <span data-ttu-id="d1199-137">En el cuadro **Nombre**, escriba `TypeEquivalenceInterface` y haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="d1199-137">In the **Name** box, type `TypeEquivalenceInterface`, and then click **OK**.</span></span> <span data-ttu-id="d1199-138">Se crea el proyecto.</span><span class="sxs-lookup"><span data-stu-id="d1199-138">The new project is created.</span></span>  
  
3.  <span data-ttu-id="d1199-139">En el **Explorador de soluciones**, haga clic con el botón derecho en el archivo Class1.cs y haga clic en **Cambiar nombre**.</span><span class="sxs-lookup"><span data-stu-id="d1199-139">In **Solution Explorer**, right-click the Class1.cs file and click **Rename**.</span></span> <span data-ttu-id="d1199-140">Cambie el nombre del archivo a `ISampleInterface.cs` y pulse ENTRAR.</span><span class="sxs-lookup"><span data-stu-id="d1199-140">Rename the file to `ISampleInterface.cs` and press ENTER.</span></span> <span data-ttu-id="d1199-141">Al cambiar el nombre del archivo también se cambiará el nombre de la clase a `ISampleInterface`.</span><span class="sxs-lookup"><span data-stu-id="d1199-141">Renaming the file will also rename the class to `ISampleInterface`.</span></span> <span data-ttu-id="d1199-142">Esta clase representará la interfaz pública de la clase.</span><span class="sxs-lookup"><span data-stu-id="d1199-142">This class will represent the public interface for the class.</span></span>  
  
4.  <span data-ttu-id="d1199-143">Haga clic con el botón derecho en el proyecto TypeEquivalenceInterface y haga clic en **Propiedades**.</span><span class="sxs-lookup"><span data-stu-id="d1199-143">Right-click the TypeEquivalenceInterface project and click **Properties**.</span></span> <span data-ttu-id="d1199-144">Haga clic en la pestaña **Compilar**. Establezca la ruta de acceso de salida en una ubicación válida en el equipo de desarrollo, como `C:\TypeEquivalenceSample`.</span><span class="sxs-lookup"><span data-stu-id="d1199-144">Click the **Build** tab. Set the output path to a valid location on your development computer, such as `C:\TypeEquivalenceSample`.</span></span> <span data-ttu-id="d1199-145">Esta ubicación también se usará en un paso posterior en este tutorial.</span><span class="sxs-lookup"><span data-stu-id="d1199-145">This location will also be used in a later step in this walkthrough.</span></span>  
  
5.  <span data-ttu-id="d1199-146">Mientras sigue editando las propiedades del proyecto, haga clic en la pestaña **Firma**. Seleccione la opción **Firmar el ensamblado**.</span><span class="sxs-lookup"><span data-stu-id="d1199-146">While still editing the project properties, click the **Signing** tab. Select the **Sign the assembly** option.</span></span> <span data-ttu-id="d1199-147">En la lista **Elija un archivo de clave de nombre seguro**, haga clic en **<Nuevo...>**.</span><span class="sxs-lookup"><span data-stu-id="d1199-147">In the **Choose a strong name key file** list, click **<New...>**.</span></span> <span data-ttu-id="d1199-148">En el cuadro **Nombre del archivo de clave**, escriba `key.snk`.</span><span class="sxs-lookup"><span data-stu-id="d1199-148">In the **Key file name** box, type `key.snk`.</span></span> <span data-ttu-id="d1199-149">Desactive la casilla **Proteger mi archivo de clave mediante contraseña**.</span><span class="sxs-lookup"><span data-stu-id="d1199-149">Clear the **Protect my key file with a password** check box.</span></span> <span data-ttu-id="d1199-150">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="d1199-150">Click **OK**.</span></span>  
  
6.  <span data-ttu-id="d1199-151">Abra el archivo ISampleInterface.cs.</span><span class="sxs-lookup"><span data-stu-id="d1199-151">Open the ISampleInterface.cs file.</span></span> <span data-ttu-id="d1199-152">Agregue el código siguiente al archivo de clase ISampleInterface para crear la interfaz ISampleInterface.</span><span class="sxs-lookup"><span data-stu-id="d1199-152">Add the following code to the ISampleInterface class file to create the ISampleInterface interface.</span></span>  
  
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
  
7.  <span data-ttu-id="d1199-153">En el menú **Herramientas**, haga clic en **Crear GUID**.</span><span class="sxs-lookup"><span data-stu-id="d1199-153">On the **Tools** menu, click **Create Guid**.</span></span> <span data-ttu-id="d1199-154">En el cuadro de diálogo **Crear GUID**, haga clic en **Formato de Registro** y luego en **Copiar**.</span><span class="sxs-lookup"><span data-stu-id="d1199-154">In the **Create GUID** dialog box, click **Registry Format** and then click **Copy**.</span></span> <span data-ttu-id="d1199-155">Haga clic en **Salir**.</span><span class="sxs-lookup"><span data-stu-id="d1199-155">Click **Exit**.</span></span>  
  
8.  <span data-ttu-id="d1199-156">En el atributo `Guid`, elimine el GUID de ejemplo y pegue el GUID que ha copiado del cuadro de diálogo **Crear GUID**.</span><span class="sxs-lookup"><span data-stu-id="d1199-156">In the `Guid` attribute, delete the sample GUID and paste in the GUID that you copied from the **Create GUID** dialog box.</span></span> <span data-ttu-id="d1199-157">Quite las llaves ({}) del GUID copiado.</span><span class="sxs-lookup"><span data-stu-id="d1199-157">Remove the braces ({}) from the copied GUID.</span></span>  
  
9. <span data-ttu-id="d1199-158">En el **Explorador de soluciones**, expanda la carpeta **Propiedades**.</span><span class="sxs-lookup"><span data-stu-id="d1199-158">In **Solution Explorer**, expand the **Properties** folder.</span></span> <span data-ttu-id="d1199-159">Haga doble clic en el archivo AssemblyInfo.cs.</span><span class="sxs-lookup"><span data-stu-id="d1199-159">Double-click the AssemblyInfo.cs file.</span></span> <span data-ttu-id="d1199-160">Agregue el atributo siguiente al archivo.</span><span class="sxs-lookup"><span data-stu-id="d1199-160">Add the following attribute to the file.</span></span>  
  
    ```csharp  
    [assembly: ImportedFromTypeLib("")]  
    ```  
  
     <span data-ttu-id="d1199-161">Guarde el archivo.</span><span class="sxs-lookup"><span data-stu-id="d1199-161">Save the file.</span></span>  
  
10. <span data-ttu-id="d1199-162">Guarde el proyecto.</span><span class="sxs-lookup"><span data-stu-id="d1199-162">Save the project.</span></span>  
  
11. <span data-ttu-id="d1199-163">Haga clic con el botón derecho en el proyecto TypeEquivalenceInterface y haga clic en **Compilar**.</span><span class="sxs-lookup"><span data-stu-id="d1199-163">Right-click the TypeEquivalenceInterface project and click **Build**.</span></span> <span data-ttu-id="d1199-164">El archivo .dll de biblioteca de clases se compila y se guarda en la ruta de acceso de salida de la compilación especificada (por ejemplo, C:\TypeEquivalenceSample).</span><span class="sxs-lookup"><span data-stu-id="d1199-164">The class library .dll file is compiled and saved to the specified build output path (for example, C:\TypeEquivalenceSample).</span></span>  
  
## <a name="creating-a-runtime-class"></a><span data-ttu-id="d1199-165">Creación de una clase en tiempo de ejecución</span><span class="sxs-lookup"><span data-stu-id="d1199-165">Creating a Runtime Class</span></span>  
  
#### <a name="to-create-the-type-equivalence-runtime-project"></a><span data-ttu-id="d1199-166">Para crear el proyecto en tiempo de ejecución de equivalencia de tipos</span><span class="sxs-lookup"><span data-stu-id="d1199-166">To create the type equivalence runtime project</span></span>  
  
1.  <span data-ttu-id="d1199-167">En el menú **Archivo** de Visual Studio, apunte a **Nuevo** y haga clic en **Proyecto**.</span><span class="sxs-lookup"><span data-stu-id="d1199-167">In Visual Studio, on the **File** menu, point to **New** and then click **Project**.</span></span>  
  
2.  <span data-ttu-id="d1199-168">En el panel **Tipos de proyecto** del cuadro de diálogo **Nuevo proyecto**, asegúrese de que esté seleccionado **Windows**.</span><span class="sxs-lookup"><span data-stu-id="d1199-168">In the **New Project** dialog box, in the **Project Types** pane, make sure that **Windows** is selected.</span></span> <span data-ttu-id="d1199-169">Seleccione **Biblioteca de clases** en el panel **Plantillas**.</span><span class="sxs-lookup"><span data-stu-id="d1199-169">Select **Class Library** in the **Templates** pane.</span></span> <span data-ttu-id="d1199-170">En el cuadro **Nombre**, escriba `TypeEquivalenceRuntime` y haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="d1199-170">In the **Name** box, type `TypeEquivalenceRuntime`, and then click **OK**.</span></span> <span data-ttu-id="d1199-171">Se crea el proyecto.</span><span class="sxs-lookup"><span data-stu-id="d1199-171">The new project is created.</span></span>  
  
3.  <span data-ttu-id="d1199-172">En el **Explorador de soluciones**, haga clic con el botón derecho en el archivo Class1.cs y haga clic en **Cambiar nombre**.</span><span class="sxs-lookup"><span data-stu-id="d1199-172">In **Solution Explorer**, right-click the Class1.cs file and click **Rename**.</span></span> <span data-ttu-id="d1199-173">Cambie el nombre del archivo a `SampleClass.cs` y pulse ENTRAR.</span><span class="sxs-lookup"><span data-stu-id="d1199-173">Rename the file to `SampleClass.cs` and press ENTER.</span></span> <span data-ttu-id="d1199-174">Al cambiar el nombre del archivo también se cambiará el nombre de la clase a `SampleClass`.</span><span class="sxs-lookup"><span data-stu-id="d1199-174">Renaming the file also renames the class to `SampleClass`.</span></span> <span data-ttu-id="d1199-175">Esta clase implementará la interfaz `ISampleInterface`.</span><span class="sxs-lookup"><span data-stu-id="d1199-175">This class will implement the `ISampleInterface` interface.</span></span>  
  
4.  <span data-ttu-id="d1199-176">Haga clic con el botón derecho en el proyecto TypeEquivalenceRuntime y haga clic en **Propiedades**.</span><span class="sxs-lookup"><span data-stu-id="d1199-176">Right-click the TypeEquivalenceRuntime project and click **Properties**.</span></span> <span data-ttu-id="d1199-177">Haga clic en la pestaña **Compilar**. Establezca la ruta de acceso de salida en la misma ubicación que se usa en el proyecto TypeEquivalenceInterface, por ejemplo, `C:\TypeEquivalenceSample`.</span><span class="sxs-lookup"><span data-stu-id="d1199-177">Click the **Build** tab. Set the output path to the same location you used in the TypeEquivalenceInterface project, for example, `C:\TypeEquivalenceSample`.</span></span>  
  
5.  <span data-ttu-id="d1199-178">Mientras sigue editando las propiedades del proyecto, haga clic en la pestaña **Firma**. Seleccione la opción **Firmar el ensamblado**.</span><span class="sxs-lookup"><span data-stu-id="d1199-178">While still editing the project properties, click the **Signing** tab. Select the **Sign the assembly** option.</span></span> <span data-ttu-id="d1199-179">En la lista **Elija un archivo de clave de nombre seguro**, haga clic en **<Nuevo...>**.</span><span class="sxs-lookup"><span data-stu-id="d1199-179">In the **Choose a strong name key file** list, click **<New...>**.</span></span> <span data-ttu-id="d1199-180">En el cuadro **Nombre del archivo de clave**, escriba `key.snk`.</span><span class="sxs-lookup"><span data-stu-id="d1199-180">In the **Key file name** box, type `key.snk`.</span></span> <span data-ttu-id="d1199-181">Desactive la casilla **Proteger mi archivo de clave mediante contraseña**.</span><span class="sxs-lookup"><span data-stu-id="d1199-181">Clear the **Protect my key file with a password** check box.</span></span> <span data-ttu-id="d1199-182">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="d1199-182">Click **OK**.</span></span>  
  
6.  <span data-ttu-id="d1199-183">Haga clic con el botón derecho en el proyecto TypeEquivalenceRuntime y haga clic en **Agregar referencia**.</span><span class="sxs-lookup"><span data-stu-id="d1199-183">Right-click the TypeEquivalenceRuntime project and click **Add Reference**.</span></span> <span data-ttu-id="d1199-184">Haga clic en la pestaña **Examinar** y vaya a la carpeta de la ruta de acceso de salida.</span><span class="sxs-lookup"><span data-stu-id="d1199-184">Click the **Browse** tab and browse to the output path folder.</span></span> <span data-ttu-id="d1199-185">Seleccione el archivo TypeEquivalenceInterface.dll y haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="d1199-185">Select the TypeEquivalenceInterface.dll file and click **OK**.</span></span>  
  
7.  <span data-ttu-id="d1199-186">En el **Explorador de soluciones**, expanda la carpeta **Referencias**.</span><span class="sxs-lookup"><span data-stu-id="d1199-186">In **Solution Explorer**, expand the **References** folder.</span></span> <span data-ttu-id="d1199-187">Seleccione la referencia TypeEquivalenceInterface.</span><span class="sxs-lookup"><span data-stu-id="d1199-187">Select the TypeEquivalenceInterface reference.</span></span> <span data-ttu-id="d1199-188">En la ventana Propiedades de la referencia TypeEquivalenceInterface, establezca la propiedad **Versión específica** en **False**.</span><span class="sxs-lookup"><span data-stu-id="d1199-188">In the Properties window for the TypeEquivalenceInterface reference, set the **Specific Version** property to **False**.</span></span>  
  
8.  <span data-ttu-id="d1199-189">Agregue el código siguiente al archivo de clase SampleClass para crear la clase SampleClass.</span><span class="sxs-lookup"><span data-stu-id="d1199-189">Add the following code to the SampleClass class file to create the SampleClass class.</span></span>  
  
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
    }  
    ```  
  
9. <span data-ttu-id="d1199-190">Guarde el proyecto.</span><span class="sxs-lookup"><span data-stu-id="d1199-190">Save the project.</span></span>  
  
10. <span data-ttu-id="d1199-191">Haga clic con el botón derecho en el proyecto TypeEquivalenceRuntime y haga clic en **Compilar**.</span><span class="sxs-lookup"><span data-stu-id="d1199-191">Right-click the TypeEquivalenceRuntime project and click **Build**.</span></span> <span data-ttu-id="d1199-192">El archivo .dll de biblioteca de clases se compila y se guarda en la ruta de acceso de salida de la compilación especificada (por ejemplo, C:\TypeEquivalenceSample).</span><span class="sxs-lookup"><span data-stu-id="d1199-192">The class library .dll file is compiled and saved to the specified build output path (for example, C:\TypeEquivalenceSample).</span></span>  
  
## <a name="creating-a-client-project"></a><span data-ttu-id="d1199-193">Creación de un proyecto de cliente</span><span class="sxs-lookup"><span data-stu-id="d1199-193">Creating a Client Project</span></span>  
  
#### <a name="to-create-the-type-equivalence-client-project"></a><span data-ttu-id="d1199-194">Para crear el proyecto de cliente de equivalencia de tipos</span><span class="sxs-lookup"><span data-stu-id="d1199-194">To create the type equivalence client project</span></span>  
  
1.  <span data-ttu-id="d1199-195">En el menú **Archivo** de Visual Studio, apunte a **Nuevo** y haga clic en **Proyecto**.</span><span class="sxs-lookup"><span data-stu-id="d1199-195">In Visual Studio, on the **File** menu, point to **New** and then click **Project**.</span></span>  
  
2.  <span data-ttu-id="d1199-196">En el panel **Tipos de proyecto** del cuadro de diálogo **Nuevo proyecto**, asegúrese de que esté seleccionado **Windows**.</span><span class="sxs-lookup"><span data-stu-id="d1199-196">In the **New Project** dialog box, in the **Project Types** pane, make sure that **Windows** is selected.</span></span> <span data-ttu-id="d1199-197">Seleccione **Aplicación de consola** en el panel **Plantillas**.</span><span class="sxs-lookup"><span data-stu-id="d1199-197">Select **Console Application** in the **Templates** pane.</span></span> <span data-ttu-id="d1199-198">En el cuadro **Nombre**, escriba `TypeEquivalenceClient` y haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="d1199-198">In the **Name** box, type `TypeEquivalenceClient`, and then click **OK**.</span></span> <span data-ttu-id="d1199-199">Se crea el proyecto.</span><span class="sxs-lookup"><span data-stu-id="d1199-199">The new project is created.</span></span>  
  
3.  <span data-ttu-id="d1199-200">Haga clic con el botón derecho en el proyecto TypeEquivalenceClient y haga clic en **Propiedades**.</span><span class="sxs-lookup"><span data-stu-id="d1199-200">Right-click the TypeEquivalenceClient project and click **Properties**.</span></span> <span data-ttu-id="d1199-201">Haga clic en la pestaña **Compilar**. Establezca la ruta de acceso de salida en la misma ubicación que se usa en el proyecto TypeEquivalenceInterface, por ejemplo, `C:\TypeEquivalenceSample`.</span><span class="sxs-lookup"><span data-stu-id="d1199-201">Click the **Build** tab. Set the output path to the same location you used in the TypeEquivalenceInterface project, for example, `C:\TypeEquivalenceSample`.</span></span>  
  
4.  <span data-ttu-id="d1199-202">Haga clic con el botón derecho en el proyecto TypeEquivalenceClient y haga clic en **Agregar referencia**.</span><span class="sxs-lookup"><span data-stu-id="d1199-202">Right-click the TypeEquivalenceClient project and click **Add Reference**.</span></span> <span data-ttu-id="d1199-203">Haga clic en la pestaña **Examinar** y vaya a la carpeta de la ruta de acceso de salida.</span><span class="sxs-lookup"><span data-stu-id="d1199-203">Click the **Browse** tab and browse to the output path folder.</span></span> <span data-ttu-id="d1199-204">Seleccione el archivo TypeEquivalenceInterface.dll file (no el TypeEquivalenceRuntime.dll) y haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="d1199-204">Select the TypeEquivalenceInterface.dll file (not the TypeEquivalenceRuntime.dll) and click **OK**.</span></span>  
  
5.  <span data-ttu-id="d1199-205">En el **Explorador de soluciones**, expanda la carpeta **Referencias**.</span><span class="sxs-lookup"><span data-stu-id="d1199-205">In **Solution Explorer**, expand the **References** folder.</span></span> <span data-ttu-id="d1199-206">Seleccione la referencia TypeEquivalenceInterface.</span><span class="sxs-lookup"><span data-stu-id="d1199-206">Select the TypeEquivalenceInterface reference.</span></span> <span data-ttu-id="d1199-207">En la ventana Propiedades de la referencia TypeEquivalenceInterface, establezca la propiedad **Incrustar tipos de interoperabilidad** en **True**.</span><span class="sxs-lookup"><span data-stu-id="d1199-207">In the Properties window for the TypeEquivalenceInterface reference, set the **Embed Interop Types** property to **True**.</span></span>  
  
6.  <span data-ttu-id="d1199-208">Agregue el código siguiente al archivo Program.cs para crear el programa cliente.</span><span class="sxs-lookup"><span data-stu-id="d1199-208">Add the following code to the Program.cs file to create the client program.</span></span>  
  
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
  
7.  <span data-ttu-id="d1199-209">Pulse CTRL+F5 para compilar y ejecutar el programa.</span><span class="sxs-lookup"><span data-stu-id="d1199-209">Press CTRL+F5 to build and run the program.</span></span>  
  
## <a name="modifying-the-interface"></a><span data-ttu-id="d1199-210">Modificación de la interfaz</span><span class="sxs-lookup"><span data-stu-id="d1199-210">Modifying the Interface</span></span>  
  
#### <a name="to-modify-the-interface"></a><span data-ttu-id="d1199-211">Para modificar la interfaz</span><span class="sxs-lookup"><span data-stu-id="d1199-211">To modify the interface</span></span>  
  
1.  <span data-ttu-id="d1199-212">En el menú **Archivo** de Visual Studio, apunte a **Abrir** y haga clic en **Proyecto o solución**.</span><span class="sxs-lookup"><span data-stu-id="d1199-212">In Visual Studio, on the **File** menu, point to **Open**, and then click **Project/Solution**.</span></span>  
  
2.  <span data-ttu-id="d1199-213">En el cuadro de diálogo **Abrir proyecto**, haga clic con el botón derecho en el proyecto TypeEquivalenceInterface y haga clic en **Propiedades**.</span><span class="sxs-lookup"><span data-stu-id="d1199-213">In the **Open Project** dialog box, right-click the TypeEquivalenceInterface project, and then click **Properties**.</span></span> <span data-ttu-id="d1199-214">Haga clic en la pestaña **Aplicación** . Haga clic en el botón **Información de ensamblado**.</span><span class="sxs-lookup"><span data-stu-id="d1199-214">Click the **Application** tab. Click the **Assembly Information** button.</span></span> <span data-ttu-id="d1199-215">Cambie los valores de **Versión de ensamblado** y **Versión de archivo** a `2.0.0.0`.</span><span class="sxs-lookup"><span data-stu-id="d1199-215">Change the **Assembly Version** and **File Version** values to `2.0.0.0`.</span></span>  
  
3.  <span data-ttu-id="d1199-216">Abra el archivo SampleInterface.cs.</span><span class="sxs-lookup"><span data-stu-id="d1199-216">Open the SampleInterface.cs file.</span></span> <span data-ttu-id="d1199-217">Agregue la línea de código siguiente a la interfaz ISampleInterface.</span><span class="sxs-lookup"><span data-stu-id="d1199-217">Add the following line of code to the ISampleInterface interface.</span></span>  
  
    ```csharp  
    DateTime GetDate();  
    ```  
  
     <span data-ttu-id="d1199-218">Guarde el archivo.</span><span class="sxs-lookup"><span data-stu-id="d1199-218">Save the file.</span></span>  
  
4.  <span data-ttu-id="d1199-219">Guarde el proyecto.</span><span class="sxs-lookup"><span data-stu-id="d1199-219">Save the project.</span></span>  
  
5.  <span data-ttu-id="d1199-220">Haga clic con el botón derecho en el proyecto TypeEquivalenceInterface y haga clic en **Compilar**.</span><span class="sxs-lookup"><span data-stu-id="d1199-220">Right-click the TypeEquivalenceInterface project and click **Build**.</span></span> <span data-ttu-id="d1199-221">Una nueva versión del archivo .dll de biblioteca de clases se compila y se guarda en la ruta de acceso de salida de la compilación especificada (por ejemplo, C:\TypeEquivalenceSample).</span><span class="sxs-lookup"><span data-stu-id="d1199-221">A new version of the class library .dll file is compiled and saved in the specified build output path (for example, C:\TypeEquivalenceSample).</span></span>  
  
## <a name="modifying-the-runtime-class"></a><span data-ttu-id="d1199-222">Modificación de la clase en tiempo de ejecución</span><span class="sxs-lookup"><span data-stu-id="d1199-222">Modifying the Runtime Class</span></span>  
  
#### <a name="to-modify-the-runtime-class"></a><span data-ttu-id="d1199-223">Para modificar la clase en tiempo de ejecución</span><span class="sxs-lookup"><span data-stu-id="d1199-223">To modify the runtime class</span></span>  
  
1.  <span data-ttu-id="d1199-224">En el menú **Archivo** de Visual Studio, apunte a **Abrir** y haga clic en **Proyecto o solución**.</span><span class="sxs-lookup"><span data-stu-id="d1199-224">In Visual Studio, on the **File** menu, point to **Open**, and then click **Project/Solution**.</span></span>  
  
2.  <span data-ttu-id="d1199-225">En el cuadro de diálogo **Abrir proyecto**, haga clic con el botón derecho en el proyecto TypeEquivalenceRuntime y haga clic en **Propiedades**.</span><span class="sxs-lookup"><span data-stu-id="d1199-225">In the **Open Project** dialog box, right-click the TypeEquivalenceRuntime project and click **Properties**.</span></span> <span data-ttu-id="d1199-226">Haga clic en la pestaña **Aplicación** . Haga clic en el botón **Información de ensamblado**.</span><span class="sxs-lookup"><span data-stu-id="d1199-226">Click the **Application** tab. Click the **Assembly Information** button.</span></span> <span data-ttu-id="d1199-227">Cambie los valores de **Versión de ensamblado** y **Versión de archivo** a `2.0.0.0`.</span><span class="sxs-lookup"><span data-stu-id="d1199-227">Change the **Assembly Version** and **File Version** values to `2.0.0.0`.</span></span>  
  
3.  <span data-ttu-id="d1199-228">Abra el archivo SampleClass.cs.</span><span class="sxs-lookup"><span data-stu-id="d1199-228">Open the SampleClass.cs file.</span></span> <span data-ttu-id="d1199-229">Agregue las líneas de código siguientes a la clase SampleClass.</span><span class="sxs-lookup"><span data-stu-id="d1199-229">Add the following lines of code to the SampleClass class.</span></span>  
  
    ```csharp  
    public DateTime GetDate()  
    {  
        return DateTime.Now;  
    }  
    ```  
  
     <span data-ttu-id="d1199-230">Guarde el archivo.</span><span class="sxs-lookup"><span data-stu-id="d1199-230">Save the file.</span></span>  
  
4.  <span data-ttu-id="d1199-231">Guarde el proyecto.</span><span class="sxs-lookup"><span data-stu-id="d1199-231">Save the project.</span></span>  
  
5.  <span data-ttu-id="d1199-232">Haga clic con el botón derecho en el proyecto TypeEquivalenceRuntime y haga clic en **Compilar**.</span><span class="sxs-lookup"><span data-stu-id="d1199-232">Right-click the TypeEquivalenceRuntime project and click **Build**.</span></span> <span data-ttu-id="d1199-233">Una versión actualizada del archivo .dll de biblioteca de clases se compila y se guarda en la ruta de acceso de salida de la compilación especificada anteriormente (por ejemplo, C:\TypeEquivalenceSample).</span><span class="sxs-lookup"><span data-stu-id="d1199-233">An updated version of the class library .dll file is compiled and saved in the previously specified build output path (for example, C:\TypeEquivalenceSample).</span></span>  
  
6.  <span data-ttu-id="d1199-234">En el Explorador de archivos, abra la carpeta de la ruta de acceso de salida (por ejemplo, C:\TypeEquivalenceSample).</span><span class="sxs-lookup"><span data-stu-id="d1199-234">In File Explorer, open the output path folder (for example, C:\TypeEquivalenceSample).</span></span> <span data-ttu-id="d1199-235">Haga doble clic en el archivo TypeEquivalenceClient.exe para ejecutar el programa.</span><span class="sxs-lookup"><span data-stu-id="d1199-235">Double-click the TypeEquivalenceClient.exe to run the program.</span></span> <span data-ttu-id="d1199-236">El programa reflejará la nueva versión del ensamblado TypeEquivalenceRuntime sin tener que volver a compilarse de nuevo.</span><span class="sxs-lookup"><span data-stu-id="d1199-236">The program will reflect the new version of the TypeEquivalenceRuntime assembly without having been recompiled.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d1199-237">Vea también</span><span class="sxs-lookup"><span data-stu-id="d1199-237">See also</span></span>

- [<span data-ttu-id="d1199-238">/link (Opciones del compilador de C#)</span><span class="sxs-lookup"><span data-stu-id="d1199-238">/link (C# Compiler Options)</span></span>](../../../../csharp/language-reference/compiler-options/link-compiler-option.md)
- [<span data-ttu-id="d1199-239">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="d1199-239">C# Programming Guide</span></span>](../../../../csharp/programming-guide/index.md)
- [<span data-ttu-id="d1199-240">Programar con ensamblados</span><span class="sxs-lookup"><span data-stu-id="d1199-240">Programming with Assemblies</span></span>](../../../../framework/app-domains/programming-with-assemblies.md)
- <span data-ttu-id="d1199-241">[Assemblies and the Global Assembly Cache (C#)](../../../../csharp/programming-guide/concepts/assemblies-gac/index.md) (Ensamblados y caché global de ensamblados [C#])</span><span class="sxs-lookup"><span data-stu-id="d1199-241">[Assemblies and the Global Assembly Cache (C#)](../../../../csharp/programming-guide/concepts/assemblies-gac/index.md)</span></span>
