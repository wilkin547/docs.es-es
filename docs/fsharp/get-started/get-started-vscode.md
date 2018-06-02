---
title: 'Empezar a trabajar con F # en el código de Visual Studio'
description: 'Obtenga información acerca de cómo usar F # con código de Visual Studio y el conjunto de complemento Ionide.'
ms.date: 05/28/2018
ms.openlocfilehash: e56274caf36be231338876ded5a6d7c7968906b0
ms.sourcegitcommit: bbf70abe6b46073148f78cbf0619de6092b5800c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/02/2018
ms.locfileid: "34728633"
---
# <a name="get-started-with-f-in-visual-studio-code"></a><span data-ttu-id="6d68f-103">Empezar a trabajar con F # en el código de Visual Studio</span><span class="sxs-lookup"><span data-stu-id="6d68f-103">Get Started with F# in Visual Studio Code</span></span>

<span data-ttu-id="6d68f-104">Puede escribir F # en [código de Visual Studio](https://code.visualstudio.com) con el [Ionide complemento](https://marketplace.visualstudio.com/items?itemName=Ionide.Ionide-fsharp)para obtener una gran experiencia de entorno de desarrollo integrado (IDE) de multiplataforma, ligera con IntelliSense y el código básico refactorizaciones.</span><span class="sxs-lookup"><span data-stu-id="6d68f-104">You can write F# in [Visual Studio Code](https://code.visualstudio.com) with the [Ionide plugin](https://marketplace.visualstudio.com/items?itemName=Ionide.Ionide-fsharp), to get a great cross-platform, lightweight Integrated Development Environment (IDE) experience with IntelliSense and basic code refactorings.</span></span> <span data-ttu-id="6d68f-105">Visite [Ionide.io](http://ionide.io) para obtener más información sobre el conjunto de complementos.</span><span class="sxs-lookup"><span data-stu-id="6d68f-105">Visit [Ionide.io](http://ionide.io) to learn more about the plugin suite.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="6d68f-106">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="6d68f-106">Prerequisites</span></span>

