---
description: Más información sobre -keyfile
title: -keyfile
ms.date: 03/10/2018
helpviewer_keywords:
- /keyfile compiler option [Visual Basic]
- keyfile compiler option [Visual Basic]
- -keyfile compiler option [Visual Basic]
ms.assetid: ffa82a4b-517a-4c6c-9889-5bae7b534bb8
ms.openlocfilehash: 6d19f136d5961e8a933380164a3a77055e1da329
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/14/2021
ms.locfileid: "100466944"
---
# <a name="-keyfile"></a><span data-ttu-id="fc601-103">-keyfile</span><span class="sxs-lookup"><span data-stu-id="fc601-103">-keyfile</span></span>

<span data-ttu-id="fc601-104">Especifica un archivo que contiene una clave o un par de claves que asigna un nombre seguro al ensamblado.</span><span class="sxs-lookup"><span data-stu-id="fc601-104">Specifies a file containing a key or key pair to give an assembly a strong name.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fc601-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="fc601-105">Syntax</span></span>  
  
```console
-keyfile:file  
```  
  
## <a name="arguments"></a><span data-ttu-id="fc601-106">Argumentos</span><span class="sxs-lookup"><span data-stu-id="fc601-106">Arguments</span></span>  

 `file`  
 <span data-ttu-id="fc601-107">Obligatorio.</span><span class="sxs-lookup"><span data-stu-id="fc601-107">Required.</span></span> <span data-ttu-id="fc601-108">Archivo que contiene la clave.</span><span class="sxs-lookup"><span data-stu-id="fc601-108">File that contains the key.</span></span> <span data-ttu-id="fc601-109">Si el nombre de archivo contiene un espacio, escríbalo entre comillas (" ").</span><span class="sxs-lookup"><span data-stu-id="fc601-109">If the file name contains a space, enclose the name in quotation marks (" ").</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="fc601-110">Comentarios</span><span class="sxs-lookup"><span data-stu-id="fc601-110">Remarks</span></span>  

 <span data-ttu-id="fc601-111">El compilador inserta la clave pública en el manifiesto del ensamblado y firma después el ensamblado final con la clave privada.</span><span class="sxs-lookup"><span data-stu-id="fc601-111">The compiler inserts the public key into the assembly manifest and then signs the final assembly with the private key.</span></span> <span data-ttu-id="fc601-112">Para generar un archivo de claves, escriba `sn -k file` en la línea de comandos.</span><span class="sxs-lookup"><span data-stu-id="fc601-112">To generate a key file, type `sn -k file` at the command line.</span></span> <span data-ttu-id="fc601-113">Para obtener más información, consulte [Sn.exe (herramienta de nombre seguro)](../../../framework/tools/sn-exe-strong-name-tool.md).</span><span class="sxs-lookup"><span data-stu-id="fc601-113">For more information, see [Sn.exe (Strong Name Tool)](../../../framework/tools/sn-exe-strong-name-tool.md)).</span></span>  
  
 <span data-ttu-id="fc601-114">Si se compila con `-target:module`, el nombre del archivo de claves se mantiene en el módulo y se incorpora al ensamblado que se crea al compilar un ensamblado con [-addmodule](addmodule.md).</span><span class="sxs-lookup"><span data-stu-id="fc601-114">If you compile with `-target:module`, the name of the key file is held in the module and incorporated into the assembly that is created when you compile an assembly with [-addmodule](addmodule.md).</span></span>  
  
 <span data-ttu-id="fc601-115">También puede pasar la información de cifrado al compilador con [-keycontainer](keycontainer.md).</span><span class="sxs-lookup"><span data-stu-id="fc601-115">You can also pass your encryption information to the compiler with [-keycontainer](keycontainer.md).</span></span> <span data-ttu-id="fc601-116">Use [-delaysign](delaysign.md) para firmar el ensamblado de forma parcial.</span><span class="sxs-lookup"><span data-stu-id="fc601-116">Use [-delaysign](delaysign.md) if you want a partially signed assembly.</span></span>  
  
 <span data-ttu-id="fc601-117">También se puede especificar esta opción como atributo personalizado (<xref:System.Reflection.AssemblyKeyFileAttribute>) en el código fuente de cualquier módulo de Lenguaje Intermedio de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="fc601-117">You can also specify this option as a custom attribute (<xref:System.Reflection.AssemblyKeyFileAttribute>) in the source code for any Microsoft intermediate language module.</span></span>  
  
 <span data-ttu-id="fc601-118">Si en una misma compilación se especifica tanto `-keyfile` como [-keycontainer](keycontainer.md) (ya sea mediante una opción de línea de comandos o mediante un atributo personalizado), el compilador probará primero el contenedor de claves.</span><span class="sxs-lookup"><span data-stu-id="fc601-118">In case both `-keyfile` and [-keycontainer](keycontainer.md) are specified (either by command-line option or by custom attribute) in the same compilation, the compiler first tries the key container.</span></span> <span data-ttu-id="fc601-119">Si lo consigue, el ensamblado se firma con la información del contenedor de claves.</span><span class="sxs-lookup"><span data-stu-id="fc601-119">If that succeeds, then the assembly is signed with the information in the key container.</span></span> <span data-ttu-id="fc601-120">Si el compilador no encuentra el contenedor de claves, probará el archivo especificado con `-keyfile`.</span><span class="sxs-lookup"><span data-stu-id="fc601-120">If the compiler does not find the key container, it tries the file specified with `-keyfile`.</span></span> <span data-ttu-id="fc601-121">Si lo consigue, el ensamblado se firma con la información del archivo de claves, y la información de la clave se instalará en el contenedor de claves (similar a `sn -i`) de modo que, en la próxima compilación, el contenedor de claves será válido.</span><span class="sxs-lookup"><span data-stu-id="fc601-121">If this succeeds, the assembly is signed with the information in the key file, and the key information is installed in the key container (similar to `sn -i`) so that on the next compilation, the key container will be valid.</span></span>  
  
 <span data-ttu-id="fc601-122">Tenga en cuenta que un archivo de clave puede contener solo la clave pública.</span><span class="sxs-lookup"><span data-stu-id="fc601-122">Note that a key file might contain only the public key.</span></span>  
  
 <span data-ttu-id="fc601-123">Consulte [Creación y uso de ensamblados con nombre seguro](../../../standard/assembly/create-use-strong-named.md) para obtener más información sobre cómo firmar un ensamblado.</span><span class="sxs-lookup"><span data-stu-id="fc601-123">See [Creating and Using Strong-Named Assemblies](../../../standard/assembly/create-use-strong-named.md) for more information on signing an assembly.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="fc601-124">La opción `-keyfile` no está disponible en el entorno de desarrollo de Visual Studio; solo lo está cuando se compila desde la línea de comandos.</span><span class="sxs-lookup"><span data-stu-id="fc601-124">The `-keyfile` option is not available from within the Visual Studio development environment; it is available only when compiling from the command line.</span></span>

