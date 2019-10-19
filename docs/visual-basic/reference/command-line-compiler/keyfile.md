---
title: -keyfile
ms.date: 03/10/2018
helpviewer_keywords:
- /keyfile compiler option [Visual Basic]
- keyfile compiler option [Visual Basic]
- -keyfile compiler option [Visual Basic]
ms.assetid: ffa82a4b-517a-4c6c-9889-5bae7b534bb8
ms.openlocfilehash: 84b291a28cd4e253f44063258894aa672904d15b
ms.sourcegitcommit: 1f12db2d852d05bed8c53845f0b5a57a762979c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2019
ms.locfileid: "72581992"
---
# <a name="-keyfile"></a><span data-ttu-id="38adb-102">-keyfile</span><span class="sxs-lookup"><span data-stu-id="38adb-102">-keyfile</span></span>

<span data-ttu-id="38adb-103">Especifica un archivo que contiene una clave o un par de claves que asigna un nombre seguro al ensamblado.</span><span class="sxs-lookup"><span data-stu-id="38adb-103">Specifies a file containing a key or key pair to give an assembly a strong name.</span></span>

## <a name="syntax"></a><span data-ttu-id="38adb-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="38adb-104">Syntax</span></span>

```console
-keyfile:file
```

## <a name="arguments"></a><span data-ttu-id="38adb-105">Argumentos</span><span class="sxs-lookup"><span data-stu-id="38adb-105">Arguments</span></span>

`file`  
<span data-ttu-id="38adb-106">Requerido.</span><span class="sxs-lookup"><span data-stu-id="38adb-106">Required.</span></span> <span data-ttu-id="38adb-107">Archivo que contiene la clave.</span><span class="sxs-lookup"><span data-stu-id="38adb-107">File that contains the key.</span></span> <span data-ttu-id="38adb-108">Si el nombre de archivo contiene un espacio, incluya el nombre entre comillas ("").</span><span class="sxs-lookup"><span data-stu-id="38adb-108">If the file name contains a space, enclose the name in quotation marks (" ").</span></span>

## <a name="remarks"></a><span data-ttu-id="38adb-109">Comentarios</span><span class="sxs-lookup"><span data-stu-id="38adb-109">Remarks</span></span>

<span data-ttu-id="38adb-110">El compilador inserta la clave pública en el manifiesto del ensamblado y, a continuación, firma el ensamblado final con la clave privada.</span><span class="sxs-lookup"><span data-stu-id="38adb-110">The compiler inserts the public key into the assembly manifest and then signs the final assembly with the private key.</span></span> <span data-ttu-id="38adb-111">Para generar un archivo de claves, escriba `sn -k file` en la línea de comandos.</span><span class="sxs-lookup"><span data-stu-id="38adb-111">To generate a key file, type `sn -k file` at the command line.</span></span> <span data-ttu-id="38adb-112">Para obtener más información, consulte [SN. exe (herramienta de nombre seguro)](../../../framework/tools/sn-exe-strong-name-tool.md)).</span><span class="sxs-lookup"><span data-stu-id="38adb-112">For more information, see [Sn.exe (Strong Name Tool)](../../../framework/tools/sn-exe-strong-name-tool.md)).</span></span>

<span data-ttu-id="38adb-113">Si compila con `-target:module`, el nombre del archivo de clave se mantiene en el módulo y se incorpora en el ensamblado que se crea al compilar un ensamblado con [/AddModule](../../../visual-basic/reference/command-line-compiler/addmodule.md).</span><span class="sxs-lookup"><span data-stu-id="38adb-113">If you compile with `-target:module`, the name of the key file is held in the module and incorporated into the assembly that is created when you compile an assembly with [/addmodule](../../../visual-basic/reference/command-line-compiler/addmodule.md).</span></span>

<span data-ttu-id="38adb-114">También puede pasar la información de cifrado al compilador con [-keycontainer](../../../visual-basic/reference/command-line-compiler/keycontainer.md).</span><span class="sxs-lookup"><span data-stu-id="38adb-114">You can also pass your encryption information to the compiler with [-keycontainer](../../../visual-basic/reference/command-line-compiler/keycontainer.md).</span></span> <span data-ttu-id="38adb-115">Use [-delaysign](../../../visual-basic/reference/command-line-compiler/delaysign.md) para firmar el ensamblado de forma parcial.</span><span class="sxs-lookup"><span data-stu-id="38adb-115">Use [-delaysign](../../../visual-basic/reference/command-line-compiler/delaysign.md) if you want a partially signed assembly.</span></span>

