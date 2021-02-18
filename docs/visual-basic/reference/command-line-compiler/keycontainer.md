---
description: Más información sobre -keycontainer
title: -keycontainer
ms.date: 03/10/2018
helpviewer_keywords:
- -keycontainer compiler option [Visual Basic]
- keycontainer compiler option [Visual Basic]
- /keycontainer compiler option [Visual Basic]
ms.assetid: 6a9bc861-1752-4db1-9f64-b5252f0482cc
ms.openlocfilehash: d8b83162d9404eb2ce80e5e531457360b040f27d
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/14/2021
ms.locfileid: "100436817"
---
# <a name="-keycontainer"></a><span data-ttu-id="84432-103">-keycontainer</span><span class="sxs-lookup"><span data-stu-id="84432-103">-keycontainer</span></span>

<span data-ttu-id="84432-104">Especifica un nombre de contenedor de claves para un par de claves que asigna un nombre seguro al ensamblado.</span><span class="sxs-lookup"><span data-stu-id="84432-104">Specifies a key container name for a key pair to give an assembly a strong name.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="84432-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="84432-105">Syntax</span></span>  
  
```console  
-keycontainer:container  
```  
  
## <a name="arguments"></a><span data-ttu-id="84432-106">Argumentos</span><span class="sxs-lookup"><span data-stu-id="84432-106">Arguments</span></span>  
  
|<span data-ttu-id="84432-107">Término</span><span class="sxs-lookup"><span data-stu-id="84432-107">Term</span></span>|<span data-ttu-id="84432-108">Definición</span><span class="sxs-lookup"><span data-stu-id="84432-108">Definition</span></span>|  
|---|---|  
|`container`|<span data-ttu-id="84432-109">Obligatorio.</span><span class="sxs-lookup"><span data-stu-id="84432-109">Required.</span></span> <span data-ttu-id="84432-110">Archivo contenedor que contiene la clave.</span><span class="sxs-lookup"><span data-stu-id="84432-110">Container file that contains the key.</span></span> <span data-ttu-id="84432-111">Si el nombre de archivo contiene un espacio, escríbalo entre comillas (" ").</span><span class="sxs-lookup"><span data-stu-id="84432-111">Enclose the file name in quotation marks ("") if the name contains a space.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="84432-112">Comentarios</span><span class="sxs-lookup"><span data-stu-id="84432-112">Remarks</span></span>  

 <span data-ttu-id="84432-113">El compilador crea un componente compartible mediante la inserción de una clave pública en el manifiesto del ensamblado y la firma del ensamblado final con la clave privada.</span><span class="sxs-lookup"><span data-stu-id="84432-113">The compiler creates the sharable component by inserting a public key into the assembly manifest and by signing the final assembly with the private key.</span></span> <span data-ttu-id="84432-114">Para generar un archivo de claves, escriba `sn -k file` en la línea de comandos.</span><span class="sxs-lookup"><span data-stu-id="84432-114">To generate a key file, type `sn -k file` at the command line.</span></span> <span data-ttu-id="84432-115">La opción `-i` instala el par de claves en un contenedor.</span><span class="sxs-lookup"><span data-stu-id="84432-115">The `-i` option installs the key pair into a container.</span></span> <span data-ttu-id="84432-116">Para obtener más información, vea [Sn.exe (herramienta de nombre seguro)](../../../framework/tools/sn-exe-strong-name-tool.md).</span><span class="sxs-lookup"><span data-stu-id="84432-116">For more information, see [Sn.exe (Strong Name Tool)](../../../framework/tools/sn-exe-strong-name-tool.md)).</span></span>  
  
 <span data-ttu-id="84432-117">Si se compila con `-target:module`, el nombre del archivo de claves se mantiene en el módulo y se incorpora al ensamblado que se crea al compilar un ensamblado con [-addmodule](addmodule.md).</span><span class="sxs-lookup"><span data-stu-id="84432-117">If you compile with `-target:module`, the name of the key file is held in the module and incorporated into the assembly that is created when you compile an assembly with [-addmodule](addmodule.md).</span></span>  
  
 <span data-ttu-id="84432-118">También se puede especificar esta opción como un atributo personalizado (<xref:System.Reflection.AssemblyKeyNameAttribute>) en el código fuente de cualquier módulo del Lenguaje Intermedio de Microsoft (MSIL).</span><span class="sxs-lookup"><span data-stu-id="84432-118">You can also specify this option as a custom attribute (<xref:System.Reflection.AssemblyKeyNameAttribute>) in the source code for any Microsoft intermediate language (MSIL) module.</span></span>  
  
 <span data-ttu-id="84432-119">También se puede pasar la información de cifrado al compilador con [-keyfile](keyfile.md).</span><span class="sxs-lookup"><span data-stu-id="84432-119">You can also pass your encryption information to the compiler with [-keyfile](keyfile.md).</span></span> <span data-ttu-id="84432-120">Use [-delaysign](delaysign.md) para firmar el ensamblado de forma parcial.</span><span class="sxs-lookup"><span data-stu-id="84432-120">Use [-delaysign](delaysign.md) if you want a partially signed assembly.</span></span>  
  
 <span data-ttu-id="84432-121">Para obtener más información sobre cómo firmar un ensamblado, vea [Creación y uso de ensamblados con nombre seguro](../../../standard/assembly/create-use-strong-named.md).</span><span class="sxs-lookup"><span data-stu-id="84432-121">See [Creating and Using Strong-Named Assemblies](../../../standard/assembly/create-use-strong-named.md) for more information on signing an assembly.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="84432-122">La opción `-keycontainer` no está disponible en el entorno de desarrollo de Visual Studio; solo lo está cuando se compila desde la línea de comandos.</span><span class="sxs-lookup"><span data-stu-id="84432-122">The `-keycontainer` option is not available from within the Visual Studio development environment; it is available only when compiling from the command line.</span></span>  
  
## <a name="example"></a><span data-ttu-id="84432-123">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="84432-123">Example</span></span>  

 <span data-ttu-id="84432-124">En el código siguiente se compila el archivo de código fuente `Input.vb` y se especifica un contenedor de claves.</span><span class="sxs-lookup"><span data-stu-id="84432-124">The following code compiles source file `Input.vb` and specifies a key container.</span></span>  
  
```console  
vbc -keycontainer:key1 input.vb  
```  
  
## <a name="see-also"></a><span data-ttu-id="84432-125">Vea también</span><span class="sxs-lookup"><span data-stu-id="84432-125">See also</span></span>

- [<span data-ttu-id="84432-126">Ensamblados de .NET</span><span class="sxs-lookup"><span data-stu-id="84432-126">Assemblies in .NET</span></span>](../../../standard/assembly/index.md)
- [<span data-ttu-id="84432-127">Compilador de línea de comandos de Visual Basic</span><span class="sxs-lookup"><span data-stu-id="84432-127">Visual Basic Command-Line Compiler</span></span>](index.md)
- [<span data-ttu-id="84432-128">-keyfile</span><span class="sxs-lookup"><span data-stu-id="84432-128">-keyfile</span></span>](keyfile.md)
- [<span data-ttu-id="84432-129">Líneas de comandos de compilación de ejemplo</span><span class="sxs-lookup"><span data-stu-id="84432-129">Sample Compilation Command Lines</span></span>](sample-compilation-command-lines.md)
