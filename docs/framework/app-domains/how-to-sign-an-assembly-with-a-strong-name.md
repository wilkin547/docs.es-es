---
title: "Cómo: Firmar un ensamblado con un nombre seguro"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-bcl
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- strong-named assemblies, signing with strong names
- signing assemblies
- assemblies [.NET Framework], signing
- assemblies [.NET Framework], strong-named
ms.assetid: 2c30799a-a826-46b4-a25d-c584027a6c67
caps.latest.revision: 23
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 7758871a22b8b58d7df5cf2df481db185c07a987
ms.contentlocale: es-es
ms.lasthandoff: 07/28/2017

---
# <a name="how-to-sign-an-assembly-with-a-strong-name"></a><span data-ttu-id="86e4d-102">Cómo: Firmar un ensamblado con un nombre seguro</span><span class="sxs-lookup"><span data-stu-id="86e4d-102">How to: Sign an Assembly with a Strong Name</span></span>
<span data-ttu-id="86e4d-103">Existen varias formas de firmar un ensamblado con un nombre seguro:</span><span class="sxs-lookup"><span data-stu-id="86e4d-103">There are a number of ways to sign an assembly with a strong name:</span></span>  
  
-   <span data-ttu-id="86e4d-104">Mediante la pestaña **Firma** del cuadro de diálogo **Propiedades** de un proyecto en Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="86e4d-104">By using the **Signing** tab in a project's **Properties** dialog box in Visual Studio.</span></span> <span data-ttu-id="86e4d-105">Esta es la forma más sencilla y cómoda de firmar un ensamblado con un nombre seguro.</span><span class="sxs-lookup"><span data-stu-id="86e4d-105">This is the easiest and most convenient way to sign an assembly with a strong name.</span></span>  
  
-   <span data-ttu-id="86e4d-106">Mediante el uso de [Assembly Linker (Al.exe)](../../../docs/framework/tools/al-exe-assembly-linker.md) para vincular un módulo de código de .NET Framework (un archivo .netmodule) a un archivo de claves.</span><span class="sxs-lookup"><span data-stu-id="86e4d-106">By using the [Assembly Linker (Al.exe)](../../../docs/framework/tools/al-exe-assembly-linker.md) to link a .NET Framework code module (a .netmodule file) with a key file.</span></span>  
  
-   <span data-ttu-id="86e4d-107">Mediante el uso de atributos de ensamblado para insertar la información de nombre seguro en el código.</span><span class="sxs-lookup"><span data-stu-id="86e4d-107">By using assembly attributes to insert the strong name information into your code.</span></span> <span data-ttu-id="86e4d-108">Se puede usar el atributo <xref:System.Reflection.AssemblyKeyFileAttribute> o <xref:System.Reflection.AssemblyKeyNameAttribute> , dependiendo de dónde esté ubicado el archivo de claves que se va a utilizar.</span><span class="sxs-lookup"><span data-stu-id="86e4d-108">You can use either the <xref:System.Reflection.AssemblyKeyFileAttribute> or the <xref:System.Reflection.AssemblyKeyNameAttribute> attribute, depending on where the key file to be used is located.</span></span>  
  
-   <span data-ttu-id="86e4d-109">Mediante el uso de opciones del compilador.</span><span class="sxs-lookup"><span data-stu-id="86e4d-109">By using compiler options.</span></span>  
  
 <span data-ttu-id="86e4d-110">Es necesario disponer de un par de claves criptográficas para firmar un ensamblado con un nombre seguro.</span><span class="sxs-lookup"><span data-stu-id="86e4d-110">You must have a cryptographic key pair to sign an assembly with a strong name.</span></span> <span data-ttu-id="86e4d-111">Para más información sobre la creación de un par de claves, vea [Cómo: Crear un par de claves privada y pública](../../../docs/framework/app-domains/how-to-create-a-public-private-key-pair.md).</span><span class="sxs-lookup"><span data-stu-id="86e4d-111">For more information about creating a key pair, see [How to: Create a Public-Private Key Pair](../../../docs/framework/app-domains/how-to-create-a-public-private-key-pair.md).</span></span>  
  
