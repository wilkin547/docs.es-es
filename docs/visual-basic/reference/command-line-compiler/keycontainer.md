---
title: -keycontainer
ms.date: 03/10/2018
helpviewer_keywords:
- -keycontainer compiler option [Visual Basic]
- keycontainer compiler option [Visual Basic]
- /keycontainer compiler option [Visual Basic]
ms.assetid: 6a9bc861-1752-4db1-9f64-b5252f0482cc
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: d682533f96b5fb56430a0826d37a9794dc8c5d8f
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33655315"
---
# <a name="-keycontainer"></a><span data-ttu-id="e1b70-102">-keycontainer</span><span class="sxs-lookup"><span data-stu-id="e1b70-102">-keycontainer</span></span>
<span data-ttu-id="e1b70-103">Especifica un nombre de contenedor de claves para un par de claves que asigna un nombre seguro al ensamblado.</span><span class="sxs-lookup"><span data-stu-id="e1b70-103">Specifies a key container name for a key pair to give an assembly a strong name.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e1b70-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="e1b70-104">Syntax</span></span>  
  
```  
-keycontainer:container  
```  
  
## <a name="arguments"></a><span data-ttu-id="e1b70-105">Argumentos</span><span class="sxs-lookup"><span data-stu-id="e1b70-105">Arguments</span></span>  
  
