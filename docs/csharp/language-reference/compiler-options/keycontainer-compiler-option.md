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
ms.openlocfilehash: fead2d4296cfa6fb0195cb4b43f6448c0fc7e6a9
ms.sourcegitcommit: 7b1ce327e8c84f115f007be4728d29a89efe11ef
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/13/2019
ms.locfileid: "70970149"
---
# <a name="-keycontainer-c-compiler-options"></a><span data-ttu-id="23c25-102">-keycontainer (Opciones del compilador de C#)</span><span class="sxs-lookup"><span data-stu-id="23c25-102">-keycontainer (C# Compiler Options)</span></span>
<span data-ttu-id="23c25-103">Especifica el nombre del contenedor de claves criptográficas.</span><span class="sxs-lookup"><span data-stu-id="23c25-103">Specifies the name of the cryptographic key container.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="23c25-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="23c25-104">Syntax</span></span>  
  
```console  
-keycontainer:string  
```  
  
## <a name="arguments"></a><span data-ttu-id="23c25-105">Argumentos</span><span class="sxs-lookup"><span data-stu-id="23c25-105">Arguments</span></span>  
 `string`  
 <span data-ttu-id="23c25-106">El nombre del contenedor de claves de nombre seguro.</span><span class="sxs-lookup"><span data-stu-id="23c25-106">The name of the strong name key container.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="23c25-107">Comentarios</span><span class="sxs-lookup"><span data-stu-id="23c25-107">Remarks</span></span>  
 <span data-ttu-id="23c25-108">Cuando se utiliza la opción **-keycontainer**, el compilador crea un componente que se puede compartir.</span><span class="sxs-lookup"><span data-stu-id="23c25-108">When the **-keycontainer** option is used, the compiler creates a sharable component.</span></span> <span data-ttu-id="23c25-109">El compilador inserta una clave pública del contenedor especificado en el manifiesto del ensamblado y firma el último ensamblado con la clave privada.</span><span class="sxs-lookup"><span data-stu-id="23c25-109">The compiler inserts a public key from the specified container into the assembly manifest and signs the final assembly with the private key.</span></span> <span data-ttu-id="23c25-110">Para generar un archivo de claves, escriba `sn -k file` en la línea de comandos.</span><span class="sxs-lookup"><span data-stu-id="23c25-110">To generate a key file, type `sn -k file` at the command line.</span></span> <span data-ttu-id="23c25-111">`sn -i` instala el par de claves en un contenedor.</span><span class="sxs-lookup"><span data-stu-id="23c25-111">`sn -i` installs the key pair into a container.</span></span> <span data-ttu-id="23c25-112">Esta opción no se admite cuando el compilador se ejecuta en CoreCLR.</span><span class="sxs-lookup"><span data-stu-id="23c25-112">This option is not supported when the compiler runs on CoreCLR.</span></span> <span data-ttu-id="23c25-113">Para firmar un ensamblado al compilar en CoreCLR, utilice la opción [-keyfile](keyfile-compiler-option.md).</span><span class="sxs-lookup"><span data-stu-id="23c25-113">To sign an assembly when building on CoreCLR, use the [-keyfile](keyfile-compiler-option.md) option.</span></span>
  
 <span data-ttu-id="23c25-114">Si se compila con [-target:module](./target-module-compiler-option.md), el nombre del archivo de claves se mantiene en el módulo y se incorpora al ensamblado al compilar este módulo en un ensamblado con [-addmodule](./addmodule-compiler-option.md).</span><span class="sxs-lookup"><span data-stu-id="23c25-114">If you compile with [-target:module](./target-module-compiler-option.md), the name of the key file is held in the module and incorporated into the assembly when you compile this module into an assembly with [-addmodule](./addmodule-compiler-option.md).</span></span>  
  
 <span data-ttu-id="23c25-115">También se puede especificar esta opción como un atributo personalizado (<xref:System.Reflection.AssemblyKeyNameAttribute?displayProperty=nameWithType>) en el código fuente de cualquier módulo del Lenguaje Intermedio de Microsoft (MSIL).</span><span class="sxs-lookup"><span data-stu-id="23c25-115">You can also specify this option as a custom attribute (<xref:System.Reflection.AssemblyKeyNameAttribute?displayProperty=nameWithType>) in the source code for any Microsoft intermediate language (MSIL) module.</span></span>  
  
 <span data-ttu-id="23c25-116">También se puede pasar la información de cifrado al compilador con [-keyfile](./keyfile-compiler-option.md).</span><span class="sxs-lookup"><span data-stu-id="23c25-116">You can also pass your encryption information to the compiler with [-keyfile](./keyfile-compiler-option.md).</span></span> <span data-ttu-id="23c25-117">Use [-delaysign](./delaysign-compiler-option.md) si quiere agregar la clave pública al manifiesto del ensamblado pero retrasar la firma del ensamblado hasta que se haya probado.</span><span class="sxs-lookup"><span data-stu-id="23c25-117">Use [-delaysign](./delaysign-compiler-option.md) if you want the public key added to the assembly manifest but want to delay signing the assembly until it has been tested.</span></span>  
  
 <span data-ttu-id="23c25-118">Para obtener más información, vea [Crear y usar ensamblados con nombre seguro](../../../standard/assembly/create-use-strong-named.md) y [Delay Signing an Assembly](../../../standard/assembly/delay-sign.md) (Retrasar la firma de un ensamblado).</span><span class="sxs-lookup"><span data-stu-id="23c25-118">For more information, see [Creating and Using Strong-Named Assemblies](../../../standard/assembly/create-use-strong-named.md) and [Delay Signing an Assembly](../../../standard/assembly/delay-sign.md).</span></span>  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a><span data-ttu-id="23c25-119">Para establecer esta opción del compilador en el entorno de desarrollo de Visual Studio</span><span class="sxs-lookup"><span data-stu-id="23c25-119">To set this compiler option in the Visual Studio development environment</span></span>  
  
1. <span data-ttu-id="23c25-120">Esta opción del compilador no está disponible en el entorno de desarrollo de Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="23c25-120">This compiler option is not available in the Visual Studio development environment.</span></span>  
  
 <span data-ttu-id="23c25-121">Puede tener acceso mediante programación a esta opción del compilador con <xref:VSLangProj.ProjectProperties.AssemblyKeyContainerName%2A>.</span><span class="sxs-lookup"><span data-stu-id="23c25-121">You can programmatically access this compiler option with <xref:VSLangProj.ProjectProperties.AssemblyKeyContainerName%2A>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="23c25-122">Vea también</span><span class="sxs-lookup"><span data-stu-id="23c25-122">See also</span></span>

- [<span data-ttu-id="23c25-123">Opción -keyfile del compilador de C#</span><span class="sxs-lookup"><span data-stu-id="23c25-123">C# Compiler -keyfile option</span></span>](keyfile-compiler-option.md)
- [<span data-ttu-id="23c25-124">Opciones del compilador de C#</span><span class="sxs-lookup"><span data-stu-id="23c25-124">C# Compiler Options</span></span>](index.md)
- [<span data-ttu-id="23c25-125">Administrar propiedades de soluciones y proyectos</span><span class="sxs-lookup"><span data-stu-id="23c25-125">Managing Project and Solution Properties</span></span>](/visualstudio/ide/managing-project-and-solution-properties)
