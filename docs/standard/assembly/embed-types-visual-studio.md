---
title: 'Tutorial: Inserción de tipos de ensamblados administrados en Visual Studio'
ms.date: 08/19/2019
ms.assetid: 55ed13c9-c5bb-4bc2-bcd8-0587eb568864
dev_langs:
- csharp
- vb
ms.openlocfilehash: f11fbedad766753ee462c5f597b823493cdaf7cf
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/25/2019
ms.locfileid: "75338555"
---
# <a name="walkthrough-embed-types-from-managed-assemblies-in-visual-studio"></a><span data-ttu-id="e7c5b-102">Tutorial: Inserción de tipos de ensamblados administrados en Visual Studio</span><span class="sxs-lookup"><span data-stu-id="e7c5b-102">Walkthrough: Embed types from managed assemblies in Visual Studio</span></span>

<span data-ttu-id="e7c5b-103">Si inserta información de tipos de un ensamblado administrado con nombre seguro, puede acoplar tipos holgadamente en una aplicación para lograr independencia de versiones.</span><span class="sxs-lookup"><span data-stu-id="e7c5b-103">If you embed type information from a strong-named managed assembly, you can loosely couple types in an application to achieve version independence.</span></span> <span data-ttu-id="e7c5b-104">Es decir, el programa puede escribirse de modo que use tipos de cualquier versión de una biblioteca administrada sin tener que volver a compilarse para cada nueva versión.</span><span class="sxs-lookup"><span data-stu-id="e7c5b-104">That is, your program can be written to use types from any version of a managed library without having to be recompiled for each new version.</span></span>

<span data-ttu-id="e7c5b-105">La inserción de tipos se usa a menudo con interoperabilidad COM, como, por ejemplo, una aplicación que use objetos de automatización de Microsoft Office.</span><span class="sxs-lookup"><span data-stu-id="e7c5b-105">Type embedding is frequently used with COM interop, such as an application that uses automation objects from Microsoft Office.</span></span> <span data-ttu-id="e7c5b-106">La inserción de información de tipos permite que la misma versión de un programa funcione con distintas versiones de Microsoft Office en equipos diferentes.</span><span class="sxs-lookup"><span data-stu-id="e7c5b-106">Embedding type information enables the same build of a program to work with different versions of Microsoft Office on different computers.</span></span> <span data-ttu-id="e7c5b-107">No obstante, la inserción de tipos también se puede usar con soluciones totalmente administradas.</span><span class="sxs-lookup"><span data-stu-id="e7c5b-107">However, you can also use type embedding with fully managed solutions.</span></span>

<span data-ttu-id="e7c5b-108">Después de especificar las interfaces públicas que se pueden insertar, puede crear clases de tiempo de ejecución que implementen esas interfaces.</span><span class="sxs-lookup"><span data-stu-id="e7c5b-108">After you specify the public interfaces that can be embedded, you create runtime classes that implement those interfaces.</span></span> <span data-ttu-id="e7c5b-109">Un programa cliente puede incrustar la información de tipo de las interfaces en tiempo de diseño haciendo referencia al ensamblado que contiene la configuración y las interfaces públicas de la propiedad `Embed Interop Types` de la referencia a `True`.</span><span class="sxs-lookup"><span data-stu-id="e7c5b-109">A client program can embed the type information for the interfaces at design time by referencing the assembly that contains the public interfaces and setting the `Embed Interop Types` property of the reference to `True`.</span></span> <span data-ttu-id="e7c5b-110">A continuación, el programa cliente puede cargar instancias de los objetos de tiempo de ejecución escritos como esas interfaces.</span><span class="sxs-lookup"><span data-stu-id="e7c5b-110">The client program can then load instances of the runtime objects typed as those interfaces.</span></span> <span data-ttu-id="e7c5b-111">Esto equivale a usar el compilador de línea de comandos y hacer referencia al ensamblado mediante la [opción -link del compilador](../../csharp/language-reference/compiler-options/link-compiler-option.md).</span><span class="sxs-lookup"><span data-stu-id="e7c5b-111">This is equivalent to using the command line compiler and referencing the assembly by using the [-link compiler option](../../csharp/language-reference/compiler-options/link-compiler-option.md).</span></span>

<span data-ttu-id="e7c5b-112">Si crea otra versión del ensamblado de tiempo de ejecución con nombre seguro, el programa cliente no tiene que volver a compilarse.</span><span class="sxs-lookup"><span data-stu-id="e7c5b-112">If you create a new version of your strong-named runtime assembly, the client program doesn't have to be recompiled.</span></span> <span data-ttu-id="e7c5b-113">El programa cliente sigue usando cualquier versión del ensamblado de tiempo de ejecución que encuentre disponible y usa la información de tipo insertada para las interfaces públicas.</span><span class="sxs-lookup"><span data-stu-id="e7c5b-113">The client program continues to use whichever version of the runtime assembly is available to it, using the embedded type information for the public interfaces.</span></span>

<span data-ttu-id="e7c5b-114">En este tutorial, hará lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="e7c5b-114">In this walkthrough, you:</span></span>

