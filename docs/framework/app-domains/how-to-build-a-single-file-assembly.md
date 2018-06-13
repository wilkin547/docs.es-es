---
title: 'Cómo: Compilar un ensamblado de un solo archivo'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- assembly manifest, single-file assemblies
- library assemblies
- command-line compilers
- assemblies [.NET Framework], single-file
- output file name for assemblies
- code modules
- single-file assemblies
ms.assetid: a6063221-43a5-4d3e-814c-288a4ec69aec
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 6aa39671da519ebf54dad52638ab940897209517
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/03/2018
ms.locfileid: "32744322"
---
# <a name="how-to-build-a-single-file-assembly"></a><span data-ttu-id="a42a2-102">Cómo: Compilar un ensamblado de un solo archivo</span><span class="sxs-lookup"><span data-stu-id="a42a2-102">How to: Build a Single-File Assembly</span></span>
<span data-ttu-id="a42a2-103">Un ensamblado de único archivo, que es el tipo de ensamblado más sencillo, contiene información y la implementación del tipo, así como el [manifiesto del ensamblado](../../../docs/framework/app-domains/assembly-manifest.md).</span><span class="sxs-lookup"><span data-stu-id="a42a2-103">A single-file assembly, which is the simplest type of assembly, contains type information and implementation, as well as the [assembly manifest](../../../docs/framework/app-domains/assembly-manifest.md).</span></span> <span data-ttu-id="a42a2-104">Puede usar los compiladores de la línea de comandos o [!INCLUDE[vsprvslong](../../../includes/vsprvslong-md.md)] para crear un ensamblado de único archivo.</span><span class="sxs-lookup"><span data-stu-id="a42a2-104">You can use command-line compilers or [!INCLUDE[vsprvslong](../../../includes/vsprvslong-md.md)] to create a single-file assembly.</span></span> <span data-ttu-id="a42a2-105">De forma predeterminada, el compilador crea un archivo de ensamblado con la extensión .exe.</span><span class="sxs-lookup"><span data-stu-id="a42a2-105">By default, the compiler creates an assembly file with an .exe extension.</span></span>  
  
> [!NOTE]
>  [!INCLUDE[vsprvslong](../../../includes/vsprvslong-md.md)]<span data-ttu-id="a42a2-106"> para C# y Visual Basic solo se puede usar para crear ensamblados de único archivo.</span><span class="sxs-lookup"><span data-stu-id="a42a2-106"> for C# and Visual Basic can be used only to create single-file assemblies.</span></span> <span data-ttu-id="a42a2-107">Si desea crear ensamblados de múltiples archivos, debe usar compiladores de la línea de comandos o [!INCLUDE[vsprvslong](../../../includes/vsprvslong-md.md)] para Visual C++.</span><span class="sxs-lookup"><span data-stu-id="a42a2-107">If you want to create multifile assemblies, you must use command-line compilers or [!INCLUDE[vsprvslong](../../../includes/vsprvslong-md.md)] for Visual C++.</span></span>  
  
 <span data-ttu-id="a42a2-108">En los procedimientos siguientes se muestra cómo crear ensamblados de único archivo mediante los compiladores de la línea de comandos.</span><span class="sxs-lookup"><span data-stu-id="a42a2-108">The following procedures show how to create single-file assemblies using command-line compilers.</span></span>  
  
### <a name="to-create-an-assembly-with-an-exe-extension"></a><span data-ttu-id="a42a2-109">Para crear un ensamblado con una extensión .exe</span><span class="sxs-lookup"><span data-stu-id="a42a2-109">To create an assembly with an .exe extension</span></span>  
  
1.  <span data-ttu-id="a42a2-110">En el símbolo del sistema, escriba el siguiente comando:</span><span class="sxs-lookup"><span data-stu-id="a42a2-110">At the command prompt, type the following command:</span></span>  
  
     <span data-ttu-id="a42a2-111">\<*comando del compilador*> \<*nombre del módulo*></span><span class="sxs-lookup"><span data-stu-id="a42a2-111">\<*compiler command*> \<*module name*></span></span>  
  
     <span data-ttu-id="a42a2-112">En este comando, *comando de compilador* es el comando del compilador del lenguaje usado en el módulo del código, mientras que *nombre del módulo* es el nombre del módulo del código al compilarlo en el ensamblado.</span><span class="sxs-lookup"><span data-stu-id="a42a2-112">In this command, *compiler command* is the compiler command for the language used in your code module, and *module name* is the name of the code module to compile into the assembly.</span></span>  
  
 <span data-ttu-id="a42a2-113">En el ejemplo siguiente se crea un ensamblado llamado `myCode.exe` desde un módulo de código llamado `myCode`.</span><span class="sxs-lookup"><span data-stu-id="a42a2-113">The following example creates an assembly named `myCode.exe` from a code module called `myCode`.</span></span>  
  
```console
csc myCode.cs  
```  

```console
vbc myCode.vb  
```  
  
#### <a name="to-create-an-assembly-with-an-exe-extension-and-specify-the-output-file-name"></a><span data-ttu-id="a42a2-114">Para crear un ensamblado con la extensión .exe y especificar el nombre de archivo de salida</span><span class="sxs-lookup"><span data-stu-id="a42a2-114">To create an assembly with an .exe extension and specify the output file name</span></span>  
  
