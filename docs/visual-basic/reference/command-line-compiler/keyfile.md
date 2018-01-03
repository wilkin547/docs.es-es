---
title: /keyfile
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- /keyfile compiler option [Visual Basic]
- keyfile compiler option [Visual Basic]
- -keyfile compiler option [Visual Basic]
ms.assetid: ffa82a4b-517a-4c6c-9889-5bae7b534bb8
caps.latest.revision: "17"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: e0be7d230f16750395aaceb3c94539546716b8fd
ms.sourcegitcommit: 34ec7753acf76f90a0fa845235ef06663dc9e36e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/21/2017
---
# <a name="keyfile"></a><span data-ttu-id="9c7ff-102">/keyfile</span><span class="sxs-lookup"><span data-stu-id="9c7ff-102">/keyfile</span></span>
<span data-ttu-id="9c7ff-103">Especifica un archivo que contiene una clave o un par de claves que asigna un nombre seguro al ensamblado.</span><span class="sxs-lookup"><span data-stu-id="9c7ff-103">Specifies a file containing a key or key pair to give an assembly a strong name.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9c7ff-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="9c7ff-104">Syntax</span></span>  
  
```  
/keyfile:file  
```  
  
## <a name="arguments"></a><span data-ttu-id="9c7ff-105">Argumentos</span><span class="sxs-lookup"><span data-stu-id="9c7ff-105">Arguments</span></span>  
 `file`  
 <span data-ttu-id="9c7ff-106">Requerido.</span><span class="sxs-lookup"><span data-stu-id="9c7ff-106">Required.</span></span> <span data-ttu-id="9c7ff-107">Archivo que contiene la clave.</span><span class="sxs-lookup"><span data-stu-id="9c7ff-107">File that contains the key.</span></span> <span data-ttu-id="9c7ff-108">Si el nombre de archivo contiene un espacio, incluya el nombre entre comillas ("").</span><span class="sxs-lookup"><span data-stu-id="9c7ff-108">If the file name contains a space, enclose the name in quotation marks (" ").</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="9c7ff-109">Comentarios</span><span class="sxs-lookup"><span data-stu-id="9c7ff-109">Remarks</span></span>  
 <span data-ttu-id="9c7ff-110">El compilador inserta la clave pública en el manifiesto del ensamblado y firma después el ensamblado final con la clave privada.</span><span class="sxs-lookup"><span data-stu-id="9c7ff-110">The compiler inserts the public key into the assembly manifest and then signs the final assembly with the private key.</span></span> <span data-ttu-id="9c7ff-111">Para generar un archivo de clave, escriba `sn -k file` en la línea de comandos.</span><span class="sxs-lookup"><span data-stu-id="9c7ff-111">To generate a key file, type `sn -k file` at the command line.</span></span> <span data-ttu-id="9c7ff-112">Para obtener más información, consulte [Sn.exe (herramienta de nombre seguro)][Sn.exe (herramienta de nombre seguro)](../../../framework/tools/sn-exe-strong-name-tool.md)).</span><span class="sxs-lookup"><span data-stu-id="9c7ff-112">For more information, see [Sn.exe (Strong Name Tool)][Sn.exe (Strong Name Tool)](../../../framework/tools/sn-exe-strong-name-tool.md)).</span></span>  
  
 <span data-ttu-id="9c7ff-113">Si se compila con `/target:module`, el nombre del archivo de clave se mantiene en el módulo y se incorpora en el ensamblado que se crea cuando se compila un ensamblado con [/addmodule](../../../visual-basic/reference/command-line-compiler/addmodule.md).</span><span class="sxs-lookup"><span data-stu-id="9c7ff-113">If you compile with `/target:module`, the name of the key file is held in the module and incorporated into the assembly that is created when you compile an assembly with [/addmodule](../../../visual-basic/reference/command-line-compiler/addmodule.md).</span></span>  
  
 <span data-ttu-id="9c7ff-114">También puede pasar la información de cifrado al compilador con [/keycontainer](../../../visual-basic/reference/command-line-compiler/keycontainer.md).</span><span class="sxs-lookup"><span data-stu-id="9c7ff-114">You can also pass your encryption information to the compiler with [/keycontainer](../../../visual-basic/reference/command-line-compiler/keycontainer.md).</span></span> <span data-ttu-id="9c7ff-115">Use [/delaysign](../../../visual-basic/reference/command-line-compiler/delaysign.md) para firmar el ensamblado de forma parcial.</span><span class="sxs-lookup"><span data-stu-id="9c7ff-115">Use [/delaysign](../../../visual-basic/reference/command-line-compiler/delaysign.md) if you want a partially signed assembly.</span></span>  
  
 <span data-ttu-id="9c7ff-116">También puede especificar esta opción como un atributo personalizado (<xref:System.Reflection.AssemblyKeyFileAttribute>) en el código fuente de cualquier módulo de lenguaje intermedio de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="9c7ff-116">You can also specify this option as a custom attribute (<xref:System.Reflection.AssemblyKeyFileAttribute>) in the source code for any Microsoft intermediate language module.</span></span>  
  
 <span data-ttu-id="9c7ff-117">En caso de ambos `/keyfile` y [/keycontainer](../../../visual-basic/reference/command-line-compiler/keycontainer.md) se especifican (ya sea mediante una opción de línea de comandos o mediante un atributo personalizado) en la misma compilación, el compilador intenta utilizar primero el contenedor de claves.</span><span class="sxs-lookup"><span data-stu-id="9c7ff-117">In case both `/keyfile` and [/keycontainer](../../../visual-basic/reference/command-line-compiler/keycontainer.md) are specified (either by command-line option or by custom attribute) in the same compilation, the compiler first tries the key container.</span></span> <span data-ttu-id="9c7ff-118">Si lo consigue, el ensamblado se firma con la información del contenedor de claves.</span><span class="sxs-lookup"><span data-stu-id="9c7ff-118">If that succeeds, then the assembly is signed with the information in the key container.</span></span> <span data-ttu-id="9c7ff-119">Si el compilador no encuentra el contenedor de claves, trata el archivo especificado con `/keyfile`.</span><span class="sxs-lookup"><span data-stu-id="9c7ff-119">If the compiler does not find the key container, it tries the file specified with `/keyfile`.</span></span> <span data-ttu-id="9c7ff-120">Si se ejecuta correctamente, el ensamblado se firma con la información en el archivo de clave y la información de clave se instala en el contenedor de claves (similar a `sn -i`) para que en la siguiente compilación, el contenedor de claves será válido.</span><span class="sxs-lookup"><span data-stu-id="9c7ff-120">If this succeeds, the assembly is signed with the information in the key file, and the key information is installed in the key container (similar to `sn -i`) so that on the next compilation, the key container will be valid.</span></span>  
  
 <span data-ttu-id="9c7ff-121">Tenga en cuenta que un archivo de clave puede contener solo la clave pública.</span><span class="sxs-lookup"><span data-stu-id="9c7ff-121">Note that a key file might contain only the public key.</span></span>  
  
 <span data-ttu-id="9c7ff-122">Vea [crear y utilizar ensamblados](../../../framework/app-domains/create-and-use-strong-named-assemblies.md) para obtener más información sobre cómo firmar un ensamblado.</span><span class="sxs-lookup"><span data-stu-id="9c7ff-122">See [Creating and Using Strong-Named Assemblies](../../../framework/app-domains/create-and-use-strong-named-assemblies.md) for more information on signing an assembly.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="9c7ff-123">El `/keyfile` opción no está disponible en la [!INCLUDE[vsprvs](~/includes/vsprvs-md.md)] entorno de desarrollo; está disponible solo cuando se compila desde la línea de comandos.</span><span class="sxs-lookup"><span data-stu-id="9c7ff-123">The `/keyfile` option is not available from within the [!INCLUDE[vsprvs](~/includes/vsprvs-md.md)] development environment; it is available only when compiling from the command line.</span></span>  
  
