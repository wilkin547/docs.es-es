---
title: -keycontainer (Opciones del compilador de C#)
ms.date: 07/20/2015
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- /keycontainer
helpviewer_keywords:
- /keycontainer compiler option [C#]
- keycontainer compiler option [C#]
- -keycontainer compiler option [C#]
ms.assetid: b3982b6d-2382-4f7e-bebd-ce98eaa30763
caps.latest.revision: 
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 944a9b4dbbed76f388642d67be9518343f750de5
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/19/2018
---
# <a name="-keycontainer-c-compiler-options"></a><span data-ttu-id="5423f-102">-keycontainer (Opciones del compilador de C#)</span><span class="sxs-lookup"><span data-stu-id="5423f-102">-keycontainer (C# Compiler Options)</span></span>
<span data-ttu-id="5423f-103">Especifica el nombre del contenedor de claves criptográficas.</span><span class="sxs-lookup"><span data-stu-id="5423f-103">Specifies the name of the cryptographic key container.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5423f-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="5423f-104">Syntax</span></span>  
  
```console  
-keycontainer:string  
```  
  
## <a name="arguments"></a><span data-ttu-id="5423f-105">Argumentos</span><span class="sxs-lookup"><span data-stu-id="5423f-105">Arguments</span></span>  
 `string`  
 <span data-ttu-id="5423f-106">El nombre del contenedor de claves de nombre seguro.</span><span class="sxs-lookup"><span data-stu-id="5423f-106">The name of the strong name key container.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="5423f-107">Comentarios</span><span class="sxs-lookup"><span data-stu-id="5423f-107">Remarks</span></span>  
 <span data-ttu-id="5423f-108">Cuando se usa la opción **-keycontainer**, el compilador crea un componente compartible insertando una clave pública desde el contenedor especificado en el manifiesto del ensamblado y firma el ensamblado final con la clave privada.</span><span class="sxs-lookup"><span data-stu-id="5423f-108">When the **-keycontainer** option is used, the compiler creates a sharable component by inserting a public key from the specified container into the assembly manifest and signing the final assembly with the private key.</span></span> <span data-ttu-id="5423f-109">Para generar un archivo de clave, escriba sn -k `file` en la línea de comandos.</span><span class="sxs-lookup"><span data-stu-id="5423f-109">To generate a key file, type sn -k `file` at the command line.</span></span> <span data-ttu-id="5423f-110">sn -i instala el par de claves en un contenedor.</span><span class="sxs-lookup"><span data-stu-id="5423f-110">sn -i installs the key pair into a container.</span></span>  
  
 <span data-ttu-id="5423f-111">Si se compila con [-target:module](../../../csharp/language-reference/compiler-options/target-module-compiler-option.md), el nombre del archivo de claves se mantiene en el módulo y se incorpora al ensamblado al compilar este módulo en un ensamblado con [-addmodule](../../../csharp/language-reference/compiler-options/addmodule-compiler-option.md).</span><span class="sxs-lookup"><span data-stu-id="5423f-111">If you compile with [-target:module](../../../csharp/language-reference/compiler-options/target-module-compiler-option.md), the name of the key file is held in the module and incorporated into the assembly when you compile this module into an assembly with [-addmodule](../../../csharp/language-reference/compiler-options/addmodule-compiler-option.md).</span></span>  
  
 <span data-ttu-id="5423f-112">También se puede especificar esta opción como un atributo personalizado (<xref:System.Reflection.AssemblyKeyNameAttribute?displayProperty=nameWithType>) en el código fuente de cualquier módulo del Lenguaje Intermedio de Microsoft (MSIL).</span><span class="sxs-lookup"><span data-stu-id="5423f-112">You can also specify this option as a custom attribute (<xref:System.Reflection.AssemblyKeyNameAttribute?displayProperty=nameWithType>) in the source code for any Microsoft intermediate language (MSIL) module.</span></span>  
  
 <span data-ttu-id="5423f-113">También se puede pasar la información de cifrado al compilador con [-keyfile](../../../csharp/language-reference/compiler-options/keyfile-compiler-option.md).</span><span class="sxs-lookup"><span data-stu-id="5423f-113">You can also pass your encryption information to the compiler with [-keyfile](../../../csharp/language-reference/compiler-options/keyfile-compiler-option.md).</span></span> <span data-ttu-id="5423f-114">Use [-delaysign](../../../csharp/language-reference/compiler-options/delaysign-compiler-option.md) si quiere agregar la clave pública al manifiesto del ensamblado pero retrasar la firma del ensamblado hasta que se haya probado.</span><span class="sxs-lookup"><span data-stu-id="5423f-114">Use [-delaysign](../../../csharp/language-reference/compiler-options/delaysign-compiler-option.md) if you want the public key added to the assembly manifest but want to delay signing the assembly until it has been tested.</span></span>  
  
 <span data-ttu-id="5423f-115">Para obtener más información, vea [Crear y usar ensamblados con nombre seguro](../../../framework/app-domains/create-and-use-strong-named-assemblies.md) y [Delay Signing an Assembly](../../../framework/app-domains/delay-sign-assembly.md) (Retrasar la firma de un ensamblado).</span><span class="sxs-lookup"><span data-stu-id="5423f-115">For more information, see [Creating and Using Strong-Named Assemblies](../../../framework/app-domains/create-and-use-strong-named-assemblies.md) and [Delay Signing an Assembly](../../../framework/app-domains/delay-sign-assembly.md).</span></span>  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a><span data-ttu-id="5423f-116">Para establecer esta opción del compilador en el entorno de desarrollo de Visual Studio</span><span class="sxs-lookup"><span data-stu-id="5423f-116">To set this compiler option in the Visual Studio development environment</span></span>  
  
1.  <span data-ttu-id="5423f-117">Esta opción del compilador no está disponible en el entorno de desarrollo de Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="5423f-117">This compiler option is not available in the Visual Studio development environment.</span></span>  
  
 <span data-ttu-id="5423f-118">Puede tener acceso mediante programación a esta opción del compilador con <xref:VSLangProj.ProjectProperties.AssemblyKeyContainerName%2A>.</span><span class="sxs-lookup"><span data-stu-id="5423f-118">You can programmatically access this compiler option with <xref:VSLangProj.ProjectProperties.AssemblyKeyContainerName%2A>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5423f-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="5423f-119">See Also</span></span>  
 [<span data-ttu-id="5423f-120">Opciones del compilador de C#</span><span class="sxs-lookup"><span data-stu-id="5423f-120">C# Compiler Options</span></span>](../../../csharp/language-reference/compiler-options/index.md)  
 [<span data-ttu-id="5423f-121">Administrar propiedades de soluciones y proyectos</span><span class="sxs-lookup"><span data-stu-id="5423f-121">Managing Project and Solution Properties</span></span>](/visualstudio/ide/managing-project-and-solution-properties)
