---
title: -resource
ms.date: 03/13/2018
helpviewer_keywords:
- /resource compiler option [Visual Basic]
- -resource compiler option [Visual Basic]
- /res compiler option [Visual Basic]
- res compiler option [Visual Basic]
- -res compiler option [Visual Basic]
- resource compiler option [Visual Basic]
ms.assetid: eee2f227-91f2-4f2b-a9d6-1c51c5320858
ms.openlocfilehash: a781d543dd32ffb3d0ac0b11c544dbfd8cd5d806
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/22/2019
ms.locfileid: "74348566"
---
# <a name="-resource-visual-basic"></a><span data-ttu-id="f1ffa-102">-resource (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="f1ffa-102">-resource (Visual Basic)</span></span>
<span data-ttu-id="f1ffa-103">Inserta un recurso administrado en un ensamblado.</span><span class="sxs-lookup"><span data-stu-id="f1ffa-103">Embeds a managed resource in an assembly.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f1ffa-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="f1ffa-104">Syntax</span></span>  
  
```console  
-resource:filename[,identifier[,public|private]]  
```

<span data-ttu-id="f1ffa-105">o</span><span class="sxs-lookup"><span data-stu-id="f1ffa-105">or</span></span>  

```console
-res:filename[,identifier[,public|private]]  
```  
  
## <a name="arguments"></a><span data-ttu-id="f1ffa-106">Argumentos</span><span class="sxs-lookup"><span data-stu-id="f1ffa-106">Arguments</span></span>  
  
|<span data-ttu-id="f1ffa-107">Término</span><span class="sxs-lookup"><span data-stu-id="f1ffa-107">Term</span></span>|<span data-ttu-id="f1ffa-108">de esquema JSON</span><span class="sxs-lookup"><span data-stu-id="f1ffa-108">Definition</span></span>|  
|---|---|  
|`filename`|<span data-ttu-id="f1ffa-109">Requerido.</span><span class="sxs-lookup"><span data-stu-id="f1ffa-109">Required.</span></span> <span data-ttu-id="f1ffa-110">The name of the resource file to embed in the output file.</span><span class="sxs-lookup"><span data-stu-id="f1ffa-110">The name of the resource file to embed in the output file.</span></span> <span data-ttu-id="f1ffa-111">By default, `filename` is public in the assembly.</span><span class="sxs-lookup"><span data-stu-id="f1ffa-111">By default, `filename` is public in the assembly.</span></span> <span data-ttu-id="f1ffa-112">Enclose the file name in quotation marks (" ") if it contains a space.</span><span class="sxs-lookup"><span data-stu-id="f1ffa-112">Enclose the file name in quotation marks (" ") if it contains a space.</span></span>|  
|`identifier`|<span data-ttu-id="f1ffa-113">Opcional.</span><span class="sxs-lookup"><span data-stu-id="f1ffa-113">Optional.</span></span> <span data-ttu-id="f1ffa-114">The logical name for the resource; the name used to load it.</span><span class="sxs-lookup"><span data-stu-id="f1ffa-114">The logical name for the resource; the name used to load it.</span></span> <span data-ttu-id="f1ffa-115">El valor predeterminado es el nombre del archivo.</span><span class="sxs-lookup"><span data-stu-id="f1ffa-115">The default is the name of the file.</span></span> <span data-ttu-id="f1ffa-116">Optionally, you can specify whether the resource is public or private in the assembly manifest, as with the following: `-res:filename.res, myname.res, public`</span><span class="sxs-lookup"><span data-stu-id="f1ffa-116">Optionally, you can specify whether the resource is public or private in the assembly manifest, as with the following: `-res:filename.res, myname.res, public`</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f1ffa-117">Comentarios</span><span class="sxs-lookup"><span data-stu-id="f1ffa-117">Remarks</span></span>  
 <span data-ttu-id="f1ffa-118">Use `-linkresource` to link a resource to an assembly without placing the resource file in the output file.</span><span class="sxs-lookup"><span data-stu-id="f1ffa-118">Use `-linkresource` to link a resource to an assembly without placing the resource file in the output file.</span></span>  
  
 <span data-ttu-id="f1ffa-119">If `filename` is a .NET Framework resource file created, for example, by the [Resgen.exe (Resource File Generator)](../../../framework/tools/resgen-exe-resource-file-generator.md) or in the development environment, it can be accessed with members in the <xref:System.Resources> namespace (see <xref:System.Resources.ResourceManager> for more information).</span><span class="sxs-lookup"><span data-stu-id="f1ffa-119">If `filename` is a .NET Framework resource file created, for example, by the [Resgen.exe (Resource File Generator)](../../../framework/tools/resgen-exe-resource-file-generator.md) or in the development environment, it can be accessed with members in the <xref:System.Resources> namespace (see <xref:System.Resources.ResourceManager> for more information).</span></span> <span data-ttu-id="f1ffa-120">To access all other resources at run time, use one of the following methods: <xref:System.Reflection.Assembly.GetManifestResourceInfo%2A>, <xref:System.Reflection.Assembly.GetManifestResourceNames%2A>, or <xref:System.Reflection.Assembly.GetManifestResourceStream%2A>.</span><span class="sxs-lookup"><span data-stu-id="f1ffa-120">To access all other resources at run time, use one of the following methods: <xref:System.Reflection.Assembly.GetManifestResourceInfo%2A>, <xref:System.Reflection.Assembly.GetManifestResourceNames%2A>, or <xref:System.Reflection.Assembly.GetManifestResourceStream%2A>.</span></span>  
  
 <span data-ttu-id="f1ffa-121">La forma abreviada de `-resource` es `-res`.</span><span class="sxs-lookup"><span data-stu-id="f1ffa-121">The short form of `-resource` is `-res`.</span></span>  
  
 <span data-ttu-id="f1ffa-122">For information about how to set `-resource` in the Visual Studio IDE, see [Managing Application Resources (.NET)](/visualstudio/ide/managing-application-resources-dotnet).</span><span class="sxs-lookup"><span data-stu-id="f1ffa-122">For information about how to set `-resource` in the Visual Studio IDE, see [Managing Application Resources (.NET)](/visualstudio/ide/managing-application-resources-dotnet).</span></span>  
  