## <a name="example"></a><span data-ttu-id="9c7ff-124">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="9c7ff-124">Example</span></span>  
 <span data-ttu-id="9c7ff-125">El código siguiente compila el archivo de código fuente `Input.vb` y especifica un archivo de clave.</span><span class="sxs-lookup"><span data-stu-id="9c7ff-125">The following code compiles source file `Input.vb` and specifies a key file.</span></span>  
  
```  
vbc /keyfile:myfile.sn input.vb  
```  
  
## <a name="see-also"></a><span data-ttu-id="9c7ff-126">Vea también</span><span class="sxs-lookup"><span data-stu-id="9c7ff-126">See Also</span></span>  
 [<span data-ttu-id="9c7ff-127">Ensamblados y Caché global de ensamblados</span><span class="sxs-lookup"><span data-stu-id="9c7ff-127">Assemblies and the Global Assembly Cache</span></span>](../../../visual-basic/programming-guide/concepts/assemblies-gac/index.md)  
 [<span data-ttu-id="9c7ff-128">Compilador de línea de comandos de Visual Basic</span><span class="sxs-lookup"><span data-stu-id="9c7ff-128">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)  
 [<span data-ttu-id="9c7ff-129">/ Reference (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="9c7ff-129">/reference (Visual Basic)</span></span>](../../../visual-basic/reference/command-line-compiler/reference.md)  
 [<span data-ttu-id="9c7ff-130">Líneas de comandos de compilación de ejemplo</span><span class="sxs-lookup"><span data-stu-id="9c7ff-130">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