<span data-ttu-id="6d68f-107">Debe tener [git instalado](https://git-scm.com/download) y están disponibles en la ruta de acceso al hacer uso de plantillas de proyecto en Ionide.</span><span class="sxs-lookup"><span data-stu-id="6d68f-107">You must have [git installed](https://git-scm.com/download) and available on your PATH to make use of project templates in Ionide.</span></span> <span data-ttu-id="6d68f-108">Puede comprobar que está instalado correctamente escribiendo `git --version` en un símbolo del sistema y presione **ENTRAR**.</span><span class="sxs-lookup"><span data-stu-id="6d68f-108">You can verify that it is installed correctly by typing `git --version` at a command prompt and pressing **Enter**.</span></span>

### <a name="macostabmacos"></a>[<span data-ttu-id="6d68f-109">macOS</span><span class="sxs-lookup"><span data-stu-id="6d68f-109">macOS</span></span>](#tab/macos)

<span data-ttu-id="6d68f-110">Usa Ionide [Mono](http://www.mono-project.com).</span><span class="sxs-lookup"><span data-stu-id="6d68f-110">Ionide uses [Mono](http://www.mono-project.com).</span></span> <span data-ttu-id="6d68f-111">La manera más fácil de instalar Mono en macOS es a través de Homebrew.</span><span class="sxs-lookup"><span data-stu-id="6d68f-111">The easiest way to install Mono on macOS is via Homebrew.</span></span> <span data-ttu-id="6d68f-112">Basta con escribir lo siguiente en su terminal:</span><span class="sxs-lookup"><span data-stu-id="6d68f-112">Simply type the following into your terminal:</span></span>

```
brew install mono
```

<span data-ttu-id="6d68f-113">También debe instalar la [.NET Core SDK](https://www.microsoft.com/net/download).</span><span class="sxs-lookup"><span data-stu-id="6d68f-113">You must also install the [.NET Core SDK](https://www.microsoft.com/net/download).</span></span>

### <a name="linuxtablinux"></a>[<span data-ttu-id="6d68f-114">Linux</span><span class="sxs-lookup"><span data-stu-id="6d68f-114">Linux</span></span>](#tab/linux)

<span data-ttu-id="6d68f-115">En Linux, también utiliza Ionide [Mono](https://www.mono-project.com).</span><span class="sxs-lookup"><span data-stu-id="6d68f-115">On Linux, Ionide also uses [Mono](https://www.mono-project.com).</span></span> <span data-ttu-id="6d68f-116">Si encuentra en Debian o Ubuntu, puede utilizar lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="6d68f-116">If you're on Debian or Ubuntu, you can use the following:</span></span>

```
sudo apt-get update
sudo apt-get install mono-complete fsharp
```

<span data-ttu-id="6d68f-117">También debe instalar la [.NET Core SDK](https://www.microsoft.com/net/download).</span><span class="sxs-lookup"><span data-stu-id="6d68f-117">You must also install the [.NET Core SDK](https://www.microsoft.com/net/download).</span></span>

### <a name="windowstabwindows"></a>[<span data-ttu-id="6d68f-118">Windows</span><span class="sxs-lookup"><span data-stu-id="6d68f-118">Windows</span></span>](#tab/windows)

<span data-ttu-id="6d68f-119">Si está en Windows, debe [instalar Visual Studio con compatibilidad con F #](get-started-visual-studio.md#installing-f).</span><span class="sxs-lookup"><span data-stu-id="6d68f-119">If you're on Windows, you must [install Visual Studio with F# support](get-started-visual-studio.md#installing-f).</span></span> <span data-ttu-id="6d68f-120">Esto instala todos los componentes necesarios para escribir, compilar y ejecutar código de F #.</span><span class="sxs-lookup"><span data-stu-id="6d68f-120">This installs all the necessary components to write, compile, and execute F# code.</span></span>

<span data-ttu-id="6d68f-121">También debe instalar la [.NET Core SDK](https://www.microsoft.com/net/download/).</span><span class="sxs-lookup"><span data-stu-id="6d68f-121">You must also install the [.NET Core SDK](https://www.microsoft.com/net/download/).</span></span>

---

## <a name="installing-visual-studio-code-and-the-ionide-plugin"></a><span data-ttu-id="6d68f-122">Instalar el complemento de Ionide y código de Visual Studio</span><span class="sxs-lookup"><span data-stu-id="6d68f-122">Installing Visual Studio Code and the Ionide plugin</span></span>

<span data-ttu-id="6d68f-123">Puede instalar Visual Studio Code desde el [code.visualstudio.com](https://code.visualstudio.com) sitio Web.</span><span class="sxs-lookup"><span data-stu-id="6d68f-123">You can install Visual Studio Code from the [code.visualstudio.com](https://code.visualstudio.com) website.</span></span>

<span data-ttu-id="6d68f-124">A continuación, haga clic en el icono de extensiones y busque "Ionide":</span><span class="sxs-lookup"><span data-stu-id="6d68f-124">Next, click the Extensions icon and search for "Ionide":</span></span>

<span data-ttu-id="6d68f-125">El complemento sólo para compatibilidad con F # en Visual Studio Code es [Ionide fsharp](https://marketplace.visualstudio.com/items?itemName=Ionide.Ionide-fsharp).</span><span class="sxs-lookup"><span data-stu-id="6d68f-125">The only plugin required for F# support in Visual Studio Code is [Ionide-fsharp](https://marketplace.visualstudio.com/items?itemName=Ionide.Ionide-fsharp).</span></span> <span data-ttu-id="6d68f-126">Sin embargo, también puede instalar [Ionide emulación](https://marketplace.visualstudio.com/items?itemName=Ionide.Ionide-FAKE) para obtener [IMITAR](https://fsharp.github.io/FAKE/) admite y [Ionide Paket](https://marketplace.visualstudio.com/items?itemName=Ionide.Ionide-Paket) para obtener [Paket](https://fsprojects.github.io/Paket/) admite.</span><span class="sxs-lookup"><span data-stu-id="6d68f-126">However, you can also install [Ionide-FAKE](https://marketplace.visualstudio.com/items?itemName=Ionide.Ionide-FAKE) to get [FAKE](https://fsharp.github.io/FAKE/) support and [Ionide-Paket](https://marketplace.visualstudio.com/items?itemName=Ionide.Ionide-Paket) to get [Paket](https://fsprojects.github.io/Paket/) support.</span></span> <span data-ttu-id="6d68f-127">FALSIFICAR y Paket son F # Comunidad herramientas adicionales para compilar proyectos y administrar dependencias, respectivamente.</span><span class="sxs-lookup"><span data-stu-id="6d68f-127">FAKE and Paket are additional F# community tools for building projects and managing dependencies, respectively.</span></span>

## <a name="creating-your-first-project-with-ionide"></a><span data-ttu-id="6d68f-128">Crear su primer proyecto con Ionide</span><span class="sxs-lookup"><span data-stu-id="6d68f-128">Creating your first project with Ionide</span></span>

<span data-ttu-id="6d68f-129">Para crear un nuevo proyecto de F #, abra el código de Visual Studio en una nueva carpeta (puede nombre nombre que quiera).</span><span class="sxs-lookup"><span data-stu-id="6d68f-129">To create a new F# project, open Visual Studio Code in a new folder (you can name it whatever you like).</span></span>

<span data-ttu-id="6d68f-130">A continuación, abrir la paleta de comando (**Vista > comando paleta**) y escriba lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="6d68f-130">Next, open the command pallette (**View > Command Pallette**) and type the following:</span></span>

```
> F# new project
```

<span data-ttu-id="6d68f-131">Esto se realiza gracias la [FORGE](https://github.com/fsharp-editing/Forge) proyecto.</span><span class="sxs-lookup"><span data-stu-id="6d68f-131">This is powered by the [FORGE](https://github.com/fsharp-editing/Forge) project.</span></span>

> [!NOTE]
<span data-ttu-id="6d68f-132">Si no ve ninguna opción de plantilla, pruebe a actualizar plantillas ejecutando el siguiente comando en la paleta de comando: `>F#: Refresh Project Templates`.</span><span class="sxs-lookup"><span data-stu-id="6d68f-132">If you don't see template options, try refreshing templates by running the following command in the Command Palette: `>F#: Refresh Project Templates`.</span></span>

<span data-ttu-id="6d68f-133">Seleccione ": nuevo proyecto de F #" pulsando **ENTRAR**.</span><span class="sxs-lookup"><span data-stu-id="6d68f-133">Select "F#: New Project" by hitting **Enter**.</span></span> <span data-ttu-id="6d68f-134">Esto le llevará al paso siguiente, que es para seleccionar una plantilla de proyecto.</span><span class="sxs-lookup"><span data-stu-id="6d68f-134">This takes you to the next step, which is for selecting a project template.</span></span>

<span data-ttu-id="6d68f-135">Elegir el `classlib` plantilla del sistema y presione **ENTRAR**.</span><span class="sxs-lookup"><span data-stu-id="6d68f-135">Pick the `classlib` template and hit **Enter**.</span></span>

<span data-ttu-id="6d68f-136">A continuación, seleccione un directorio para crear el proyecto en.</span><span class="sxs-lookup"><span data-stu-id="6d68f-136">Next, pick a directory to create the project in.</span></span> <span data-ttu-id="6d68f-137">Si se deja en blanco, usa el directorio actual.</span><span class="sxs-lookup"><span data-stu-id="6d68f-137">If you leave it blank, it uses the current directory.</span></span>

<span data-ttu-id="6d68f-138">Por último, denomine el proyecto en el paso final.</span><span class="sxs-lookup"><span data-stu-id="6d68f-138">Finally, name your project in the final step.</span></span> <span data-ttu-id="6d68f-139">F # utiliza [mayúsculas y minúsculas Pascal](http://c2.com/cgi/wiki?PascalCase) para los nombres de proyecto.</span><span class="sxs-lookup"><span data-stu-id="6d68f-139">F# uses [Pascal case](http://c2.com/cgi/wiki?PascalCase) for project names.</span></span> <span data-ttu-id="6d68f-140">Este artículo usa `ClassLibraryDemo` como el nombre.</span><span class="sxs-lookup"><span data-stu-id="6d68f-140">This article uses `ClassLibraryDemo` as the name.</span></span> <span data-ttu-id="6d68f-141">Una vez que ha escrito el nombre que desea para el proyecto, presione **ENTRAR**.</span><span class="sxs-lookup"><span data-stu-id="6d68f-141">Once you've entered the name you want for your project, hit **Enter**.</span></span>

<span data-ttu-id="6d68f-142">Si ha seguido el paso anterior, debe obtener el Visual Studio código de área de trabajo en el lado izquierdo para que aparezca con lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="6d68f-142">If you followed the previous step, you should get the Visual Studio Code Workspace on the left-hand side to appear with the following:</span></span>

1. <span data-ttu-id="6d68f-143">F # del proyecto, debajo de la directiva la `ClassLibraryDemo` carpeta.</span><span class="sxs-lookup"><span data-stu-id="6d68f-143">The F# project itself, underneath the `ClassLibraryDemo` folder.</span></span>
2. <span data-ttu-id="6d68f-144">La estructura de directorio correcto para agregar paquetes a través de [ `Paket` ](https://fsprojects.github.io/Paket/).</span><span class="sxs-lookup"><span data-stu-id="6d68f-144">The correct directory structure for adding packages via [`Paket`](https://fsprojects.github.io/Paket/).</span></span>
3. <span data-ttu-id="6d68f-145">Una multiplataforma Generar script con [ `FAKE` ](https://fsharp.github.io/FAKE/).</span><span class="sxs-lookup"><span data-stu-id="6d68f-145">A cross-platform build script with [`FAKE`](https://fsharp.github.io/FAKE/).</span></span>
4. <span data-ttu-id="6d68f-146">El `paket.exe` ejecutable que puede capturar paquetes y resolver las dependencias para usted.</span><span class="sxs-lookup"><span data-stu-id="6d68f-146">The `paket.exe` executable that can fetch packages and resolve dependencies for you.</span></span>
5. <span data-ttu-id="6d68f-147">Un `.gitignore` archivo si desea agregar este proyecto al control de origen basado en Git.</span><span class="sxs-lookup"><span data-stu-id="6d68f-147">A `.gitignore` file if you wish to add this project to Git-based source control.</span></span>

## <a name="writing-some-code"></a><span data-ttu-id="6d68f-148">Escribir código</span><span class="sxs-lookup"><span data-stu-id="6d68f-148">Writing some code</span></span>

<span data-ttu-id="6d68f-149">Abra la *ClassLibraryDemo* carpeta.</span><span class="sxs-lookup"><span data-stu-id="6d68f-149">Open the *ClassLibraryDemo* folder.</span></span>  <span data-ttu-id="6d68f-150">Debería ver los siguientes archivos:</span><span class="sxs-lookup"><span data-stu-id="6d68f-150">You should see the following files:</span></span>

1. <span data-ttu-id="6d68f-151">`ClassLibraryDemo.fs`, un archivo de implementación de F # con una clase definida.</span><span class="sxs-lookup"><span data-stu-id="6d68f-151">`ClassLibraryDemo.fs`, an F# implementation file with a class defined.</span></span>
2. <span data-ttu-id="6d68f-152">`ClassLibraryDemo.fsproj`, un archivo de proyecto de F # utilizado para compilar este proyecto.</span><span class="sxs-lookup"><span data-stu-id="6d68f-152">`ClassLibraryDemo.fsproj`, an F# project file used to build this project.</span></span>
3. <span data-ttu-id="6d68f-153">`Script.fsx`, un archivo script de F # que carga el archivo de origen.</span><span class="sxs-lookup"><span data-stu-id="6d68f-153">`Script.fsx`, an F# script file that loads the source file.</span></span>
4. <span data-ttu-id="6d68f-154">`paket.references`, un archivo Paket que especifica las dependencias del proyecto.</span><span class="sxs-lookup"><span data-stu-id="6d68f-154">`paket.references`, a Paket file that specifies the project dependencies.</span></span>

<span data-ttu-id="6d68f-155">Abra `Script.fsx`y agregue el código siguiente al final de la misma:</span><span class="sxs-lookup"><span data-stu-id="6d68f-155">Open `Script.fsx`, and add the following code at the end of it:</span></span>

[!code-fsharp[ToPigLatin](../../../samples/snippets/fsharp/getting-started/to-pig-latin.fsx)]

<span data-ttu-id="6d68f-156">Esta función convierte una palabra en un formulario de [Pig latino](https://en.wikipedia.org/wiki/Pig_Latin).</span><span class="sxs-lookup"><span data-stu-id="6d68f-156">This function converts a word to a form of [Pig Latin](https://en.wikipedia.org/wiki/Pig_Latin).</span></span> <span data-ttu-id="6d68f-157">El siguiente paso es evaluar con F # Interactive (FSI).</span><span class="sxs-lookup"><span data-stu-id="6d68f-157">The next step is to evaluate it using F# Interactive (FSI).</span></span>

<span data-ttu-id="6d68f-158">Resalte toda la función (debe ser 11 líneas de longitud).</span><span class="sxs-lookup"><span data-stu-id="6d68f-158">Highlight the entire function (it should be 11 lines long).</span></span> <span data-ttu-id="6d68f-159">Una vez que se resalte, mantenga el **Alt** clave y posicionamiento **ENTRAR**.</span><span class="sxs-lookup"><span data-stu-id="6d68f-159">Once it is highlighted, hold the **Alt** key and hit **Enter**.</span></span> <span data-ttu-id="6d68f-160">Verá una ventana emergente a continuación y debe mostrar algo parecido a esto:</span><span class="sxs-lookup"><span data-stu-id="6d68f-160">You'll notice a window pop up below, and it should show something like this:</span></span>

![Ejemplo de salida de F # Interactive con Ionide](media/getting-started-vscode/vscode-fsi.png)

<span data-ttu-id="6d68f-162">Esto hizo tres cosas:</span><span class="sxs-lookup"><span data-stu-id="6d68f-162">This did three things:</span></span>

1. <span data-ttu-id="6d68f-163">Inició el proceso FSI.</span><span class="sxs-lookup"><span data-stu-id="6d68f-163">It started the FSI process.</span></span>
2. <span data-ttu-id="6d68f-164">El código resaltado que envían a través de los procesos FSI.</span><span class="sxs-lookup"><span data-stu-id="6d68f-164">It sent the code you highlighted over the FSI process.</span></span>
3. <span data-ttu-id="6d68f-165">El proceso FSI evalúa el código enviados a través de.</span><span class="sxs-lookup"><span data-stu-id="6d68f-165">The FSI process evaluated the code you sent over.</span></span>

<span data-ttu-id="6d68f-166">Porque lo que envía a través no era un [función](../language-reference/functions/index.md), ahora puede llamar a esa función FSI!</span><span class="sxs-lookup"><span data-stu-id="6d68f-166">Because what you sent over was a [function](../language-reference/functions/index.md), you can now call that function with FSI!</span></span> <span data-ttu-id="6d68f-167">En la ventana interactiva, escriba lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="6d68f-167">In the interactive window, type the following:</span></span>

```fsharp
toPigLatin "banana";;
```

<span data-ttu-id="6d68f-168">Debe ver el siguiente resultado:</span><span class="sxs-lookup"><span data-stu-id="6d68f-168">You should see the following result:</span></span>

```fsharp
val it : string = "ananabay"
```

<span data-ttu-id="6d68f-169">Ahora, vamos a intentarlo con una vocal como la primera letra.</span><span class="sxs-lookup"><span data-stu-id="6d68f-169">Now, let's try with a vowel as the first letter.</span></span> <span data-ttu-id="6d68f-170">Escriba lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="6d68f-170">Enter the following:</span></span>

```fsharp
toPigLatin "apple";;
```

<span data-ttu-id="6d68f-171">Debe ver el siguiente resultado:</span><span class="sxs-lookup"><span data-stu-id="6d68f-171">You should see the following result:</span></span>

```fsharp
val it : string = "appleyay"
```

<span data-ttu-id="6d68f-172">La función parece funcionar según lo esperado.</span><span class="sxs-lookup"><span data-stu-id="6d68f-172">The function appears to be working as expected.</span></span> <span data-ttu-id="6d68f-173">Enhorabuena, simplemente se escribió la primera función de F # en el código de Visual Studio y se evalúa con FSI.</span><span class="sxs-lookup"><span data-stu-id="6d68f-173">Congratulations, you just wrote your first F# function in Visual Studio Code and evaluated it with FSI!</span></span>

>[!NOTE]
<span data-ttu-id="6d68f-174">Tal y como se observa, las líneas de FSI terminan con `;;`.</span><span class="sxs-lookup"><span data-stu-id="6d68f-174">As you may have noticed, the lines in FSI are terminated with `;;`.</span></span> <span data-ttu-id="6d68f-175">Esto es porque FSI le permite escribir varias líneas.</span><span class="sxs-lookup"><span data-stu-id="6d68f-175">This is because FSI allows you to enter multiple lines.</span></span> <span data-ttu-id="6d68f-176">El `;;` al final, FSI podrá saber cuando finalice el código.</span><span class="sxs-lookup"><span data-stu-id="6d68f-176">The `;;` at the end lets FSI know when the code is finished.</span></span>

## <a name="explaining-the-code"></a><span data-ttu-id="6d68f-177">Que explica el código</span><span class="sxs-lookup"><span data-stu-id="6d68f-177">Explaining the code</span></span>

<span data-ttu-id="6d68f-178">Si no está seguro de lo que realmente está haciendo el código, este es un paso a paso.</span><span class="sxs-lookup"><span data-stu-id="6d68f-178">If you're not sure about what the code is actually doing, here's a step-by-step.</span></span>

<span data-ttu-id="6d68f-179">Como puede ver, `toPigLatin` es una función que toma una palabra como entrada y lo convierte en una representación de Pig latino de esa palabra.</span><span class="sxs-lookup"><span data-stu-id="6d68f-179">As you can see, `toPigLatin` is a function that takes a word as its input and converts it to a Pig-Latin representation of that word.</span></span> <span data-ttu-id="6d68f-180">Las reglas para esto son los siguientes:</span><span class="sxs-lookup"><span data-stu-id="6d68f-180">The rules for this are as follows:</span></span>

<span data-ttu-id="6d68f-181">Si el primer carácter de una palabra comienza con una vocal, agregue "yay" al final de la palabra.</span><span class="sxs-lookup"><span data-stu-id="6d68f-181">If the first character in a word starts with a vowel, add "yay" to the end of the word.</span></span> <span data-ttu-id="6d68f-182">Si no se inicia con una vocal, mover ese primer carácter al final de la palabra y "en" Agregar a ella.</span><span class="sxs-lookup"><span data-stu-id="6d68f-182">If it doesn't start with a vowel, move that first character to the end of the word and add "ay" to it.</span></span>

<span data-ttu-id="6d68f-183">Es podrán que haya observado lo siguiente en FSI:</span><span class="sxs-lookup"><span data-stu-id="6d68f-183">You may have noticed the following in FSI:</span></span>

```fsharp
val toPigLatin : word:string -> string
```

<span data-ttu-id="6d68f-184">Esto indica que `toPigLatin` es una función que toma un `string` como entrada (llamado `word`) y devuelve otro `string`.</span><span class="sxs-lookup"><span data-stu-id="6d68f-184">This states that `toPigLatin` is a function that takes in a `string` as input (called `word`), and returns another `string`.</span></span> <span data-ttu-id="6d68f-185">Esto se conoce como el [signatura de tipo de la función](https://fsharpforfunandprofit.com/posts/function-signatures/), una parte fundamental de F #, que es clave para comprender el código de F #.</span><span class="sxs-lookup"><span data-stu-id="6d68f-185">This is known as the [type signature of the function](https://fsharpforfunandprofit.com/posts/function-signatures/), a fundamental piece of F# that's key to understanding F# code.</span></span> <span data-ttu-id="6d68f-186">También podrá observar si mantiene el mouse sobre la función en código de Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="6d68f-186">You'll also notice this if you hover over the function in Visual Studio Code.</span></span>

<span data-ttu-id="6d68f-187">En el cuerpo de la función, verá dos partes distintas:</span><span class="sxs-lookup"><span data-stu-id="6d68f-187">In the body of the function, you'll notice two distinct parts:</span></span>

1. <span data-ttu-id="6d68f-188">Una función interna, denominada `isVowel`, que determina si un carácter determinado (`c`) es una vocal comprobando si coincide con uno de los modelos proporcionados a través de [coincidencia de patrones](../language-reference/pattern-matching.md):</span><span class="sxs-lookup"><span data-stu-id="6d68f-188">An inner function, called `isVowel`, that determines if a given character (`c`) is a vowel by checking if it matches one of the provided patterns via [Pattern Matching](../language-reference/pattern-matching.md):</span></span>

   [!code-fsharp[ToPigLatin](../../../samples/snippets/fsharp/getting-started/to-pig-latin.fsx#L2-L6)]

2. <span data-ttu-id="6d68f-189">Un [ `if..then..else` ](../language-reference/conditional-expressions-if-then-else.md) expresión que comprueba si el primer carácter es una vocal, y construcciones un retorno de valor fuera de los caracteres de entrada según if el primer carácter era una vocal o no:</span><span class="sxs-lookup"><span data-stu-id="6d68f-189">An [`if..then..else`](../language-reference/conditional-expressions-if-then-else.md) expression that checks if the first character is a vowel, and constructs a return value out of the input characters based on if the first character was a vowel or not:</span></span>

   [!code-fsharp[ToPigLatin](../../../samples/snippets/fsharp/getting-started/to-pig-latin.fsx#L8-L11)]

<span data-ttu-id="6d68f-190">El flujo de `toPigLatin` es así:</span><span class="sxs-lookup"><span data-stu-id="6d68f-190">The flow of `toPigLatin` is thus:</span></span>

<span data-ttu-id="6d68f-191">Compruebe si el primer carácter de la palabra de entrada es una vocal.</span><span class="sxs-lookup"><span data-stu-id="6d68f-191">Check if the first character of the input word is a vowel.</span></span> <span data-ttu-id="6d68f-192">Si es así, adjuntar "yay" al final de la palabra.</span><span class="sxs-lookup"><span data-stu-id="6d68f-192">If it is, attach "yay" to the end of the word.</span></span> <span data-ttu-id="6d68f-193">En caso contrario, mueva ese primer carácter al final de la palabra y "en" Agregar a ella.</span><span class="sxs-lookup"><span data-stu-id="6d68f-193">Otherwise, move that first character to the end of the word and add "ay" to it.</span></span>

<span data-ttu-id="6d68f-194">Hay una última cosa deben tener en cuenta esto: no hay ninguna instrucción explícita para devolver de la función, a diferencia de muchos otros lenguajes por ahí.</span><span class="sxs-lookup"><span data-stu-id="6d68f-194">There's one final thing to notice about this: there's no explicit instruction to return from the function, unlike many other languages out there.</span></span> <span data-ttu-id="6d68f-195">Esto es porque F # es basadas en expresiones y la última expresión en el cuerpo de una función es el valor devuelto.</span><span class="sxs-lookup"><span data-stu-id="6d68f-195">This is because F# is Expression-based, and the last expression in the body of a function is the return value.</span></span> <span data-ttu-id="6d68f-196">Dado que `if..then..else` es en sí mismo una expresión, el cuerpo de la `then` bloque o en el cuerpo de la `else` bloque se devolverán según el valor de entrada.</span><span class="sxs-lookup"><span data-stu-id="6d68f-196">Because `if..then..else` is itself an expression, the body of the `then` block or the body of the `else` block will be returned depending on the input value.</span></span>

## <a name="moving-your-script-code-into-the-implementation-file"></a><span data-ttu-id="6d68f-197">Mover el código de script en el archivo de implementación</span><span class="sxs-lookup"><span data-stu-id="6d68f-197">Moving your script code into the implementation file</span></span>

<span data-ttu-id="6d68f-198">Las secciones anteriores de este artículo muestran un primer paso comunes para escribir código de F #: escribir una función inicial y se ejecuta de forma interactiva con FSI.</span><span class="sxs-lookup"><span data-stu-id="6d68f-198">The previous sections in this article demonstrated a common first step in writing F# code: writing an initial function and executing it interactively with FSI.</span></span> <span data-ttu-id="6d68f-199">Esto se conoce como el desarrollo basado en replicación, donde [REPL](https://en.wikipedia.org/wiki/Read%E2%80%93eval%E2%80%93print_loop) es el acrónimo "Bucle de impresión evaluar lectura".</span><span class="sxs-lookup"><span data-stu-id="6d68f-199">This is known as REPL-driven development, where [REPL](https://en.wikipedia.org/wiki/Read%E2%80%93eval%E2%80%93print_loop) stands for "Read-Evaluate-Print Loop".</span></span> <span data-ttu-id="6d68f-200">Es una excelente manera de experimentar con funcionalidad hasta que haya algo a funcionar.</span><span class="sxs-lookup"><span data-stu-id="6d68f-200">It's a great way to experiment with functionality until you have something working.</span></span>

<span data-ttu-id="6d68f-201">El siguiente paso en el desarrollo controlado por la replicación es mover el código de trabajo en un archivo de implementación de F #.</span><span class="sxs-lookup"><span data-stu-id="6d68f-201">The next step in REPL-driven development is to move working code into an F# implementation file.</span></span> <span data-ttu-id="6d68f-202">A continuación, se pueden compilar por el compilador de F # en un ensamblado que se pueden ejecutar.</span><span class="sxs-lookup"><span data-stu-id="6d68f-202">It can then be compiled by the F# compiler into an assembly that can be executed.</span></span>

<span data-ttu-id="6d68f-203">Para comenzar, abra `ClassLibraryDemo.fs`.</span><span class="sxs-lookup"><span data-stu-id="6d68f-203">To begin, open `ClassLibraryDemo.fs`.</span></span>  <span data-ttu-id="6d68f-204">Observará que parte del código está en ella.</span><span class="sxs-lookup"><span data-stu-id="6d68f-204">You'll notice that some code is already in there.</span></span> <span data-ttu-id="6d68f-205">Siga adelante y eliminar la definición de clase, pero asegúrese de dejar el [ `namespace` ](../language-reference/namespaces.md) declaración en la parte superior.</span><span class="sxs-lookup"><span data-stu-id="6d68f-205">Go ahead and delete the class definition, but make sure to leave the [`namespace`](../language-reference/namespaces.md) declaration at the top.</span></span>

<span data-ttu-id="6d68f-206">A continuación, cree un nuevo [ `module` ](../language-reference/modules.md) llama `PigLatin` y copie la `toPigLatin` función en él como tales:</span><span class="sxs-lookup"><span data-stu-id="6d68f-206">Next, create a new [`module`](../language-reference/modules.md) called `PigLatin` and copy the `toPigLatin` function into it as such:</span></span>

[!code-fsharp[ToPigLatin](../../../samples/snippets/fsharp/getting-started/pig-latin.fs#L1-L14)]

<span data-ttu-id="6d68f-207">A continuación, abra el `Script.fsx` archivo nuevo y eliminar toda la matriz `toPigLatin` funcionando, pero debe asegurarse de mantener las dos líneas siguientes en el archivo:</span><span class="sxs-lookup"><span data-stu-id="6d68f-207">Next, open the `Script.fsx` file again, and delete the entire `toPigLatin` function, but make sure to keep the following two lines in the file:</span></span>

```fsharp
#load "ClassLibraryDemo.fs"
open ClassLibraryDemo
```

<span data-ttu-id="6d68f-208">La primera línea es necesario para FSI secuencias de comandos para cargar `ClassLibraryDemo.fs`.</span><span class="sxs-lookup"><span data-stu-id="6d68f-208">The first line is needed for FSI scripting to load `ClassLibraryDemo.fs`.</span></span> <span data-ttu-id="6d68f-209">La segunda línea es su comodidad: omitiéndola es opcional, pero debe escribir `open ClassLibraryDemo` en una ventana FSI si desea volver a poner el `ToPigLatin` módulo en el ámbito.</span><span class="sxs-lookup"><span data-stu-id="6d68f-209">The second line is a convenience: omitting it is optional, but you will need to type `open ClassLibraryDemo` in an FSI window if you wish to bring the `ToPigLatin` module into scope.</span></span>

<span data-ttu-id="6d68f-210">A continuación, en la ventana FSI, llame a la función con el `PigLatin` módulo que definió anteriormente:</span><span class="sxs-lookup"><span data-stu-id="6d68f-210">Next, in the FSI window, call the function with the `PigLatin` module that you defined earlier:</span></span>

```
> PigLatin.toPigLatin "banana";;
val it : string = "ananabay"
> PigLatin.toPigLatin "apple";;
val it : string = "appleyay"
```

<span data-ttu-id="6d68f-211">Correcto</span><span class="sxs-lookup"><span data-stu-id="6d68f-211">Success!</span></span> <span data-ttu-id="6d68f-212">Obtener los mismos resultados que antes, pero ahora se carga desde un archivo de implementación de F #.</span><span class="sxs-lookup"><span data-stu-id="6d68f-212">You get the same results as before, but now loaded from an F# implementation file.</span></span> <span data-ttu-id="6d68f-213">La principal diferencia es que los archivos de código fuente de F # se compilan en ensamblados que se pueden ejecutar en cualquier lugar, no solo en FSI.</span><span class="sxs-lookup"><span data-stu-id="6d68f-213">The major difference here is that F# source files are compiled into assemblies that can be executed anywhere, not just in FSI.</span></span>

## <a name="summary"></a><span data-ttu-id="6d68f-214">Resumen</span><span class="sxs-lookup"><span data-stu-id="6d68f-214">Summary</span></span>

<span data-ttu-id="6d68f-215">En este artículo, ha aprendido:</span><span class="sxs-lookup"><span data-stu-id="6d68f-215">In this article, you've learned:</span></span>

1. <span data-ttu-id="6d68f-216">Cómo configurar el código de Visual Studio con Ionide.</span><span class="sxs-lookup"><span data-stu-id="6d68f-216">How to set up Visual Studio Code with Ionide.</span></span>
2. <span data-ttu-id="6d68f-217">Cómo crear su primer proyecto de F # con Ionide.</span><span class="sxs-lookup"><span data-stu-id="6d68f-217">How to create your first F# project with Ionide.</span></span>
3. <span data-ttu-id="6d68f-218">Describe cómo usar Scripting F # para escribir su primera función de F # en Ionide y, a continuación, se ejecutan en FSI.</span><span class="sxs-lookup"><span data-stu-id="6d68f-218">How to use F# Scripting to write your first F# function in Ionide and then execute it in FSI.</span></span>
4. <span data-ttu-id="6d68f-219">Cómo migrar el código de script al código fuente de F # y, a continuación, llame a ese código desde FSI.</span><span class="sxs-lookup"><span data-stu-id="6d68f-219">How to migrate your script code to F# source and then call that code from FSI.</span></span>

<span data-ttu-id="6d68f-220">Ahora está equipado para escribir mucho más código F # mediante código de Visual Studio y Ionide.</span><span class="sxs-lookup"><span data-stu-id="6d68f-220">You're now equipped to write much more F# code using Visual Studio Code and Ionide.</span></span>

## <a name="troubleshooting"></a><span data-ttu-id="6d68f-221">Solución de problemas</span><span class="sxs-lookup"><span data-stu-id="6d68f-221">Troubleshooting</span></span>

<span data-ttu-id="6d68f-222">Aquí se muestran algunas maneras de que puede solucionar determinados problemas que pueden surgir:</span><span class="sxs-lookup"><span data-stu-id="6d68f-222">Here are a few ways you can troubleshoot certain problems that you might run into:</span></span>

1. <span data-ttu-id="6d68f-223">Para obtener la características de Ionide de edición de código, los archivos de F # deben guardarse en el disco y dentro de una carpeta que está abierta en el área de trabajo de código de Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="6d68f-223">To get the code editing features of Ionide, your F# files need to be saved to disk and inside of a folder that is open in the Visual Studio Code workspace.</span></span>
2. <span data-ttu-id="6d68f-224">Si ha realizado cambios en el sistema o instalar requisitos previos de Ionide con código de Visual Studio abierto, reinicie Visual Studio Code.</span><span class="sxs-lookup"><span data-stu-id="6d68f-224">If you've made changes to your system or installed Ionide prerequisites with Visual Studio Code open, restart Visual Studio Code.</span></span>
3. <span data-ttu-id="6d68f-225">Compruebe que puede utilizar el compilador de F # y F # interactive desde la línea de comandos sin una ruta de acceso completa.</span><span class="sxs-lookup"><span data-stu-id="6d68f-225">Check that you can use the F# compiler and F# interactive from the command line without a fully-qualified path.</span></span> <span data-ttu-id="6d68f-226">Puede hacerlo escribiendo `fsc` en una línea de comandos para el compilador de F #, y `fsi` o `fsharpi` para Visual F # las herramientas de Windows y Mono en Mac o Linux, respectivamente.</span><span class="sxs-lookup"><span data-stu-id="6d68f-226">You can do so by typing `fsc` in a command line for the F# compiler, and `fsi` or `fsharpi` for the Visual F# tools on Windows and Mono on Mac/Linux, respectively.</span></span>
4. <span data-ttu-id="6d68f-227">Si tiene caracteres no válidos en los directorios del proyecto, Ionide podrían no funcionar.</span><span class="sxs-lookup"><span data-stu-id="6d68f-227">If you have invalid characters in your project directories, Ionide might not work.</span></span>  <span data-ttu-id="6d68f-228">Cambiar el nombre de los directorios del proyecto si éste es el caso.</span><span class="sxs-lookup"><span data-stu-id="6d68f-228">Rename your project directories if this is the case.</span></span>
5. <span data-ttu-id="6d68f-229">Si ninguno de los comandos Ionide está trabajando, compruebe su [enlaces de teclado de Visual Studio Code](https://code.visualstudio.com/docs/customization/keybindings#_customizing-shortcuts) para ver si se está reemplazando por accidente.</span><span class="sxs-lookup"><span data-stu-id="6d68f-229">If none of the Ionide commands are working, check your [Visual Studio Code keybindings](https://code.visualstudio.com/docs/customization/keybindings#_customizing-shortcuts) to see if you're overriding them by accident.</span></span>
6. <span data-ttu-id="6d68f-230">Si se divide Ionide en su equipo y ninguno de los anteriores solucionó el problema, pruebe a quitar el `ionide-fsharp` directorio en su equipo y vuelva a instalar el conjunto de complementos.</span><span class="sxs-lookup"><span data-stu-id="6d68f-230">If Ionide is broken on your machine and none of the above has fixed your problem, try removing the `ionide-fsharp` directory on your machine and reinstall the plugin suite.</span></span>

<span data-ttu-id="6d68f-231">Ionide es un proyecto de código abierto crea y mantiene los miembros de la Comunidad de F #.</span><span class="sxs-lookup"><span data-stu-id="6d68f-231">Ionide is an open source project built and maintained by members of the F# community.</span></span> <span data-ttu-id="6d68f-232">Por favor, notificar problemas y no dude en contribuir en el [Ionide VSCode: repositorio de FSharp GitHub](https://github.com/ionide/ionide-vscode-fsharp).</span><span class="sxs-lookup"><span data-stu-id="6d68f-232">Please report issues and feel free to contribute at the [Ionide-VSCode: FSharp GitHub repository](https://github.com/ionide/ionide-vscode-fsharp).</span></span>

<span data-ttu-id="6d68f-233">Si tiene un problema al informe, siga [las instrucciones para obtener los registros que se utilizará al informar de un problema](https://github.com/ionide/ionide-vscode-fsharp#how-to-get-logs-for-debugging--issue-reporting).</span><span class="sxs-lookup"><span data-stu-id="6d68f-233">If you have an issue to report, please follow [the instructions for getting logs to use when reporting an issue](https://github.com/ionide/ionide-vscode-fsharp#how-to-get-logs-for-debugging--issue-reporting).</span></span>

<span data-ttu-id="6d68f-234">También puede pedir ayuda adicional de los desarrolladores de Ionide y la Comunidad de F # en el [Ionide Gitter canal](https://gitter.im/ionide/ionide-project).</span><span class="sxs-lookup"><span data-stu-id="6d68f-234">You can also ask for further help from the Ionide developers and F# community in the [Ionide Gitter channel](https://gitter.im/ionide/ionide-project).</span></span>

## <a name="next-steps"></a><span data-ttu-id="6d68f-235">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="6d68f-235">Next steps</span></span>

<span data-ttu-id="6d68f-236">Para obtener más información sobre F # y las características del lenguaje, visite [paseo de F #](../tour.md).</span><span class="sxs-lookup"><span data-stu-id="6d68f-236">To learn more about F# and the features of the language, check out [Tour of F#](../tour.md).</span></span>