1. <span data-ttu-id="e7c5b-115">Crear un ensamblado con nombre seguro que tenga una interfaz pública e incluya información de tipo que se puede insertar.</span><span class="sxs-lookup"><span data-stu-id="e7c5b-115">Create a strong-named assembly with a public interface containing type information that can be embedded.</span></span>
1. <span data-ttu-id="e7c5b-116">Crear un ensamblado de tiempo de ejecución con nombre seguro que implemente la interfaz pública.</span><span class="sxs-lookup"><span data-stu-id="e7c5b-116">Create a strong-named runtime assembly that implements the public interface.</span></span>
1. <span data-ttu-id="e7c5b-117">Crear un programa cliente que inserte la información de tipo de la interfaz pública y cree una instancia de la clase del ensamblado en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="e7c5b-117">Create a client program that embeds the type information from the public interface and creates an instance of the class from the runtime assembly.</span></span>
1. <span data-ttu-id="e7c5b-118">Modificar y recompilar el ensamblado en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="e7c5b-118">Modify and rebuild the runtime assembly.</span></span>
1. <span data-ttu-id="e7c5b-119">Ejecute el programa cliente para ver que usa la nueva versión del ensamblado de tiempo de ejecución sin tener que volver a compilarlo.</span><span class="sxs-lookup"><span data-stu-id="e7c5b-119">Run the client program to see that it uses the new version of the runtime assembly without having to be recompiled.</span></span>

[!INCLUDE[note_settings_general](../../../includes/note-settings-general-md.md)]

## <a name="conditions-and-limitations"></a><span data-ttu-id="e7c5b-120">Condiciones y limitaciones</span><span class="sxs-lookup"><span data-stu-id="e7c5b-120">Conditions and limitations</span></span>

<span data-ttu-id="e7c5b-121">Puede insertar información de tipos desde un ensamblado si se dan las siguientes condiciones:</span><span class="sxs-lookup"><span data-stu-id="e7c5b-121">You can embed type information from an assembly under the following conditions:</span></span>

- <span data-ttu-id="e7c5b-122">El ensamblado expone al menos una interfaz pública.</span><span class="sxs-lookup"><span data-stu-id="e7c5b-122">The assembly exposes at least one public interface.</span></span>
- <span data-ttu-id="e7c5b-123">Las interfaces insertadas se anotan con atributos `ComImport` y atributos `Guid` con GUID únicos.</span><span class="sxs-lookup"><span data-stu-id="e7c5b-123">The embedded interfaces are annotated with `ComImport` attributes and `Guid` attributes with unique GUIDs.</span></span>
- <span data-ttu-id="e7c5b-124">El ensamblado se anota con los atributos `ImportedFromTypeLib` o `PrimaryInteropAssembly` y un atributo `Guid` de nivel de ensamblado.</span><span class="sxs-lookup"><span data-stu-id="e7c5b-124">The assembly is annotated with the `ImportedFromTypeLib` attribute or the `PrimaryInteropAssembly` attribute, and an assembly-level `Guid` attribute.</span></span> <span data-ttu-id="e7c5b-125">Las plantillas de proyecto de Visual C# y Visual Basic incluyen un atributo `Guid` de nivel de ensamblado de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="e7c5b-125">The Visual C# and Visual Basic project templates include an assembly-level `Guid` attribute by default.</span></span>

<span data-ttu-id="e7c5b-126">Dado que la función principal de la inserción de tipos es admitir ensamblados de interoperabilidad COM, cuando se inserta información de tipos en una solución totalmente administrada, se aplican las siguientes limitaciones:</span><span class="sxs-lookup"><span data-stu-id="e7c5b-126">Because the primary function of type embedding is to support COM interop assemblies, the following limitations apply when you embed type information in a fully-managed solution:</span></span>

- <span data-ttu-id="e7c5b-127">Solo se insertan los atributos específicos de interoperabilidad COM.</span><span class="sxs-lookup"><span data-stu-id="e7c5b-127">Only attributes specific to COM interop are embedded.</span></span> <span data-ttu-id="e7c5b-128">El resto de atributos se omiten.</span><span class="sxs-lookup"><span data-stu-id="e7c5b-128">Other attributes are ignored.</span></span>
- <span data-ttu-id="e7c5b-129">Si un tipo usa parámetros genéricos y el tipo del parámetro genérico es insertado, ese tipo no se puede usar más allá de un límite de ensamblado.</span><span class="sxs-lookup"><span data-stu-id="e7c5b-129">If a type uses generic parameters, and the type of the generic parameter is an embedded type, that type cannot be used across an assembly boundary.</span></span> <span data-ttu-id="e7c5b-130">Entre los ejemplos de cruce de un límite de ensamblado se incluyen llamar a un método desde otro ensamblado o derivar un tipo desde un tipo definido en otro ensamblado.</span><span class="sxs-lookup"><span data-stu-id="e7c5b-130">Examples of crossing an assembly boundary include calling a method from another assembly or deriving a type from a type defined in another assembly.</span></span>
- <span data-ttu-id="e7c5b-131">Las constantes no se insertan.</span><span class="sxs-lookup"><span data-stu-id="e7c5b-131">Constants are not embedded.</span></span>
- <span data-ttu-id="e7c5b-132">La clase <xref:System.Collections.Generic.Dictionary%602?displayProperty=nameWithType> no admite un tipo insertado como clave.</span><span class="sxs-lookup"><span data-stu-id="e7c5b-132">The <xref:System.Collections.Generic.Dictionary%602?displayProperty=nameWithType> class does not support an embedded type as a key.</span></span> <span data-ttu-id="e7c5b-133">Puede implementar su propio tipo de diccionario que admita un tipo insertado como clave.</span><span class="sxs-lookup"><span data-stu-id="e7c5b-133">You can implement your own dictionary type to support an embedded type as a key.</span></span>

## <a name="create-an-interface"></a><span data-ttu-id="e7c5b-134">Creación de una interfaz</span><span class="sxs-lookup"><span data-stu-id="e7c5b-134">Create an interface</span></span>