## <a name="example"></a><span data-ttu-id="f1ffa-123">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="f1ffa-123">Example</span></span>  
 <span data-ttu-id="f1ffa-124">The following code compiles `In.vb` and attaches resource file `Rf.resource`.</span><span class="sxs-lookup"><span data-stu-id="f1ffa-124">The following code compiles `In.vb` and attaches resource file `Rf.resource`.</span></span>  
  
```console
vbc -res:rf.resource in.vb  
```  
  
## <a name="see-also"></a><span data-ttu-id="f1ffa-125">Vea también</span><span class="sxs-lookup"><span data-stu-id="f1ffa-125">See also</span></span>

- [<span data-ttu-id="f1ffa-126">Compilador de línea de comandos de Visual Basic</span><span class="sxs-lookup"><span data-stu-id="f1ffa-126">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)
- [<span data-ttu-id="f1ffa-127">-win32resource</span><span class="sxs-lookup"><span data-stu-id="f1ffa-127">-win32resource</span></span>](../../../visual-basic/reference/command-line-compiler/win32resource.md)
- [<span data-ttu-id="f1ffa-128">-linkresource (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="f1ffa-128">-linkresource (Visual Basic)</span></span>](../../../visual-basic/reference/command-line-compiler/linkresource.md)
- [<span data-ttu-id="f1ffa-129">-target (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="f1ffa-129">-target (Visual Basic)</span></span>](../../../visual-basic/reference/command-line-compiler/target.md)
- [<span data-ttu-id="f1ffa-130">Líneas de comandos de compilación de ejemplo</span><span class="sxs-lookup"><span data-stu-id="f1ffa-130">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
