---
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
ms.openlocfilehash: 43ebb61efa26ed11af573e2c4e73a6fd71ac0902
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/04/2020
ms.locfileid: "84403205"
---
# <a name="-linkresource-visual-basic"></a><span data-ttu-id="ebbbe-102">-linkresource (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="ebbbe-102">-linkresource (Visual Basic)</span></span>
<span data-ttu-id="ebbbe-103">Crea un vínculo a un recurso administrado.</span><span class="sxs-lookup"><span data-stu-id="ebbbe-103">Creates a link to a managed resource.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ebbbe-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="ebbbe-104">Syntax</span></span>  
  
```console  
-linkresource:filename[,identifier[,public|private]]  
```

<span data-ttu-id="ebbbe-105">o</span><span class="sxs-lookup"><span data-stu-id="ebbbe-105">or</span></span>  

```console
-linkres:filename[,identifier[,public|private]]  
```  
  
## <a name="arguments"></a><span data-ttu-id="ebbbe-106">Argumentos</span><span class="sxs-lookup"><span data-stu-id="ebbbe-106">Arguments</span></span>  
 `filename`  
 <span data-ttu-id="ebbbe-107">Obligatorio.</span><span class="sxs-lookup"><span data-stu-id="ebbbe-107">Required.</span></span> <span data-ttu-id="ebbbe-108">El archivo de recursos que se va a vincular al ensamblado.</span><span class="sxs-lookup"><span data-stu-id="ebbbe-108">The resource file to link to the assembly.</span></span> <span data-ttu-id="ebbbe-109">Si el nombre de archivo contiene un espacio, escríbalo entre comillas (" ").</span><span class="sxs-lookup"><span data-stu-id="ebbbe-109">If the file name contains a space, enclose the name in quotation marks (" ").</span></span>  
  
 `identifier`  
 <span data-ttu-id="ebbbe-110">Opcional.</span><span class="sxs-lookup"><span data-stu-id="ebbbe-110">Optional.</span></span> <span data-ttu-id="ebbbe-111">El nombre lógico del recurso.</span><span class="sxs-lookup"><span data-stu-id="ebbbe-111">The logical name for the resource.</span></span> <span data-ttu-id="ebbbe-112">El nombre que se usa para cargar el recurso.</span><span class="sxs-lookup"><span data-stu-id="ebbbe-112">The name that is used to load the resource.</span></span> <span data-ttu-id="ebbbe-113">El valor predeterminado es el nombre del archivo.</span><span class="sxs-lookup"><span data-stu-id="ebbbe-113">The default is the name of the file.</span></span> <span data-ttu-id="ebbbe-114">Opcionalmente, puede especificar si el archivo es público o privado en el manifiesto del ensamblado, por ejemplo: `-linkres:filename.res,myname.res,public`.</span><span class="sxs-lookup"><span data-stu-id="ebbbe-114">Optionally, you can specify whether the file is public or private in the assembly manifest, for example: `-linkres:filename.res,myname.res,public`.</span></span> <span data-ttu-id="ebbbe-115">De forma predeterminada, `filename` es público en el ensamblado.</span><span class="sxs-lookup"><span data-stu-id="ebbbe-115">By default, `filename` is public in the assembly.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ebbbe-116">Comentarios</span><span class="sxs-lookup"><span data-stu-id="ebbbe-116">Remarks</span></span>  
 <span data-ttu-id="ebbbe-117">La opción `-linkresource` no inserta el archivo de recursos en el archivo de salida; para hacerlo, use la opción `-resource`.</span><span class="sxs-lookup"><span data-stu-id="ebbbe-117">The `-linkresource` option does not embed the resource file in the output file; use the `-resource` option to do this.</span></span>  
  
 <span data-ttu-id="ebbbe-118">La opción `-linkresource` requiere una de las opciones de `-target` que no sea `-target:module`.</span><span class="sxs-lookup"><span data-stu-id="ebbbe-118">The `-linkresource` option requires one of the `-target` options other than `-target:module`.</span></span>  
  
 <span data-ttu-id="ebbbe-119">Si `filename` es un archivo de recursos de .NET Framework creado, por ejemplo, por Resgen.exe ([Generador de archivos de recursos](../../../framework/tools/resgen-exe-resource-file-generator.md)) o en el entorno de desarrollo, se puede acceder al mismo con miembros del espacio de nombres <xref:System.Resources>.</span><span class="sxs-lookup"><span data-stu-id="ebbbe-119">If `filename` is a .NET Framework resource file created, for example, by the [Resgen.exe (Resource File Generator)](../../../framework/tools/resgen-exe-resource-file-generator.md) or in the development environment, it can be accessed with members in the <xref:System.Resources> namespace.</span></span> <span data-ttu-id="ebbbe-120">(Para obtener más información, vea <xref:System.Resources.ResourceManager>). Para acceder a todos los demás recursos en tiempo de ejecución, use los métodos que empiezan por `GetManifestResource` de la clase <xref:System.Reflection.Assembly>.</span><span class="sxs-lookup"><span data-stu-id="ebbbe-120">(For more information, see <xref:System.Resources.ResourceManager>.) To access all other resources at run time, use the methods that begin with `GetManifestResource` in the <xref:System.Reflection.Assembly> class.</span></span>  
  
 <span data-ttu-id="ebbbe-121">El nombre de archivo puede tener cualquier formato de archivo.</span><span class="sxs-lookup"><span data-stu-id="ebbbe-121">The file name can be any file format.</span></span> <span data-ttu-id="ebbbe-122">Por ejemplo, se puede hacer que una DLL nativa forme parte de un ensamblado para que se pueda instalar en la caché global de ensamblados y sea accesible desde código administrado del ensamblado.</span><span class="sxs-lookup"><span data-stu-id="ebbbe-122">For example, you may want to make a native DLL part of the assembly, so that it can be installed into the global assembly cache and accessed from managed code in the assembly.</span></span>  
  
 <span data-ttu-id="ebbbe-123">La forma abreviada de `-linkresource` es `-linkres`.</span><span class="sxs-lookup"><span data-stu-id="ebbbe-123">The short form of `-linkresource` is `-linkres`.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="ebbbe-124">La opción `-linkresource` no está disponible en el entorno de desarrollo de Visual Studio; solo está disponible cuando se compila desde la línea de comandos.</span><span class="sxs-lookup"><span data-stu-id="ebbbe-124">The `-linkresource` option is not available from the Visual Studio development environment; it is available only when you compile from the command line.</span></span>  
  
