---
title: Procedimiento para firmar un ensamblado con un nombre seguro
ms.date: 08/20/2019
helpviewer_keywords:
- strong-named assemblies, signing with strong names
- signing assemblies
- assemblies [.NET Framework], signing
- assemblies [.NET Framework], strong-named
ms.assetid: 2c30799a-a826-46b4-a25d-c584027a6c67
dev_langs:
- csharp
- vb
- cpp
ms.openlocfilehash: 9998e69e8bf1505bcfc7a9103e9d89616dad9633
ms.sourcegitcommit: 00aa62e2f469c2272a457b04e66b4cc3c97a800b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/28/2020
ms.locfileid: "78160318"
---
# <a name="how-to-sign-an-assembly-with-a-strong-name"></a><span data-ttu-id="794c1-102">Procedimiento para firmar un ensamblado con un nombre seguro</span><span class="sxs-lookup"><span data-stu-id="794c1-102">How to: Sign an assembly with a strong name</span></span>

> [!NOTE]
> <span data-ttu-id="794c1-103">Aunque .NET Core admite ensamblados con nombre seguro, y todos los ensamblados de la biblioteca .NET Core están firmados, la mayoría de los ensamblados de terceros no necesitan nombres seguros.</span><span class="sxs-lookup"><span data-stu-id="794c1-103">Although .NET Core supports strong-named assemblies, and all assemblies in the .NET Core library are signed, the majority of third-party assemblies do not need strong names.</span></span> <span data-ttu-id="794c1-104">Para obtener más información, consulte [Strong Name Signing (Firma con nombre seguro)](https://github.com/dotnet/runtime/blob/master/docs/project/strong-name-signing.md) en GitHub.</span><span class="sxs-lookup"><span data-stu-id="794c1-104">For more information, see [Strong Name Signing](https://github.com/dotnet/runtime/blob/master/docs/project/strong-name-signing.md) on GitHub.</span></span>

<span data-ttu-id="794c1-105">Existen varias formas de firmar un ensamblado con un nombre seguro:</span><span class="sxs-lookup"><span data-stu-id="794c1-105">There are a number of ways to sign an assembly with a strong name:</span></span>  
  
- <span data-ttu-id="794c1-106">Mediante la pestaña **Firma** del cuadro de diálogo **Propiedades** de un proyecto en Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="794c1-106">By using the **Signing** tab in a project's **Properties** dialog box in Visual Studio.</span></span> <span data-ttu-id="794c1-107">Esta es la forma más sencilla y cómoda de firmar un ensamblado con un nombre seguro.</span><span class="sxs-lookup"><span data-stu-id="794c1-107">This is the easiest and most convenient way to sign an assembly with a strong name.</span></span>  
  
- <span data-ttu-id="794c1-108">Mediante el uso de [Assembly Linker (Al.exe)](../../framework/tools/al-exe-assembly-linker.md) para vincular un módulo de código de .NET Framework (un archivo *.netmodule*) a un archivo de claves.</span><span class="sxs-lookup"><span data-stu-id="794c1-108">By using the [Assembly Linker (Al.exe)](../../framework/tools/al-exe-assembly-linker.md) to link a .NET Framework code module (a *.netmodule* file) with a key file.</span></span>  
  
- <span data-ttu-id="794c1-109">Mediante el uso de atributos de ensamblado para insertar la información de nombre seguro en el código.</span><span class="sxs-lookup"><span data-stu-id="794c1-109">By using assembly attributes to insert the strong name information into your code.</span></span> <span data-ttu-id="794c1-110">Se puede usar el atributo <xref:System.Reflection.AssemblyKeyFileAttribute> o <xref:System.Reflection.AssemblyKeyNameAttribute> , dependiendo de dónde esté ubicado el archivo de claves que se va a utilizar.</span><span class="sxs-lookup"><span data-stu-id="794c1-110">You can use either the <xref:System.Reflection.AssemblyKeyFileAttribute> or the <xref:System.Reflection.AssemblyKeyNameAttribute> attribute, depending on where the key file to be used is located.</span></span>  
  
- <span data-ttu-id="794c1-111">Mediante el uso de opciones del compilador.</span><span class="sxs-lookup"><span data-stu-id="794c1-111">By using compiler options.</span></span>  
  
 <span data-ttu-id="794c1-112">Es necesario disponer de un par de claves criptográficas para firmar un ensamblado con un nombre seguro.</span><span class="sxs-lookup"><span data-stu-id="794c1-112">You must have a cryptographic key pair to sign an assembly with a strong name.</span></span> <span data-ttu-id="794c1-113">Para obtener más información sobre la creación de un par de claves, vea [Cómo: Crear un par de claves privada y pública](create-public-private-key-pair.md).</span><span class="sxs-lookup"><span data-stu-id="794c1-113">For more information about creating a key pair, see [How to: Create a public-private key pair](create-public-private-key-pair.md).</span></span>  
  
## <a name="create-and-sign-an-assembly-with-a-strong-name-by-using-visual-studio"></a><span data-ttu-id="794c1-114">Creación y firma de un ensamblado con un nombre seguro mediante el uso de Visual Studio</span><span class="sxs-lookup"><span data-stu-id="794c1-114">Create and sign an assembly with a strong name by using Visual Studio</span></span>  
  
1. <span data-ttu-id="794c1-115">En el **Explorador de soluciones**, abra el menú contextual del proyecto y luego elija **Propiedades**.</span><span class="sxs-lookup"><span data-stu-id="794c1-115">In **Solution Explorer**, open the shortcut menu for the project, and then choose **Properties**.</span></span>  
  
2. <span data-ttu-id="794c1-116">Elija la pestaña **Firma** .</span><span class="sxs-lookup"><span data-stu-id="794c1-116">Choose the **Signing** tab.</span></span>  
  
3. <span data-ttu-id="794c1-117">Active la casilla **Firmar el ensamblado** .</span><span class="sxs-lookup"><span data-stu-id="794c1-117">Select the **Sign the assembly** box.</span></span>  
  
4. <span data-ttu-id="794c1-118">En la casilla **Elija un archivo de clave de nombre seguro**, elija **Examinar** y, a continuación, navegue hasta el archivo de claves.</span><span class="sxs-lookup"><span data-stu-id="794c1-118">In the **Choose a strong name key file** box, choose **Browse**, and then navigate to the key file.</span></span> <span data-ttu-id="794c1-119">Para crear un nuevo archivo de claves, elija **Nuevo** y escriba su nombre en el cuadro de diálogo **Crear clave de nombre seguro**.</span><span class="sxs-lookup"><span data-stu-id="794c1-119">To create a new key file, choose **New** and enter its name in the **Create Strong Name Key** dialog box.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="794c1-120">Para [retrasar la firma de un ensamblado](delay-sign.md), elija un archivo de clave pública.</span><span class="sxs-lookup"><span data-stu-id="794c1-120">In order to [delay sign an assembly](delay-sign.md), choose a public key file.</span></span>  
  
### <a name="create-and-sign-an-assembly-with-a-strong-name-by-using-the-assembly-linker"></a><span data-ttu-id="794c1-121">Creación y firma de un ensamblado con un nombre seguro mediante el uso de la herramienta Assembly Linker</span><span class="sxs-lookup"><span data-stu-id="794c1-121">Create and sign an assembly with a strong name by using the Assembly Linker</span></span>  
  
<span data-ttu-id="794c1-122">En [Símbolo del sistema para desarrolladores de Visual Studio](../../framework/tools/developer-command-prompt-for-vs.md), escriba el comando siguiente:</span><span class="sxs-lookup"><span data-stu-id="794c1-122">At the [Developer Command Prompt for Visual Studio](../../framework/tools/developer-command-prompt-for-vs.md), enter the following command:</span></span>  

<span data-ttu-id="794c1-123">**al** **/out:** \<*assemblyName*>  *\<moduleName>* **/keyfile:** \<*keyfileName*></span><span class="sxs-lookup"><span data-stu-id="794c1-123">**al** **/out:**\<*assemblyName*> *\<moduleName>* **/keyfile:**\<*keyfileName*></span></span>  

<span data-ttu-id="794c1-124">Dónde:</span><span class="sxs-lookup"><span data-stu-id="794c1-124">Where:</span></span>  

- <span data-ttu-id="794c1-125">*assemblyName* es el nombre del ensamblado seguro con firma (un archivo *.dll* o *.exe*) que emitirá la herramienta Assembly Linker.</span><span class="sxs-lookup"><span data-stu-id="794c1-125">*assemblyName* is the name of the strongly signed assembly (a *.dll* or *.exe* file) that Assembly Linker will emit.</span></span>  
  
- <span data-ttu-id="794c1-126">*moduleName* es el nombre de un módulo de código de .NET Framework (un archivo *.netmodule*) que incluye uno o varios tipos.</span><span class="sxs-lookup"><span data-stu-id="794c1-126">*moduleName* is the name of a .NET Framework code module (a *.netmodule* file) that includes one or more types.</span></span> <span data-ttu-id="794c1-127">Puede crear un archivo *.netmodule* si compila el código con el modificador `/target:module` en C# o Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="794c1-127">You can create a *.netmodule* file by compiling your code with the `/target:module` switch in C# or Visual Basic.</span></span>
  
- <span data-ttu-id="794c1-128">*keyfileName* es el nombre del contenedor o del archivo que incluye el par de claves.</span><span class="sxs-lookup"><span data-stu-id="794c1-128">*keyfileName* is the name of the container or file that contains the key pair.</span></span> <span data-ttu-id="794c1-129">Assembly Linker interpreta una ruta de acceso relativa en relación con el directorio actual.</span><span class="sxs-lookup"><span data-stu-id="794c1-129">Assembly Linker interprets a relative path in relation to the current directory.</span></span>  

<span data-ttu-id="794c1-130">En el ejemplo siguiente se firma el ensamblado *MyAssembly.dll* con un nombre seguro mediante el uso del archivo de clave *sgKey.snk*.</span><span class="sxs-lookup"><span data-stu-id="794c1-130">The following example signs the assembly *MyAssembly.dll* with a strong name by using the key file *sgKey.snk*.</span></span>  

```console
al /out:MyAssembly.dll MyModule.netmodule /keyfile:sgKey.snk  
```  
  
<span data-ttu-id="794c1-131">Para obtener más información sobre esta herramienta, consulte el tema sobre [Assembly Linker](../../framework/tools/al-exe-assembly-linker.md).</span><span class="sxs-lookup"><span data-stu-id="794c1-131">For more information about this tool, see [Assembly Linker](../../framework/tools/al-exe-assembly-linker.md).</span></span>  
  
## <a name="sign-an-assembly-with-a-strong-name-by-using-attributes"></a><span data-ttu-id="794c1-132">Firma de un ensamblado con un nombre seguro mediante el uso de atributos</span><span class="sxs-lookup"><span data-stu-id="794c1-132">Sign an assembly with a strong name by using attributes</span></span>  
  
1. <span data-ttu-id="794c1-133">Agregue el atributo <xref:System.Reflection.AssemblyKeyFileAttribute?displayProperty=nameWithType> o <xref:System.Reflection.AssemblyKeyNameAttribute> al archivo de código fuente y especifique el nombre del archivo o contenedor donde se incluye el par de claves que se va a usar al firmar el ensamblado con un nombre seguro.</span><span class="sxs-lookup"><span data-stu-id="794c1-133">Add the <xref:System.Reflection.AssemblyKeyFileAttribute?displayProperty=nameWithType> or <xref:System.Reflection.AssemblyKeyNameAttribute> attribute to your source code file, and specify the name of the file or container that contains the key pair to use when signing the assembly with a strong name.</span></span>  

2. <span data-ttu-id="794c1-134">Compile el archivo de código fuente normalmente.</span><span class="sxs-lookup"><span data-stu-id="794c1-134">Compile the source code file normally.</span></span>  

   > [!NOTE]
   > <span data-ttu-id="794c1-135">Los compiladores de C# y Visual Basic emiten advertencias del compilador (CS1699 y BC41008, respectivamente) cuando encuentran el atributo <xref:System.Reflection.AssemblyKeyFileAttribute> o <xref:System.Reflection.AssemblyKeyNameAttribute> en el código fuente.</span><span class="sxs-lookup"><span data-stu-id="794c1-135">The C# and Visual Basic compilers issue compiler warnings (CS1699 and BC41008, respectively) when they encounter the <xref:System.Reflection.AssemblyKeyFileAttribute> or <xref:System.Reflection.AssemblyKeyNameAttribute> attribute in source code.</span></span> <span data-ttu-id="794c1-136">Las advertencias se pueden omitir.</span><span class="sxs-lookup"><span data-stu-id="794c1-136">You can ignore the warnings.</span></span>  

<span data-ttu-id="794c1-137">En el ejemplo siguiente se usa el atributo <xref:System.Reflection.AssemblyKeyFileAttribute> con un archivo de claves denominado *keyfile.snk*, que está ubicado en el directorio en el cual se compila el ensamblado.</span><span class="sxs-lookup"><span data-stu-id="794c1-137">The following example uses the <xref:System.Reflection.AssemblyKeyFileAttribute> attribute with a key file called *keyfile.snk*, which is located in the directory where the assembly is compiled.</span></span>  

```cpp
[assembly:AssemblyKeyFileAttribute("keyfile.snk")];
```

```csharp
[assembly:AssemblyKeyFileAttribute("keyfile.snk")]
```

```vb
<Assembly:AssemblyKeyFileAttribute("keyfile.snk")>
```

<span data-ttu-id="794c1-138">También se puede retrasar la firma de un ensamblado al compilar el archivo de código fuente.</span><span class="sxs-lookup"><span data-stu-id="794c1-138">You can also delay sign an assembly when compiling your source file.</span></span> <span data-ttu-id="794c1-139">Para obtener más información, vea [Retraso de la firma de un ensamblado](delay-sign.md).</span><span class="sxs-lookup"><span data-stu-id="794c1-139">For more information, see [Delay-sign an assembly](delay-sign.md).</span></span>  

## <a name="sign-an-assembly-with-a-strong-name-by-using-the-compiler"></a><span data-ttu-id="794c1-140">Firma de un ensamblado con un nombre seguro mediante el uso del compilador</span><span class="sxs-lookup"><span data-stu-id="794c1-140">Sign an assembly with a strong name by using the compiler</span></span>  

<span data-ttu-id="794c1-141">Compile el archivo o archivos de código fuente con la opción del compilador `/keyfile` o de `/delaysign` en C# y Visual Basic, o la opción del vinculador `/KEYFILE` o `/DELAYSIGN` en C++.</span><span class="sxs-lookup"><span data-stu-id="794c1-141">Compile your source code file or files with the `/keyfile` or `/delaysign` compiler option in C# and Visual Basic, or the `/KEYFILE` or `/DELAYSIGN` linker option in C++.</span></span> <span data-ttu-id="794c1-142">Tras el nombre de la opción, agregue dos puntos y el nombre del archivo de claves.</span><span class="sxs-lookup"><span data-stu-id="794c1-142">After the option name, add a colon and the name of the key file.</span></span> <span data-ttu-id="794c1-143">Si se usan compiladores de la línea de comandos, se puede copiar el archivo de claves en el directorio que contiene los archivos de código fuente.</span><span class="sxs-lookup"><span data-stu-id="794c1-143">When using command-line compilers, you can copy the key file to the directory that contains your source code files.</span></span>  

<span data-ttu-id="794c1-144">Para obtener información sobre la firma retardada, vea [Retraso de la firma de un ensamblado](delay-sign.md).</span><span class="sxs-lookup"><span data-stu-id="794c1-144">For information on delay signing, see [Delay-sign an assembly](delay-sign.md).</span></span>  

<span data-ttu-id="794c1-145">En el ejemplo siguiente se usa el compilador de C# y se firma el ensamblado *UtilityLibrary.dll* con un nombre seguro mediante el archivo de claves *sgKey.snk*.</span><span class="sxs-lookup"><span data-stu-id="794c1-145">The following example uses the C# compiler and signs the assembly *UtilityLibrary.dll* with a strong name by using the key file *sgKey.snk*.</span></span>  

```cmd
csc /t:library UtilityLibrary.cs /keyfile:sgKey.snk  
```  

## <a name="see-also"></a><span data-ttu-id="794c1-146">Vea también</span><span class="sxs-lookup"><span data-stu-id="794c1-146">See also</span></span>

- [<span data-ttu-id="794c1-147">Creación y uso de ensamblados con nombre seguro</span><span class="sxs-lookup"><span data-stu-id="794c1-147">Create and use strong-named assemblies</span></span>](create-use-strong-named.md)
- [<span data-ttu-id="794c1-148">Cómo: Crear un par de claves privada y pública</span><span class="sxs-lookup"><span data-stu-id="794c1-148">How to: Create a public-private key pair</span></span>](create-public-private-key-pair.md)
- [<span data-ttu-id="794c1-149">Al.exe (Assembly Linker)</span><span class="sxs-lookup"><span data-stu-id="794c1-149">Al.exe (Assembly Linker)</span></span>](../../framework/tools/al-exe-assembly-linker.md)
- [<span data-ttu-id="794c1-150">Retraso de la firma de un ensamblado</span><span class="sxs-lookup"><span data-stu-id="794c1-150">Delay-sign an assembly</span></span>](delay-sign.md)
- [<span data-ttu-id="794c1-151">Administración de la firma de ensamblados y manifiestos</span><span class="sxs-lookup"><span data-stu-id="794c1-151">Manage assembly and manifest signing</span></span>](/visualstudio/ide/managing-assembly-and-manifest-signing)
- [<span data-ttu-id="794c1-152">Página Firma, Diseñador de proyectos</span><span class="sxs-lookup"><span data-stu-id="794c1-152">Signing page, Project Designer</span></span>](/visualstudio/ide/reference/signing-page-project-designer)
