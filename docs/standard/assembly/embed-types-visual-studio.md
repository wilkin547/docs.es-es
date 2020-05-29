---
title: 'Tutorial: Inserción de tipos de ensamblados administrados en Visual Studio'
description: En este tutorial se muestra cómo insertar tipos de ensamblados administrados en .NET mediante Visual Studio. Los tipos insertados pueden admitir la independencia de versiones.
ms.date: 08/19/2019
ms.assetid: 55ed13c9-c5bb-4bc2-bcd8-0587eb568864
dev_langs:
- csharp
- vb
ms.openlocfilehash: 636e5f8095b64cd0f445555c96d00945ccf7eaf8
ms.sourcegitcommit: d6bd7903d7d46698e9d89d3725f3bb4876891aa3
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/13/2020
ms.locfileid: "83378985"
---
# <a name="walkthrough-embed-types-from-managed-assemblies-in-visual-studio"></a><span data-ttu-id="02c88-104">Tutorial: Inserción de tipos de ensamblados administrados en Visual Studio</span><span class="sxs-lookup"><span data-stu-id="02c88-104">Walkthrough: Embed types from managed assemblies in Visual Studio</span></span>

<span data-ttu-id="02c88-105">Si inserta información de tipos de un ensamblado administrado con nombre seguro, puede acoplar tipos holgadamente en una aplicación para lograr independencia de versiones.</span><span class="sxs-lookup"><span data-stu-id="02c88-105">If you embed type information from a strong-named managed assembly, you can loosely couple types in an application to achieve version independence.</span></span> <span data-ttu-id="02c88-106">Es decir, el programa puede escribirse de modo que use tipos de cualquier versión de una biblioteca administrada sin tener que volver a compilarse para cada nueva versión.</span><span class="sxs-lookup"><span data-stu-id="02c88-106">That is, your program can be written to use types from any version of a managed library without having to be recompiled for each new version.</span></span>

<span data-ttu-id="02c88-107">La inserción de tipos se usa a menudo con interoperabilidad COM, como, por ejemplo, una aplicación que use objetos de automatización de Microsoft Office.</span><span class="sxs-lookup"><span data-stu-id="02c88-107">Type embedding is frequently used with COM interop, such as an application that uses automation objects from Microsoft Office.</span></span> <span data-ttu-id="02c88-108">La inserción de información de tipos permite que la misma versión de un programa funcione con distintas versiones de Microsoft Office en equipos diferentes.</span><span class="sxs-lookup"><span data-stu-id="02c88-108">Embedding type information enables the same build of a program to work with different versions of Microsoft Office on different computers.</span></span> <span data-ttu-id="02c88-109">No obstante, la inserción de tipos también se puede usar con soluciones totalmente administradas.</span><span class="sxs-lookup"><span data-stu-id="02c88-109">However, you can also use type embedding with fully managed solutions.</span></span>

<span data-ttu-id="02c88-110">Después de especificar las interfaces públicas que se pueden insertar, puede crear clases de tiempo de ejecución que implementen esas interfaces.</span><span class="sxs-lookup"><span data-stu-id="02c88-110">After you specify the public interfaces that can be embedded, you create runtime classes that implement those interfaces.</span></span> <span data-ttu-id="02c88-111">Un programa cliente puede incrustar la información de tipo de las interfaces en tiempo de diseño haciendo referencia al ensamblado que contiene la configuración y las interfaces públicas de la propiedad `Embed Interop Types` de la referencia a `True`.</span><span class="sxs-lookup"><span data-stu-id="02c88-111">A client program can embed the type information for the interfaces at design time by referencing the assembly that contains the public interfaces and setting the `Embed Interop Types` property of the reference to `True`.</span></span> <span data-ttu-id="02c88-112">A continuación, el programa cliente puede cargar instancias de los objetos de tiempo de ejecución escritos como esas interfaces.</span><span class="sxs-lookup"><span data-stu-id="02c88-112">The client program can then load instances of the runtime objects typed as those interfaces.</span></span> <span data-ttu-id="02c88-113">Esto equivale a usar el compilador de línea de comandos y hacer referencia al ensamblado mediante la [opción -link del compilador](../../csharp/language-reference/compiler-options/link-compiler-option.md).</span><span class="sxs-lookup"><span data-stu-id="02c88-113">This is equivalent to using the command line compiler and referencing the assembly by using the [-link compiler option](../../csharp/language-reference/compiler-options/link-compiler-option.md).</span></span>

<span data-ttu-id="02c88-114">Si crea otra versión del ensamblado de tiempo de ejecución con nombre seguro, el programa cliente no tiene que volver a compilarse.</span><span class="sxs-lookup"><span data-stu-id="02c88-114">If you create a new version of your strong-named runtime assembly, the client program doesn't have to be recompiled.</span></span> <span data-ttu-id="02c88-115">El programa cliente sigue usando cualquier versión del ensamblado de tiempo de ejecución que encuentre disponible y usa la información de tipo insertada para las interfaces públicas.</span><span class="sxs-lookup"><span data-stu-id="02c88-115">The client program continues to use whichever version of the runtime assembly is available to it, using the embedded type information for the public interfaces.</span></span>

<span data-ttu-id="02c88-116">En este tutorial, hará lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="02c88-116">In this walkthrough, you:</span></span>

