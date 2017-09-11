---
title: "Cómo: Compilar un ensamblado de un solo archivo"
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
- assembly manifest, single-file assemblies
- library assemblies
- command-line compilers
- assemblies [.NET Framework], single-file
- output file name for assemblies
- code modules
- single-file assemblies
ms.assetid: a6063221-43a5-4d3e-814c-288a4ec69aec
caps.latest.revision: 10
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 1a584e6ded79489e5e33b07d02dde618541c6cc8
ms.contentlocale: es-es
ms.lasthandoff: 07/28/2017

---
# <a name="how-to-build-a-single-file-assembly"></a><span data-ttu-id="010de-102">Cómo: Compilar un ensamblado de un solo archivo</span><span class="sxs-lookup"><span data-stu-id="010de-102">How to: Build a Single-File Assembly</span></span>
<span data-ttu-id="010de-103">Un ensamblado de único archivo, que es el tipo de ensamblado más sencillo, contiene información y la implementación del tipo, así como el [manifiesto del ensamblado](../../../docs/framework/app-domains/assembly-manifest.md).</span><span class="sxs-lookup"><span data-stu-id="010de-103">A single-file assembly, which is the simplest type of assembly, contains type information and implementation, as well as the [assembly manifest](../../../docs/framework/app-domains/assembly-manifest.md).</span></span> <span data-ttu-id="010de-104">Puede usar los compiladores de la línea de comandos o [!INCLUDE[vsprvslong](../../../includes/vsprvslong-md.md)] para crear un ensamblado de único archivo.</span><span class="sxs-lookup"><span data-stu-id="010de-104">You can use command-line compilers or [!INCLUDE[vsprvslong](../../../includes/vsprvslong-md.md)] to create a single-file assembly.</span></span> <span data-ttu-id="010de-105">De forma predeterminada, el compilador crea un archivo de ensamblado con la extensión .exe.</span><span class="sxs-lookup"><span data-stu-id="010de-105">By default, the compiler creates an assembly file with an .exe extension.</span></span>  
  
> [!NOTE]
>  [!INCLUDE[vsprvslong](../../../includes/vsprvslong-md.md)]<span data-ttu-id="010de-106"> para C# y Visual Basic solo se puede usar para crear ensamblados de único archivo.</span><span class="sxs-lookup"><span data-stu-id="010de-106"> for C# and Visual Basic can be used only to create single-file assemblies.</span></span> <span data-ttu-id="010de-107">Si desea crear ensamblados de múltiples archivos, debe usar compiladores de la línea de comandos o [!INCLUDE[vsprvslong](../../../includes/vsprvslong-md.md)] para Visual C++.</span><span class="sxs-lookup"><span data-stu-id="010de-107">If you want to create multifile assemblies, you must use command-line compilers or [!INCLUDE[vsprvslong](../../../includes/vsprvslong-md.md)] for Visual C++.</span></span>  
  
 <span data-ttu-id="010de-108">En los procedimientos siguientes se muestra cómo crear ensamblados de único archivo mediante los compiladores de la línea de comandos.</span><span class="sxs-lookup"><span data-stu-id="010de-108">The following procedures show how to create single-file assemblies using command-line compilers.</span></span>  
  
### <a name="to-create-an-assembly-with-an-exe-extension"></a><span data-ttu-id="010de-109">Para crear un ensamblado con una extensión .exe</span><span class="sxs-lookup"><span data-stu-id="010de-109">To create an assembly with an .exe extension</span></span>  
  
1.  <span data-ttu-id="010de-110">En el símbolo del sistema, escriba el siguiente comando:</span><span class="sxs-lookup"><span data-stu-id="010de-110">At the command prompt, type the following command:</span></span>  
  
     <span data-ttu-id="010de-111">\<*comando del compilador*> \<*nombre del módulo*></span><span class="sxs-lookup"><span data-stu-id="010de-111">\<*compiler command*> \<*module name*></span></span>  
  
     <span data-ttu-id="010de-112">En este comando, *comando de compilador* es el comando del compilador del lenguaje usado en el módulo del código, mientras que *nombre del módulo* es el nombre del módulo del código al compilarlo en el ensamblado.</span><span class="sxs-lookup"><span data-stu-id="010de-112">In this command, *compiler command* is the compiler command for the language used in your code module, and *module name* is the name of the code module to compile into the assembly.</span></span>  
  
 <span data-ttu-id="010de-113">En el ejemplo siguiente se crea un ensamblado llamado `myCode.exe` desde un módulo de código llamado `myCode`.</span><span class="sxs-lookup"><span data-stu-id="010de-113">The following example creates an assembly named `myCode.exe` from a code module called `myCode`.</span></span>  
  
```csharp  
csc myCode.cs  
```  
  
```vb  
vbc myCode.vb  
```  
  
#### <a name="to-create-an-assembly-with-an-exe-extension-and-specify-the-output-file-name"></a><span data-ttu-id="010de-114">Para crear un ensamblado con la extensión .exe y especificar el nombre de archivo de salida</span><span class="sxs-lookup"><span data-stu-id="010de-114">To create an assembly with an .exe extension and specify the output file name</span></span>  
  
