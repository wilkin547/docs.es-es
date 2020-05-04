---
title: -keycontainer
ms.date: 03/10/2018
helpviewer_keywords:
- -keycontainer compiler option [Visual Basic]
- keycontainer compiler option [Visual Basic]
- /keycontainer compiler option [Visual Basic]
ms.assetid: 6a9bc861-1752-4db1-9f64-b5252f0482cc
ms.openlocfilehash: be2ad1416e801398fb513593c7f3828e5488bfaf
ms.sourcegitcommit: eff6adb61852369ab690f3f047818c90580e7eb1
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/07/2019
ms.locfileid: "72005529"
---
# <a name="-keycontainer"></a><span data-ttu-id="d2b26-102">-keycontainer</span><span class="sxs-lookup"><span data-stu-id="d2b26-102">-keycontainer</span></span>
<span data-ttu-id="d2b26-103">Especifica un nombre de contenedor de claves para un par de claves que asigna un nombre seguro al ensamblado.</span><span class="sxs-lookup"><span data-stu-id="d2b26-103">Specifies a key container name for a key pair to give an assembly a strong name.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d2b26-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="d2b26-104">Syntax</span></span>  
  
```console  
-keycontainer:container  
```  
  
## <a name="arguments"></a><span data-ttu-id="d2b26-105">Argumentos</span><span class="sxs-lookup"><span data-stu-id="d2b26-105">Arguments</span></span>  
  