1. <span data-ttu-id="02c88-117">Crear un ensamblado con nombre seguro que tenga una interfaz pública e incluya información de tipo que se puede insertar.</span><span class="sxs-lookup"><span data-stu-id="02c88-117">Create a strong-named assembly with a public interface containing type information that can be embedded.</span></span>
1. <span data-ttu-id="02c88-118">Crear un ensamblado de tiempo de ejecución con nombre seguro que implemente la interfaz pública.</span><span class="sxs-lookup"><span data-stu-id="02c88-118">Create a strong-named runtime assembly that implements the public interface.</span></span>
1. <span data-ttu-id="02c88-119">Crear un programa cliente que inserte la información de tipo de la interfaz pública y cree una instancia de la clase del ensamblado en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="02c88-119">Create a client program that embeds the type information from the public interface and creates an instance of the class from the runtime assembly.</span></span>
1. <span data-ttu-id="02c88-120">Modificar y recompilar el ensamblado en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="02c88-120">Modify and rebuild the runtime assembly.</span></span>
1. <span data-ttu-id="02c88-121">Ejecute el programa cliente para ver que usa la nueva versión del ensamblado de tiempo de ejecución sin tener que volver a compilarlo.</span><span class="sxs-lookup"><span data-stu-id="02c88-121">Run the client program to see that it uses the new version of the runtime assembly without having to be recompiled.</span></span>

[!INCLUDE[note_settings_general](../../../includes/note-settings-general-md.md)]

## <a name="conditions-and-limitations"></a><span data-ttu-id="02c88-122">Condiciones y limitaciones</span><span class="sxs-lookup"><span data-stu-id="02c88-122">Conditions and limitations</span></span>

<span data-ttu-id="02c88-123">Puede insertar información de tipos desde un ensamblado si se dan las siguientes condiciones:</span><span class="sxs-lookup"><span data-stu-id="02c88-123">You can embed type information from an assembly under the following conditions:</span></span>

- <span data-ttu-id="02c88-124">El ensamblado expone al menos una interfaz pública.</span><span class="sxs-lookup"><span data-stu-id="02c88-124">The assembly exposes at least one public interface.</span></span>
- <span data-ttu-id="02c88-125">Las interfaces insertadas se anotan con atributos `ComImport` y atributos `Guid` con GUID únicos.</span><span class="sxs-lookup"><span data-stu-id="02c88-125">The embedded interfaces are annotated with `ComImport` attributes and `Guid` attributes with unique GUIDs.</span></span>
- <span data-ttu-id="02c88-126">El ensamblado se anota con los atributos `ImportedFromTypeLib` o `PrimaryInteropAssembly` y un atributo `Guid` de nivel de ensamblado.</span><span class="sxs-lookup"><span data-stu-id="02c88-126">The assembly is annotated with the `ImportedFromTypeLib` attribute or the `PrimaryInteropAssembly` attribute, and an assembly-level `Guid` attribute.</span></span> <span data-ttu-id="02c88-127">Las plantillas de proyecto de Visual C# y Visual Basic incluyen un atributo `Guid` de nivel de ensamblado de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="02c88-127">The Visual C# and Visual Basic project templates include an assembly-level `Guid` attribute by default.</span></span>

<span data-ttu-id="02c88-128">Dado que la función principal de la inserción de tipos es admitir ensamblados de interoperabilidad COM, cuando se inserta información de tipos en una solución totalmente administrada, se aplican las siguientes limitaciones:</span><span class="sxs-lookup"><span data-stu-id="02c88-128">Because the primary function of type embedding is to support COM interop assemblies, the following limitations apply when you embed type information in a fully-managed solution:</span></span>

- <span data-ttu-id="02c88-129">Solo se insertan los atributos específicos de interoperabilidad COM.</span><span class="sxs-lookup"><span data-stu-id="02c88-129">Only attributes specific to COM interop are embedded.</span></span> <span data-ttu-id="02c88-130">El resto de atributos se omiten.</span><span class="sxs-lookup"><span data-stu-id="02c88-130">Other attributes are ignored.</span></span>
- <span data-ttu-id="02c88-131">Si un tipo usa parámetros genéricos y el tipo del parámetro genérico es insertado, ese tipo no se puede usar más allá de un límite de ensamblado.</span><span class="sxs-lookup"><span data-stu-id="02c88-131">If a type uses generic parameters, and the type of the generic parameter is an embedded type, that type cannot be used across an assembly boundary.</span></span> <span data-ttu-id="02c88-132">Entre los ejemplos de cruce de un límite de ensamblado se incluyen llamar a un método desde otro ensamblado o derivar un tipo desde un tipo definido en otro ensamblado.</span><span class="sxs-lookup"><span data-stu-id="02c88-132">Examples of crossing an assembly boundary include calling a method from another assembly or deriving a type from a type defined in another assembly.</span></span>
- <span data-ttu-id="02c88-133">Las constantes no se insertan.</span><span class="sxs-lookup"><span data-stu-id="02c88-133">Constants are not embedded.</span></span>
- <span data-ttu-id="02c88-134">La clase <xref:System.Collections.Generic.Dictionary%602?displayProperty=nameWithType> no admite un tipo insertado como clave.</span><span class="sxs-lookup"><span data-stu-id="02c88-134">The <xref:System.Collections.Generic.Dictionary%602?displayProperty=nameWithType> class does not support an embedded type as a key.</span></span> <span data-ttu-id="02c88-135">Puede implementar su propio tipo de diccionario que admita un tipo insertado como clave.</span><span class="sxs-lookup"><span data-stu-id="02c88-135">You can implement your own dictionary type to support an embedded type as a key.</span></span>