1.  <span data-ttu-id="010de-115">En el símbolo del sistema, escriba el siguiente comando:</span><span class="sxs-lookup"><span data-stu-id="010de-115">At the command prompt, type the following command:</span></span>  
  
     <span data-ttu-id="010de-116">\<*comando del compilador*> **/out:**\<*nombre del archivo*> \<*nombre del módulo*></span><span class="sxs-lookup"><span data-stu-id="010de-116">\<*compiler command*> **/out:**\<*file name*> \<*module name*></span></span>  
  
     <span data-ttu-id="010de-117">En este comando, *comando del compilador* es el comando del compilador del lenguaje usado en el módulo del código, *nombre del archivo* es el nombre del archivo de salida y *nombre del módulo* es el nombre del módulo del código al compilarlo en el ensamblado.</span><span class="sxs-lookup"><span data-stu-id="010de-117">In this command, *compiler command* is the compiler command for the language used in your code module, *file name* is the output file name, and *module name* is the name of the code module to compile into the assembly.</span></span>  
  
 <span data-ttu-id="010de-118">En el ejemplo siguiente se crea un ensamblado llamado `myAssembly.exe` desde un módulo de código llamado `myCode`.</span><span class="sxs-lookup"><span data-stu-id="010de-118">The following example creates an assembly named `myAssembly.exe` from a code module called `myCode`.</span></span>  
  
```csharp  
csc /out:myAssembly.exe myCode.cs  
```  
  
```vb  
vbc /out:myAssembly.exe myCode.vb  
```  
  
## <a name="creating-library-assemblies"></a><span data-ttu-id="010de-119">Crear ensamblados de biblioteca</span><span class="sxs-lookup"><span data-stu-id="010de-119">Creating Library Assemblies</span></span>  
 <span data-ttu-id="010de-120">Los ensamblados de biblioteca se parecen a las bibliotecas de clases.</span><span class="sxs-lookup"><span data-stu-id="010de-120">A library assembly is similar to a class library.</span></span> <span data-ttu-id="010de-121">Contiene tipos a los que harán referencia otros ensamblados, pero no tiene ningún punto de entrada para comenzar la ejecución.</span><span class="sxs-lookup"><span data-stu-id="010de-121">It contains types that will be referenced by other assemblies, but it has no entry point to begin execution.</span></span>  
  
#### <a name="to-create-a-library-assembly"></a><span data-ttu-id="010de-122">Para crear un ensamblado de biblioteca</span><span class="sxs-lookup"><span data-stu-id="010de-122">To create a library assembly</span></span>  
  
1.  <span data-ttu-id="010de-123">En el símbolo del sistema, escriba el siguiente comando:</span><span class="sxs-lookup"><span data-stu-id="010de-123">At the command prompt, type the following command:</span></span>  
  
     <span data-ttu-id="010de-124">\<*comando del compilador*> **/t:library** \<*nombre del módulo*></span><span class="sxs-lookup"><span data-stu-id="010de-124">\<*compiler command*> **/t:library** \<*module name*></span></span>  
  
     <span data-ttu-id="010de-125">En este comando, *comando de compilador* es el comando del compilador del lenguaje usado en el módulo del código, mientras que *nombre del módulo* es el nombre del módulo del código al compilarlo en el ensamblado.</span><span class="sxs-lookup"><span data-stu-id="010de-125">In this command, *compiler command* is the compiler command for the language used in your code module, and *module name* is the name of the code module to compile into the assembly.</span></span> <span data-ttu-id="010de-126">También puede usar otras opciones del compilador, como la opción **/out:**.</span><span class="sxs-lookup"><span data-stu-id="010de-126">You can also use other compiler options, such as the **/out:** option.</span></span>  
  
 <span data-ttu-id="010de-127">En el ejemplo siguiente se crea un ensamblado de biblioteca llamado `myCodeAssembly.dll` desde un módulo de código llamado `myCode`.</span><span class="sxs-lookup"><span data-stu-id="010de-127">The following example creates a library assembly named `myCodeAssembly.dll` from a code module called `myCode`.</span></span>  
  
```csharp  
csc /out:myCodeLibrary.dll /t:library myCode.cs  
```  
  
```vb  
vbc /out:myCodeLibrary.dll /t:library myCode.vb  
```  
  
## <a name="see-also"></a><span data-ttu-id="010de-128">Vea también</span><span class="sxs-lookup"><span data-stu-id="010de-128">See Also</span></span>  
 <span data-ttu-id="010de-129">[Creación de ensamblados](../../../docs/framework/app-domains/create-assemblies.md) </span><span class="sxs-lookup"><span data-stu-id="010de-129">[Creating Assemblies](../../../docs/framework/app-domains/create-assemblies.md) </span></span>  
 <span data-ttu-id="010de-130">[Ensamblados de múltiples archivos](../../../docs/framework/app-domains/multifile-assemblies.md) </span><span class="sxs-lookup"><span data-stu-id="010de-130">[Multifile Assemblies](../../../docs/framework/app-domains/multifile-assemblies.md) </span></span>  
 <span data-ttu-id="010de-131">[Cómo: Compilar un ensamblado de varios archivos](../../../docs/framework/app-domains/how-to-build-a-multifile-assembly.md) </span><span class="sxs-lookup"><span data-stu-id="010de-131">[How to: Build a Multifile Assembly](../../../docs/framework/app-domains/how-to-build-a-multifile-assembly.md) </span></span>  
 [<span data-ttu-id="010de-132">Programar con ensamblados</span><span class="sxs-lookup"><span data-stu-id="010de-132">Programming with Assemblies</span></span>](../../../docs/framework/app-domains/programming-with-assemblies.md)