<span data-ttu-id="e7c5b-135">El primer paso es crear el ensamblado de la interfaz de equivalencia de tipos.</span><span class="sxs-lookup"><span data-stu-id="e7c5b-135">The first step is to create the type equivalence interface assembly.</span></span>

1. <span data-ttu-id="e7c5b-136">En Visual Studio, seleccione **Archivo** > **Nuevo** > **Proyecto**.</span><span class="sxs-lookup"><span data-stu-id="e7c5b-136">In Visual Studio, select **File** > **New** > **Project**.</span></span>

1. <span data-ttu-id="e7c5b-137">En el cuadro de diálogo **Crear un nuevo proyecto**, escriba *biblioteca de clases* en el cuadro **Buscar plantillas**.</span><span class="sxs-lookup"><span data-stu-id="e7c5b-137">In the **Create a new project** dialog box, type *class library* in the **Search for templates** box.</span></span> <span data-ttu-id="e7c5b-138">Seleccione la plantilla **Biblioteca de clases (.NET Framework)** de C# o Visual Basic de la lista y, luego, seleccione **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="e7c5b-138">Select either the C# or Visual Basic **Class Library (.NET Framework)** template from the list, and then select **Next**.</span></span>

1. <span data-ttu-id="e7c5b-139">En el cuadro de diálogo **Configure su nuevo proyecto**, en **Nombre del proyecto**, escriba *TypeEquivalenceInterface* y, a continuación, seleccione **Crear**.</span><span class="sxs-lookup"><span data-stu-id="e7c5b-139">In the **Configure your new project** dialog box, under **Project name**, type *TypeEquivalenceInterface*, and then select **Create**.</span></span> <span data-ttu-id="e7c5b-140">Se crea el proyecto.</span><span class="sxs-lookup"><span data-stu-id="e7c5b-140">The new project is created.</span></span>

1. <span data-ttu-id="e7c5b-141">En el **Explorador de soluciones**, haga clic con el botón derecho en el archivo *Class1.cs* o en *Class1.vb*, seleccione **Cambiar nombre** y cambie el nombre del archivo de *Class1* a *ISampleInterface*.</span><span class="sxs-lookup"><span data-stu-id="e7c5b-141">In **Solution Explorer**, right-click the *Class1.cs* or *Class1.vb* file, select **Rename**, and rename the file from *Class1* to *ISampleInterface*.</span></span> <span data-ttu-id="e7c5b-142">Responda **Sí** al aviso para cambiar también el nombre de la clase a `ISampleInterface`.</span><span class="sxs-lookup"><span data-stu-id="e7c5b-142">Respond **Yes** to the prompt to also rename the class to `ISampleInterface`.</span></span> <span data-ttu-id="e7c5b-143">Esta clase representa la interfaz pública de la clase.</span><span class="sxs-lookup"><span data-stu-id="e7c5b-143">This class represents the public interface for the class.</span></span>

1. <span data-ttu-id="e7c5b-144">En el **Explorador de soluciones**, haga clic con el botón derecho en el proyecto **TypeEquivalenceInterface** y, a continuación, seleccione **Propiedades**.</span><span class="sxs-lookup"><span data-stu-id="e7c5b-144">In **Solution Explorer**, right-click the **TypeEquivalenceInterface** project, and then select **Properties**.</span></span>

1. <span data-ttu-id="e7c5b-145">Seleccione **Compilar** en el panel izquierdo de la pantalla **Propiedades** y establezca la **Ruta de acceso de salida** en una ubicación del equipo, como *C:\TypeEquivalenceSample* .</span><span class="sxs-lookup"><span data-stu-id="e7c5b-145">Select **Build** on the left pane of the **Properties** screen, and set the **Output path** to a location on your computer, such as *C:\TypeEquivalenceSample*.</span></span> <span data-ttu-id="e7c5b-146">En este tutorial se utiliza la misma ubicación.</span><span class="sxs-lookup"><span data-stu-id="e7c5b-146">You use the same location throughout this walkthrough.</span></span>

1. <span data-ttu-id="e7c5b-147">Seleccione **Firmar** en el panel izquierdo de la pantalla **Propiedades** y, a continuación, active la casilla **Firmar el ensamblado**.</span><span class="sxs-lookup"><span data-stu-id="e7c5b-147">Select **Signing** on the left pane of the **Properties** screen, and then select the **Sign the assembly** check box.</span></span> <span data-ttu-id="e7c5b-148">En la lista desplegable de **Elija un archivo de clave de nombre seguro**, seleccione **Nuevo**.</span><span class="sxs-lookup"><span data-stu-id="e7c5b-148">In the dropdown for **Choose a strong name key file**, select **New**.</span></span>

1. <span data-ttu-id="e7c5b-149">En el cuadro de diálogo **Crear clave de nombre seguro**, en **Nombre de archivo de clave**, escriba *key.snk*.</span><span class="sxs-lookup"><span data-stu-id="e7c5b-149">In the **Create Strong Name Key** dialog, under **Key file name**, type *key.snk*.</span></span> <span data-ttu-id="e7c5b-150">Desactive la casilla **Proteger mi archivo de clave mediante contraseña** y, a continuación, seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="e7c5b-150">Deselect the **Protect my key file with a password** check box, and then select **OK**.</span></span>

