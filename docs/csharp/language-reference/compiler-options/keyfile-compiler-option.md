---
title: -keyfile (Opciones del compilador de C#)
ms.date: 07/20/2015
f1_keywords:
- /keyfile
helpviewer_keywords:
- /keyfile compiler option [C#]
- -keyfile compiler option [C#]
- keyfile compiler option [C#]
ms.assetid: 0815f9de-ace4-4e98-b4c6-13c55dea40c2
ms.openlocfilehash: bf271cc6b6887e930911071d4603b51daed55e61
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/14/2020
ms.locfileid: "70970260"
---
# <a name="-keyfile-c-compiler-options"></a><span data-ttu-id="77c58-102">-keyfile (Opciones del compilador de C#)</span><span class="sxs-lookup"><span data-stu-id="77c58-102">-keyfile (C# Compiler Options)</span></span>
<span data-ttu-id="77c58-103">Especifica el nombre de archivo que contiene la clave criptográfica.</span><span class="sxs-lookup"><span data-stu-id="77c58-103">Specifies the filename containing the cryptographic key.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="77c58-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="77c58-104">Syntax</span></span>  
  
```console  
-keyfile:file  
```  
  
## <a name="arguments"></a><span data-ttu-id="77c58-105">Argumentos</span><span class="sxs-lookup"><span data-stu-id="77c58-105">Arguments</span></span>  
  
|<span data-ttu-id="77c58-106">Término</span><span class="sxs-lookup"><span data-stu-id="77c58-106">Term</span></span>|<span data-ttu-id="77c58-107">Definición</span><span class="sxs-lookup"><span data-stu-id="77c58-107">Definition</span></span>|  
|----------|----------------|  
|`file`|<span data-ttu-id="77c58-108">El nombre del archivo que contiene la clave de nombre seguro.</span><span class="sxs-lookup"><span data-stu-id="77c58-108">The name of the file containing the strong name key.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="77c58-109">Comentarios</span><span class="sxs-lookup"><span data-stu-id="77c58-109">Remarks</span></span>  
 <span data-ttu-id="77c58-110">Cuando se usa esta opción, el compilador inserta la clave pública del archivo especificado en el manifiesto del ensamblado y, después, firma el último ensamblado con la clave privada.</span><span class="sxs-lookup"><span data-stu-id="77c58-110">When this option is used, the compiler inserts the public key from the specified file into the assembly manifest and then signs the final assembly with the private key.</span></span> <span data-ttu-id="77c58-111">Para generar un archivo de clave, escriba sn -k `file` en la línea de comandos.</span><span class="sxs-lookup"><span data-stu-id="77c58-111">To generate a key file, type sn -k `file` at the command line.</span></span>  
  
 <span data-ttu-id="77c58-112">Si se compila con la opción **-target:module**, el nombre del archivo de claves se mantiene en el módulo y se incorpora en el ensamblado que se crea al compilar un ensamblado con la opción [-addmodule](./addmodule-compiler-option.md).</span><span class="sxs-lookup"><span data-stu-id="77c58-112">If you compile with **-target:module**, the name of the key file is held in the module and incorporated into the assembly that is created when you compile an assembly with [-addmodule](./addmodule-compiler-option.md).</span></span>  
  
 <span data-ttu-id="77c58-113">También puede pasar la información de cifrado al compilador con [-keycontainer](./keycontainer-compiler-option.md).</span><span class="sxs-lookup"><span data-stu-id="77c58-113">You can also pass your encryption information to the compiler with [-keycontainer](./keycontainer-compiler-option.md).</span></span> <span data-ttu-id="77c58-114">Use [-delaysign](./delaysign-compiler-option.md) para firmar el ensamblado de forma parcial.</span><span class="sxs-lookup"><span data-stu-id="77c58-114">Use [-delaysign](./delaysign-compiler-option.md) if you want a partially signed assembly.</span></span>  
  
 <span data-ttu-id="77c58-115">Si se especifica tanto -keyfile como -keycontainer (ya sea mediante una opción de línea de comandos o mediante un atributo personalizado) en la misma compilación, el compilador probará primero el contenedor de claves.</span><span class="sxs-lookup"><span data-stu-id="77c58-115">In case both -keyfile and -keycontainer are specified (either by command line option or by custom attribute) in the same compilation, the compiler will first try the key container.</span></span> <span data-ttu-id="77c58-116">Si lo consigue, el ensamblado se firma con la información del contenedor de claves.</span><span class="sxs-lookup"><span data-stu-id="77c58-116">If that succeeds, then the assembly is signed with the information in the key container.</span></span> <span data-ttu-id="77c58-117">Si el compilador no encuentra el contenedor de claves, probará el archivo especificado con -keyfile.</span><span class="sxs-lookup"><span data-stu-id="77c58-117">If the compiler does not find the key container, it will try the file specified with -keyfile.</span></span> <span data-ttu-id="77c58-118">Si lo consigue, el ensamblado se firma con la información del archivo de clave y la información de la clave se instalará en el contenedor de claves (similar a sn -i) de modo que, en la próxima compilación, el contenedor de claves será válido.</span><span class="sxs-lookup"><span data-stu-id="77c58-118">If that succeeds, the assembly is signed with the information in the key file and the key information will be installed in the key container (similar to sn -i) so that on the next compilation, the key container will be valid.</span></span>  
  
 <span data-ttu-id="77c58-119">Tenga en cuenta que un archivo de clave puede contener solo la clave pública.</span><span class="sxs-lookup"><span data-stu-id="77c58-119">Note that a key file might contain only the public key.</span></span>  
  
 <span data-ttu-id="77c58-120">Para obtener más información, vea [Crear y usar ensamblados con nombre seguro](../../../standard/assembly/create-use-strong-named.md) y [Delay Signing an Assembly](../../../standard/assembly/delay-sign.md) (Retrasar la firma de un ensamblado).</span><span class="sxs-lookup"><span data-stu-id="77c58-120">For more information, see [Creating and Using Strong-Named Assemblies](../../../standard/assembly/create-use-strong-named.md) and [Delay Signing an Assembly](../../../standard/assembly/delay-sign.md).</span></span>  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a><span data-ttu-id="77c58-121">Para establecer esta opción del compilador en el entorno de desarrollo de Visual Studio</span><span class="sxs-lookup"><span data-stu-id="77c58-121">To set this compiler option in the Visual Studio development environment</span></span>  
  
1. <span data-ttu-id="77c58-122">Abra la página **Propiedades** del proyecto.</span><span class="sxs-lookup"><span data-stu-id="77c58-122">Open the **Properties** page for the project.</span></span>  
  
2. <span data-ttu-id="77c58-123">Haga clic en la página de propiedades **Firma**.</span><span class="sxs-lookup"><span data-stu-id="77c58-123">Click the **Signing** property page.</span></span>  
  
3. <span data-ttu-id="77c58-124">Modifique la propiedad **Seleccione un archivo de clave de nombre seguro**.</span><span class="sxs-lookup"><span data-stu-id="77c58-124">Modify the **Choose a strong name key file** property.</span></span>  
  
 <span data-ttu-id="77c58-125">Puede tener acceso mediante programación a esta opción del compilador con <xref:VSLangProj.ProjectProperties.AssemblyOriginatorKeyFile%2A>.</span><span class="sxs-lookup"><span data-stu-id="77c58-125">You can programmatically access this compiler option with <xref:VSLangProj.ProjectProperties.AssemblyOriginatorKeyFile%2A>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="77c58-126">Vea también</span><span class="sxs-lookup"><span data-stu-id="77c58-126">See also</span></span>

- [<span data-ttu-id="77c58-127">Opciones del compilador de C#</span><span class="sxs-lookup"><span data-stu-id="77c58-127">C# Compiler Options</span></span>](./index.md)
- [<span data-ttu-id="77c58-128">Administrar propiedades de proyectos y de soluciones</span><span class="sxs-lookup"><span data-stu-id="77c58-128">Managing Project and Solution Properties</span></span>](/visualstudio/ide/managing-project-and-solution-properties)
