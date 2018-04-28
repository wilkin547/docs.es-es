---
title: 'Empezar a trabajar con F # en el código de Visual Studio'
description: 'Obtenga información acerca de cómo usar F # con código de Visual Studio y el conjunto de complemento Ionide.'
author: cartermp
ms.author: phcart
ms.date: 02/28/2018
ms.topic: conceptual
ms.prod: dotnet-fsharp
ms.devlang: fsharp
ms.openlocfilehash: 43fed76a57bd7749a7f22a2039ad625e3d26d132
ms.sourcegitcommit: 03ee570f6f528a7d23a4221dcb26a9498edbdf8c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/28/2018
---
# <a name="get-started-with-f-in-visual-studio-code"></a><span data-ttu-id="d1f75-103">Empezar a trabajar con F # en el código de Visual Studio</span><span class="sxs-lookup"><span data-stu-id="d1f75-103">Get Started with F# in Visual Studio Code</span></span>

<span data-ttu-id="d1f75-104">Puede escribir F # en [código de Visual Studio](https://code.visualstudio.com) con el [Ionide complemento](https://marketplace.visualstudio.com/items?itemName=Ionide.Ionide-fsharp)para obtener una gran experiencia IDE (Integrade caracterizan un entorno de desarrollo) multiplataforma, ligera con IntelliSense y el código básico refactorizaciones.</span><span class="sxs-lookup"><span data-stu-id="d1f75-104">You can write F# in [Visual Studio Code](https://code.visualstudio.com) with the [Ionide plugin](https://marketplace.visualstudio.com/items?itemName=Ionide.Ionide-fsharp), to get a great cross-platform, lightweight IDE (Integrade Development Enivronment) experience with IntelliSense and basic code refactorings.</span></span>  <span data-ttu-id="d1f75-105">Visite [Ionide.io](http://ionide.io) para obtener más información sobre el conjunto de complementos.</span><span class="sxs-lookup"><span data-stu-id="d1f75-105">Visit [Ionide.io](http://ionide.io) to learn more about the plugin suite.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="d1f75-106">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="d1f75-106">Prerequisites</span></span>

