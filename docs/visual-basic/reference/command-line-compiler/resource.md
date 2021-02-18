---
description: Más información sobre -resource (Visual Basic)
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
ms.openlocfilehash: 830d89ab4f4063aa12d12a5206b76e49c5355708
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/14/2021
ms.locfileid: "100474114"
---
# <a name="-resource-visual-basic"></a><span data-ttu-id="12a76-103">-resource (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="12a76-103">-resource (Visual Basic)</span></span>

<span data-ttu-id="12a76-104">Inserta un recurso administrado en un ensamblado.</span><span class="sxs-lookup"><span data-stu-id="12a76-104">Embeds a managed resource in an assembly.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="12a76-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="12a76-105">Syntax</span></span>  
  
```console  
-resource:filename[,identifier[,public|private]]  
```

<span data-ttu-id="12a76-106">o</span><span class="sxs-lookup"><span data-stu-id="12a76-106">or</span></span>  

```console
-res:filename[,identifier[,public|private]]  
```  
  
## <a name="arguments"></a><span data-ttu-id="12a76-107">Argumentos</span><span class="sxs-lookup"><span data-stu-id="12a76-107">Arguments</span></span>  
  
|<span data-ttu-id="12a76-108">Término</span><span class="sxs-lookup"><span data-stu-id="12a76-108">Term</span></span>|<span data-ttu-id="12a76-109">Definición</span><span class="sxs-lookup"><span data-stu-id="12a76-109">Definition</span></span>|  
|---|---|  
|`filename`|<span data-ttu-id="12a76-110">Obligatorio.</span><span class="sxs-lookup"><span data-stu-id="12a76-110">Required.</span></span> <span data-ttu-id="12a76-111">Nombre del archivo de recursos que se va a insertar en el archivo de salida.</span><span class="sxs-lookup"><span data-stu-id="12a76-111">The name of the resource file to embed in the output file.</span></span> <span data-ttu-id="12a76-112">De forma predeterminada, `filename` es público en el ensamblado.</span><span class="sxs-lookup"><span data-stu-id="12a76-112">By default, `filename` is public in the assembly.</span></span> <span data-ttu-id="12a76-113">Si el nombre de archivo contiene un espacio, escríbalo entre comillas (" ").</span><span class="sxs-lookup"><span data-stu-id="12a76-113">Enclose the file name in quotation marks (" ") if it contains a space.</span></span>|  
|`identifier`|<span data-ttu-id="12a76-114">Opcional.</span><span class="sxs-lookup"><span data-stu-id="12a76-114">Optional.</span></span> <span data-ttu-id="12a76-115">Nombre lógico del recurso; nombre que se usa para cargarlo.</span><span class="sxs-lookup"><span data-stu-id="12a76-115">The logical name for the resource; the name used to load it.</span></span> <span data-ttu-id="12a76-116">El valor predeterminado es el nombre del archivo.</span><span class="sxs-lookup"><span data-stu-id="12a76-116">The default is the name of the file.</span></span> <span data-ttu-id="12a76-117">Opcionalmente, puede especificar si el recurso es público o privado en el manifiesto del ensamblado, como en el siguiente ejemplo: `-res:filename.res, myname.res, public`.</span><span class="sxs-lookup"><span data-stu-id="12a76-117">Optionally, you can specify whether the resource is public or private in the assembly manifest, as with the following: `-res:filename.res, myname.res, public`</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="12a76-118">Comentarios</span><span class="sxs-lookup"><span data-stu-id="12a76-118">Remarks</span></span>  

 <span data-ttu-id="12a76-119">Use `-linkresource` para vincular un recurso a un ensamblado sin colocar el archivo de recursos en el archivo de salida.</span><span class="sxs-lookup"><span data-stu-id="12a76-119">Use `-linkresource` to link a resource to an assembly without placing the resource file in the output file.</span></span>  
  
 <span data-ttu-id="12a76-120">Si `filename` es un archivo de recursos de .NET Framework creado, por ejemplo, por Resgen.exe ([Generador de archivos de recursos](../../../framework/tools/resgen-exe-resource-file-generator.md)) o en el entorno de desarrollo, se puede acceder a este con miembros del espacio de nombres <xref:System.Resources> (vea <xref:System.Resources.ResourceManager> para obtener más información).</span><span class="sxs-lookup"><span data-stu-id="12a76-120">If `filename` is a .NET Framework resource file created, for example, by the [Resgen.exe (Resource File Generator)](../../../framework/tools/resgen-exe-resource-file-generator.md) or in the development environment, it can be accessed with members in the <xref:System.Resources> namespace (see <xref:System.Resources.ResourceManager> for more information).</span></span> <span data-ttu-id="12a76-121">Para acceder a todos los demás recursos en tiempo de ejecución, use uno de los siguientes métodos: <xref:System.Reflection.Assembly.GetManifestResourceInfo%2A>, <xref:System.Reflection.Assembly.GetManifestResourceNames%2A> o <xref:System.Reflection.Assembly.GetManifestResourceStream%2A>.</span><span class="sxs-lookup"><span data-stu-id="12a76-121">To access all other resources at run time, use one of the following methods: <xref:System.Reflection.Assembly.GetManifestResourceInfo%2A>, <xref:System.Reflection.Assembly.GetManifestResourceNames%2A>, or <xref:System.Reflection.Assembly.GetManifestResourceStream%2A>.</span></span>  
  
 <span data-ttu-id="12a76-122">La forma abreviada de `-resource` es `-res`.</span><span class="sxs-lookup"><span data-stu-id="12a76-122">The short form of `-resource` is `-res`.</span></span>  
  
 <span data-ttu-id="12a76-123">Para obtener información sobre cómo definir `-resource` en el IDE de Visual Studio, vea [Administración de los recursos de aplicación (.NET)](/visualstudio/ide/managing-application-resources-dotnet).</span><span class="sxs-lookup"><span data-stu-id="12a76-123">For information about how to set `-resource` in the Visual Studio IDE, see [Managing Application Resources (.NET)](/visualstudio/ide/managing-application-resources-dotnet).</span></span>  
  
## <a name="example"></a><span data-ttu-id="12a76-124">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="12a76-124">Example</span></span>  

 <span data-ttu-id="12a76-125">El siguiente código compila `In.vb` y adjunta un archivo de recursos `Rf.resource`.</span><span class="sxs-lookup"><span data-stu-id="12a76-125">The following code compiles `In.vb` and attaches resource file `Rf.resource`.</span></span>  
  
```console
vbc -res:rf.resource in.vb  
```  
  
## <a name="see-also"></a><span data-ttu-id="12a76-126">Vea también</span><span class="sxs-lookup"><span data-stu-id="12a76-126">See also</span></span>

- [<span data-ttu-id="12a76-127">Compilador de línea de comandos de Visual Basic</span><span class="sxs-lookup"><span data-stu-id="12a76-127">Visual Basic Command-Line Compiler</span></span>](index.md)
- [<span data-ttu-id="12a76-128">-win32resource</span><span class="sxs-lookup"><span data-stu-id="12a76-128">-win32resource</span></span>](win32resource.md)
- [<span data-ttu-id="12a76-129">-linkresource (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="12a76-129">-linkresource (Visual Basic)</span></span>](linkresource.md)
- [<span data-ttu-id="12a76-130">-target (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="12a76-130">-target (Visual Basic)</span></span>](target.md)
- [<span data-ttu-id="12a76-131">Líneas de comandos de compilación de ejemplo</span><span class="sxs-lookup"><span data-stu-id="12a76-131">Sample Compilation Command Lines</span></span>](sample-compilation-command-lines.md)