1.  <span data-ttu-id="a42a2-115">En el símbolo del sistema, escriba el siguiente comando:</span><span class="sxs-lookup"><span data-stu-id="a42a2-115">At the command prompt, type the following command:</span></span>  
  
     <span data-ttu-id="a42a2-116">\<*comando del compilador*> **/out:**\<*nombre del archivo*> \<*nombre del módulo*></span><span class="sxs-lookup"><span data-stu-id="a42a2-116">\<*compiler command*> **/out:**\<*file name*> \<*module name*></span></span>  
  
     <span data-ttu-id="a42a2-117">En este comando, *comando del compilador* es el comando del compilador del lenguaje usado en el módulo del código, *nombre del archivo* es el nombre del archivo de salida y *nombre del módulo* es el nombre del módulo del código al compilarlo en el ensamblado.</span><span class="sxs-lookup"><span data-stu-id="a42a2-117">In this command, *compiler command* is the compiler command for the language used in your code module, *file name* is the output file name, and *module name* is the name of the code module to compile into the assembly.</span></span>  
  
 <span data-ttu-id="a42a2-118">En el ejemplo siguiente se crea un ensamblado llamado `myAssembly.exe` desde un módulo de código llamado `myCode`.</span><span class="sxs-lookup"><span data-stu-id="a42a2-118">The following example creates an assembly named `myAssembly.exe` from a code module called `myCode`.</span></span>  
  
```console  
csc -out:myAssembly.exe myCode.cs  
```  
  
```console
vbc -out:myAssembly.exe myCode.vb  
```  
  
## <a name="creating-library-assemblies"></a><span data-ttu-id="a42a2-119">Crear ensamblados de biblioteca</span><span class="sxs-lookup"><span data-stu-id="a42a2-119">Creating Library Assemblies</span></span>  
 <span data-ttu-id="a42a2-120">Los ensamblados de biblioteca se parecen a las bibliotecas de clases.</span><span class="sxs-lookup"><span data-stu-id="a42a2-120">A library assembly is similar to a class library.</span></span> <span data-ttu-id="a42a2-121">Contiene tipos a los que harán referencia otros ensamblados, pero no tiene ningún punto de entrada para comenzar la ejecución.</span><span class="sxs-lookup"><span data-stu-id="a42a2-121">It contains types that will be referenced by other assemblies, but it has no entry point to begin execution.</span></span>  
  
#### <a name="to-create-a-library-assembly"></a><span data-ttu-id="a42a2-122">Para crear un ensamblado de biblioteca</span><span class="sxs-lookup"><span data-stu-id="a42a2-122">To create a library assembly</span></span>  
  
1.  <span data-ttu-id="a42a2-123">En el símbolo del sistema, escriba el siguiente comando:</span><span class="sxs-lookup"><span data-stu-id="a42a2-123">At the command prompt, type the following command:</span></span>  
  
     <span data-ttu-id="a42a2-124">\<*comando del compilador*> **-t:library** \<*nombre del módulo*></span><span class="sxs-lookup"><span data-stu-id="a42a2-124">\<*compiler command*> **-t:library** \<*module name*></span></span>  
  
     <span data-ttu-id="a42a2-125">En este comando, *comando de compilador* es el comando del compilador del lenguaje usado en el módulo del código, mientras que *nombre del módulo* es el nombre del módulo del código al compilarlo en el ensamblado.</span><span class="sxs-lookup"><span data-stu-id="a42a2-125">In this command, *compiler command* is the compiler command for the language used in your code module, and *module name* is the name of the code module to compile into the assembly.</span></span> <span data-ttu-id="a42a2-126">También puede usar otras opciones del compilador, como la opción **-out:**.</span><span class="sxs-lookup"><span data-stu-id="a42a2-126">You can also use other compiler options, such as the **-out:** option.</span></span>  
  
 <span data-ttu-id="a42a2-127">En el ejemplo siguiente se crea un ensamblado de biblioteca llamado `myCodeAssembly.dll` desde un módulo de código llamado `myCode`.</span><span class="sxs-lookup"><span data-stu-id="a42a2-127">The following example creates a library assembly named `myCodeAssembly.dll` from a code module called `myCode`.</span></span>  
  
```console  
csc -out:myCodeLibrary.dll -t:library myCode.cs  
```  
  
```console
vbc -out:myCodeLibrary.dll -t:library myCode.vb  
```  
  
## <a name="see-also"></a><span data-ttu-id="a42a2-128">Vea también</span><span class="sxs-lookup"><span data-stu-id="a42a2-128">See Also</span></span>  
 [<span data-ttu-id="a42a2-129">Creación de ensamblados</span><span class="sxs-lookup"><span data-stu-id="a42a2-129">Creating Assemblies</span></span>](../../../docs/framework/app-domains/create-assemblies.md)  
 [<span data-ttu-id="a42a2-130">Ensamblados de múltiples archivos</span><span class="sxs-lookup"><span data-stu-id="a42a2-130">Multifile Assemblies</span></span>](../../../docs/framework/app-domains/multifile-assemblies.md)  
 [<span data-ttu-id="a42a2-131">Compilar un ensamblado de varios archivos</span><span class="sxs-lookup"><span data-stu-id="a42a2-131">How to: Build a Multifile Assembly</span></span>](../../../docs/framework/app-domains/how-to-build-a-multifile-assembly.md)  
 [<span data-ttu-id="a42a2-132">Programar con ensamblados</span><span class="sxs-lookup"><span data-stu-id="a42a2-132">Programming with Assemblies</span></span>](../../../docs/framework/app-domains/programming-with-assemblies.md)