### <a name="to-create-and-sign-an-assembly-with-a-strong-name-by-using-visual-studio"></a><span data-ttu-id="86e4d-112">Para crear y firmar un ensamblado con un nombre seguro utilizando Visual Studio</span><span class="sxs-lookup"><span data-stu-id="86e4d-112">To create and sign an assembly with a strong name by using Visual Studio</span></span>  
  
1.  <span data-ttu-id="86e4d-113">En el **Explorador de soluciones**, abra el menú contextual del proyecto y luego elija **Propiedades**.</span><span class="sxs-lookup"><span data-stu-id="86e4d-113">In **Solution Explorer**, open the shortcut menu for the project, and then choose **Properties**.</span></span>  
  
2.  <span data-ttu-id="86e4d-114">Elija la pestaña **Firma** .</span><span class="sxs-lookup"><span data-stu-id="86e4d-114">Choose the **Signing** tab.</span></span>  
  
3.  <span data-ttu-id="86e4d-115">Active la casilla **Firmar el ensamblado**.</span><span class="sxs-lookup"><span data-stu-id="86e4d-115">Select the **Sign the assembly** box.</span></span>  
  
4.  <span data-ttu-id="86e4d-116">En la casilla **Elija un archivo de clave de nombre seguro**, elija **\<Examinar...>** y, a continuación, navegue hasta el archivo de claves.</span><span class="sxs-lookup"><span data-stu-id="86e4d-116">In the **Choose a strong name key file** box, choose **\<Browse…>**, and then navigate to the key file.</span></span> <span data-ttu-id="86e4d-117">Para crear un nuevo archivo de claves, elija **\<Nuevo...>** y escriba su nombre en el cuadro de diálogo **Crear clave de nombre seguro**.</span><span class="sxs-lookup"><span data-stu-id="86e4d-117">To create a new key file, choose **\<New…>** and enter its name in the **Create Strong Name Key** dialog box.</span></span>  
  
### <a name="to-create-and-sign-an-assembly-with-a-strong-name-by-using-the-assembly-linker"></a><span data-ttu-id="86e4d-118">Para crear y firmar un ensamblado con un nombre seguro utilizando la herramienta Assembly Linker</span><span class="sxs-lookup"><span data-stu-id="86e4d-118">To create and sign an assembly with a strong name by using the Assembly Linker</span></span>  
  