1. <span data-ttu-id="e7c5b-151">Abra el archivo de clase *ISampleInterface* en el editor de código y reemplace su contenido por el código siguiente para crear la interfaz `ISampleInterface`:</span><span class="sxs-lookup"><span data-stu-id="e7c5b-151">Open the *ISampleInterface* class file in the code editor, and replace its contents with the following code to create the `ISampleInterface` interface:</span></span>

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

1. <span data-ttu-id="e7c5b-152">En el menú **Herramientas**, seleccione **Crear GUID** y, en el cuadro de diálogo **Crear GUID**, seleccione **Formato de registro**.</span><span class="sxs-lookup"><span data-stu-id="e7c5b-152">On the **Tools** menu, select **Create Guid**, and in the **Create GUID** dialog box, select **Registry Format**.</span></span> <span data-ttu-id="e7c5b-153">Seleccione **Copiar** y, a continuación, **Salir**.</span><span class="sxs-lookup"><span data-stu-id="e7c5b-153">Select **Copy**, and then select **Exit**.</span></span>

1. <span data-ttu-id="e7c5b-154">En el atributo `Guid` del código, reemplace el GUID de ejemplo por el GUID que ha copiado y elimine las llaves ( **{ }** ).</span><span class="sxs-lookup"><span data-stu-id="e7c5b-154">In the `Guid` attribute of your code, replace the sample GUID with the GUID you copied, and remove the braces (**{ }**).</span></span>

1. <span data-ttu-id="e7c5b-155">En el **Explorador de soluciones**, expanda la carpeta **Propiedades** y seleccione el archivo *AssemblyInfo.cs* o el archivo *AssemblyInfo.vb*.</span><span class="sxs-lookup"><span data-stu-id="e7c5b-155">In **Solution Explorer**, expand the **Properties** folder and select the *AssemblyInfo.cs* or *AssemblyInfo.vb* file.</span></span> <span data-ttu-id="e7c5b-156">En el editor de código, agregue el siguiente atributo al archivo:</span><span class="sxs-lookup"><span data-stu-id="e7c5b-156">In the code editor, add the following attribute to the file:</span></span>

   ```csharp
   [assembly: ImportedFromTypeLib("")]
   ```

   ```vb
   <Assembly: ImportedFromTypeLib("")>
   ```

1. <span data-ttu-id="e7c5b-157">Seleccione **Archivo** > **Guardar todo** o presione **Ctrl**+**Mayús**+**S** para guardar los archivos y el proyecto.</span><span class="sxs-lookup"><span data-stu-id="e7c5b-157">Select **File** > **Save All** or press **Ctrl**+**Shift**+**S** to save the files and project.</span></span>

1. <span data-ttu-id="e7c5b-158">En el **Explorador de soluciones**, haga clic con el botón derecho en el proyecto **TypeEquivalenceInterface** y seleccione **Compilar**.</span><span class="sxs-lookup"><span data-stu-id="e7c5b-158">In **Solution Explorer**, right-click the **TypeEquivalenceInterface** project and select **Build**.</span></span> <span data-ttu-id="e7c5b-159">El archivo DLL de biblioteca de clases se compila y se guarda en la ruta de acceso de salida de la compilación especificada, por ejemplo, *C:\TypeEquivalenceSample*.</span><span class="sxs-lookup"><span data-stu-id="e7c5b-159">The class library DLL file is compiled and saved to the specified build output path, for example *C:\TypeEquivalenceSample*.</span></span>

## <a name="create-a-runtime-class"></a><span data-ttu-id="e7c5b-160">Creación de una clase en tiempo de ejecución</span><span class="sxs-lookup"><span data-stu-id="e7c5b-160">Create a runtime class</span></span>

<span data-ttu-id="e7c5b-161">A continuación, cree la clase en tiempo de ejecución de equivalencia de tipos.</span><span class="sxs-lookup"><span data-stu-id="e7c5b-161">Next, create the type equivalence runtime class.</span></span>

1. <span data-ttu-id="e7c5b-162">En Visual Studio, seleccione **Archivo** > **Nuevo** > **Proyecto**.</span><span class="sxs-lookup"><span data-stu-id="e7c5b-162">In Visual Studio, select **File** > **New** > **Project**.</span></span>

1. <span data-ttu-id="e7c5b-163">En el cuadro de diálogo **Crear un nuevo proyecto**, escriba *biblioteca de clases* en el cuadro **Buscar plantillas**.</span><span class="sxs-lookup"><span data-stu-id="e7c5b-163">In the **Create a new project** dialog box, type *class library* in the **Search for templates** box.</span></span> <span data-ttu-id="e7c5b-164">Seleccione la plantilla **Biblioteca de clases (.NET Framework)** de C# o Visual Basic de la lista y, luego, seleccione **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="e7c5b-164">Select either the C# or Visual Basic **Class Library (.NET Framework)** template from the list, and then select **Next**.</span></span>

1. <span data-ttu-id="e7c5b-165">En el cuadro de diálogo **Configure su nuevo proyecto**, en **Nombre del proyecto**, escriba *TypeEquivalenceRuntime* y, a continuación, seleccione **Crear**.</span><span class="sxs-lookup"><span data-stu-id="e7c5b-165">In the **Configure your new project** dialog box, under **Project name**, type *TypeEquivalenceRuntime*, and then select **Create**.</span></span> <span data-ttu-id="e7c5b-166">Se crea el proyecto.</span><span class="sxs-lookup"><span data-stu-id="e7c5b-166">The new project is created.</span></span>