|<span data-ttu-id="e1b70-106">Término</span><span class="sxs-lookup"><span data-stu-id="e1b70-106">Term</span></span>|<span data-ttu-id="e1b70-107">Definición</span><span class="sxs-lookup"><span data-stu-id="e1b70-107">Definition</span></span>|  
|---|---|  
|`container`|<span data-ttu-id="e1b70-108">Requerido.</span><span class="sxs-lookup"><span data-stu-id="e1b70-108">Required.</span></span> <span data-ttu-id="e1b70-109">Archivo contenedor que contiene la clave.</span><span class="sxs-lookup"><span data-stu-id="e1b70-109">Container file that contains the key.</span></span> <span data-ttu-id="e1b70-110">Ponga el nombre de archivo entre comillas ("") si el nombre contiene un espacio.</span><span class="sxs-lookup"><span data-stu-id="e1b70-110">Enclose the file name in quotation marks ("") if the name contains a space.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e1b70-111">Comentarios</span><span class="sxs-lookup"><span data-stu-id="e1b70-111">Remarks</span></span>  
 <span data-ttu-id="e1b70-112">El compilador crea el componente compartible insertando una clave pública en el manifiesto del ensamblado y firma el ensamblado final con la clave privada.</span><span class="sxs-lookup"><span data-stu-id="e1b70-112">The compiler creates the sharable component by inserting a public key into the assembly manifest and by signing the final assembly with the private key.</span></span> <span data-ttu-id="e1b70-113">Para generar un archivo de clave, escriba `sn -k``file` en la línea de comandos.</span><span class="sxs-lookup"><span data-stu-id="e1b70-113">To generate a key file, type `sn -k``file` at the command line.</span></span> <span data-ttu-id="e1b70-114">El `-i` opción instala el par de claves en un contenedor.</span><span class="sxs-lookup"><span data-stu-id="e1b70-114">The `-i` option installs the key pair into a container.</span></span> <span data-ttu-id="e1b70-115">Para obtener más información, consulte [Sn.exe (herramienta de nombre seguro)][Sn.exe (herramienta de nombre seguro)](../../../framework/tools/sn-exe-strong-name-tool.md)).</span><span class="sxs-lookup"><span data-stu-id="e1b70-115">For more information, see [Sn.exe (Strong Name Tool)][Sn.exe (Strong Name Tool)](../../../framework/tools/sn-exe-strong-name-tool.md)).</span></span>  
  
 <span data-ttu-id="e1b70-116">Si se compila con `-target:module`, el nombre del archivo de clave se mantiene en el módulo y se incorpora en el ensamblado que se crea cuando se compila un ensamblado con [- addmodule](../../../visual-basic/reference/command-line-compiler/addmodule.md).</span><span class="sxs-lookup"><span data-stu-id="e1b70-116">If you compile with `-target:module`, the name of the key file is held in the module and incorporated into the assembly that is created when you compile an assembly with [-addmodule](../../../visual-basic/reference/command-line-compiler/addmodule.md).</span></span>  
  
 <span data-ttu-id="e1b70-117">También se puede especificar esta opción como un atributo personalizado (<xref:System.Reflection.AssemblyKeyNameAttribute>) en el código fuente de cualquier módulo del Lenguaje Intermedio de Microsoft (MSIL).</span><span class="sxs-lookup"><span data-stu-id="e1b70-117">You can also specify this option as a custom attribute (<xref:System.Reflection.AssemblyKeyNameAttribute>) in the source code for any Microsoft intermediate language (MSIL) module.</span></span>  
  
 <span data-ttu-id="e1b70-118">También se puede pasar la información de cifrado al compilador con [-keyfile](../../../visual-basic/reference/command-line-compiler/keyfile.md).</span><span class="sxs-lookup"><span data-stu-id="e1b70-118">You can also pass your encryption information to the compiler with [-keyfile](../../../visual-basic/reference/command-line-compiler/keyfile.md).</span></span> <span data-ttu-id="e1b70-119">Use [-delaysign](../../../visual-basic/reference/command-line-compiler/delaysign.md) para firmar el ensamblado de forma parcial.</span><span class="sxs-lookup"><span data-stu-id="e1b70-119">Use [-delaysign](../../../visual-basic/reference/command-line-compiler/delaysign.md) if you want a partially signed assembly.</span></span>  
  
 <span data-ttu-id="e1b70-120">Vea [crear y utilizar ensamblados](../../../framework/app-domains/create-and-use-strong-named-assemblies.md) para obtener más información sobre cómo firmar un ensamblado.</span><span class="sxs-lookup"><span data-stu-id="e1b70-120">See [Creating and Using Strong-Named Assemblies](../../../framework/app-domains/create-and-use-strong-named-assemblies.md) for more information on signing an assembly.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="e1b70-121">El `-keycontainer` opción no está disponible en el entorno de desarrollo de Visual Studio, que está disponible sólo cuando se compila desde la línea de comandos.</span><span class="sxs-lookup"><span data-stu-id="e1b70-121">The `-keycontainer` option is not available from within the Visual Studio development environment; it is available only when compiling from the command line.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e1b70-122">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="e1b70-122">Example</span></span>  
 <span data-ttu-id="e1b70-123">El código siguiente compila el archivo de código fuente `Input.vb` y especifica un contenedor de claves.</span><span class="sxs-lookup"><span data-stu-id="e1b70-123">The following code compiles source file `Input.vb` and specifies a key container.</span></span>  
  
```  
vbc -keycontainer:key1 input.vb  
```  
  
## <a name="see-also"></a><span data-ttu-id="e1b70-124">Vea también</span><span class="sxs-lookup"><span data-stu-id="e1b70-124">See Also</span></span>  
 [<span data-ttu-id="e1b70-125">Ensamblados y Caché global de ensamblados</span><span class="sxs-lookup"><span data-stu-id="e1b70-125">Assemblies and the Global Assembly Cache</span></span>](../../../visual-basic/programming-guide/concepts/assemblies-gac/index.md)  
 [<span data-ttu-id="e1b70-126">Compilador de línea de comandos de Visual Basic</span><span class="sxs-lookup"><span data-stu-id="e1b70-126">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)  
 [<span data-ttu-id="e1b70-127">-keyfile</span><span class="sxs-lookup"><span data-stu-id="e1b70-127">-keyfile</span></span>](../../../visual-basic/reference/command-line-compiler/keyfile.md)  
 [<span data-ttu-id="e1b70-128">Líneas de comandos de compilación de ejemplo</span><span class="sxs-lookup"><span data-stu-id="e1b70-128">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