## <a name="create-an-interface"></a><span data-ttu-id="02c88-136">Creación de una interfaz</span><span class="sxs-lookup"><span data-stu-id="02c88-136">Create an interface</span></span>

<span data-ttu-id="02c88-137">El primer paso es crear el ensamblado de la interfaz de equivalencia de tipos.</span><span class="sxs-lookup"><span data-stu-id="02c88-137">The first step is to create the type equivalence interface assembly.</span></span>

1. <span data-ttu-id="02c88-138">En Visual Studio, seleccione **Archivo** > **Nuevo** > **Proyecto**.</span><span class="sxs-lookup"><span data-stu-id="02c88-138">In Visual Studio, select **File** > **New** > **Project**.</span></span>

1. <span data-ttu-id="02c88-139">En el cuadro de diálogo **Crear un nuevo proyecto**, escriba *biblioteca de clases* en el cuadro **Buscar plantillas**.</span><span class="sxs-lookup"><span data-stu-id="02c88-139">In the **Create a new project** dialog box, type *class library* in the **Search for templates** box.</span></span> <span data-ttu-id="02c88-140">Seleccione la plantilla **Biblioteca de clases (.NET Framework)** de C# o Visual Basic de la lista y, luego, seleccione **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="02c88-140">Select either the C# or Visual Basic **Class Library (.NET Framework)** template from the list, and then select **Next**.</span></span>

1. <span data-ttu-id="02c88-141">En el cuadro de diálogo **Configure su nuevo proyecto**, en **Nombre del proyecto**, escriba *TypeEquivalenceInterface* y, a continuación, seleccione **Crear**.</span><span class="sxs-lookup"><span data-stu-id="02c88-141">In the **Configure your new project** dialog box, under **Project name**, type *TypeEquivalenceInterface*, and then select **Create**.</span></span> <span data-ttu-id="02c88-142">Se crea el proyecto.</span><span class="sxs-lookup"><span data-stu-id="02c88-142">The new project is created.</span></span>

1. <span data-ttu-id="02c88-143">En el **Explorador de soluciones**, haga clic con el botón derecho en el archivo *Class1.cs* o en *Class1.vb*, seleccione **Cambiar nombre** y cambie el nombre del archivo de *Class1* a *ISampleInterface*.</span><span class="sxs-lookup"><span data-stu-id="02c88-143">In **Solution Explorer**, right-click the *Class1.cs* or *Class1.vb* file, select **Rename**, and rename the file from *Class1* to *ISampleInterface*.</span></span> <span data-ttu-id="02c88-144">Responda **Sí** al aviso para cambiar también el nombre de la clase a `ISampleInterface`.</span><span class="sxs-lookup"><span data-stu-id="02c88-144">Respond **Yes** to the prompt to also rename the class to `ISampleInterface`.</span></span> <span data-ttu-id="02c88-145">Esta clase representa la interfaz pública de la clase.</span><span class="sxs-lookup"><span data-stu-id="02c88-145">This class represents the public interface for the class.</span></span>

1. <span data-ttu-id="02c88-146">En el **Explorador de soluciones**, haga clic con el botón derecho en el proyecto **TypeEquivalenceInterface** y, a continuación, seleccione **Propiedades**.</span><span class="sxs-lookup"><span data-stu-id="02c88-146">In **Solution Explorer**, right-click the **TypeEquivalenceInterface** project, and then select **Properties**.</span></span>

1. <span data-ttu-id="02c88-147">Seleccione **Compilar** en el panel izquierdo de la pantalla **Propiedades** y establezca la **Ruta de acceso de salida** en una ubicación del equipo, como *C:\TypeEquivalenceSample* .</span><span class="sxs-lookup"><span data-stu-id="02c88-147">Select **Build** on the left pane of the **Properties** screen, and set the **Output path** to a location on your computer, such as *C:\TypeEquivalenceSample*.</span></span> <span data-ttu-id="02c88-148">En este tutorial se utiliza la misma ubicación.</span><span class="sxs-lookup"><span data-stu-id="02c88-148">You use the same location throughout this walkthrough.</span></span>

1. <span data-ttu-id="02c88-149">Seleccione **Firmar** en el panel izquierdo de la pantalla **Propiedades** y, a continuación, active la casilla **Firmar el ensamblado**.</span><span class="sxs-lookup"><span data-stu-id="02c88-149">Select **Signing** on the left pane of the **Properties** screen, and then select the **Sign the assembly** check box.</span></span> <span data-ttu-id="02c88-150">En la lista desplegable de **Elija un archivo de clave de nombre seguro**, seleccione **Nuevo**.</span><span class="sxs-lookup"><span data-stu-id="02c88-150">In the dropdown for **Choose a strong name key file**, select **New**.</span></span>

1. <span data-ttu-id="02c88-151">En el cuadro de diálogo **Crear clave de nombre seguro**, en **Nombre de archivo de clave**, escriba *key.snk*.</span><span class="sxs-lookup"><span data-stu-id="02c88-151">In the **Create Strong Name Key** dialog, under **Key file name**, type *key.snk*.</span></span> <span data-ttu-id="02c88-152">Desactive la casilla **Proteger mi archivo de clave mediante contraseña** y, a continuación, seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="02c88-152">Deselect the **Protect my key file with a password** check box, and then select **OK**.</span></span>

