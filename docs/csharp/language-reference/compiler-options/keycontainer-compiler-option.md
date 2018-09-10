---
title: -keycontainer (Opciones del compilador de C#)
ms.date: 05/16/2018
f1_keywords:
- /keycontainer
helpviewer_keywords:
- /keycontainer compiler option [C#]
- keycontainer compiler option [C#]
- -keycontainer compiler option [C#]
ms.assetid: b3982b6d-2382-4f7e-bebd-ce98eaa30763
ms.openlocfilehash: 57d3acb4fe128e07020bfe7c85ed86563b16f40a
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/04/2018
ms.locfileid: "43518408"
---
# <a name="-keycontainer-c-compiler-options"></a><span data-ttu-id="c41a6-102">-keycontainer (Opciones del compilador de C#)</span><span class="sxs-lookup"><span data-stu-id="c41a6-102">-keycontainer (C# Compiler Options)</span></span>
<span data-ttu-id="c41a6-103">Especifica el nombre del contenedor de claves criptográficas.</span><span class="sxs-lookup"><span data-stu-id="c41a6-103">Specifies the name of the cryptographic key container.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c41a6-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="c41a6-104">Syntax</span></span>  
  
```console  
-keycontainer:string  
```  
  
## <a name="arguments"></a><span data-ttu-id="c41a6-105">Argumentos</span><span class="sxs-lookup"><span data-stu-id="c41a6-105">Arguments</span></span>  
 `string`  
 <span data-ttu-id="c41a6-106">El nombre del contenedor de claves de nombre seguro.</span><span class="sxs-lookup"><span data-stu-id="c41a6-106">The name of the strong name key container.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c41a6-107">Comentarios</span><span class="sxs-lookup"><span data-stu-id="c41a6-107">Remarks</span></span>  
 <span data-ttu-id="c41a6-108">Cuando se utiliza la opción **-keycontainer**, el compilador crea un componente que se puede compartir.</span><span class="sxs-lookup"><span data-stu-id="c41a6-108">When the **-keycontainer** option is used, the compiler creates a sharable component.</span></span> <span data-ttu-id="c41a6-109">El compilador inserta una clave pública del contenedor especificado en el manifiesto del ensamblado y firma el último ensamblado con la clave privada.</span><span class="sxs-lookup"><span data-stu-id="c41a6-109">The compiler inserts a public key from the specified container into the assembly manifest and signs the final assembly with the private key.</span></span> <span data-ttu-id="c41a6-110">Para generar un archivo de claves, escriba `sn -k file` en la línea de comandos.</span><span class="sxs-lookup"><span data-stu-id="c41a6-110">To generate a key file, type `sn -k file` at the command line.</span></span> <span data-ttu-id="c41a6-111">`sn -i` instala el par de claves en un contenedor.</span><span class="sxs-lookup"><span data-stu-id="c41a6-111">`sn -i` installs the key pair into a container.</span></span> <span data-ttu-id="c41a6-112">Esta opción no se admite cuando el compilador se ejecuta en CoreCLR.</span><span class="sxs-lookup"><span data-stu-id="c41a6-112">This option is not supported when the compiler runs on CoreCLR.</span></span> <span data-ttu-id="c41a6-113">Para firmar un ensamblado al compilar en CoreCLR, utilice la opción [-keyfile](keyfile-compiler-option.md).</span><span class="sxs-lookup"><span data-stu-id="c41a6-113">To sign an assembly when building on CoreCLR, use the [-keyfile](keyfile-compiler-option.md) option.</span></span>
  
 <span data-ttu-id="c41a6-114">Si se compila con [-target:module](../../../csharp/language-reference/compiler-options/target-module-compiler-option.md), el nombre del archivo de claves se mantiene en el módulo y se incorpora al ensamblado al compilar este módulo en un ensamblado con [-addmodule](../../../csharp/language-reference/compiler-options/addmodule-compiler-option.md).</span><span class="sxs-lookup"><span data-stu-id="c41a6-114">If you compile with [-target:module](../../../csharp/language-reference/compiler-options/target-module-compiler-option.md), the name of the key file is held in the module and incorporated into the assembly when you compile this module into an assembly with [-addmodule](../../../csharp/language-reference/compiler-options/addmodule-compiler-option.md).</span></span>  
  
 <span data-ttu-id="c41a6-115">También se puede especificar esta opción como un atributo personalizado (<xref:System.Reflection.AssemblyKeyNameAttribute?displayProperty=nameWithType>) en el código fuente de cualquier módulo del Lenguaje Intermedio de Microsoft (MSIL).</span><span class="sxs-lookup"><span data-stu-id="c41a6-115">You can also specify this option as a custom attribute (<xref:System.Reflection.AssemblyKeyNameAttribute?displayProperty=nameWithType>) in the source code for any Microsoft intermediate language (MSIL) module.</span></span>  
  
 <span data-ttu-id="c41a6-116">También se puede pasar la información de cifrado al compilador con [-keyfile](../../../csharp/language-reference/compiler-options/keyfile-compiler-option.md).</span><span class="sxs-lookup"><span data-stu-id="c41a6-116">You can also pass your encryption information to the compiler with [-keyfile](../../../csharp/language-reference/compiler-options/keyfile-compiler-option.md).</span></span> <span data-ttu-id="c41a6-117">Use [-delaysign](../../../csharp/language-reference/compiler-options/delaysign-compiler-option.md) si quiere agregar la clave pública al manifiesto del ensamblado pero retrasar la firma del ensamblado hasta que se haya probado.</span><span class="sxs-lookup"><span data-stu-id="c41a6-117">Use [-delaysign](../../../csharp/language-reference/compiler-options/delaysign-compiler-option.md) if you want the public key added to the assembly manifest but want to delay signing the assembly until it has been tested.</span></span>  
  
 <span data-ttu-id="c41a6-118">Para obtener más información, vea [Crear y usar ensamblados con nombre seguro](../../../framework/app-domains/create-and-use-strong-named-assemblies.md) y [Delay Signing an Assembly](../../../framework/app-domains/delay-sign-assembly.md) (Retrasar la firma de un ensamblado).</span><span class="sxs-lookup"><span data-stu-id="c41a6-118">For more information, see [Creating and Using Strong-Named Assemblies](../../../framework/app-domains/create-and-use-strong-named-assemblies.md) and [Delay Signing an Assembly](../../../framework/app-domains/delay-sign-assembly.md).</span></span>  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a><span data-ttu-id="c41a6-119">Para establecer esta opción del compilador en el entorno de desarrollo de Visual Studio</span><span class="sxs-lookup"><span data-stu-id="c41a6-119">To set this compiler option in the Visual Studio development environment</span></span>  
  
1.  <span data-ttu-id="c41a6-120">Esta opción del compilador no está disponible en el entorno de desarrollo de Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="c41a6-120">This compiler option is not available in the Visual Studio development environment.</span></span>  
  
 <span data-ttu-id="c41a6-121">Puede tener acceso mediante programación a esta opción del compilador con <xref:VSLangProj.ProjectProperties.AssemblyKeyContainerName%2A>.</span><span class="sxs-lookup"><span data-stu-id="c41a6-121">You can programmatically access this compiler option with <xref:VSLangProj.ProjectProperties.AssemblyKeyContainerName%2A>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c41a6-122">Vea también</span><span class="sxs-lookup"><span data-stu-id="c41a6-122">See Also</span></span>

- [<span data-ttu-id="c41a6-123">Opción -keyfile del compilador de C#</span><span class="sxs-lookup"><span data-stu-id="c41a6-123">C# Compiler -keyfile option</span></span>](keyfile-compiler-option.md)
- [<span data-ttu-id="c41a6-124">Opciones del compilador de C#</span><span class="sxs-lookup"><span data-stu-id="c41a6-124">C# Compiler Options</span></span>](index.md)  
- [<span data-ttu-id="c41a6-125">Administrar propiedades de soluciones y proyectos</span><span class="sxs-lookup"><span data-stu-id="c41a6-125">Managing Project and Solution Properties</span></span>](/visualstudio/ide/managing-project-and-solution-properties)
