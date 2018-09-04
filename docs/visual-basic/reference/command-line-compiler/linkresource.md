---
title: -linkresource (Visual Basic)
ms.date: 03/10/2018
helpviewer_keywords:
- /linkresource compiler option [Visual Basic]
- -linkresource compiler option [Visual Basic]
- linkresource compiler option [Visual Basic]
- /linkres compiler option [Visual Basic]
- linkres compiler option [Visual Basic]
- -linkres compiler option [Visual Basic]
ms.assetid: cf4dcad8-17b7-404c-9184-29358aa05b15
ms.openlocfilehash: 4f4b3db768b5466f8912b66a0a4709d0f773c1f3
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/04/2018
ms.locfileid: "43554830"
---
# <a name="-linkresource-visual-basic"></a><span data-ttu-id="52ab7-102">-linkresource (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="52ab7-102">-linkresource (Visual Basic)</span></span>
<span data-ttu-id="52ab7-103">Crea un vínculo a un recurso administrado.</span><span class="sxs-lookup"><span data-stu-id="52ab7-103">Creates a link to a managed resource.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="52ab7-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="52ab7-104">Syntax</span></span>  
  
```  
-linkresource:filename[,identifier[,public|private]]  
' -or-  
-linkres:filename[,identifier[,public|private]]  
```  
  