1. <span data-ttu-id="02c88-153">Abra el archivo de clase *ISampleInterface* en el editor de código y reemplace su contenido por el código siguiente para crear la interfaz `ISampleInterface`:</span><span class="sxs-lookup"><span data-stu-id="02c88-153">Open the *ISampleInterface* class file in the code editor, and replace its contents with the following code to create the `ISampleInterface` interface:</span></span>

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

   ```vb
   Imports System.Runtime.InteropServices

   <ComImport()>
   <Guid("8DA56996-A151-4136-B474-32784559F6DF")>
   Public Interface ISampleInterface
       Sub GetUserInput()
       ReadOnly Property UserInput As String
   End Interface
   ```

1. <span data-ttu-id="02c88-154">En el menú **Herramientas**, seleccione **Crear GUID** y, en el cuadro de diálogo **Crear GUID**, seleccione **Formato de registro**.</span><span class="sxs-lookup"><span data-stu-id="02c88-154">On the **Tools** menu, select **Create Guid**, and in the **Create GUID** dialog box, select **Registry Format**.</span></span> <span data-ttu-id="02c88-155">Seleccione **Copiar** y, a continuación, **Salir**.</span><span class="sxs-lookup"><span data-stu-id="02c88-155">Select **Copy**, and then select **Exit**.</span></span>

1. <span data-ttu-id="02c88-156">En el atributo `Guid` del código, reemplace el GUID de ejemplo por el GUID que ha copiado y elimine las llaves ( **{ }** ).</span><span class="sxs-lookup"><span data-stu-id="02c88-156">In the `Guid` attribute of your code, replace the sample GUID with the GUID you copied, and remove the braces (**{ }**).</span></span>

1. <span data-ttu-id="02c88-157">En el **Explorador de soluciones**, expanda la carpeta **Propiedades** y seleccione el archivo *AssemblyInfo.cs* o el archivo *AssemblyInfo.vb*.</span><span class="sxs-lookup"><span data-stu-id="02c88-157">In **Solution Explorer**, expand the **Properties** folder and select the *AssemblyInfo.cs* or *AssemblyInfo.vb* file.</span></span> <span data-ttu-id="02c88-158">En el editor de código, agregue el siguiente atributo al archivo:</span><span class="sxs-lookup"><span data-stu-id="02c88-158">In the code editor, add the following attribute to the file:</span></span>

   ```csharp
   [assembly: ImportedFromTypeLib("")]
   ```

   ```vb
   <Assembly: ImportedFromTypeLib("")>
   ```

1. <span data-ttu-id="02c88-159">Seleccione **Archivo** > **Guardar todo** o presione **Ctrl**+**Mayús**+**S** para guardar los archivos y el proyecto.</span><span class="sxs-lookup"><span data-stu-id="02c88-159">Select **File** > **Save All** or press **Ctrl**+**Shift**+**S** to save the files and project.</span></span>

1. <span data-ttu-id="02c88-160">En el **Explorador de soluciones**, haga clic con el botón derecho en el proyecto **TypeEquivalenceInterface** y seleccione **Compilar**.</span><span class="sxs-lookup"><span data-stu-id="02c88-160">In **Solution Explorer**, right-click the **TypeEquivalenceInterface** project and select **Build**.</span></span> <span data-ttu-id="02c88-161">El archivo DLL de biblioteca de clases se compila y se guarda en la ruta de acceso de salida de la compilación especificada, por ejemplo, *C:\TypeEquivalenceSample*.</span><span class="sxs-lookup"><span data-stu-id="02c88-161">The class library DLL file is compiled and saved to the specified build output path, for example *C:\TypeEquivalenceSample*.</span></span>

## <a name="create-a-runtime-class"></a><span data-ttu-id="02c88-162">Creación de una clase en tiempo de ejecución</span><span class="sxs-lookup"><span data-stu-id="02c88-162">Create a runtime class</span></span>

<span data-ttu-id="02c88-163">A continuación, cree la clase en tiempo de ejecución de equivalencia de tipos.</span><span class="sxs-lookup"><span data-stu-id="02c88-163">Next, create the type equivalence runtime class.</span></span>

1. <span data-ttu-id="02c88-164">En Visual Studio, seleccione **Archivo** > **Nuevo** > **Proyecto**.</span><span class="sxs-lookup"><span data-stu-id="02c88-164">In Visual Studio, select **File** > **New** > **Project**.</span></span>

1. <span data-ttu-id="02c88-165">En el cuadro de diálogo **Crear un nuevo proyecto**, escriba *biblioteca de clases* en el cuadro **Buscar plantillas**.</span><span class="sxs-lookup"><span data-stu-id="02c88-165">In the **Create a new project** dialog box, type *class library* in the **Search for templates** box.</span></span> <span data-ttu-id="02c88-166">Seleccione la plantilla **Biblioteca de clases (.NET Framework)** de C# o Visual Basic de la lista y, luego, seleccione **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="02c88-166">Select either the C# or Visual Basic **Class Library (.NET Framework)** template from the list, and then select **Next**.</span></span>

1. <span data-ttu-id="02c88-167">En el cuadro de diálogo **Configure su nuevo proyecto**, en **Nombre del proyecto**, escriba *TypeEquivalenceRuntime* y, a continuación, seleccione **Crear**.</span><span class="sxs-lookup"><span data-stu-id="02c88-167">In the **Configure your new project** dialog box, under **Project name**, type *TypeEquivalenceRuntime*, and then select **Create**.</span></span> <span data-ttu-id="02c88-168">Se crea el proyecto.</span><span class="sxs-lookup"><span data-stu-id="02c88-168">The new project is created.</span></span>

