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
ms.openlocfilehash: cf9fe8dae0d35df694891633a6e3cf950bfb7376
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/04/2020
ms.locfileid: "84363622"
---
# <a name="-resource-visual-basic"></a><span data-ttu-id="d5bd4-102">-resource (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="d5bd4-102">-resource (Visual Basic)</span></span>
<span data-ttu-id="d5bd4-103">Inserta un recurso administrado en un ensamblado.</span><span class="sxs-lookup"><span data-stu-id="d5bd4-103">Embeds a managed resource in an assembly.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d5bd4-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="d5bd4-104">Syntax</span></span>  
  
```console  
-resource:filename[,identifier[,public|private]]  
```

<span data-ttu-id="d5bd4-105">o</span><span class="sxs-lookup"><span data-stu-id="d5bd4-105">or</span></span>  

```console
-res:filename[,identifier[,public|private]]  
```  
  
## <a name="arguments"></a><span data-ttu-id="d5bd4-106">Argumentos</span><span class="sxs-lookup"><span data-stu-id="d5bd4-106">Arguments</span></span>  
  
|<span data-ttu-id="d5bd4-107">Término</span><span class="sxs-lookup"><span data-stu-id="d5bd4-107">Term</span></span>|<span data-ttu-id="d5bd4-108">Definición</span><span class="sxs-lookup"><span data-stu-id="d5bd4-108">Definition</span></span>|  
|---|---|  
|`filename`|<span data-ttu-id="d5bd4-109">Obligatorio.</span><span class="sxs-lookup"><span data-stu-id="d5bd4-109">Required.</span></span> <span data-ttu-id="d5bd4-110">Nombre del archivo de recursos que se va a insertar en el archivo de salida.</span><span class="sxs-lookup"><span data-stu-id="d5bd4-110">The name of the resource file to embed in the output file.</span></span> <span data-ttu-id="d5bd4-111">De forma predeterminada, `filename` es público en el ensamblado.</span><span class="sxs-lookup"><span data-stu-id="d5bd4-111">By default, `filename` is public in the assembly.</span></span> <span data-ttu-id="d5bd4-112">Si el nombre de archivo contiene un espacio, escríbalo entre comillas (" ").</span><span class="sxs-lookup"><span data-stu-id="d5bd4-112">Enclose the file name in quotation marks (" ") if it contains a space.</span></span>|  
|`identifier`|<span data-ttu-id="d5bd4-113">Opcional.</span><span class="sxs-lookup"><span data-stu-id="d5bd4-113">Optional.</span></span> <span data-ttu-id="d5bd4-114">Nombre lógico del recurso; nombre que se usa para cargarlo.</span><span class="sxs-lookup"><span data-stu-id="d5bd4-114">The logical name for the resource; the name used to load it.</span></span> <span data-ttu-id="d5bd4-115">El valor predeterminado es el nombre del archivo.</span><span class="sxs-lookup"><span data-stu-id="d5bd4-115">The default is the name of the file.</span></span> <span data-ttu-id="d5bd4-116">Opcionalmente, puede especificar si el recurso es público o privado en el manifiesto del ensamblado, como en el siguiente ejemplo: `-res:filename.res, myname.res, public`.</span><span class="sxs-lookup"><span data-stu-id="d5bd4-116">Optionally, you can specify whether the resource is public or private in the assembly manifest, as with the following: `-res:filename.res, myname.res, public`</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d5bd4-117">Comentarios</span><span class="sxs-lookup"><span data-stu-id="d5bd4-117">Remarks</span></span>  
 <span data-ttu-id="d5bd4-118">Use `-linkresource` para vincular un recurso a un ensamblado sin colocar el archivo de recursos en el archivo de salida.</span><span class="sxs-lookup"><span data-stu-id="d5bd4-118">Use `-linkresource` to link a resource to an assembly without placing the resource file in the output file.</span></span>  
  
 <span data-ttu-id="d5bd4-119">Si `filename` es un archivo de recursos de .NET Framework creado, por ejemplo, por Resgen.exe ([Generador de archivos de recursos](../../../framework/tools/resgen-exe-resource-file-generator.md)) o en el entorno de desarrollo, se puede acceder a este con miembros del espacio de nombres <xref:System.Resources> (vea <xref:System.Resources.ResourceManager> para obtener más información).</span><span class="sxs-lookup"><span data-stu-id="d5bd4-119">If `filename` is a .NET Framework resource file created, for example, by the [Resgen.exe (Resource File Generator)](../../../framework/tools/resgen-exe-resource-file-generator.md) or in the development environment, it can be accessed with members in the <xref:System.Resources> namespace (see <xref:System.Resources.ResourceManager> for more information).</span></span> <span data-ttu-id="d5bd4-120">Para acceder a todos los demás recursos en tiempo de ejecución, use uno de los siguientes métodos: <xref:System.Reflection.Assembly.GetManifestResourceInfo%2A>, <xref:System.Reflection.Assembly.GetManifestResourceNames%2A> o <xref:System.Reflection.Assembly.GetManifestResourceStream%2A>.</span><span class="sxs-lookup"><span data-stu-id="d5bd4-120">To access all other resources at run time, use one of the following methods: <xref:System.Reflection.Assembly.GetManifestResourceInfo%2A>, <xref:System.Reflection.Assembly.GetManifestResourceNames%2A>, or <xref:System.Reflection.Assembly.GetManifestResourceStream%2A>.</span></span>  
  
 <span data-ttu-id="d5bd4-121">La forma abreviada de `-resource` es `-res`.</span><span class="sxs-lookup"><span data-stu-id="d5bd4-121">The short form of `-resource` is `-res`.</span></span>  
  
 <span data-ttu-id="d5bd4-122">Para obtener información sobre cómo definir `-resource` en el IDE de Visual Studio, vea [Administración de los recursos de aplicación (.NET)](/visualstudio/ide/managing-application-resources-dotnet).</span><span class="sxs-lookup"><span data-stu-id="d5bd4-122">For information about how to set `-resource` in the Visual Studio IDE, see [Managing Application Resources (.NET)](/visualstudio/ide/managing-application-resources-dotnet).</span></span>  
  