|<span data-ttu-id="d2b26-106">Término</span><span class="sxs-lookup"><span data-stu-id="d2b26-106">Term</span></span>|<span data-ttu-id="d2b26-107">Definición</span><span class="sxs-lookup"><span data-stu-id="d2b26-107">Definition</span></span>|  
|---|---|  
|`container`|<span data-ttu-id="d2b26-108">Obligatorio.</span><span class="sxs-lookup"><span data-stu-id="d2b26-108">Required.</span></span> <span data-ttu-id="d2b26-109">Archivo contenedor que contiene la clave.</span><span class="sxs-lookup"><span data-stu-id="d2b26-109">Container file that contains the key.</span></span> <span data-ttu-id="d2b26-110">Si el nombre de archivo contiene un espacio, escríbalo entre comillas (" ").</span><span class="sxs-lookup"><span data-stu-id="d2b26-110">Enclose the file name in quotation marks ("") if the name contains a space.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d2b26-111">Comentarios</span><span class="sxs-lookup"><span data-stu-id="d2b26-111">Remarks</span></span>  
 <span data-ttu-id="d2b26-112">El compilador crea un componente compartible mediante la inserción de una clave pública en el manifiesto del ensamblado y la firma del ensamblado final con la clave privada.</span><span class="sxs-lookup"><span data-stu-id="d2b26-112">The compiler creates the sharable component by inserting a public key into the assembly manifest and by signing the final assembly with the private key.</span></span> <span data-ttu-id="d2b26-113">Para generar un archivo de claves, escriba `sn -k file` en la línea de comandos.</span><span class="sxs-lookup"><span data-stu-id="d2b26-113">To generate a key file, type `sn -k file` at the command line.</span></span> <span data-ttu-id="d2b26-114">La opción `-i` instala el par de claves en un contenedor.</span><span class="sxs-lookup"><span data-stu-id="d2b26-114">The `-i` option installs the key pair into a container.</span></span> <span data-ttu-id="d2b26-115">Para obtener más información, vea [Sn.exe (herramienta de nombre seguro)](../../../framework/tools/sn-exe-strong-name-tool.md).</span><span class="sxs-lookup"><span data-stu-id="d2b26-115">For more information, see [Sn.exe (Strong Name Tool)](../../../framework/tools/sn-exe-strong-name-tool.md)).</span></span>  
  
 <span data-ttu-id="d2b26-116">Si se compila con `-target:module`, el nombre del archivo de claves se mantiene en el módulo y se incorpora al ensamblado que se crea al compilar un ensamblado con [-addmodule](../../../visual-basic/reference/command-line-compiler/addmodule.md).</span><span class="sxs-lookup"><span data-stu-id="d2b26-116">If you compile with `-target:module`, the name of the key file is held in the module and incorporated into the assembly that is created when you compile an assembly with [-addmodule](../../../visual-basic/reference/command-line-compiler/addmodule.md).</span></span>  
  
 <span data-ttu-id="d2b26-117">También se puede especificar esta opción como un atributo personalizado (<xref:System.Reflection.AssemblyKeyNameAttribute>) en el código fuente de cualquier módulo del Lenguaje Intermedio de Microsoft (MSIL).</span><span class="sxs-lookup"><span data-stu-id="d2b26-117">You can also specify this option as a custom attribute (<xref:System.Reflection.AssemblyKeyNameAttribute>) in the source code for any Microsoft intermediate language (MSIL) module.</span></span>  
  
 <span data-ttu-id="d2b26-118">También se puede pasar la información de cifrado al compilador con [-keyfile](../../../visual-basic/reference/command-line-compiler/keyfile.md).</span><span class="sxs-lookup"><span data-stu-id="d2b26-118">You can also pass your encryption information to the compiler with [-keyfile](../../../visual-basic/reference/command-line-compiler/keyfile.md).</span></span> <span data-ttu-id="d2b26-119">Use [-delaysign](../../../visual-basic/reference/command-line-compiler/delaysign.md) para firmar el ensamblado de forma parcial.</span><span class="sxs-lookup"><span data-stu-id="d2b26-119">Use [-delaysign](../../../visual-basic/reference/command-line-compiler/delaysign.md) if you want a partially signed assembly.</span></span>  
  
 <span data-ttu-id="d2b26-120">Para obtener más información sobre cómo firmar un ensamblado, vea [Creación y uso de ensamblados con nombre seguro](../../../standard/assembly/create-use-strong-named.md).</span><span class="sxs-lookup"><span data-stu-id="d2b26-120">See [Creating and Using Strong-Named Assemblies](../../../standard/assembly/create-use-strong-named.md) for more information on signing an assembly.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="d2b26-121">La opción `-keycontainer` no está disponible en el entorno de desarrollo de Visual Studio; solo está disponible cuando se compila desde la línea de comandos.</span><span class="sxs-lookup"><span data-stu-id="d2b26-121">The `-keycontainer` option is not available from within the Visual Studio development environment; it is available only when compiling from the command line.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d2b26-122">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="d2b26-122">Example</span></span>  
 <span data-ttu-id="d2b26-123">En el código siguiente se compila el archivo de código fuente `Input.vb` y se especifica un contenedor de claves.</span><span class="sxs-lookup"><span data-stu-id="d2b26-123">The following code compiles source file `Input.vb` and specifies a key container.</span></span>  
  
```console  
vbc -keycontainer:key1 input.vb  
```  
  
## <a name="see-also"></a><span data-ttu-id="d2b26-124">Vea también</span><span class="sxs-lookup"><span data-stu-id="d2b26-124">See also</span></span>

- [<span data-ttu-id="d2b26-125">Ensamblados de .NET</span><span class="sxs-lookup"><span data-stu-id="d2b26-125">Assemblies in .NET</span></span>](../../../standard/assembly/index.md)
- [<span data-ttu-id="d2b26-126">Compilador de línea de comandos de Visual Basic</span><span class="sxs-lookup"><span data-stu-id="d2b26-126">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)
- [<span data-ttu-id="d2b26-127">-keyfile</span><span class="sxs-lookup"><span data-stu-id="d2b26-127">-keyfile</span></span>](../../../visual-basic/reference/command-line-compiler/keyfile.md)
- [<span data-ttu-id="d2b26-128">Líneas de comandos de compilación de ejemplo</span><span class="sxs-lookup"><span data-stu-id="d2b26-128">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