1. <span data-ttu-id="02c88-169">En el **Explorador de soluciones**, haga clic con el botón derecho en el archivo *Class1.cs* o en *Class1.vb*, seleccione **Cambiar nombre** y cambie el nombre del archivo de *Class1* a *SampleClass*.</span><span class="sxs-lookup"><span data-stu-id="02c88-169">In **Solution Explorer**, right-click the *Class1.cs* or *Class1.vb* file, select **Rename**, and rename the file from *Class1* to *SampleClass*.</span></span> <span data-ttu-id="02c88-170">Responda **Sí** al aviso para cambiar también el nombre de la clase a `SampleClass`.</span><span class="sxs-lookup"><span data-stu-id="02c88-170">Respond **Yes** to the prompt to also rename the class to `SampleClass`.</span></span> <span data-ttu-id="02c88-171">Esta clase implementa la interfaz `ISampleInterface` .</span><span class="sxs-lookup"><span data-stu-id="02c88-171">This class implements the `ISampleInterface` interface.</span></span>

1. <span data-ttu-id="02c88-172">En el **Explorador de soluciones**, haga clic con el botón derecho en el proyecto **TypeEquivalenceInterface** y seleccione **Propiedades**.</span><span class="sxs-lookup"><span data-stu-id="02c88-172">In **Solution Explorer**, right-click the **TypeEquivalenceInterface** project and select **Properties**.</span></span>

1. <span data-ttu-id="02c88-173">Seleccione **Compilar** en el panel izquierdo de la pantalla **Propiedades** y establezca la **Ruta de acceso de salida** en la misma ubicación que usó para el proyecto TypeEquivalenceInterface, por ejemplo, *C:\TypeEquivalenceSample*.</span><span class="sxs-lookup"><span data-stu-id="02c88-173">Select **Build** on the left pane of the **Properties** screen, and then set the **Output path** to the same location you used for the TypeEquivalenceInterface project, for example, *C:\TypeEquivalenceSample*.</span></span>

1. <span data-ttu-id="02c88-174">Seleccione **Firmar** en el panel izquierdo de la pantalla **Propiedades** y, a continuación, active la casilla **Firmar el ensamblado**.</span><span class="sxs-lookup"><span data-stu-id="02c88-174">Select **Signing** on the left pane of the **Properties** screen, and then select the **Sign the assembly** check box.</span></span> <span data-ttu-id="02c88-175">En la lista desplegable de **Elija un archivo de clave de nombre seguro**, seleccione **Nuevo**.</span><span class="sxs-lookup"><span data-stu-id="02c88-175">In the dropdown for **Choose a strong name key file**, select **New**.</span></span>

1. <span data-ttu-id="02c88-176">En el cuadro de diálogo **Crear clave de nombre seguro**, en **Nombre de archivo de clave**, escriba *key.snk*.</span><span class="sxs-lookup"><span data-stu-id="02c88-176">In the **Create Strong Name Key** dialog, under **Key file name**, type *key.snk*.</span></span> <span data-ttu-id="02c88-177">Desactive la casilla **Proteger mi archivo de clave mediante contraseña** y, a continuación, seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="02c88-177">Deselect the **Protect my key file with a password** check box, and then select **OK**.</span></span>

1. <span data-ttu-id="02c88-178">En el **Explorador de soluciones**, haga clic con el botón derecho en el proyecto **TypeEquivalenceRuntime** y seleccione **Agregar** > **referencia**.</span><span class="sxs-lookup"><span data-stu-id="02c88-178">In **Solution Explorer**, right-click the **TypeEquivalenceRuntime** project and select **Add** > **Reference**.</span></span>

1. <span data-ttu-id="02c88-179">En el cuadro de diálogo **Administrador de referencias**, seleccione **Examinar** y vaya a la ruta de acceso de la carpeta de salida.</span><span class="sxs-lookup"><span data-stu-id="02c88-179">In the **Reference Manager** dialog, select **Browse** and browse to the output path folder.</span></span> <span data-ttu-id="02c88-180">Seleccione el archivo *TypeEquivalenceInterface.dll*, seleccione **Agregar** y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="02c88-180">Select the *TypeEquivalenceInterface.dll* file, select **Add**, and then select **OK**.</span></span>

1. <span data-ttu-id="02c88-181">En el **Explorador de soluciones**, expanda la carpeta **Referencias** y seleccione la referencia **TypeEquivalenceInterface**.</span><span class="sxs-lookup"><span data-stu-id="02c88-181">In **Solution Explorer**, expand the **References** folder and select the **TypeEquivalenceInterface** reference.</span></span> <span data-ttu-id="02c88-182">En el panel **Propiedades**, establezca **Versión específica** en **False** si aún no lo está.</span><span class="sxs-lookup"><span data-stu-id="02c88-182">In the **Properties** pane, set **Specific Version** to **False** if it is not already.</span></span>

