---
description: Más información sobre -linkresource (Visual Basic)
title: -linkresource
ms.date: 03/10/2018
helpviewer_keywords:
- /linkresource compiler option [Visual Basic]
- -linkresource compiler option [Visual Basic]
- linkresource compiler option [Visual Basic]
- /linkres compiler option [Visual Basic]
- linkres compiler option [Visual Basic]
- -linkres compiler option [Visual Basic]
ms.assetid: cf4dcad8-17b7-404c-9184-29358aa05b15
ms.openlocfilehash: 21fc47ecff44230bda0f445bc695706b5ae91eff
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/14/2021
ms.locfileid: "100463707"
---
# <a name="-linkresource-visual-basic"></a><span data-ttu-id="60e71-103">-linkresource (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="60e71-103">-linkresource (Visual Basic)</span></span>

<span data-ttu-id="60e71-104">Crea un vínculo a un recurso administrado.</span><span class="sxs-lookup"><span data-stu-id="60e71-104">Creates a link to a managed resource.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="60e71-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="60e71-105">Syntax</span></span>  
  
```console  
-linkresource:filename[,identifier[,public|private]]  
```

<span data-ttu-id="60e71-106">o</span><span class="sxs-lookup"><span data-stu-id="60e71-106">or</span></span>  

```console
-linkres:filename[,identifier[,public|private]]  
```  
  
## <a name="arguments"></a><span data-ttu-id="60e71-107">Argumentos</span><span class="sxs-lookup"><span data-stu-id="60e71-107">Arguments</span></span>  

 `filename`  
 <span data-ttu-id="60e71-108">Obligatorio.</span><span class="sxs-lookup"><span data-stu-id="60e71-108">Required.</span></span> <span data-ttu-id="60e71-109">El archivo de recursos que se va a vincular al ensamblado.</span><span class="sxs-lookup"><span data-stu-id="60e71-109">The resource file to link to the assembly.</span></span> <span data-ttu-id="60e71-110">Si el nombre de archivo contiene un espacio, escríbalo entre comillas (" ").</span><span class="sxs-lookup"><span data-stu-id="60e71-110">If the file name contains a space, enclose the name in quotation marks (" ").</span></span>  
  
 `identifier`  
 <span data-ttu-id="60e71-111">Opcional.</span><span class="sxs-lookup"><span data-stu-id="60e71-111">Optional.</span></span> <span data-ttu-id="60e71-112">El nombre lógico del recurso.</span><span class="sxs-lookup"><span data-stu-id="60e71-112">The logical name for the resource.</span></span> <span data-ttu-id="60e71-113">El nombre que se usa para cargar el recurso.</span><span class="sxs-lookup"><span data-stu-id="60e71-113">The name that is used to load the resource.</span></span> <span data-ttu-id="60e71-114">El valor predeterminado es el nombre del archivo.</span><span class="sxs-lookup"><span data-stu-id="60e71-114">The default is the name of the file.</span></span> <span data-ttu-id="60e71-115">Opcionalmente, puede especificar si el archivo es público o privado en el manifiesto del ensamblado, por ejemplo: `-linkres:filename.res,myname.res,public`.</span><span class="sxs-lookup"><span data-stu-id="60e71-115">Optionally, you can specify whether the file is public or private in the assembly manifest, for example: `-linkres:filename.res,myname.res,public`.</span></span> <span data-ttu-id="60e71-116">De forma predeterminada, `filename` es público en el ensamblado.</span><span class="sxs-lookup"><span data-stu-id="60e71-116">By default, `filename` is public in the assembly.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="60e71-117">Comentarios</span><span class="sxs-lookup"><span data-stu-id="60e71-117">Remarks</span></span>  

 <span data-ttu-id="60e71-118">La opción `-linkresource` no inserta el archivo de recursos en el archivo de salida; para hacerlo, use la opción `-resource`.</span><span class="sxs-lookup"><span data-stu-id="60e71-118">The `-linkresource` option does not embed the resource file in the output file; use the `-resource` option to do this.</span></span>  
  
 <span data-ttu-id="60e71-119">La opción `-linkresource` requiere una de las opciones de `-target` que no sea `-target:module`.</span><span class="sxs-lookup"><span data-stu-id="60e71-119">The `-linkresource` option requires one of the `-target` options other than `-target:module`.</span></span>  
  
 <span data-ttu-id="60e71-120">Si `filename` es un archivo de recursos de .NET Framework creado, por ejemplo, por Resgen.exe ([Generador de archivos de recursos](../../../framework/tools/resgen-exe-resource-file-generator.md)) o en el entorno de desarrollo, se puede acceder al mismo con miembros del espacio de nombres <xref:System.Resources>.</span><span class="sxs-lookup"><span data-stu-id="60e71-120">If `filename` is a .NET Framework resource file created, for example, by the [Resgen.exe (Resource File Generator)](../../../framework/tools/resgen-exe-resource-file-generator.md) or in the development environment, it can be accessed with members in the <xref:System.Resources> namespace.</span></span> <span data-ttu-id="60e71-121">(Para obtener más información, vea <xref:System.Resources.ResourceManager>). Para acceder a todos los demás recursos en tiempo de ejecución, use los métodos que empiezan por `GetManifestResource` de la clase <xref:System.Reflection.Assembly>.</span><span class="sxs-lookup"><span data-stu-id="60e71-121">(For more information, see <xref:System.Resources.ResourceManager>.) To access all other resources at run time, use the methods that begin with `GetManifestResource` in the <xref:System.Reflection.Assembly> class.</span></span>  
  
 <span data-ttu-id="60e71-122">El nombre de archivo puede tener cualquier formato de archivo.</span><span class="sxs-lookup"><span data-stu-id="60e71-122">The file name can be any file format.</span></span> <span data-ttu-id="60e71-123">Por ejemplo, se puede hacer que una DLL nativa forme parte de un ensamblado para que se pueda instalar en la caché global de ensamblados y sea accesible desde código administrado del ensamblado.</span><span class="sxs-lookup"><span data-stu-id="60e71-123">For example, you may want to make a native DLL part of the assembly, so that it can be installed into the global assembly cache and accessed from managed code in the assembly.</span></span>  
  
 <span data-ttu-id="60e71-124">La forma abreviada de `-linkresource` es `-linkres`.</span><span class="sxs-lookup"><span data-stu-id="60e71-124">The short form of `-linkresource` is `-linkres`.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="60e71-125">La opción `-linkresource` no está disponible en el entorno de desarrollo de Visual Studio; solo está disponible cuando se compila desde la línea de comandos.</span><span class="sxs-lookup"><span data-stu-id="60e71-125">The `-linkresource` option is not available from the Visual Studio development environment; it is available only when you compile from the command line.</span></span>  
  