## <a name="arguments"></a><span data-ttu-id="52ab7-105">Argumentos</span><span class="sxs-lookup"><span data-stu-id="52ab7-105">Arguments</span></span>  
 `filename`  
 <span data-ttu-id="52ab7-106">Requerido.</span><span class="sxs-lookup"><span data-stu-id="52ab7-106">Required.</span></span> <span data-ttu-id="52ab7-107">El archivo de recursos para vincular al ensamblado.</span><span class="sxs-lookup"><span data-stu-id="52ab7-107">The resource file to link to the assembly.</span></span> <span data-ttu-id="52ab7-108">Si el nombre de archivo contiene un espacio, escriba el nombre entre comillas ("").</span><span class="sxs-lookup"><span data-stu-id="52ab7-108">If the file name contains a space, enclose the name in quotation marks (" ").</span></span>  
  
 `identifier`  
 <span data-ttu-id="52ab7-109">Opcional.</span><span class="sxs-lookup"><span data-stu-id="52ab7-109">Optional.</span></span> <span data-ttu-id="52ab7-110">El nombre lógico del recurso.</span><span class="sxs-lookup"><span data-stu-id="52ab7-110">The logical name for the resource.</span></span> <span data-ttu-id="52ab7-111">El nombre que se usa para cargar el recurso.</span><span class="sxs-lookup"><span data-stu-id="52ab7-111">The name that is used to load the resource.</span></span> <span data-ttu-id="52ab7-112">El valor predeterminado es el nombre del archivo.</span><span class="sxs-lookup"><span data-stu-id="52ab7-112">The default is the name of the file.</span></span> <span data-ttu-id="52ab7-113">Si lo desea, puede especificar si el archivo es público o privado en el manifiesto del ensamblado, por ejemplo: `-linkres:filename.res,myname.res,public`.</span><span class="sxs-lookup"><span data-stu-id="52ab7-113">Optionally, you can specify whether the file is public or private in the assembly manifest, for example: `-linkres:filename.res,myname.res,public`.</span></span> <span data-ttu-id="52ab7-114">De forma predeterminada, `filename` es público en el ensamblado.</span><span class="sxs-lookup"><span data-stu-id="52ab7-114">By default, `filename` is public in the assembly.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="52ab7-115">Comentarios</span><span class="sxs-lookup"><span data-stu-id="52ab7-115">Remarks</span></span>  
 <span data-ttu-id="52ab7-116">El `-linkresource` opción no incrusta el archivo de recursos en el archivo de salida; utilice el `-resource` opción para hacer esto.</span><span class="sxs-lookup"><span data-stu-id="52ab7-116">The `-linkresource` option does not embed the resource file in the output file; use the `-resource` option to do this.</span></span>  
  
 <span data-ttu-id="52ab7-117">El `-linkresource` opción requiere uno de los `-target` opciones distintas de `-target:module`.</span><span class="sxs-lookup"><span data-stu-id="52ab7-117">The `-linkresource` option requires one of the `-target` options other than `-target:module`.</span></span>  
  
 <span data-ttu-id="52ab7-118">Si `filename` es un [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] archivo de recursos creado, por ejemplo, con el [Resgen.exe (Resource File Generator)](https://msdn.microsoft.com/library/8ef159de-b660-4bec-9213-c3fbc4d1c6f4) o en el entorno de desarrollo, puede obtenerse con los miembros de la <xref:System.Resources> espacio de nombres.</span><span class="sxs-lookup"><span data-stu-id="52ab7-118">If `filename` is a [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] resource file created, for example, by the [Resgen.exe (Resource File Generator)](https://msdn.microsoft.com/library/8ef159de-b660-4bec-9213-c3fbc4d1c6f4) or in the development environment, it can be accessed with members in the <xref:System.Resources> namespace.</span></span> <span data-ttu-id="52ab7-119">(Para obtener más información, vea <xref:System.Resources.ResourceManager>). Para obtener acceso a todos los demás recursos en tiempo de ejecución, utilice los métodos que comienzan por `GetManifestResource` en el <xref:System.Reflection.Assembly> clase.</span><span class="sxs-lookup"><span data-stu-id="52ab7-119">(For more information, see <xref:System.Resources.ResourceManager>.) To access all other resources at run time, use the methods that begin with `GetManifestResource` in the <xref:System.Reflection.Assembly> class.</span></span>  
  
 <span data-ttu-id="52ab7-120">El nombre de archivo puede ser cualquier formato de archivo.</span><span class="sxs-lookup"><span data-stu-id="52ab7-120">The file name can be any file format.</span></span> <span data-ttu-id="52ab7-121">Por ejemplo, se puede hacer que una DLL nativa forme parte de un ensamblado para que se pueda instalar en la caché global de ensamblados y sea accesible desde código administrado del ensamblado.</span><span class="sxs-lookup"><span data-stu-id="52ab7-121">For example, you may want to make a native DLL part of the assembly, so that it can be installed into the global assembly cache and accessed from managed code in the assembly.</span></span>  
  
 <span data-ttu-id="52ab7-122">La forma abreviada de `-linkresource` es `-linkres`.</span><span class="sxs-lookup"><span data-stu-id="52ab7-122">The short form of `-linkresource` is `-linkres`.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="52ab7-123">El `-linkresource` opción no está disponible en el entorno de desarrollo de Visual Studio; está disponible solo cuando se compila desde la línea de comandos.</span><span class="sxs-lookup"><span data-stu-id="52ab7-123">The `-linkresource` option is not available from the Visual Studio development environment; it is available only when you compile from the command line.</span></span>  
  
## <a name="example"></a><span data-ttu-id="52ab7-124">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="52ab7-124">Example</span></span>  
 <span data-ttu-id="52ab7-125">El siguiente código compila `in.vb` y vínculos al archivo de recursos `rf.resource`.</span><span class="sxs-lookup"><span data-stu-id="52ab7-125">The following code compiles `in.vb` and links to resource file `rf.resource`.</span></span>  
  
```console  
vbc -linkresource:rf.resource in.vb  
```  
  
## <a name="see-also"></a><span data-ttu-id="52ab7-126">Vea también</span><span class="sxs-lookup"><span data-stu-id="52ab7-126">See Also</span></span>  
 [<span data-ttu-id="52ab7-127">Compilador de línea de comandos de Visual Basic</span><span class="sxs-lookup"><span data-stu-id="52ab7-127">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)  
 [<span data-ttu-id="52ab7-128">-target (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="52ab7-128">-target (Visual Basic)</span></span>](../../../visual-basic/reference/command-line-compiler/target.md)  
 [<span data-ttu-id="52ab7-129">-resource (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="52ab7-129">-resource (Visual Basic)</span></span>](../../../visual-basic/reference/command-line-compiler/resource.md)  
 [<span data-ttu-id="52ab7-130">Líneas de comandos de compilación de ejemplo</span><span class="sxs-lookup"><span data-stu-id="52ab7-130">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