1. <span data-ttu-id="e7c5b-167">En el **Explorador de soluciones**, haga clic con el botón derecho en el archivo *Class1.cs* o en *Class1.vb*, seleccione **Cambiar nombre** y cambie el nombre del archivo de *Class1* a *SampleClass*.</span><span class="sxs-lookup"><span data-stu-id="e7c5b-167">In **Solution Explorer**, right-click the *Class1.cs* or *Class1.vb* file, select **Rename**, and rename the file from *Class1* to *SampleClass*.</span></span> <span data-ttu-id="e7c5b-168">Responda **Sí** al aviso para cambiar también el nombre de la clase a `SampleClass`.</span><span class="sxs-lookup"><span data-stu-id="e7c5b-168">Respond **Yes** to the prompt to also rename the class to `SampleClass`.</span></span> <span data-ttu-id="e7c5b-169">Esta clase implementa la interfaz `ISampleInterface` .</span><span class="sxs-lookup"><span data-stu-id="e7c5b-169">This class implements the `ISampleInterface` interface.</span></span>

1. <span data-ttu-id="e7c5b-170">En el **Explorador de soluciones**, haga clic con el botón derecho en el proyecto **TypeEquivalenceInterface** y seleccione **Propiedades**.</span><span class="sxs-lookup"><span data-stu-id="e7c5b-170">In **Solution Explorer**, right-click the **TypeEquivalenceInterface** project and select **Properties**.</span></span>

1. <span data-ttu-id="e7c5b-171">Seleccione **Compilar** en el panel izquierdo de la pantalla **Propiedades** y establezca la **Ruta de acceso de salida** en la misma ubicación que usó para el proyecto TypeEquivalenceInterface, por ejemplo, *C:\TypeEquivalenceSample*.</span><span class="sxs-lookup"><span data-stu-id="e7c5b-171">Select **Build** on the left pane of the **Properties** screen, and then set the **Output path** to the same location you used for the TypeEquivalenceInterface project, for example, *C:\TypeEquivalenceSample*.</span></span>

1. <span data-ttu-id="e7c5b-172">Seleccione **Firmar** en el panel izquierdo de la pantalla **Propiedades** y, a continuación, active la casilla **Firmar el ensamblado**.</span><span class="sxs-lookup"><span data-stu-id="e7c5b-172">Select **Signing** on the left pane of the **Properties** screen, and then select the **Sign the assembly** check box.</span></span> <span data-ttu-id="e7c5b-173">En la lista desplegable de **Elija un archivo de clave de nombre seguro**, seleccione **Nuevo**.</span><span class="sxs-lookup"><span data-stu-id="e7c5b-173">In the dropdown for **Choose a strong name key file**, select **New**.</span></span>

1. <span data-ttu-id="e7c5b-174">En el cuadro de diálogo **Crear clave de nombre seguro**, en **Nombre de archivo de clave**, escriba *key.snk*.</span><span class="sxs-lookup"><span data-stu-id="e7c5b-174">In the **Create Strong Name Key** dialog, under **Key file name**, type *key.snk*.</span></span> <span data-ttu-id="e7c5b-175">Desactive la casilla **Proteger mi archivo de clave mediante contraseña** y, a continuación, seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="e7c5b-175">Deselect the **Protect my key file with a password** check box, and then select **OK**.</span></span>

1. <span data-ttu-id="e7c5b-176">En el **Explorador de soluciones**, haga clic con el botón derecho en el proyecto **TypeEquivalenceRuntime** y seleccione **Agregar** > **referencia**.</span><span class="sxs-lookup"><span data-stu-id="e7c5b-176">In **Solution Explorer**, right-click the **TypeEquivalenceRuntime** project and select **Add** > **Reference**.</span></span>

1. <span data-ttu-id="e7c5b-177">En el cuadro de diálogo **Administrador de referencias**, seleccione **Examinar** y vaya a la ruta de acceso de la carpeta de salida.</span><span class="sxs-lookup"><span data-stu-id="e7c5b-177">In the **Reference Manager** dialog, select **Browse** and browse to the output path folder.</span></span> <span data-ttu-id="e7c5b-178">Seleccione el archivo *TypeEquivalenceInterface.dll*, seleccione **Agregar** y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="e7c5b-178">Select the *TypeEquivalenceInterface.dll* file, select **Add**, and then select **OK**.</span></span>

1. <span data-ttu-id="e7c5b-179">En el **Explorador de soluciones**, expanda la carpeta **Referencias** y seleccione la referencia **TypeEquivalenceInterface**.</span><span class="sxs-lookup"><span data-stu-id="e7c5b-179">In **Solution Explorer**, expand the **References** folder and select the **TypeEquivalenceInterface** reference.</span></span> <span data-ttu-id="e7c5b-180">En el panel **Propiedades**, establezca **Versión específica** en **False** si aún no lo está.</span><span class="sxs-lookup"><span data-stu-id="e7c5b-180">In the **Properties** pane, set **Specific Version** to **False** if it is not already.</span></span>

1. <span data-ttu-id="e7c5b-181">Abra el archivo de clase *SampleClass* en el editor de código y reemplace su contenido por el código siguiente para crear la clase `SampleClass`:</span><span class="sxs-lookup"><span data-stu-id="e7c5b-181">Open the *SampleClass* class file in the code editor, and replace its contents with the following code to create the `SampleClass` class:</span></span>

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

1. <span data-ttu-id="e7c5b-182">Seleccione **Archivo** > **Guardar todo** o presione **Ctrl**+**Mayús**+**S** para guardar los archivos y el proyecto.</span><span class="sxs-lookup"><span data-stu-id="e7c5b-182">Select **File** > **Save All** or press **Ctrl**+**Shift**+**S** to save the files and project.</span></span>