## <a name="example"></a><span data-ttu-id="60e71-126">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="60e71-126">Example</span></span>  

 <span data-ttu-id="60e71-127">En el código siguiente se compila `in.vb` y se vincula al archivo de recursos `rf.resource`.</span><span class="sxs-lookup"><span data-stu-id="60e71-127">The following code compiles `in.vb` and links to resource file `rf.resource`.</span></span>  
  
```console  
vbc -linkresource:rf.resource in.vb  
```  
  
## <a name="see-also"></a><span data-ttu-id="60e71-128">Vea también</span><span class="sxs-lookup"><span data-stu-id="60e71-128">See also</span></span>

- [<span data-ttu-id="60e71-129">Compilador de línea de comandos de Visual Basic</span><span class="sxs-lookup"><span data-stu-id="60e71-129">Visual Basic Command-Line Compiler</span></span>](index.md)
- [<span data-ttu-id="60e71-130">-target (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="60e71-130">-target (Visual Basic)</span></span>](target.md)
- [<span data-ttu-id="60e71-131">-resource (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="60e71-131">-resource (Visual Basic)</span></span>](resource.md)
- [<span data-ttu-id="60e71-132">Líneas de comandos de compilación de ejemplo</span><span class="sxs-lookup"><span data-stu-id="60e71-132">Sample Compilation Command Lines</span></span>](sample-compilation-command-lines.md)