## <a name="example"></a><span data-ttu-id="ebbbe-125">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="ebbbe-125">Example</span></span>  
 <span data-ttu-id="ebbbe-126">En el código siguiente se compila `in.vb` y se vincula al archivo de recursos `rf.resource`.</span><span class="sxs-lookup"><span data-stu-id="ebbbe-126">The following code compiles `in.vb` and links to resource file `rf.resource`.</span></span>  
  
```console  
vbc -linkresource:rf.resource in.vb  
```  
  
## <a name="see-also"></a><span data-ttu-id="ebbbe-127">Vea también</span><span class="sxs-lookup"><span data-stu-id="ebbbe-127">See also</span></span>

- [<span data-ttu-id="ebbbe-128">Compilador de línea de comandos de Visual Basic</span><span class="sxs-lookup"><span data-stu-id="ebbbe-128">Visual Basic Command-Line Compiler</span></span>](index.md)
- [<span data-ttu-id="ebbbe-129">-target (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="ebbbe-129">-target (Visual Basic)</span></span>](target.md)
- [<span data-ttu-id="ebbbe-130">-resource (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="ebbbe-130">-resource (Visual Basic)</span></span>](resource.md)
- [<span data-ttu-id="ebbbe-131">Líneas de comandos de compilación de ejemplo</span><span class="sxs-lookup"><span data-stu-id="ebbbe-131">Sample Compilation Command Lines</span></span>](sample-compilation-command-lines.md)