-   <span data-ttu-id="86e4d-119">En el [símbolo del sistema de Visual Studio](../../../docs/framework/tools/developer-command-prompt-for-vs.md), escriba el comando siguiente:</span><span class="sxs-lookup"><span data-stu-id="86e4d-119">At the [Visual Studio Command Prompt](../../../docs/framework/tools/developer-command-prompt-for-vs.md), type the following command:</span></span>  
  
     <span data-ttu-id="86e4d-120">**al** **/out:**\<*assemblyName*> *\<moduleName>* **/keyfile:**\<*keyfileName*></span><span class="sxs-lookup"><span data-stu-id="86e4d-120">**al** **/out:**\<*assemblyName*> *\<moduleName>* **/keyfile:**\<*keyfileName*></span></span>  
  
     <span data-ttu-id="86e4d-121">donde:</span><span class="sxs-lookup"><span data-stu-id="86e4d-121">where:</span></span>  
  
     <span data-ttu-id="86e4d-122">*assemblyName*</span><span class="sxs-lookup"><span data-stu-id="86e4d-122">*assemblyName*</span></span>  
     <span data-ttu-id="86e4d-123">Nombre del ensamblado firmado seguro (archivo .dll o .exe) que la herramienta Assembly Linker emitirá.</span><span class="sxs-lookup"><span data-stu-id="86e4d-123">The name of the strongly signed assembly (a .dll or .exe file) that Assembly Linker will emit.</span></span>  
  
     <span data-ttu-id="86e4d-124">*moduleName*</span><span class="sxs-lookup"><span data-stu-id="86e4d-124">*moduleName*</span></span>  
     <span data-ttu-id="86e4d-125">Nombre de un módulo de código de .NET Framework (un archivo .netmodule) que incluye uno o varios tipos.</span><span class="sxs-lookup"><span data-stu-id="86e4d-125">The name of a .NET Framework code module (a .netmodule file) that includes one or more types.</span></span> <span data-ttu-id="86e4d-126">Puede crear un archivo .netmodule si compila el código con el modificador `/target:module` en C# o Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="86e4d-126">You can create a .netmodule file by compiling your code with the `/target:module` switch in C# or Visual Basic.</span></span>  
  
     <span data-ttu-id="86e4d-127">*keyfileName*</span><span class="sxs-lookup"><span data-stu-id="86e4d-127">*keyfileName*</span></span>  
     <span data-ttu-id="86e4d-128">Nombre del contenedor o archivo que incluye el par de claves.</span><span class="sxs-lookup"><span data-stu-id="86e4d-128">The name of the container or file that contains the key pair.</span></span> <span data-ttu-id="86e4d-129">Assembly Linker interpreta una ruta de acceso relativa en relación con el directorio actual.</span><span class="sxs-lookup"><span data-stu-id="86e4d-129">Assembly Linker interprets a relative path in relationship to the current directory.</span></span>  
  
 <span data-ttu-id="86e4d-130">En el ejemplo siguiente se firma el ensamblado `MyAssembly.dll` con un nombre seguro utilizando el archivo de clave `sgKey.snk`.</span><span class="sxs-lookup"><span data-stu-id="86e4d-130">The following example signs the assembly `MyAssembly.dll` with a strong name by using the key file `sgKey.snk`.</span></span>  
  
```  
al /out:MyAssembly.dll MyModule.netmodule /keyfile:sgKey.snk  
```  
  
 <span data-ttu-id="86e4d-131">Para obtener más información sobre esta herramienta, consulte el tema sobre [Assembly Linker](../../../docs/framework/tools/al-exe-assembly-linker.md).</span><span class="sxs-lookup"><span data-stu-id="86e4d-131">For more information about this tool, see [Assembly Linker](../../../docs/framework/tools/al-exe-assembly-linker.md).</span></span>  
  
#### <a name="to-sign-an-assembly-with-a-strong-name-by-using-attributes"></a><span data-ttu-id="86e4d-132">Para firmar un ensamblado con un nombre seguro utilizando atributos</span><span class="sxs-lookup"><span data-stu-id="86e4d-132">To sign an assembly with a strong name by using attributes</span></span>  
  
1.  <span data-ttu-id="86e4d-133">Agregue el atributo <xref:System.Reflection.AssemblyKeyFileAttribute?displayProperty=fullName> o <xref:System.Reflection.AssemblyKeyNameAttribute> al archivo de código fuente y especifique el nombre del archivo o contenedor donde se incluye el par de claves que se va a usar al firmar el ensamblado con un nombre seguro.</span><span class="sxs-lookup"><span data-stu-id="86e4d-133">Add the <xref:System.Reflection.AssemblyKeyFileAttribute?displayProperty=fullName> or <xref:System.Reflection.AssemblyKeyNameAttribute> attribute to your source code file, and specify the name of the file or container that contains the key pair to use when signing the assembly with a strong name.</span></span>  
  