## <a name="example"></a><span data-ttu-id="d5bd4-123">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="d5bd4-123">Example</span></span>  
 <span data-ttu-id="d5bd4-124">El siguiente código compila `In.vb` y adjunta un archivo de recursos `Rf.resource`.</span><span class="sxs-lookup"><span data-stu-id="d5bd4-124">The following code compiles `In.vb` and attaches resource file `Rf.resource`.</span></span>  
  
```console
vbc -res:rf.resource in.vb  
```  
  
## <a name="see-also"></a><span data-ttu-id="d5bd4-125">Vea también</span><span class="sxs-lookup"><span data-stu-id="d5bd4-125">See also</span></span>

- [<span data-ttu-id="d5bd4-126">Compilador de línea de comandos de Visual Basic</span><span class="sxs-lookup"><span data-stu-id="d5bd4-126">Visual Basic Command-Line Compiler</span></span>](index.md)
- [<span data-ttu-id="d5bd4-127">-win32resource</span><span class="sxs-lookup"><span data-stu-id="d5bd4-127">-win32resource</span></span>](win32resource.md)
- [<span data-ttu-id="d5bd4-128">-linkresource (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="d5bd4-128">-linkresource (Visual Basic)</span></span>](linkresource.md)
- [<span data-ttu-id="d5bd4-129">-target (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="d5bd4-129">-target (Visual Basic)</span></span>](target.md)
- [<span data-ttu-id="d5bd4-130">Líneas de comandos de compilación de ejemplo</span><span class="sxs-lookup"><span data-stu-id="d5bd4-130">Sample Compilation Command Lines</span></span>](sample-compilation-command-lines.md)