<span data-ttu-id="38adb-116">También puede especificar esta opción como un atributo personalizado (<xref:System.Reflection.AssemblyKeyFileAttribute>) en el código fuente de cualquier módulo de lenguaje intermedio de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="38adb-116">You can also specify this option as a custom attribute (<xref:System.Reflection.AssemblyKeyFileAttribute>) in the source code for any Microsoft intermediate language module.</span></span>

<span data-ttu-id="38adb-117">En caso de que se especifiquen `-keyfile` y [-keycontainer](../../../visual-basic/reference/command-line-compiler/keycontainer.md) (ya sea mediante la opción de línea de comandos o mediante un atributo personalizado) en la misma compilación, el compilador primero intentará el contenedor de claves.</span><span class="sxs-lookup"><span data-stu-id="38adb-117">In case both `-keyfile` and [-keycontainer](../../../visual-basic/reference/command-line-compiler/keycontainer.md) are specified (either by command-line option or by custom attribute) in the same compilation, the compiler first tries the key container.</span></span> <span data-ttu-id="38adb-118">Si lo consigue, el ensamblado se firma con la información del contenedor de claves.</span><span class="sxs-lookup"><span data-stu-id="38adb-118">If that succeeds, then the assembly is signed with the information in the key container.</span></span> <span data-ttu-id="38adb-119">Si el compilador no encuentra el contenedor de claves, intenta el archivo especificado con `-keyfile`.</span><span class="sxs-lookup"><span data-stu-id="38adb-119">If the compiler does not find the key container, it tries the file specified with `-keyfile`.</span></span> <span data-ttu-id="38adb-120">Si esto se realiza correctamente, el ensamblado se firma con la información del archivo de clave y la información de clave se instala en el contenedor de claves (similar a `sn -i`) para que en la siguiente compilación, el contenedor de claves sea válido.</span><span class="sxs-lookup"><span data-stu-id="38adb-120">If this succeeds, the assembly is signed with the information in the key file, and the key information is installed in the key container (similar to `sn -i`) so that on the next compilation, the key container will be valid.</span></span>

<span data-ttu-id="38adb-121">Tenga en cuenta que un archivo de clave puede contener solo la clave pública.</span><span class="sxs-lookup"><span data-stu-id="38adb-121">Note that a key file might contain only the public key.</span></span>

<span data-ttu-id="38adb-122">Vea [crear y utilizar ensamblados con nombre seguro](../../../standard/assembly/create-use-strong-named.md) para obtener más información sobre la firma de un ensamblado.</span><span class="sxs-lookup"><span data-stu-id="38adb-122">See [Creating and Using Strong-Named Assemblies](../../../standard/assembly/create-use-strong-named.md) for more information on signing an assembly.</span></span>

> [!NOTE]
> <span data-ttu-id="38adb-123">La opción `-keyfile` no está disponible en el entorno de desarrollo de Visual Studio; solo está disponible al compilar desde la línea de comandos.</span><span class="sxs-lookup"><span data-stu-id="38adb-123">The `-keyfile` option is not available from within the Visual Studio development environment; it is available only when compiling from the command line.</span></span>

## <a name="example"></a><span data-ttu-id="38adb-124">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="38adb-124">Example</span></span>

<span data-ttu-id="38adb-125">El código siguiente compila el archivo de código fuente `Input.vb` y especifica un archivo de clave.</span><span class="sxs-lookup"><span data-stu-id="38adb-125">The following code compiles source file `Input.vb` and specifies a key file.</span></span>

```console
vbc -keyfile:myfile.sn input.vb
```

## <a name="see-also"></a><span data-ttu-id="38adb-126">Vea también</span><span class="sxs-lookup"><span data-stu-id="38adb-126">See also</span></span>

- [<span data-ttu-id="38adb-127">Ensamblados de .NET</span><span class="sxs-lookup"><span data-stu-id="38adb-127">Assemblies in .NET</span></span>](../../../standard/assembly/index.md)
- [<span data-ttu-id="38adb-128">Compilador de línea de comandos de Visual Basic</span><span class="sxs-lookup"><span data-stu-id="38adb-128">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)
- [<span data-ttu-id="38adb-129">-Reference (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="38adb-129">-reference (Visual Basic)</span></span>](../../../visual-basic/reference/command-line-compiler/reference.md)
- [<span data-ttu-id="38adb-130">Líneas de comandos de compilación de ejemplo</span><span class="sxs-lookup"><span data-stu-id="38adb-130">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