1. <span data-ttu-id="02c88-183">Abra el archivo de clase *SampleClass* en el editor de código y reemplace su contenido por el código siguiente para crear la clase `SampleClass`:</span><span class="sxs-lookup"><span data-stu-id="02c88-183">Open the *SampleClass* class file in the code editor, and replace its contents with the following code to create the `SampleClass` class:</span></span>

   ```csharp
   using System;
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

1. <span data-ttu-id="02c88-184">Seleccione **Archivo** > **Guardar todo** o presione **Ctrl**+**Mayús**+**S** para guardar los archivos y el proyecto.</span><span class="sxs-lookup"><span data-stu-id="02c88-184">Select **File** > **Save All** or press **Ctrl**+**Shift**+**S** to save the files and project.</span></span>

1. <span data-ttu-id="02c88-185">En el **Explorador de soluciones**, haga clic con el botón derecho en el proyecto **TypeEquivalenceRuntime** y seleccione **Compilar**.</span><span class="sxs-lookup"><span data-stu-id="02c88-185">In **Solution Explorer**, right-click the **TypeEquivalenceRuntime** project and select **Build**.</span></span> <span data-ttu-id="02c88-186">El archivo DLL de biblioteca de clases se compila y se guarda en la ruta de acceso de salida de la compilación especificada.</span><span class="sxs-lookup"><span data-stu-id="02c88-186">The class library DLL file is compiled and saved to the specified build output path.</span></span>

## <a name="create-a-client-project"></a><span data-ttu-id="02c88-187">Creación de un proyecto de cliente</span><span class="sxs-lookup"><span data-stu-id="02c88-187">Create a client project</span></span>

<span data-ttu-id="02c88-188">Por último, cree un programa cliente de equivalencia de tipos que haga referencia al ensamblado de la interfaz.</span><span class="sxs-lookup"><span data-stu-id="02c88-188">Finally, create a type equivalence client program that references the interface assembly.</span></span>

1. <span data-ttu-id="02c88-189">En Visual Studio, seleccione **Archivo** > **Nuevo** > **Proyecto**.</span><span class="sxs-lookup"><span data-stu-id="02c88-189">In Visual Studio, select **File** > **New** > **Project**.</span></span>

1. <span data-ttu-id="02c88-190">En el cuadro de diálogo **Crear un nuevo proyecto**, escriba *consola* en el cuadro **Buscar plantillas**.</span><span class="sxs-lookup"><span data-stu-id="02c88-190">In the **Create a new project** dialog box, type *console* in the **Search for templates** box.</span></span> <span data-ttu-id="02c88-191">Seleccione la plantilla **Aplicación de consola (.NET Framework)** de C# o Visual Basic de la lista y, a continuación, seleccione **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="02c88-191">Select either the C# or Visual Basic **Console App (.NET Framework)** template from the list, and then select **Next**.</span></span>

1. <span data-ttu-id="02c88-192">En el cuadro de diálogo **Configure su nuevo proyecto**, en **Nombre del proyecto**, escriba *TypeEquivalenceClient* y, a continuación, seleccione **Crear**.</span><span class="sxs-lookup"><span data-stu-id="02c88-192">In the **Configure your new project** dialog box, under **Project name**, type *TypeEquivalenceClient*, and then select **Create**.</span></span> <span data-ttu-id="02c88-193">Se crea el proyecto.</span><span class="sxs-lookup"><span data-stu-id="02c88-193">The new project is created.</span></span>

1. <span data-ttu-id="02c88-194">En el **Explorador de soluciones**, haga clic con el botón derecho en el proyecto **TypeEquivalenceClient** y seleccione **Propiedades**.</span><span class="sxs-lookup"><span data-stu-id="02c88-194">In **Solution Explorer**, right-click the **TypeEquivalenceClient** project and select **Properties**.</span></span>

1. <span data-ttu-id="02c88-195">Seleccione **Compilar** en el panel izquierdo de la pantalla **Propiedades** y establezca la **Ruta de acceso de salida** en la misma ubicación que usó para el proyecto TypeEquivalenceInterface, por ejemplo, *C:\TypeEquivalenceSample*.</span><span class="sxs-lookup"><span data-stu-id="02c88-195">Select **Build** on the left pane of the **Properties** screen, and then set the **Output path** to the same location you used for the TypeEquivalenceInterface project, for example, *C:\TypeEquivalenceSample*.</span></span>

1. <span data-ttu-id="02c88-196">En el **Explorador de soluciones**, haga clic con el botón derecho en el proyecto **TypeEquivalenceClient** y seleccione **Agregar** > **referencia**.</span><span class="sxs-lookup"><span data-stu-id="02c88-196">In **Solution Explorer**, right-click the **TypeEquivalenceClient** project and select **Add** > **Reference**.</span></span>

1. <span data-ttu-id="02c88-197">En el cuadro de diálogo **Administrador de referencias**, si el archivo **TypeEquivalenceInterface.dll** ya aparece en la lista, selecciónelo.</span><span class="sxs-lookup"><span data-stu-id="02c88-197">In the **Reference Manager** dialog, if the **TypeEquivalenceInterface.dll** file is already listed, select it.</span></span> <span data-ttu-id="02c88-198">Si no es así, seleccione **Examinar**, vaya a la carpeta de la ruta de acceso de salida, seleccione el archivo *TypeEquivalenceInterface.dll* (no *TypeEquivalenceRuntime.dll*) y, después, seleccione **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="02c88-198">If not, select **Browse**, browse to the output path folder, select the *TypeEquivalenceInterface.dll* file (not the *TypeEquivalenceRuntime.dll*), and select **Add**.</span></span> <span data-ttu-id="02c88-199">Seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="02c88-199">Select **OK**.</span></span>

1. <span data-ttu-id="02c88-200">En el **Explorador de soluciones**, expanda la carpeta **Referencias** y seleccione la referencia **TypeEquivalenceInterface**.</span><span class="sxs-lookup"><span data-stu-id="02c88-200">In **Solution Explorer**, expand the **References** folder and select the **TypeEquivalenceInterface** reference.</span></span> <span data-ttu-id="02c88-201">En el panel **Propiedades**, establezca **Incrustar tipos de interoperabilidad** en **True**.</span><span class="sxs-lookup"><span data-stu-id="02c88-201">In the **Properties** pane, set **Embed Interop Types** to **True**.</span></span>

1. <span data-ttu-id="02c88-202">Abra el archivo *Program.cs* o el archivo *Module1.vb* en el editor de código y reemplace su contenido por el código siguiente para crear el programa cliente:</span><span class="sxs-lookup"><span data-stu-id="02c88-202">Open the *Program.cs* or *Module1.vb* file in the code editor, and replace its contents with the following code to create the client program:</span></span>

   ```csharp
   using System;
   using System.Reflection;
   using TypeEquivalenceInterface;

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

   ```vb
   Imports System.Reflection
   Imports TypeEquivalenceInterface

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

1. <span data-ttu-id="02c88-203">Seleccione **Archivo** > **Guardar todo** o presione **Ctrl**+**Mayús**+**S** para guardar los archivos y el proyecto.</span><span class="sxs-lookup"><span data-stu-id="02c88-203">Select **File** > **Save All** or press **Ctrl**+**Shift**+**S** to save the files and project.</span></span>

1. <span data-ttu-id="02c88-204">Presione **Ctrl**+**F5** para compilar y ejecutar el programa.</span><span class="sxs-lookup"><span data-stu-id="02c88-204">Press **Ctrl**+**F5** to build and run the program.</span></span> <span data-ttu-id="02c88-205">Tenga en cuenta que la salida de la consola devuelve la versión de ensamblado **1.0.0.0**.</span><span class="sxs-lookup"><span data-stu-id="02c88-205">Note that the console output returns the assembly version **1.0.0.0**.</span></span>

## <a name="modify-the-interface"></a><span data-ttu-id="02c88-206">Modificación de la interfaz</span><span class="sxs-lookup"><span data-stu-id="02c88-206">Modify the interface</span></span>

<span data-ttu-id="02c88-207">Ahora, modifique el ensamblado de la interfaz y cambie su versión.</span><span class="sxs-lookup"><span data-stu-id="02c88-207">Now, modify the interface assembly, and change its version.</span></span>

1. <span data-ttu-id="02c88-208">En Visual Studio, seleccione **Archivo** > **Abrir** > **Proyecto o solución** y abra el proyecto **TypeEquivalenceInterface**.</span><span class="sxs-lookup"><span data-stu-id="02c88-208">In Visual Studio, select **File** > **Open** > **Project/Solution**, and open the **TypeEquivalenceInterface** project.</span></span>

1. <span data-ttu-id="02c88-209">En el **Explorador de soluciones**, haga clic con el botón derecho en el proyecto **TypeEquivalenceInterface** y seleccione **Propiedades**.</span><span class="sxs-lookup"><span data-stu-id="02c88-209">In **Solution Explorer**, right-click the **TypeEquivalenceInterface** project and select **Properties**.</span></span>

1. <span data-ttu-id="02c88-210">Seleccione **Aplicación** en el panel izquierdo de la pantalla **Propiedades** y, a continuación, seleccione **Información de ensamblado**.</span><span class="sxs-lookup"><span data-stu-id="02c88-210">Select **Application** on the left pane of the **Properties** screen, and then select **Assembly Information**.</span></span>

1. <span data-ttu-id="02c88-211">En el cuadro de diálogo **Información de ensamblado**, cambie los valores de **Versión del ensamblado** y **Versión del archivo** a *2.0.0.0* y, a continuación, seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="02c88-211">In the **Assembly Information** dialog box, change the **Assembly version** and **File version** values to *2.0.0.0*, and then select **OK**.</span></span>

1. <span data-ttu-id="02c88-212">Abra el archivo *SampleInterface.cs* o *SampleInterface.vb* y agregue la siguiente línea de código a la interfaz `ISampleInterface`:</span><span class="sxs-lookup"><span data-stu-id="02c88-212">Open the *SampleInterface.cs* or *SampleInterface.vb* file, and add the following line of code to the `ISampleInterface` interface:</span></span>

   ```csharp
   DateTime GetDate();
   ```

   ```vb
   Function GetDate() As Date
   ```

1. <span data-ttu-id="02c88-213">Seleccione **Archivo** > **Guardar todo** o presione **Ctrl**+**Mayús**+**S** para guardar los archivos y el proyecto.</span><span class="sxs-lookup"><span data-stu-id="02c88-213">Select **File** > **Save All** or press **Ctrl**+**Shift**+**S** to save the files and project.</span></span>

1. <span data-ttu-id="02c88-214">En el **Explorador de soluciones**, haga clic con el botón derecho en el proyecto **TypeEquivalenceInterface** y seleccione **Compilar**.</span><span class="sxs-lookup"><span data-stu-id="02c88-214">In **Solution Explorer**, right-click the **TypeEquivalenceInterface** project and select **Build**.</span></span> <span data-ttu-id="02c88-215">Se compila una nueva versión del archivo DLL de biblioteca de clases y se guarda en la ruta de acceso de salida de la compilación.</span><span class="sxs-lookup"><span data-stu-id="02c88-215">A new version of the class library DLL file is compiled and saved to the build output path.</span></span>

## <a name="modify-the-runtime-class"></a><span data-ttu-id="02c88-216">Modificación de la clase en tiempo de ejecución</span><span class="sxs-lookup"><span data-stu-id="02c88-216">Modify the runtime class</span></span>

<span data-ttu-id="02c88-217">Modifique también la clase en tiempo de ejecución y actualice su versión.</span><span class="sxs-lookup"><span data-stu-id="02c88-217">Also modify the runtime class and update its version.</span></span>

1. <span data-ttu-id="02c88-218">En Visual Studio, seleccione **Archivo** > **Abrir** > **Proyecto o solución** y abra el proyecto **TypeEquivalenceRuntime**.</span><span class="sxs-lookup"><span data-stu-id="02c88-218">In Visual Studio, select **File** > **Open** > **Project/Solution**, and open the **TypeEquivalenceRuntime** project.</span></span>

1. <span data-ttu-id="02c88-219">En el **Explorador de soluciones**, haga clic con el botón derecho en el proyecto **TypeEquivalenceRuntime** y seleccione **Propiedades**.</span><span class="sxs-lookup"><span data-stu-id="02c88-219">In **Solution Explorer**, right-click the **TypeEquivalenceRuntime** project and select **Properties**.</span></span>

1. <span data-ttu-id="02c88-220">Seleccione **Aplicación** en el panel izquierdo de la pantalla **Propiedades** y, a continuación, seleccione **Información de ensamblado**.</span><span class="sxs-lookup"><span data-stu-id="02c88-220">Select **Application** on the left pane of the **Properties** screen, and then select **Assembly Information**.</span></span>

1. <span data-ttu-id="02c88-221">En el cuadro de diálogo **Información de ensamblado**, cambie los valores de **Versión del ensamblado** y **Versión del archivo** a *2.0.0.0* y, a continuación, seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="02c88-221">In the **Assembly Information** dialog box, change the **Assembly version** and **File version** values to *2.0.0.0*, and then select **OK**.</span></span>

1. <span data-ttu-id="02c88-222">Abra el archivo *SampleClass.cs* o el archivo *SampleClass.vb* y agregue el código siguiente a la clase `SampleClass`:</span><span class="sxs-lookup"><span data-stu-id="02c88-222">Open the *SampleClass.cs* or *SampleClass.vb* file, and add the following code to the `SampleClass` class:</span></span>

   ```csharp
    public DateTime GetDate()
    {
        return DateTime.Now;
    }
   ```

   ```vb
   Public Function GetDate() As DateTime Implements ISampleInterface.GetDate
       Return Now
   End Function
   ```

1. <span data-ttu-id="02c88-223">Seleccione **Archivo** > **Guardar todo** o presione **Ctrl**+**Mayús**+**S** para guardar los archivos y el proyecto.</span><span class="sxs-lookup"><span data-stu-id="02c88-223">Select **File** > **Save All** or press **Ctrl**+**Shift**+**S** to save the files and project.</span></span>

1. <span data-ttu-id="02c88-224">En el **Explorador de soluciones**, haga clic con el botón derecho en el proyecto **TypeEquivalenceRuntime** y seleccione **Compilar**.</span><span class="sxs-lookup"><span data-stu-id="02c88-224">In **Solution Explorer**, right-click the **TypeEquivalenceRuntime** project and select **Build**.</span></span> <span data-ttu-id="02c88-225">Se compila una nueva versión del archivo DLL de biblioteca de clases y se guarda en la ruta de acceso de salida de la compilación.</span><span class="sxs-lookup"><span data-stu-id="02c88-225">A new version of the class library DLL file is compiled and saved to the build output path.</span></span>

## <a name="run-the-updated-client-program"></a><span data-ttu-id="02c88-226">Ejecución del programa cliente actualizado</span><span class="sxs-lookup"><span data-stu-id="02c88-226">Run the updated client program</span></span>

<span data-ttu-id="02c88-227">Vaya a la ubicación de la carpeta de resultados de compilación y ejecute *TypeEquivalenceClient.exe*.</span><span class="sxs-lookup"><span data-stu-id="02c88-227">Go to the build output folder location and run *TypeEquivalenceClient.exe*.</span></span> <span data-ttu-id="02c88-228">Tenga en cuenta que la salida de la consola ahora refleja la nueva versión del ensamblado `TypeEquivalenceRuntime`, *2.0.0.0*, sin que el programa se vuelva a compilar.</span><span class="sxs-lookup"><span data-stu-id="02c88-228">Note that the console output now reflects the new version of the `TypeEquivalenceRuntime` assembly, *2.0.0.0*, without the program being recompiled.</span></span>

## <a name="see-also"></a><span data-ttu-id="02c88-229">Vea también</span><span class="sxs-lookup"><span data-stu-id="02c88-229">See also</span></span>

- [<span data-ttu-id="02c88-230">-link (Opciones del compilador de C#)</span><span class="sxs-lookup"><span data-stu-id="02c88-230">-link (C# Compiler Options)</span></span>](../../csharp/language-reference/compiler-options/link-compiler-option.md)
- [<span data-ttu-id="02c88-231">-link (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="02c88-231">-link (Visual Basic)</span></span>](../../visual-basic/reference/command-line-compiler/link.md)
- [<span data-ttu-id="02c88-232">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="02c88-232">C# programming guide</span></span>](../../csharp/programming-guide/index.md)
- [<span data-ttu-id="02c88-233">Conceptos de programación (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="02c88-233">Programming concepts (Visual Basic)</span></span>](../../visual-basic/programming-guide/concepts/index.md)
- [<span data-ttu-id="02c88-234">Ensamblados de .NET</span><span class="sxs-lookup"><span data-stu-id="02c88-234">Assemblies in .NET</span></span>](index.md)