## <a name="example"></a><span data-ttu-id="fc601-125">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="fc601-125">Example</span></span>

<span data-ttu-id="fc601-126">En el código siguiente se compila el archivo de código fuente `Input.vb` y se especifica un archivo de claves.</span><span class="sxs-lookup"><span data-stu-id="fc601-126">The following code compiles source file `Input.vb` and specifies a key file.</span></span>

```console
vbc -keyfile:myfile.sn input.vb
```

## <a name="see-also"></a><span data-ttu-id="fc601-127">Vea también</span><span class="sxs-lookup"><span data-stu-id="fc601-127">See also</span></span>

- [<span data-ttu-id="fc601-128">Ensamblados de .NET</span><span class="sxs-lookup"><span data-stu-id="fc601-128">Assemblies in .NET</span></span>](../../../standard/assembly/index.md)
- [<span data-ttu-id="fc601-129">Compilador de línea de comandos de Visual Basic</span><span class="sxs-lookup"><span data-stu-id="fc601-129">Visual Basic Command-Line Compiler</span></span>](index.md)
- [<span data-ttu-id="fc601-130">-reference (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="fc601-130">-reference (Visual Basic)</span></span>](reference.md)
- [<span data-ttu-id="fc601-131">Líneas de comandos de compilación de ejemplo</span><span class="sxs-lookup"><span data-stu-id="fc601-131">Sample Compilation Command Lines</span></span>](sample-compilation-command-lines.md)
