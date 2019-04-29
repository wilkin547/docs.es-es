---
title: -resource (Visual Basic)
ms.date: 03/13/2018
helpviewer_keywords:
- /resource compiler option [Visual Basic]
- -resource compiler option [Visual Basic]
- /res compiler option [Visual Basic]
- res compiler option [Visual Basic]
- -res compiler option [Visual Basic]
- resource compiler option [Visual Basic]
ms.assetid: eee2f227-91f2-4f2b-a9d6-1c51c5320858
ms.openlocfilehash: 46122eaa7ca54679c9a52b939f9100c9a0747e7b
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61639091"
---
# <a name="-resource-visual-basic"></a><span data-ttu-id="719fe-102">-resource (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="719fe-102">-resource (Visual Basic)</span></span>
<span data-ttu-id="719fe-103">Inserta un recurso administrado en un ensamblado.</span><span class="sxs-lookup"><span data-stu-id="719fe-103">Embeds a managed resource in an assembly.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="719fe-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="719fe-104">Syntax</span></span>  
  
```  
-resource:filename[,identifier[,public|private]]  
' -or-  
-res:filename[,identifier[,public|private]]  
```  
  
## <a name="arguments"></a><span data-ttu-id="719fe-105">Argumentos</span><span class="sxs-lookup"><span data-stu-id="719fe-105">Arguments</span></span>  
  
|<span data-ttu-id="719fe-106">Término</span><span class="sxs-lookup"><span data-stu-id="719fe-106">Term</span></span>|<span data-ttu-id="719fe-107">Definición</span><span class="sxs-lookup"><span data-stu-id="719fe-107">Definition</span></span>|  
|---|---|  
|`filename`|<span data-ttu-id="719fe-108">Obligatorio.</span><span class="sxs-lookup"><span data-stu-id="719fe-108">Required.</span></span> <span data-ttu-id="719fe-109">El nombre del archivo de recursos para insertar en el archivo de salida.</span><span class="sxs-lookup"><span data-stu-id="719fe-109">The name of the resource file to embed in the output file.</span></span> <span data-ttu-id="719fe-110">De forma predeterminada, `filename` es público en el ensamblado.</span><span class="sxs-lookup"><span data-stu-id="719fe-110">By default, `filename` is public in the assembly.</span></span> <span data-ttu-id="719fe-111">Ponga el nombre de archivo entre comillas ("") si contiene un espacio.</span><span class="sxs-lookup"><span data-stu-id="719fe-111">Enclose the file name in quotation marks (" ") if it contains a space.</span></span>|  
|`identifier`|<span data-ttu-id="719fe-112">Opcional.</span><span class="sxs-lookup"><span data-stu-id="719fe-112">Optional.</span></span> <span data-ttu-id="719fe-113">El nombre lógico del recurso; el nombre utilizado para cargarlo.</span><span class="sxs-lookup"><span data-stu-id="719fe-113">The logical name for the resource; the name used to load it.</span></span> <span data-ttu-id="719fe-114">El valor predeterminado es el nombre del archivo.</span><span class="sxs-lookup"><span data-stu-id="719fe-114">The default is the name of the file.</span></span> <span data-ttu-id="719fe-115">Si lo desea, puede especificar si el recurso es público o privado en el manifiesto del ensamblado, al igual que con los siguientes: `-res:filename.res, myname.res, public`</span><span class="sxs-lookup"><span data-stu-id="719fe-115">Optionally, you can specify whether the resource is public or private in the assembly manifest, as with the following: `-res:filename.res, myname.res, public`</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="719fe-116">Comentarios</span><span class="sxs-lookup"><span data-stu-id="719fe-116">Remarks</span></span>  
 <span data-ttu-id="719fe-117">Use `-linkresource` para vincular un recurso a un ensamblado sin incluir el archivo de recursos en el archivo de salida.</span><span class="sxs-lookup"><span data-stu-id="719fe-117">Use `-linkresource` to link a resource to an assembly without placing the resource file in the output file.</span></span>  
  
 <span data-ttu-id="719fe-118">Si `filename` es un [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] archivo de recursos creado, por ejemplo, con el [Resgen.exe (Resource File Generator)](../../../framework/tools/resgen-exe-resource-file-generator.md) o en el entorno de desarrollo, puede obtenerse con los miembros de la <xref:System.Resources> espacio de nombres (consulte <xref:System.Resources.ResourceManager> para obtener más información).</span><span class="sxs-lookup"><span data-stu-id="719fe-118">If `filename` is a [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] resource file created, for example, by the [Resgen.exe (Resource File Generator)](../../../framework/tools/resgen-exe-resource-file-generator.md) or in the development environment, it can be accessed with members in the <xref:System.Resources> namespace (see <xref:System.Resources.ResourceManager> for more information).</span></span> <span data-ttu-id="719fe-119">Para obtener acceso a todos los demás recursos en tiempo de ejecución, utilice uno de los métodos siguientes: <xref:System.Reflection.Assembly.GetManifestResourceInfo%2A>, <xref:System.Reflection.Assembly.GetManifestResourceNames%2A>, o <xref:System.Reflection.Assembly.GetManifestResourceStream%2A>.</span><span class="sxs-lookup"><span data-stu-id="719fe-119">To access all other resources at run time, use one of the following methods: <xref:System.Reflection.Assembly.GetManifestResourceInfo%2A>, <xref:System.Reflection.Assembly.GetManifestResourceNames%2A>, or <xref:System.Reflection.Assembly.GetManifestResourceStream%2A>.</span></span>  
  
 <span data-ttu-id="719fe-120">La forma abreviada de `-resource` es `-res`.</span><span class="sxs-lookup"><span data-stu-id="719fe-120">The short form of `-resource` is `-res`.</span></span>  
  
 <span data-ttu-id="719fe-121">Para obtener información sobre cómo establecer `-resource` en el IDE de Visual Studio, consulte [administrar aplicación de recursos (. NET)](/visualstudio/ide/managing-application-resources-dotnet).</span><span class="sxs-lookup"><span data-stu-id="719fe-121">For information about how to set `-resource` in the Visual Studio IDE, see [Managing Application Resources (.NET)](/visualstudio/ide/managing-application-resources-dotnet).</span></span>  
  