1. <span data-ttu-id="e7c5b-183">En el **Explorador de soluciones**, haga clic con el botón derecho en el proyecto **TypeEquivalenceRuntime** y seleccione **Compilar**.</span><span class="sxs-lookup"><span data-stu-id="e7c5b-183">In **Solution Explorer**, right-click the **TypeEquivalenceRuntime** project and select **Build**.</span></span> <span data-ttu-id="e7c5b-184">El archivo DLL de biblioteca de clases se compila y se guarda en la ruta de acceso de salida de la compilación especificada.</span><span class="sxs-lookup"><span data-stu-id="e7c5b-184">The class library DLL file is compiled and saved to the specified build output path.</span></span>

## <a name="create-a-client-project"></a><span data-ttu-id="e7c5b-185">Creación de un proyecto de cliente</span><span class="sxs-lookup"><span data-stu-id="e7c5b-185">Create a client project</span></span>

<span data-ttu-id="e7c5b-186">Por último, cree un programa cliente de equivalencia de tipos que haga referencia al ensamblado de la interfaz.</span><span class="sxs-lookup"><span data-stu-id="e7c5b-186">Finally, create a type equivalence client program that references the interface assembly.</span></span>

1. <span data-ttu-id="e7c5b-187">En Visual Studio, seleccione **Archivo** > **Nuevo** > **Proyecto**.</span><span class="sxs-lookup"><span data-stu-id="e7c5b-187">In Visual Studio, select **File** > **New** > **Project**.</span></span>

1. <span data-ttu-id="e7c5b-188">En el cuadro de diálogo **Crear un nuevo proyecto**, escriba *consola* en el cuadro **Buscar plantillas**.</span><span class="sxs-lookup"><span data-stu-id="e7c5b-188">In the **Create a new project** dialog box, type *console* in the **Search for templates** box.</span></span> <span data-ttu-id="e7c5b-189">Seleccione la plantilla **Aplicación de consola (.NET Framework)** de C# o Visual Basic de la lista y, a continuación, seleccione **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="e7c5b-189">Select either the C# or Visual Basic **Console App (.NET Framework)** template from the list, and then select **Next**.</span></span>

1. <span data-ttu-id="e7c5b-190">En el cuadro de diálogo **Configure su nuevo proyecto**, en **Nombre del proyecto**, escriba *TypeEquivalenceClient* y, a continuación, seleccione **Crear**.</span><span class="sxs-lookup"><span data-stu-id="e7c5b-190">In the **Configure your new project** dialog box, under **Project name**, type *TypeEquivalenceClient*, and then select **Create**.</span></span> <span data-ttu-id="e7c5b-191">Se crea el proyecto.</span><span class="sxs-lookup"><span data-stu-id="e7c5b-191">The new project is created.</span></span>

1. <span data-ttu-id="e7c5b-192">En el **Explorador de soluciones**, haga clic con el botón derecho en el proyecto **TypeEquivalenceClient** y seleccione **Propiedades**.</span><span class="sxs-lookup"><span data-stu-id="e7c5b-192">In **Solution Explorer**, right-click the **TypeEquivalenceClient** project and select **Properties**.</span></span>

1. <span data-ttu-id="e7c5b-193">Seleccione **Compilar** en el panel izquierdo de la pantalla **Propiedades** y establezca la **Ruta de acceso de salida** en la misma ubicación que usó para el proyecto TypeEquivalenceInterface, por ejemplo, *C:\TypeEquivalenceSample*.</span><span class="sxs-lookup"><span data-stu-id="e7c5b-193">Select **Build** on the left pane of the **Properties** screen, and then set the **Output path** to the same location you used for the TypeEquivalenceInterface project, for example, *C:\TypeEquivalenceSample*.</span></span>

1. <span data-ttu-id="e7c5b-194">En el **Explorador de soluciones**, haga clic con el botón derecho en el proyecto **TypeEquivalenceClient** y seleccione **Agregar** > **referencia**.</span><span class="sxs-lookup"><span data-stu-id="e7c5b-194">In **Solution Explorer**, right-click the **TypeEquivalenceClient** project and select **Add** > **Reference**.</span></span>

1. <span data-ttu-id="e7c5b-195">En el cuadro de diálogo **Administrador de referencias**, si el archivo **TypeEquivalenceInterface.dll** ya aparece en la lista, selecciónelo.</span><span class="sxs-lookup"><span data-stu-id="e7c5b-195">In the **Reference Manager** dialog, if the **TypeEquivalenceInterface.dll** file is already listed, select it.</span></span> <span data-ttu-id="e7c5b-196">Si no es así, seleccione **Examinar**, vaya a la carpeta de la ruta de acceso de salida, seleccione el archivo *TypeEquivalenceInterface.dll* (no *TypeEquivalenceRuntime.dll*) y, después, seleccione **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="e7c5b-196">If not, select **Browse**, browse to the output path folder, select the *TypeEquivalenceInterface.dll* file (not the *TypeEquivalenceRuntime.dll*), and select **Add**.</span></span> <span data-ttu-id="e7c5b-197">Seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="e7c5b-197">Select **OK**.</span></span>