2.  <span data-ttu-id="86e4d-134">Compile el archivo de código fuente normalmente.</span><span class="sxs-lookup"><span data-stu-id="86e4d-134">Compile the source code file normally.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="86e4d-135">Los compiladores de C# y Visual Basic emiten advertencias del compilador (CS1699 y BC41008, respectivamente) cuando encuentran el atributo <xref:System.Reflection.AssemblyKeyFileAttribute> o <xref:System.Reflection.AssemblyKeyNameAttribute> en el código fuente.</span><span class="sxs-lookup"><span data-stu-id="86e4d-135">The C# and Visual Basic compilers issue compiler warnings (CS1699 and BC41008, respectively) when they encounter the <xref:System.Reflection.AssemblyKeyFileAttribute> or <xref:System.Reflection.AssemblyKeyNameAttribute> attribute in source code.</span></span> <span data-ttu-id="86e4d-136">Las advertencias se pueden omitir.</span><span class="sxs-lookup"><span data-stu-id="86e4d-136">You can ignore the warnings.</span></span>  
  
 <span data-ttu-id="86e4d-137">En el ejemplo siguiente se usa el atributo <xref:System.Reflection.AssemblyKeyFileAttribute> con un archivo de claves denominado `keyfile.snk`, ubicado en el directorio en el que se compila el ensamblado.</span><span class="sxs-lookup"><span data-stu-id="86e4d-137">The following example uses the <xref:System.Reflection.AssemblyKeyFileAttribute> attribute with a key file called `keyfile.snk`, which is located in the directory where the assembly is compiled.</span></span>  
  
 <span data-ttu-id="86e4d-138">[!code-cpp[AssemblyName_KeyPair#21](../../../samples/snippets/cpp/VS_Snippets_CLR/AssemblyName_KeyPair/CPP/keyfileattrib.cpp#21)] [!code-csharp[AssemblyName_KeyPair#21](../../../samples/snippets/csharp/VS_Snippets_CLR/AssemblyName_KeyPair/CS/keyfileattrib.cs#21)] [!code-vb[AssemblyName_KeyPair#21](../../../samples/snippets/visualbasic/VS_Snippets_CLR/AssemblyName_KeyPair/VB/keyfileattrib.vb#21)]</span><span class="sxs-lookup"><span data-stu-id="86e4d-138">[!code-cpp[AssemblyName_KeyPair#21](../../../samples/snippets/cpp/VS_Snippets_CLR/AssemblyName_KeyPair/CPP/keyfileattrib.cpp#21)] [!code-csharp[AssemblyName_KeyPair#21](../../../samples/snippets/csharp/VS_Snippets_CLR/AssemblyName_KeyPair/CS/keyfileattrib.cs#21)] [!code-vb[AssemblyName_KeyPair#21](../../../samples/snippets/visualbasic/VS_Snippets_CLR/AssemblyName_KeyPair/VB/keyfileattrib.vb#21)]</span></span>  
  
 <span data-ttu-id="86e4d-139">También se puede retrasar la firma de un ensamblado al compilar el archivo de código fuente.</span><span class="sxs-lookup"><span data-stu-id="86e4d-139">You can also delay sign an assembly when compiling your source file.</span></span> <span data-ttu-id="86e4d-140">Para obtener más información, vea [Retrasar la firma de un ensamblado](../../../docs/framework/app-domains/delay-sign-assembly.md).</span><span class="sxs-lookup"><span data-stu-id="86e4d-140">For more information, see [Delay Signing an Assembly](../../../docs/framework/app-domains/delay-sign-assembly.md).</span></span>  
  
### <a name="to-sign-an-assembly-with-a-strong-name-by-using-the-compiler"></a><span data-ttu-id="86e4d-141">Para firmar un ensamblado con un nombre seguro utilizando el compilador</span><span class="sxs-lookup"><span data-stu-id="86e4d-141">To sign an assembly with a strong name by using the compiler</span></span>  
  
-   <span data-ttu-id="86e4d-142">Compile el archivo o archivos de código fuente con la opción del compilador `/keyfile` o de `/delaysign` en C# y Visual Basic, o la opción del vinculador `/KEYFILE` o `/DELAYSIGN` en C++.</span><span class="sxs-lookup"><span data-stu-id="86e4d-142">Compile your source code file or files with the `/keyfile` or `/delaysign` compiler option in C# and Visual Basic, or the `/KEYFILE` or `/DELAYSIGN` linker option in C++.</span></span> <span data-ttu-id="86e4d-143">Tras el nombre de la opción, agregue dos puntos y el nombre del archivo de claves.</span><span class="sxs-lookup"><span data-stu-id="86e4d-143">After the option name, add a colon and the name of the key file.</span></span> <span data-ttu-id="86e4d-144">Si se usan compiladores de la línea de comandos, se puede copiar el archivo de claves en el directorio que contiene los archivos de código fuente.</span><span class="sxs-lookup"><span data-stu-id="86e4d-144">When using command-line compilers, you can copy the key file to the directory that contains your source code files.</span></span>  
  
     <span data-ttu-id="86e4d-145">Para obtener información sobre la firma retardada, vea [Delay Signing an Assembly](../../../docs/framework/app-domains/delay-sign-assembly.md).</span><span class="sxs-lookup"><span data-stu-id="86e4d-145">For information on delay signing, see [Delay Signing an Assembly](../../../docs/framework/app-domains/delay-sign-assembly.md).</span></span>  
  
     <span data-ttu-id="86e4d-146">En el ejemplo siguiente se usa el compilador de C# y se firma el ensamblado `UtilityLibrary.dll` con un nombre seguro mediante el archivo de claves `sgKey.snk`.</span><span class="sxs-lookup"><span data-stu-id="86e4d-146">The following example uses the C# compiler and signs the assembly `UtilityLibrary.dll` with a strong name by using the key file `sgKey.snk`.</span></span>  
  
    ```  
    csc /t:library UtilityLibrary.cs /keyfile:sgKey.snk  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="86e4d-147">Vea también</span><span class="sxs-lookup"><span data-stu-id="86e4d-147">See Also</span></span>  
 <span data-ttu-id="86e4d-148">[Crear y utilizar ensamblados con nombre seguro](../../../docs/framework/app-domains/create-and-use-strong-named-assemblies.md) </span><span class="sxs-lookup"><span data-stu-id="86e4d-148">[Creating and Using Strong-Named Assemblies](../../../docs/framework/app-domains/create-and-use-strong-named-assemblies.md) </span></span>  
 <span data-ttu-id="86e4d-149">[Cómo: Crear un par de claves privada y pública](../../../docs/framework/app-domains/how-to-create-a-public-private-key-pair.md) </span><span class="sxs-lookup"><span data-stu-id="86e4d-149">[How to: Create a Public-Private Key Pair](../../../docs/framework/app-domains/how-to-create-a-public-private-key-pair.md) </span></span>  
 <span data-ttu-id="86e4d-150">[Al.exe (Assembly Linker)](../../../docs/framework/tools/al-exe-assembly-linker.md) </span><span class="sxs-lookup"><span data-stu-id="86e4d-150">[Al.exe (Assembly Linker)](../../../docs/framework/tools/al-exe-assembly-linker.md) </span></span>  
 <span data-ttu-id="86e4d-151">[Retrasar la firma de un ensamblado](../../../docs/framework/app-domains/delay-sign-assembly.md) </span><span class="sxs-lookup"><span data-stu-id="86e4d-151">[Delay Signing an Assembly](../../../docs/framework/app-domains/delay-sign-assembly.md) </span></span>  
 <span data-ttu-id="86e4d-152">[Administrar la firma de ensamblados y manifiestos](/visualstudio/ide/managing-assembly-and-manifest-signing) </span><span class="sxs-lookup"><span data-stu-id="86e4d-152">[Managing Assembly and Manifest Signing](/visualstudio/ide/managing-assembly-and-manifest-signing) </span></span>  
 [<span data-ttu-id="86e4d-153">Página Firma, Diseñador de proyectos</span><span class="sxs-lookup"><span data-stu-id="86e4d-153">Signing Page, Project Designer</span></span>](https://msdn.microsoft.com/library/0k50fs3b)