## <a name="example"></a><span data-ttu-id="719fe-122">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="719fe-122">Example</span></span>  
 <span data-ttu-id="719fe-123">El siguiente código compila `In.vb` y archivo de recursos adjunta `Rf.resource`.</span><span class="sxs-lookup"><span data-stu-id="719fe-123">The following code compiles `In.vb` and attaches resource file `Rf.resource`.</span></span>  
  
```console
vbc -res:rf.resource in.vb  
```  
  
## <a name="see-also"></a><span data-ttu-id="719fe-124">Vea también</span><span class="sxs-lookup"><span data-stu-id="719fe-124">See also</span></span>

- [<span data-ttu-id="719fe-125">Compilador de línea de comandos de Visual Basic</span><span class="sxs-lookup"><span data-stu-id="719fe-125">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)
- [<span data-ttu-id="719fe-126">-win32resource</span><span class="sxs-lookup"><span data-stu-id="719fe-126">-win32resource</span></span>](../../../visual-basic/reference/command-line-compiler/win32resource.md)
- [<span data-ttu-id="719fe-127">-linkresource (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="719fe-127">-linkresource (Visual Basic)</span></span>](../../../visual-basic/reference/command-line-compiler/linkresource.md)
- [<span data-ttu-id="719fe-128">-target (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="719fe-128">-target (Visual Basic)</span></span>](../../../visual-basic/reference/command-line-compiler/target.md)
- [<span data-ttu-id="719fe-129">Líneas de comandos de compilación de ejemplo</span><span class="sxs-lookup"><span data-stu-id="719fe-129">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