<span data-ttu-id="d1f75-107">Debe tener [git instalado](https://git-scm.com/download) y están disponibles en la ruta de acceso al hacer uso de plantillas de proyecto en Ionide.</span><span class="sxs-lookup"><span data-stu-id="d1f75-107">You must have [git installed](https://git-scm.com/download) and available on your PATH to make use of project templates in Ionide.</span></span>  <span data-ttu-id="d1f75-108">Puede comprobar que está instalado correctamente escribiendo `git --version` en un símbolo del sistema y presione **ENTRAR**.</span><span class="sxs-lookup"><span data-stu-id="d1f75-108">You can verify that it is installed correctly by typing `git --version` at a command prompt and pressing **Enter**.</span></span>

### <a name="macostabmacos"></a>[<span data-ttu-id="d1f75-109">macOS</span><span class="sxs-lookup"><span data-stu-id="d1f75-109">macOS</span></span>](#tab/macos)

<span data-ttu-id="d1f75-110">Usa Ionide [Mono](http://www.mono-project.com).</span><span class="sxs-lookup"><span data-stu-id="d1f75-110">Ionide uses [Mono](http://www.mono-project.com).</span></span>  <span data-ttu-id="d1f75-111">La manera más fácil de instalar Mono en macOS es a través de Homebrew.</span><span class="sxs-lookup"><span data-stu-id="d1f75-111">The easiest way to install Mono on macOS is via Homebrew.</span></span>  <span data-ttu-id="d1f75-112">Basta con escribir lo siguiente en su terminal:</span><span class="sxs-lookup"><span data-stu-id="d1f75-112">Simply type the following into your terminal:</span></span>

```
brew install mono
```

<span data-ttu-id="d1f75-113">También debe instalar la [.NET Core SDK](https://www.microsoft.com/net/download).</span><span class="sxs-lookup"><span data-stu-id="d1f75-113">You must also install the [.NET Core SDK](https://www.microsoft.com/net/download).</span></span>

### <a name="linuxtablinux"></a>[<span data-ttu-id="d1f75-114">Linux</span><span class="sxs-lookup"><span data-stu-id="d1f75-114">Linux</span></span>](#tab/linux)

<span data-ttu-id="d1f75-115">En Linux, también utiliza Ionide [Mono](https://www.mono-project.com).</span><span class="sxs-lookup"><span data-stu-id="d1f75-115">On Linux, Ionide also uses [Mono](https://www.mono-project.com).</span></span> <span data-ttu-id="d1f75-116">Si encuentra en Debian o Ubuntu, puede utilizar lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="d1f75-116">If you're on Debian or Ubuntu, you can use the following:</span></span>

```
sudo apt-get update
sudo apt-get install mono-complete fsharp
```

<span data-ttu-id="d1f75-117">También debe instalar la [.NET Core SDK](https://www.microsoft.com/net/download).</span><span class="sxs-lookup"><span data-stu-id="d1f75-117">You must also install the [.NET Core SDK](https://www.microsoft.com/net/download).</span></span>

### <a name="windowstabwindows"></a>[<span data-ttu-id="d1f75-118">Windows</span><span class="sxs-lookup"><span data-stu-id="d1f75-118">Windows</span></span>](#tab/windows)

<span data-ttu-id="d1f75-119">Si está en Windows, debe [instalar Visual Studio con compatibilidad con F #](get-started-visual-studio.md#installing-f).</span><span class="sxs-lookup"><span data-stu-id="d1f75-119">If you're on Windows, you must [install Visual Studio with F# support](get-started-visual-studio.md#installing-f).</span></span> <span data-ttu-id="d1f75-120">Esto instala todos los componentes necesarios para escribir, compilar y ejecutar código de F #.</span><span class="sxs-lookup"><span data-stu-id="d1f75-120">This installs all the necessary components to write, compile, and execute F# code.</span></span>

<span data-ttu-id="d1f75-121">También debe instalar la [.NET Core SDK](https://www.microsoft.com/net/download/).</span><span class="sxs-lookup"><span data-stu-id="d1f75-121">You must also install the [.NET Core SDK](https://www.microsoft.com/net/download/).</span></span>

---

## <a name="installing-visual-studio-code-and-the-ionide-plugin"></a><span data-ttu-id="d1f75-122">Instalar el complemento de Ionide y código de Visual Studio</span><span class="sxs-lookup"><span data-stu-id="d1f75-122">Installing Visual Studio Code and the Ionide plugin</span></span>

<span data-ttu-id="d1f75-123">Puede instalar Visual Studio Code desde el [code.visualstudio.com](https://code.visualstudio.com) sitio Web.</span><span class="sxs-lookup"><span data-stu-id="d1f75-123">You can install Visual Studio Code from the [code.visualstudio.com](https://code.visualstudio.com) website.</span></span> <span data-ttu-id="d1f75-124">Después de eso, hay dos formas de buscar el complemento Ionide:</span><span class="sxs-lookup"><span data-stu-id="d1f75-124">After that, there are two ways to find the Ionide plugin:</span></span>

1. <span data-ttu-id="d1f75-125">Usa la paleta de comando (Ctrl + Mayús + P en Windows, ⌘ + MAYÚS + P en macOS, Ctrl + Mayús + P en Linux) y escriba lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="d1f75-125">Use the Command Palette (Ctrl+Shift+P on Windows, ⌘+Shift+P on macOS, Ctrl+Shift+P on Linux) and type the following:</span></span>

    ```
    >ext install Ionide
    ```

2. <span data-ttu-id="d1f75-126">Haga clic en el icono de extensiones y busque "Ionide":</span><span class="sxs-lookup"><span data-stu-id="d1f75-126">Click the Extensions icon and search for "Ionide":</span></span>

    ![](media/getting-started-vscode/vscode-ext.png)

<span data-ttu-id="d1f75-127">El complemento sólo para compatibilidad con F # en Visual Studio Code es [Ionide fsharp](https://marketplace.visualstudio.com/items?itemName=Ionide.Ionide-fsharp).</span><span class="sxs-lookup"><span data-stu-id="d1f75-127">The only plugin required for F# support in Visual Studio Code is [Ionide-fsharp](https://marketplace.visualstudio.com/items?itemName=Ionide.Ionide-fsharp).</span></span> <span data-ttu-id="d1f75-128">Sin embargo, también puede instalar [Ionide emulación](https://marketplace.visualstudio.com/items?itemName=Ionide.Ionide-FAKE) y para obtener [IMITAR](https://fsharp.github.io/FAKE/) admite y [Ionide Paket](https://marketplace.visualstudio.com/items?itemName=Ionide.Ionide-Paket) para obtener [Paket](https://fsprojects.github.io/Paket/) admite.</span><span class="sxs-lookup"><span data-stu-id="d1f75-128">However, you can also install [Ionide-FAKE](https://marketplace.visualstudio.com/items?itemName=Ionide.Ionide-FAKE) and to get [FAKE](https://fsharp.github.io/FAKE/) support and [Ionide-Paket](https://marketplace.visualstudio.com/items?itemName=Ionide.Ionide-Paket) to get [Paket](https://fsprojects.github.io/Paket/) support.</span></span> <span data-ttu-id="d1f75-129">FALSIFICAR y Paket son herramientas de la Comunidad de datos adicionales sobre F # para compilar proyectos y administrar dependencias, respectivamente.</span><span class="sxs-lookup"><span data-stu-id="d1f75-129">FAKE and Paket are additonal F# community tools for building projects and managing dependencies, respectively.</span></span>

## <a name="creating-your-first-project-with-ionide"></a><span data-ttu-id="d1f75-130">Crear su primer proyecto con Ionide</span><span class="sxs-lookup"><span data-stu-id="d1f75-130">Creating your first project with Ionide</span></span>

<span data-ttu-id="d1f75-131">Para crear un nuevo proyecto de F #, abra el código de Visual Studio en una nueva carpeta (puede nombre nombre que quiera).</span><span class="sxs-lookup"><span data-stu-id="d1f75-131">To create a new F# project, open Visual Studio Code in a new folder (you can name it whatever you like).</span></span>

![](media/getting-started-vscode/vscode-open-dir.png)

<span data-ttu-id="d1f75-132">A continuación, abra la paleta de comando (Ctrl + Mayús + P en Windows, ⌘ + MAYÚS + P en macOS, Ctrl + Mayús + P en Linux) y escriba lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="d1f75-132">Next, open the Command Palette (Ctrl+Shift+P on Windows, ⌘+Shift+P on macOS, Ctrl+Shift+P on Linux) and type the following:</span></span>

```
>f#: New Project
```

<span data-ttu-id="d1f75-133">Esto se realiza gracias la [FORGE](https://github.com/fsharp-editing/Forge) proyecto.</span><span class="sxs-lookup"><span data-stu-id="d1f75-133">This is powered by the [FORGE](https://github.com/fsharp-editing/Forge) project.</span></span>  <span data-ttu-id="d1f75-134">Verá algo parecido a esto:</span><span class="sxs-lookup"><span data-stu-id="d1f75-134">You should see something like this:</span></span>

![](media/getting-started-vscode/vscode-new-proj.png)

> [!NOTE]
<span data-ttu-id="d1f75-135">Si no ve los pasos anteriores, pruebe a actualizar plantillas ejecutando el siguiente comando en la paleta de comando: `>F#: Refresh Project Templates`.</span><span class="sxs-lookup"><span data-stu-id="d1f75-135">If you don't see the above, try refreshing templates by running the following command in the Command Palette: `>F#: Refresh Project Templates`.</span></span>

<span data-ttu-id="d1f75-136">Seleccione ": nuevo proyecto de F #" pulsando **ENTRAR**, que le permitirán a este paso:</span><span class="sxs-lookup"><span data-stu-id="d1f75-136">Select "F#: New Project" by hitting **Enter**, which will take you to this step:</span></span>

![](media/getting-started-vscode/vscode-proj-type.png)

<span data-ttu-id="d1f75-137">Se seleccionarán una plantilla para un tipo específico de proyecto.</span><span class="sxs-lookup"><span data-stu-id="d1f75-137">This will select a template for a specific type of project.</span></span>  <span data-ttu-id="d1f75-138">Existen varias opciones en este caso, como un [FsLab](https://fslab.org) plantilla de ciencia de datos o [Suave](https://suave.io) plantilla de programación Web.</span><span class="sxs-lookup"><span data-stu-id="d1f75-138">There are quite a few options here, such as an [FsLab](https://fslab.org) template for Data Science or [Suave](https://suave.io) template for Web Programming.</span></span>  <span data-ttu-id="d1f75-139">Este artículo se utiliza la `classlib` plantilla, por lo que resaltar que y presione **ENTRAR**.</span><span class="sxs-lookup"><span data-stu-id="d1f75-139">This article uses the `classlib` template, so highlight that and hit **Enter**.</span></span>  <span data-ttu-id="d1f75-140">A continuación, se le mostrará el paso siguiente:</span><span class="sxs-lookup"><span data-stu-id="d1f75-140">You will then reach the following step:</span></span>

![](media/getting-started-vscode/vscode-new-dir.png)

<span data-ttu-id="d1f75-141">Esto le permite crear el proyecto en un directorio diferente, si lo desea.</span><span class="sxs-lookup"><span data-stu-id="d1f75-141">This lets you create the project in a different directory, if you like.</span></span>  <span data-ttu-id="d1f75-142">Déjelo en blanco por ahora.</span><span class="sxs-lookup"><span data-stu-id="d1f75-142">Leave it blank for now.</span></span>  <span data-ttu-id="d1f75-143">Creará el proyecto en el directorio actual.</span><span class="sxs-lookup"><span data-stu-id="d1f75-143">It will create the project in the current directory.</span></span>  <span data-ttu-id="d1f75-144">Una vez que se presiona **ENTRAR**, alcanzará el paso siguiente:</span><span class="sxs-lookup"><span data-stu-id="d1f75-144">Once you press **Enter**, you will reach the following step:</span></span>

![](media/getting-started-vscode/vscode-proj-name.png)

<span data-ttu-id="d1f75-145">Esto le permite nombre para el proyecto.</span><span class="sxs-lookup"><span data-stu-id="d1f75-145">This lets you name your project.</span></span>  <span data-ttu-id="d1f75-146">F # utiliza [mayúsculas y minúsculas Pascal](http://c2.com/cgi/wiki?PascalCase) para los nombres de proyecto.</span><span class="sxs-lookup"><span data-stu-id="d1f75-146">F# uses [Pascal case](http://c2.com/cgi/wiki?PascalCase) for project names.</span></span>  <span data-ttu-id="d1f75-147">Este artículo usa `ClassLibraryDemo` como el nombre.</span><span class="sxs-lookup"><span data-stu-id="d1f75-147">This article uses `ClassLibraryDemo` as the name.</span></span>  <span data-ttu-id="d1f75-148">Una vez que ha escrito el nombre que desea para el proyecto, presione **ENTRAR**.</span><span class="sxs-lookup"><span data-stu-id="d1f75-148">Once you've entered the name you want for your project, hit **Enter**.</span></span>

<span data-ttu-id="d1f75-149">Si ha seguido los pasos del paso anterior, debería obtener Visual Studio código de área de trabajo en el lado izquierdo para el siguiente aspecto:</span><span class="sxs-lookup"><span data-stu-id="d1f75-149">If you followed the previous step steps, you should get the Visual Studio Code Workspace on the left-hand side to look something like this:</span></span>

![](media/getting-started-vscode/vscode-new-proj-explorer.png)

<span data-ttu-id="d1f75-150">Esta plantilla genera algunas cosas que puede encontrar útiles:</span><span class="sxs-lookup"><span data-stu-id="d1f75-150">This template generates a few things you'll find useful:</span></span>

1. <span data-ttu-id="d1f75-151">F # del proyecto, debajo de la directiva la `ClassLibraryDemo` carpeta.</span><span class="sxs-lookup"><span data-stu-id="d1f75-151">The F# project itself, underneath the `ClassLibraryDemo` folder.</span></span>
2. <span data-ttu-id="d1f75-152">La estructura de directorio correcto para agregar paquetes a través de [ `Paket` ](https://fsprojects.github.io/Paket/).</span><span class="sxs-lookup"><span data-stu-id="d1f75-152">The correct directory structure for adding packages via [`Paket`](https://fsprojects.github.io/Paket/).</span></span>
3. <span data-ttu-id="d1f75-153">Una multiplataforma Generar script con [ `FAKE` ](https://fsharp.github.io/FAKE/).</span><span class="sxs-lookup"><span data-stu-id="d1f75-153">A cross-platform build script with [`FAKE`](https://fsharp.github.io/FAKE/).</span></span>
4. <span data-ttu-id="d1f75-154">El `paket.exe` archivo ejecutable que puede capturar paquetes y resolver las dependencias para usted.</span><span class="sxs-lookup"><span data-stu-id="d1f75-154">The `paket.exe` executable which can fetch packages and resolve dependencies for you.</span></span>
5. <span data-ttu-id="d1f75-155">Un `.gitignore` archivo si desea agregar este proyecto al control de origen basado en Git.</span><span class="sxs-lookup"><span data-stu-id="d1f75-155">A `.gitignore` file if you wish to add this project to Git-based source control.</span></span>

## <a name="writing-some-code"></a><span data-ttu-id="d1f75-156">Escribir código</span><span class="sxs-lookup"><span data-stu-id="d1f75-156">Writing some code</span></span>

<span data-ttu-id="d1f75-157">Abra la *ClassLibraryDemo* carpeta.</span><span class="sxs-lookup"><span data-stu-id="d1f75-157">Open the *ClassLibraryDemo* folder.</span></span>  <span data-ttu-id="d1f75-158">Debería ver los siguientes archivos:</span><span class="sxs-lookup"><span data-stu-id="d1f75-158">You should see the following files:</span></span>

1. <span data-ttu-id="d1f75-159">`ClassLibraryDemo.fs`, un archivo de implementación de F # con una clase definida.</span><span class="sxs-lookup"><span data-stu-id="d1f75-159">`ClassLibraryDemo.fs`, an F# implementation file with a class defined.</span></span>
2. <span data-ttu-id="d1f75-160">`CassLibraryDemo.fsproj`, un archivo de proyecto de F # utilizado para compilar este proyecto.</span><span class="sxs-lookup"><span data-stu-id="d1f75-160">`CassLibraryDemo.fsproj`, an F# project file used to build this project.</span></span>
3. <span data-ttu-id="d1f75-161">`Script.fsx`, un archivo script de F # que carga el archivo de origen.</span><span class="sxs-lookup"><span data-stu-id="d1f75-161">`Script.fsx`, an F# script file which loads the source file.</span></span>
4. <span data-ttu-id="d1f75-162">`paket.references`, un archivo Paket que especifica las dependencias del proyecto.</span><span class="sxs-lookup"><span data-stu-id="d1f75-162">`paket.references`, a Paket file which specifies the project dependencies.</span></span>

<span data-ttu-id="d1f75-163">Abra `Script.fsx`y agregue el código siguiente al final de la misma:</span><span class="sxs-lookup"><span data-stu-id="d1f75-163">Open `Script.fsx`, and add the following code at the end of it:</span></span>

[!code-fsharp[ToPigLatin](../../../samples/snippets/fsharp/getting-started/to-pig-latin.fsx)]

<span data-ttu-id="d1f75-164">Esta función convierte una palabra en un formulario de [Pig latino](https://en.wikipedia.org/wiki/Pig_Latin).</span><span class="sxs-lookup"><span data-stu-id="d1f75-164">This function converts a word to a form of [Pig Latin](https://en.wikipedia.org/wiki/Pig_Latin).</span></span>  <span data-ttu-id="d1f75-165">El siguiente paso es evaluar con F # Interactive (FSI).</span><span class="sxs-lookup"><span data-stu-id="d1f75-165">The next step is to evaluate it using F# Interactive (FSI).</span></span>

<span data-ttu-id="d1f75-166">Resalte toda la función (debe ser 11 líneas de longitud).</span><span class="sxs-lookup"><span data-stu-id="d1f75-166">Highlight the entire function (it should be 11 lines long).</span></span>  <span data-ttu-id="d1f75-167">Una vez que se resalte, mantenga el **Alt** clave y posicionamiento **ENTRAR**.</span><span class="sxs-lookup"><span data-stu-id="d1f75-167">Once it is highlighted, hold the **Alt** key and hit **Enter**.</span></span>  <span data-ttu-id="d1f75-168">Verá una ventana emergente a continuación y debe mostrar algo parecido a esto:</span><span class="sxs-lookup"><span data-stu-id="d1f75-168">You'll notice a window pop up below, and it should show something like this:</span></span>

![](media/getting-started-vscode/vscode-fsi.png)

<span data-ttu-id="d1f75-169">Esto hizo tres cosas:</span><span class="sxs-lookup"><span data-stu-id="d1f75-169">This did three things:</span></span>

1. <span data-ttu-id="d1f75-170">Inició el proceso FSI.</span><span class="sxs-lookup"><span data-stu-id="d1f75-170">It started the FSI process.</span></span>
2. <span data-ttu-id="d1f75-171">El código resaltado que envían a través de los procesos FSI.</span><span class="sxs-lookup"><span data-stu-id="d1f75-171">It sent the code you highlighted over the FSI process.</span></span>
3. <span data-ttu-id="d1f75-172">El proceso FSI evalúa el código enviados a través de.</span><span class="sxs-lookup"><span data-stu-id="d1f75-172">The FSI process evaluated the code you sent over.</span></span>

<span data-ttu-id="d1f75-173">Porque lo que envía a través no era un [función](../language-reference/functions/index.md), ahora puede llamar a esa función FSI!</span><span class="sxs-lookup"><span data-stu-id="d1f75-173">Because what you sent over was a [function](../language-reference/functions/index.md), you can now call that function with FSI!</span></span>  <span data-ttu-id="d1f75-174">En la ventana interactiva, escriba lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="d1f75-174">In the interactive window, type the following:</span></span>

```fsharp
toPigLatin "banana";;
```

<span data-ttu-id="d1f75-175">Debe ver el siguiente resultado:</span><span class="sxs-lookup"><span data-stu-id="d1f75-175">You should see the following result:</span></span>

```fsharp
val it : string = "ananabay"
```

<span data-ttu-id="d1f75-176">Ahora, vamos a intentarlo con una vocal como la primera letra.</span><span class="sxs-lookup"><span data-stu-id="d1f75-176">Now, let's try with a vowel as the first letter.</span></span> <span data-ttu-id="d1f75-177">Escriba lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="d1f75-177">Enter the following:</span></span>

```fsharp
toPigLatin "apple";;
```

<span data-ttu-id="d1f75-178">Debe ver el siguiente resultado:</span><span class="sxs-lookup"><span data-stu-id="d1f75-178">You should see the following result:</span></span>

```fsharp
val it : string = "appleyay"
```

<span data-ttu-id="d1f75-179">La función parece funcionar según lo esperado.</span><span class="sxs-lookup"><span data-stu-id="d1f75-179">The function appears to be working as expected.</span></span>  <span data-ttu-id="d1f75-180">Enhorabuena, simplemente se escribió la primera función de F # en el código de Visual Studio y se evalúa con FSI.</span><span class="sxs-lookup"><span data-stu-id="d1f75-180">Congratulations, you just wrote your first F# function in Visual Studio Code and evaluated it with FSI!</span></span>

>[!NOTE]
<span data-ttu-id="d1f75-181">Tal y como se observa, las líneas de FSI terminan con `;;`.</span><span class="sxs-lookup"><span data-stu-id="d1f75-181">As you may have noticed, the lines in FSI are terminated with `;;`.</span></span>  <span data-ttu-id="d1f75-182">Esto es porque FSI le permite escribir varias líneas.</span><span class="sxs-lookup"><span data-stu-id="d1f75-182">This is because FSI allows you to enter multiple lines.</span></span>  <span data-ttu-id="d1f75-183">El `;;` al final, FSI podrá saber cuando finalice el código.</span><span class="sxs-lookup"><span data-stu-id="d1f75-183">The `;;` at the end lets FSI know when the code is finished.</span></span>

## <a name="explaining-the-code"></a><span data-ttu-id="d1f75-184">Que explica el código</span><span class="sxs-lookup"><span data-stu-id="d1f75-184">Explaining the code</span></span>

<span data-ttu-id="d1f75-185">Si no está seguro de lo que realmente está haciendo el código, este es un paso a paso.</span><span class="sxs-lookup"><span data-stu-id="d1f75-185">If you're not sure about what the code is actually doing, here's a step-by-step.</span></span>

<span data-ttu-id="d1f75-186">Como puede ver, `toPigLatin` es una función que toma una palabra como entrada y lo convierte en una representación de Pig latino de esa palabra.</span><span class="sxs-lookup"><span data-stu-id="d1f75-186">As you can see, `toPigLatin` is a function which takes a word as its input and converts it to a Pig-Latin representation of that word.</span></span>  <span data-ttu-id="d1f75-187">Las reglas para esto son los siguientes:</span><span class="sxs-lookup"><span data-stu-id="d1f75-187">The rules for this are as follows:</span></span>

<span data-ttu-id="d1f75-188">Si el primer carácter de una palabra comienza con una vocal, agregue "yay" al final de la palabra.</span><span class="sxs-lookup"><span data-stu-id="d1f75-188">If the first character in a word starts with a vowel, add "yay" to the end of the word.</span></span>  <span data-ttu-id="d1f75-189">Si no se inicia con una vocal, mover ese primer carácter al final de la palabra y "en" Agregar a ella.</span><span class="sxs-lookup"><span data-stu-id="d1f75-189">If it doesn't start with a vowel, move that first character to the end of the word and add "ay" to it.</span></span>

<span data-ttu-id="d1f75-190">Es podrán que haya observado lo siguiente en FSI:</span><span class="sxs-lookup"><span data-stu-id="d1f75-190">You may have noticed the following in FSI:</span></span>

```
val toPigLatin : word:string -> string
```

<span data-ttu-id="d1f75-191">Esto indica que `toPigLatin` es una función que toma un `string` como entrada (llamado `word`) y devuelve otro `string`.</span><span class="sxs-lookup"><span data-stu-id="d1f75-191">This states that `toPigLatin` is a function which takes in a `string` as input (called `word`), and returns another `string`.</span></span>  <span data-ttu-id="d1f75-192">Esto se conoce como el [signatura de tipo de la función](https://fsharpforfunandprofit.com/posts/function-signatures/), una parte fundamental de F #, que es clave para comprender el código de F #.</span><span class="sxs-lookup"><span data-stu-id="d1f75-192">This is known as the [type signature of the function](https://fsharpforfunandprofit.com/posts/function-signatures/), a fundamental piece of F# that's key to understanding F# code.</span></span>  <span data-ttu-id="d1f75-193">También podrá observar si mantiene el mouse sobre la función en código de Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="d1f75-193">You'll also notice this if you hover over the function in Visual Studio Code.</span></span>

<span data-ttu-id="d1f75-194">En el cuerpo de la función, verá dos partes distintas:</span><span class="sxs-lookup"><span data-stu-id="d1f75-194">In the body of the function, you'll notice two distinct parts:</span></span>

1. <span data-ttu-id="d1f75-195">Una función interna, denominada `isVowel`, que determina si un carácter determinado (`c`) es una vocal comprobando si coincide con uno de los modelos proporcionados a través de [coincidencia de patrones](../language-reference/pattern-matching.md):</span><span class="sxs-lookup"><span data-stu-id="d1f75-195">An inner function, called `isVowel`, which determines if a given character (`c`) is a vowel by checking if it matches one of the provided patterns via [Pattern Matching](../language-reference/pattern-matching.md):</span></span>

   [!code-fsharp[ToPigLatin](../../../samples/snippets/fsharp/getting-started/to-pig-latin.fsx#L2-L6)]

2. <span data-ttu-id="d1f75-196">Un [ `if..then..else` ](../language-reference/conditional-expressions-if-then-else.md) que comprueba si el primer carácter es una vocal y construye un valor devuelto de los caracteres de entrada en función de if el primer carácter de expresión era una vocal o no:</span><span class="sxs-lookup"><span data-stu-id="d1f75-196">An [`if..then..else`](../language-reference/conditional-expressions-if-then-else.md) expression which checks if the first character is a vowel, and constructs a return value out of the input characters based on if the first character was a vowel or not:</span></span>

   [!code-fsharp[ToPigLatin](../../../samples/snippets/fsharp/getting-started/to-pig-latin.fsx#L8-L11)]

<span data-ttu-id="d1f75-197">El flujo de `toPigLatin` es así:</span><span class="sxs-lookup"><span data-stu-id="d1f75-197">The flow of `toPigLatin` is thus:</span></span>

<span data-ttu-id="d1f75-198">Compruebe si el primer carácter de la palabra de entrada es una vocal.</span><span class="sxs-lookup"><span data-stu-id="d1f75-198">Check if the first character of the input word is a vowel.</span></span>  <span data-ttu-id="d1f75-199">Si es así, adjuntar "yay" al final de la palabra.</span><span class="sxs-lookup"><span data-stu-id="d1f75-199">If it is, attach "yay" to the end of the word.</span></span>  <span data-ttu-id="d1f75-200">En caso contrario, mueva ese primer carácter al final de la palabra y "en" Agregar a ella.</span><span class="sxs-lookup"><span data-stu-id="d1f75-200">Otherwise, move that first character to the end of the word and add "ay" to it.</span></span>

<span data-ttu-id="d1f75-201">Hay una última cosa deben tener en cuenta esto: no hay ninguna instrucción explícita para devolver de la función, a diferencia de muchos otros lenguajes por ahí.</span><span class="sxs-lookup"><span data-stu-id="d1f75-201">There's one final thing to notice about this: there's no explicit instruction to return from the function, unlike many other languages out there.</span></span>  <span data-ttu-id="d1f75-202">Esto es porque F # es basadas en expresiones y la última expresión en el cuerpo de una función es el valor devuelto.</span><span class="sxs-lookup"><span data-stu-id="d1f75-202">This is because F# is Expression-based, and the last expression in the body of a function is the return value.</span></span>  <span data-ttu-id="d1f75-203">Dado que `if..then..else` es en sí mismo una expresión, el cuerpo de la `then` bloque o en el cuerpo de la `else` bloque se devolverán según el valor de entrada.</span><span class="sxs-lookup"><span data-stu-id="d1f75-203">Because `if..then..else` is itself an expression, the body of the `then` block or the body of the `else` block will be returned depending on the input value.</span></span>

## <a name="moving-your-script-code-into-the-implementation-file"></a><span data-ttu-id="d1f75-204">Mover el código de script en el archivo de implementación</span><span class="sxs-lookup"><span data-stu-id="d1f75-204">Moving your script code into the implementation file</span></span>

<span data-ttu-id="d1f75-205">Las secciones anteriores de este artículo muestran un primer paso comunes para escribir código de F #: escribir una función inicial y se ejecuta de forma interactiva con FSI.</span><span class="sxs-lookup"><span data-stu-id="d1f75-205">The previous sections in this article demonstrated a common first step in writing F# code: writing an initial function and executing it interactively with FSI.</span></span>  <span data-ttu-id="d1f75-206">Esto se conoce como el desarrollo basado en la replicación, donde REPL representa "Bucle de impresión evaluar lectura".</span><span class="sxs-lookup"><span data-stu-id="d1f75-206">This is known as REPL-driven development, where REPL stands for "Read-Evaluate-Print Loop".</span></span>  <span data-ttu-id="d1f75-207">Es una excelente manera de experimentar con funcionalidad hasta que haya algo a funcionar.</span><span class="sxs-lookup"><span data-stu-id="d1f75-207">It's a great way to experiment with functionality until you have something working.</span></span>

<span data-ttu-id="d1f75-208">El siguiente paso en el desarrollo controlado por la replicación es mover el código de trabajo en un archivo de implementación de F #.</span><span class="sxs-lookup"><span data-stu-id="d1f75-208">The next step in REPL-driven development is to move working code into an F# implementation file.</span></span>  <span data-ttu-id="d1f75-209">A continuación, se pueden compilar por el compilador de F # en un ensamblado que se puede ejecutar.</span><span class="sxs-lookup"><span data-stu-id="d1f75-209">It can then be compiled by the F# compiler into an assembly which can be executed.</span></span>

<span data-ttu-id="d1f75-210">Para comenzar, abra `ClassLibraryDemo.fs`.</span><span class="sxs-lookup"><span data-stu-id="d1f75-210">To begin, open `ClassLibraryDemo.fs`.</span></span>  <span data-ttu-id="d1f75-211">Observará que parte del código está en ella.</span><span class="sxs-lookup"><span data-stu-id="d1f75-211">You'll notice that some code is already in there.</span></span>  <span data-ttu-id="d1f75-212">Siga adelante y eliminar la definición de clase, pero asegúrese de dejar el [ `namespace` ](../language-reference/namespaces.md) declaración en la parte superior.</span><span class="sxs-lookup"><span data-stu-id="d1f75-212">Go ahead and delete the class definition, but make sure to leave the [`namespace`](../language-reference/namespaces.md) declaration at the top.</span></span>

<span data-ttu-id="d1f75-213">A continuación, cree un nuevo [ `module` ](../language-reference/modules.md) llama `PigLatin` y copie la `toPigLatin` función en él como tales:</span><span class="sxs-lookup"><span data-stu-id="d1f75-213">Next, create a new [`module`](../language-reference/modules.md) called `PigLatin` and copy the `toPigLatin` function into it as such:</span></span>

[!code-fsharp[ToPigLatin](../../../samples/snippets/fsharp/getting-started/pig-latin.fs#L1-L14)]

<span data-ttu-id="d1f75-214">Esta es una de las muchas maneras de que organizar las funciones en código de F # y un enfoque común si también desea llamar al código de C# o proyectos de Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="d1f75-214">This is one of the many ways you can organize functions in F# code, and a common approach if you also want to call your code from C# or Visual Basic projects.</span></span>

<span data-ttu-id="d1f75-215">A continuación, abra el `Script.fsx` archivo nuevo y eliminar toda la matriz `toPigLatin` funcionando, pero debe asegurarse de mantener las dos líneas siguientes en el archivo:</span><span class="sxs-lookup"><span data-stu-id="d1f75-215">Next, open the `Script.fsx` file again, and delete the entire `toPigLatin` function, but make sure to keep the following two lines in the file:</span></span>

```
#load "ClassLibraryDemo.fs"
open ClassLibraryDemo
```

<span data-ttu-id="d1f75-216">La primera línea es necesario para FSI secuencias de comandos para cargar `ClassLibraryDemo.fs`.</span><span class="sxs-lookup"><span data-stu-id="d1f75-216">The first line is needed for FSI scripting to load `ClassLibraryDemo.fs`.</span></span>  <span data-ttu-id="d1f75-217">La segunda línea es su comodidad: omitiéndola es opcional, pero debe escribir `open ClassLibraryDemo` en una ventana FSI si desea volver a poner el `ToPigLatin` módulo en el ámbito.</span><span class="sxs-lookup"><span data-stu-id="d1f75-217">The second line is a convenience: omitting it is optional, but you will need to type `open ClassLibraryDemo` in an FSI window if you wish to bring the `ToPigLatin` module into scope.</span></span>

<span data-ttu-id="d1f75-218">A continuación, en la ventana FSI, llame a la función con el `PigLatin` módulo que definió anteriormente:</span><span class="sxs-lookup"><span data-stu-id="d1f75-218">Next, in the FSI window, call the function with the `PigLatin` module that you defined earlier:</span></span>

```
> PigLatin.toPigLatin "banana";;
val it : string = "ananabay"
> PigLatin.toPigLatin "apple";;
val it : string = "appleyay"
```

<span data-ttu-id="d1f75-219">Correcto</span><span class="sxs-lookup"><span data-stu-id="d1f75-219">Success!</span></span>  <span data-ttu-id="d1f75-220">Obtener los mismos resultados que antes, pero ahora se carga desde un archivo de implementación de F #.</span><span class="sxs-lookup"><span data-stu-id="d1f75-220">You get the same results as before, but now loaded from an F# implementation file.</span></span>  <span data-ttu-id="d1f75-221">La principal diferencia es que los archivos de código fuente de F # se compilan en ensamblados que se pueden ejecutar en cualquier lugar, no solo en FSI.</span><span class="sxs-lookup"><span data-stu-id="d1f75-221">The major difference here is that F# source files are compiled into assemblies which can be executed anywhere, not just in FSI.</span></span>

## <a name="summary"></a><span data-ttu-id="d1f75-222">Resumen</span><span class="sxs-lookup"><span data-stu-id="d1f75-222">Summary</span></span>

<span data-ttu-id="d1f75-223">En este artículo, ha aprendido:</span><span class="sxs-lookup"><span data-stu-id="d1f75-223">In this article, you've learned:</span></span>

1. <span data-ttu-id="d1f75-224">Cómo configurar el código de Visual Studio con Ionide.</span><span class="sxs-lookup"><span data-stu-id="d1f75-224">How to set up Visual Studio Code with Ionide.</span></span>
2. <span data-ttu-id="d1f75-225">Cómo crear su primer proyecto de F # con Ionide.</span><span class="sxs-lookup"><span data-stu-id="d1f75-225">How to create your first F# project with Ionide.</span></span>
3. <span data-ttu-id="d1f75-226">Describe cómo usar Scripting F # para escribir su primera función de F # en Ionide y, a continuación, se ejecutan en FSI.</span><span class="sxs-lookup"><span data-stu-id="d1f75-226">How to use F# Scripting to write your first F# function in Ionide and then execute it in FSI.</span></span>
4. <span data-ttu-id="d1f75-227">Cómo migrar el código de script al código fuente de F # y, a continuación, llame a ese código desde FSI.</span><span class="sxs-lookup"><span data-stu-id="d1f75-227">How to migrate your script code to F# source and then call that code from FSI.</span></span>

<span data-ttu-id="d1f75-228">Ahora está equipado para escribir mucho más código F # mediante código de Visual Studio y Ionide.</span><span class="sxs-lookup"><span data-stu-id="d1f75-228">You're now equipped to write much more F# code using Visual Studio Code and Ionide.</span></span>

## <a name="troubleshooting"></a><span data-ttu-id="d1f75-229">Solución de problemas</span><span class="sxs-lookup"><span data-stu-id="d1f75-229">Troubleshooting</span></span>

<span data-ttu-id="d1f75-230">Aquí se muestran algunas maneras de que puede solucionar determinados problemas que pueden surgir:</span><span class="sxs-lookup"><span data-stu-id="d1f75-230">Here are a few ways you can troubleshoot certain problems that you might run into:</span></span>

1. <span data-ttu-id="d1f75-231">Para obtener la características de Ionide de edición de código, los archivos de F # deben guardarse en el disco y dentro de una carpeta que está abierta en el área de trabajo de código de Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="d1f75-231">To get the code editing features of Ionide, your F# files need to be saved to disk and inside of a folder that is open in the Visual Studio Code workspace.</span></span>
2. <span data-ttu-id="d1f75-232">Si ha realizado cambios en el sistema o instalar requisitos previos de Ionide con código de Visual Studio abierto, reinicie Visual Studio Code.</span><span class="sxs-lookup"><span data-stu-id="d1f75-232">If you've made changes to your system or installed Ionide prerequisites with Visual Studio Code open, restart Visual Studio Code.</span></span>
3. <span data-ttu-id="d1f75-233">Compruebe que puede utilizar el compilador de F # y F # interactive desde la línea de comandos sin una ruta de acceso completa.</span><span class="sxs-lookup"><span data-stu-id="d1f75-233">Check that you can use the F# compiler and F# interactive from the command line without a fully-qualified path.</span></span>  <span data-ttu-id="d1f75-234">Puede hacerlo escribiendo `fsc` en una línea de comandos para el compilador de F #, y `fsi` o `fsharpi` para Visual F # las herramientas de Windows y Mono en Mac o Linux, respectivamente.</span><span class="sxs-lookup"><span data-stu-id="d1f75-234">You can do so by typing `fsc` in a command line for the F# compiler, and `fsi` or `fsharpi` for the Visual F# tools on Windows and Mono on Mac/Linux, respectively.</span></span>
4. <span data-ttu-id="d1f75-235">Si tiene caracteres no válidos en los directorios del proyecto, Ionide podrían no funcionar.</span><span class="sxs-lookup"><span data-stu-id="d1f75-235">If you have invalid characters in your project directories, Ionide might not work.</span></span>  <span data-ttu-id="d1f75-236">Cambiar el nombre de los directorios del proyecto si éste es el caso.</span><span class="sxs-lookup"><span data-stu-id="d1f75-236">Rename your project directories if this is the case.</span></span>
5. <span data-ttu-id="d1f75-237">Si ninguno de los comandos Ionide está trabajando, compruebe su [enlaces de teclado de Visual Studio Code](https://code.visualstudio.com/docs/customization/keybindings#_customizing-shortcuts) para ver si se está reemplazando por accidente.</span><span class="sxs-lookup"><span data-stu-id="d1f75-237">If none of the Ionide commands are working, check your [Visual Studio Code keybindings](https://code.visualstudio.com/docs/customization/keybindings#_customizing-shortcuts) to see if you're overriding them by accident.</span></span>
6. <span data-ttu-id="d1f75-238">Si se divide Ionide en su equipo y ninguno de los anteriores solucionó el problema, pruebe a quitar el `ionide-fsharp` directorio en su equipo y vuelva a instalar el conjunto de complementos.</span><span class="sxs-lookup"><span data-stu-id="d1f75-238">If Ionide is broken on your machine and none of the above has fixed your problem, try removing the `ionide-fsharp` directory on your machine and reinstall the plugin suite.</span></span>

<span data-ttu-id="d1f75-239">Ionide es un proyecto de código abierto crea y mantiene los miembros de la Comunidad de F #.</span><span class="sxs-lookup"><span data-stu-id="d1f75-239">Ionide is an open source project built and maintained by members of the F# community.</span></span>  <span data-ttu-id="d1f75-240">Por favor, notificar problemas y no dude en contribuir en el [Ionide VSCode: repositorio de FSharp GitHub](https://github.com/ionide/ionide-vscode-fsharp).</span><span class="sxs-lookup"><span data-stu-id="d1f75-240">Please report issues and feel free to contribute at the [Ionide-VSCode: FSharp GitHub repository](https://github.com/ionide/ionide-vscode-fsharp).</span></span>

<span data-ttu-id="d1f75-241">Si tiene un problema al informe, siga [las instrucciones para obtener los registros que se utilizará al informar de un problema](https://github.com/ionide/ionide-vscode-fsharp#how-to-get-logs-for-debugging--issue-reporting).</span><span class="sxs-lookup"><span data-stu-id="d1f75-241">If you have an issue to report, please follow [the instructions for getting logs to use when reporting an issue](https://github.com/ionide/ionide-vscode-fsharp#how-to-get-logs-for-debugging--issue-reporting).</span></span>

<span data-ttu-id="d1f75-242">También puede pedir ayuda adicional de los desarrolladores de Ionide y la Comunidad de F # en el [Ionide Gitter canal](https://gitter.im/ionide/ionide-project).</span><span class="sxs-lookup"><span data-stu-id="d1f75-242">You can also ask for further help from the Ionide developers and F# community in the [Ionide Gitter channel](https://gitter.im/ionide/ionide-project).</span></span>

## <a name="next-steps"></a><span data-ttu-id="d1f75-243">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="d1f75-243">Next steps</span></span>

<span data-ttu-id="d1f75-244">Para obtener más información sobre F # y las características del lenguaje, visite [paseo de F #](../tour.md).</span><span class="sxs-lookup"><span data-stu-id="d1f75-244">To learn more about F# and the features of the language, check out [Tour of F#](../tour.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="d1f75-245">Vea también</span><span class="sxs-lookup"><span data-stu-id="d1f75-245">See also</span></span>

[<span data-ttu-id="d1f75-246">Paseo por F</span><span class="sxs-lookup"><span data-stu-id="d1f75-246">Tour of F#</span></span>](../tour.md)

[<span data-ttu-id="d1f75-247">Referencia del lenguaje F#</span><span class="sxs-lookup"><span data-stu-id="d1f75-247">F# Language Reference</span></span>](../language-reference/index.md)

[<span data-ttu-id="d1f75-248">Funciones</span><span class="sxs-lookup"><span data-stu-id="d1f75-248">Functions</span></span>](../language-reference/functions/index.md)

[<span data-ttu-id="d1f75-249">Módulos</span><span class="sxs-lookup"><span data-stu-id="d1f75-249">Modules</span></span>](../language-reference/modules.md)

[<span data-ttu-id="d1f75-250">Espacios de nombres</span><span class="sxs-lookup"><span data-stu-id="d1f75-250">Namespaces</span></span>](../language-reference/namespaces.md)

[<span data-ttu-id="d1f75-251">Tutorial de VSCode Ionide: FSharp</span><span class="sxs-lookup"><span data-stu-id="d1f75-251">Ionide-VSCode: FSharp</span></span>](https://github.com/ionide/ionide-vscode-fsharp)