1. <span data-ttu-id="e7c5b-198">En el **Explorador de soluciones**, expanda la carpeta **Referencias** y seleccione la referencia **TypeEquivalenceInterface**.</span><span class="sxs-lookup"><span data-stu-id="e7c5b-198">In **Solution Explorer**, expand the **References** folder and select the **TypeEquivalenceInterface** reference.</span></span> <span data-ttu-id="e7c5b-199">En el panel **Propiedades**, establezca **Incrustar tipos de interoperabilidad** en **True**.</span><span class="sxs-lookup"><span data-stu-id="e7c5b-199">In the **Properties** pane, set **Embed Interop Types** to **True**.</span></span>

1. <span data-ttu-id="e7c5b-200">Abra el archivo *Program.cs* o el archivo *Module1.vb* en el editor de código y reemplace su contenido por el código siguiente para crear el programa cliente:</span><span class="sxs-lookup"><span data-stu-id="e7c5b-200">Open the *Program.cs* or *Module1.vb* file in the code editor, and replace its contents with the following code to create the client program:</span></span>

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

1. <span data-ttu-id="e7c5b-201">Seleccione **Archivo** > **Guardar todo** o presione **Ctrl**+**Mayús**+**S** para guardar los archivos y el proyecto.</span><span class="sxs-lookup"><span data-stu-id="e7c5b-201">Select **File** > **Save All** or press **Ctrl**+**Shift**+**S** to save the files and project.</span></span>

1. <span data-ttu-id="e7c5b-202">Presione **Ctrl**+**F5** para compilar y ejecutar el programa.</span><span class="sxs-lookup"><span data-stu-id="e7c5b-202">Press **Ctrl**+**F5** to build and run the program.</span></span> <span data-ttu-id="e7c5b-203">Tenga en cuenta que la salida de la consola devuelve la versión de ensamblado **1.0.0.0**.</span><span class="sxs-lookup"><span data-stu-id="e7c5b-203">Note that the console output returns the assembly version **1.0.0.0**.</span></span>

## <a name="modify-the-interface"></a><span data-ttu-id="e7c5b-204">Modificación de la interfaz</span><span class="sxs-lookup"><span data-stu-id="e7c5b-204">Modify the interface</span></span>

<span data-ttu-id="e7c5b-205">Ahora, modifique el ensamblado de la interfaz y cambie su versión.</span><span class="sxs-lookup"><span data-stu-id="e7c5b-205">Now, modify the interface assembly, and change its version.</span></span>

1. <span data-ttu-id="e7c5b-206">En Visual Studio, seleccione **Archivo** > **Abrir** > **Proyecto o solución** y abra el proyecto **TypeEquivalenceInterface**.</span><span class="sxs-lookup"><span data-stu-id="e7c5b-206">In Visual Studio, select **File** > **Open** > **Project/Solution**, and open the **TypeEquivalenceInterface** project.</span></span>

1. <span data-ttu-id="e7c5b-207">En el **Explorador de soluciones**, haga clic con el botón derecho en el proyecto **TypeEquivalenceInterface** y seleccione **Propiedades**.</span><span class="sxs-lookup"><span data-stu-id="e7c5b-207">In **Solution Explorer**, right-click the **TypeEquivalenceInterface** project and select **Properties**.</span></span>

1. <span data-ttu-id="e7c5b-208">Seleccione **Aplicación** en el panel izquierdo de la pantalla **Propiedades** y, a continuación, seleccione **Información de ensamblado**.</span><span class="sxs-lookup"><span data-stu-id="e7c5b-208">Select **Application** on the left pane of the **Properties** screen, and then select **Assembly Information**.</span></span>

1. <span data-ttu-id="e7c5b-209">En el cuadro de diálogo **Información de ensamblado**, cambie los valores de **Versión del ensamblado** y **Versión del archivo** a *2.0.0.0* y, a continuación, seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="e7c5b-209">In the **Assembly Information** dialog box, change the **Assembly version** and **File version** values to *2.0.0.0*, and then select **OK**.</span></span>

1. <span data-ttu-id="e7c5b-210">Abra el archivo *SampleInterface.cs* o *SampleInterface.vb* y agregue la siguiente línea de código a la interfaz `ISampleInterface`:</span><span class="sxs-lookup"><span data-stu-id="e7c5b-210">Open the *SampleInterface.cs* or *SampleInterface.vb* file, and add the following line of code to the `ISampleInterface` interface:</span></span>

   ```csharp
   DateTime GetDate();
   ```

   ```vb
   Function GetDate() As Date
   ```

1. <span data-ttu-id="e7c5b-211">Seleccione **Archivo** > **Guardar todo** o presione **Ctrl**+**Mayús**+**S** para guardar los archivos y el proyecto.</span><span class="sxs-lookup"><span data-stu-id="e7c5b-211">Select **File** > **Save All** or press **Ctrl**+**Shift**+**S** to save the files and project.</span></span>

1. <span data-ttu-id="e7c5b-212">En el **Explorador de soluciones**, haga clic con el botón derecho en el proyecto **TypeEquivalenceInterface** y seleccione **Compilar**.</span><span class="sxs-lookup"><span data-stu-id="e7c5b-212">In **Solution Explorer**, right-click the **TypeEquivalenceInterface** project and select **Build**.</span></span> <span data-ttu-id="e7c5b-213">Se compila una nueva versión del archivo DLL de biblioteca de clases y se guarda en la ruta de acceso de salida de la compilación.</span><span class="sxs-lookup"><span data-stu-id="e7c5b-213">A new version of the class library DLL file is compiled and saved to the build output path.</span></span>

## <a name="modify-the-runtime-class"></a><span data-ttu-id="e7c5b-214">Modificación de la clase en tiempo de ejecución</span><span class="sxs-lookup"><span data-stu-id="e7c5b-214">Modify the runtime class</span></span>

<span data-ttu-id="e7c5b-215">Modifique también la clase en tiempo de ejecución y actualice su versión.</span><span class="sxs-lookup"><span data-stu-id="e7c5b-215">Also modify the runtime class and update its version.</span></span>

1. <span data-ttu-id="e7c5b-216">En Visual Studio, seleccione **Archivo** > **Abrir** > **Proyecto o solución** y abra el proyecto **TypeEquivalenceRuntime**.</span><span class="sxs-lookup"><span data-stu-id="e7c5b-216">In Visual Studio, select **File** > **Open** > **Project/Solution**, and open the **TypeEquivalenceRuntime** project.</span></span>

1. <span data-ttu-id="e7c5b-217">En el **Explorador de soluciones**, haga clic con el botón derecho en el proyecto **TypeEquivalenceRuntime** y seleccione **Propiedades**.</span><span class="sxs-lookup"><span data-stu-id="e7c5b-217">In **Solution Explorer**, right-click the **TypeEquivalenceRuntime** project and select **Properties**.</span></span>

1. <span data-ttu-id="e7c5b-218">Seleccione **Aplicación** en el panel izquierdo de la pantalla **Propiedades** y, a continuación, seleccione **Información de ensamblado**.</span><span class="sxs-lookup"><span data-stu-id="e7c5b-218">Select **Application** on the left pane of the **Properties** screen, and then select **Assembly Information**.</span></span>

1. <span data-ttu-id="e7c5b-219">En el cuadro de diálogo **Información de ensamblado**, cambie los valores de **Versión del ensamblado** y **Versión del archivo** a *2.0.0.0* y, a continuación, seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="e7c5b-219">In the **Assembly Information** dialog box, change the **Assembly version** and **File version** values to *2.0.0.0*, and then select **OK**.</span></span>

1. <span data-ttu-id="e7c5b-220">Abra el archivo *SampleClass.cs* o el archivo *SampleClass.vb* y agregue el código siguiente a la clase `SampleClass`:</span><span class="sxs-lookup"><span data-stu-id="e7c5b-220">Open the *SampleClass.cs* or *SampleClass.vb* file, and add the following code to the `SampleClass` class:</span></span>

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

1. <span data-ttu-id="e7c5b-221">Seleccione **Archivo** > **Guardar todo** o presione **Ctrl**+**Mayús**+**S** para guardar los archivos y el proyecto.</span><span class="sxs-lookup"><span data-stu-id="e7c5b-221">Select **File** > **Save All** or press **Ctrl**+**Shift**+**S** to save the files and project.</span></span>

1. <span data-ttu-id="e7c5b-222">En el **Explorador de soluciones**, haga clic con el botón derecho en el proyecto **TypeEquivalenceRuntime** y seleccione **Compilar**.</span><span class="sxs-lookup"><span data-stu-id="e7c5b-222">In **Solution Explorer**, right-click the **TypeEquivalenceRuntime** project and select **Build**.</span></span> <span data-ttu-id="e7c5b-223">Se compila una nueva versión del archivo DLL de biblioteca de clases y se guarda en la ruta de acceso de salida de la compilación.</span><span class="sxs-lookup"><span data-stu-id="e7c5b-223">A new version of the class library DLL file is compiled and saved to the build output path.</span></span>

## <a name="run-the-updated-client-program"></a><span data-ttu-id="e7c5b-224">Ejecución del programa cliente actualizado</span><span class="sxs-lookup"><span data-stu-id="e7c5b-224">Run the updated client program</span></span>

<span data-ttu-id="e7c5b-225">Vaya a la ubicación de la carpeta de resultados de compilación y ejecute *TypeEquivalenceClient.exe*.</span><span class="sxs-lookup"><span data-stu-id="e7c5b-225">Go to the build output folder location and run *TypeEquivalenceClient.exe*.</span></span> <span data-ttu-id="e7c5b-226">Tenga en cuenta que la salida de la consola ahora refleja la nueva versión del ensamblado `TypeEquivalenceRuntime`, *2.0.0.0*, sin que el programa se vuelva a compilar.</span><span class="sxs-lookup"><span data-stu-id="e7c5b-226">Note that the console output now reflects the new version of the `TypeEquivalenceRuntime` assembly, *2.0.0.0*, without the program being recompiled.</span></span>

## <a name="see-also"></a><span data-ttu-id="e7c5b-227">Vea también</span><span class="sxs-lookup"><span data-stu-id="e7c5b-227">See also</span></span>

- [<span data-ttu-id="e7c5b-228">-link (Opciones del compilador de C#)</span><span class="sxs-lookup"><span data-stu-id="e7c5b-228">-link (C# Compiler Options)</span></span>](../../csharp/language-reference/compiler-options/link-compiler-option.md)
- [<span data-ttu-id="e7c5b-229">-link (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="e7c5b-229">-link (Visual Basic)</span></span>](../../visual-basic/reference/command-line-compiler/link.md)
- [<span data-ttu-id="e7c5b-230">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="e7c5b-230">C# programming guide</span></span>](../../csharp/programming-guide/index.md)
- [<span data-ttu-id="e7c5b-231">Conceptos de programación (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="e7c5b-231">Programming concepts (Visual Basic)</span></span>](../../visual-basic/programming-guide/concepts/index.md)
- [<span data-ttu-id="e7c5b-232">Ensamblados de .NET</span><span class="sxs-lookup"><span data-stu-id="e7c5b-232">Assemblies in .NET</span></span>](index.md)
