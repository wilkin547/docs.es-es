---
title: -libpath
ms.date: 03/10/2018
helpviewer_keywords:
- libpath compiler option [Visual Basic]
- /libpath compiler option [Visual Basic]
- -libpath compiler option [Visual Basic]
ms.assetid: 5f1c26c9-3455-4e89-bdf3-b12d6c2e655b
ms.openlocfilehash: ca5a6836a7cfbc6a36c83044caff23a7d590dfc0
ms.sourcegitcommit: 8f95d3a37e591963ebbb9af6e90686fd5f3b8707
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/23/2019
ms.locfileid: "56745990"
---
# <a name="-libpath"></a><span data-ttu-id="142bc-102">-libpath</span><span class="sxs-lookup"><span data-stu-id="142bc-102">-libpath</span></span>
<span data-ttu-id="142bc-103">Especifica la ubicación de los ensamblados que se hace referencia.</span><span class="sxs-lookup"><span data-stu-id="142bc-103">Specifies the location of referenced assemblies.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="142bc-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="142bc-104">Syntax</span></span>  
  
```  
-libpath:dirList  
```  
  
## <a name="arguments"></a><span data-ttu-id="142bc-105">Argumentos</span><span class="sxs-lookup"><span data-stu-id="142bc-105">Arguments</span></span>  
  
|<span data-ttu-id="142bc-106">Término</span><span class="sxs-lookup"><span data-stu-id="142bc-106">Term</span></span>|<span data-ttu-id="142bc-107">Definición</span><span class="sxs-lookup"><span data-stu-id="142bc-107">Definition</span></span>|  
|---|---|  
|`dirList`|<span data-ttu-id="142bc-108">Obligatorio.</span><span class="sxs-lookup"><span data-stu-id="142bc-108">Required.</span></span> <span data-ttu-id="142bc-109">Lista delimitada por punto y coma de directorios para el compilador buscar en caso de un ensamblado de referencia no se encuentra en el directorio de trabajo actual (el directorio desde el que se invoca el compilador) o el directorio del sistema de common language runtime.</span><span class="sxs-lookup"><span data-stu-id="142bc-109">Semicolon-delimited list of directories for the compiler to look in if a referenced assembly is not found in either the current working directory (the directory from which you are invoking the compiler) or the common language runtime's system directory.</span></span> <span data-ttu-id="142bc-110">Si el nombre del directorio contiene un espacio, escriba el nombre entre comillas ("").</span><span class="sxs-lookup"><span data-stu-id="142bc-110">If the directory name contains a space, enclose the name in quotation marks (" ").</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="142bc-111">Comentarios</span><span class="sxs-lookup"><span data-stu-id="142bc-111">Remarks</span></span>  
 <span data-ttu-id="142bc-112">El `-libpath` opción especifica la ubicación de los ensamblados referenciados por la [-referencia](../../../visual-basic/reference/command-line-compiler/reference.md) opción.</span><span class="sxs-lookup"><span data-stu-id="142bc-112">The `-libpath` option specifies the location of assemblies referenced by the [-reference](../../../visual-basic/reference/command-line-compiler/reference.md) option.</span></span>  
  
 <span data-ttu-id="142bc-113">El compilador busca referencias a ensamblados que no presentan la ruta completa en el siguiente orden:</span><span class="sxs-lookup"><span data-stu-id="142bc-113">The compiler searches for assembly references that are not fully qualified in the following order:</span></span>  
  
1.  <span data-ttu-id="142bc-114">Directorio de trabajo actual.</span><span class="sxs-lookup"><span data-stu-id="142bc-114">Current working directory.</span></span> <span data-ttu-id="142bc-115">Es el directorio desde donde se invoca al compilador.</span><span class="sxs-lookup"><span data-stu-id="142bc-115">This is the directory from which the compiler is invoked.</span></span>  
  
2.  <span data-ttu-id="142bc-116">El directorio del sistema de Common Language Runtime.</span><span class="sxs-lookup"><span data-stu-id="142bc-116">The common language runtime system directory.</span></span>  
  
3.  <span data-ttu-id="142bc-117">Directorios especificados por `/libpath`.</span><span class="sxs-lookup"><span data-stu-id="142bc-117">Directories specified by `/libpath`.</span></span>  
  
4.  <span data-ttu-id="142bc-118">Directorios especificados por la variable de entorno LIB.</span><span class="sxs-lookup"><span data-stu-id="142bc-118">Directories specified by the LIB environment variable.</span></span>  
  
 <span data-ttu-id="142bc-119">El `-libpath` opción es sumatoria; si se especifica más de una vez se anexa a valores ya existentes.</span><span class="sxs-lookup"><span data-stu-id="142bc-119">The `-libpath` option is additive; specifying it more than once appends to any prior values.</span></span>  
  
 <span data-ttu-id="142bc-120">Use `-reference` para especificar una referencia de ensamblado.</span><span class="sxs-lookup"><span data-stu-id="142bc-120">Use `-reference` to specify an assembly reference.</span></span>  
  
|<span data-ttu-id="142bc-121">Para establecer /libpath en Visual Studio de entorno de desarrollo integrado</span><span class="sxs-lookup"><span data-stu-id="142bc-121">To set /libpath in the Visual Studio integrated development environment</span></span>|  
|---|  
|<span data-ttu-id="142bc-122">1.  Seleccione un proyecto en el **Explorador de soluciones**.</span><span class="sxs-lookup"><span data-stu-id="142bc-122">1.  Have a project selected in **Solution Explorer**.</span></span> <span data-ttu-id="142bc-123">En el menú **Proyecto**, haga clic en **Propiedades**.</span><span class="sxs-lookup"><span data-stu-id="142bc-123">On the **Project** menu, click **Properties**.</span></span> <br /><span data-ttu-id="142bc-124">2.  Haga clic en la pestaña **Referencias**.</span><span class="sxs-lookup"><span data-stu-id="142bc-124">2.  Click the **References** tab.</span></span><br /><span data-ttu-id="142bc-125">3.  Haga clic en el **hacen referencia a las rutas de acceso...**  botón.</span><span class="sxs-lookup"><span data-stu-id="142bc-125">3.  Click the **Reference Paths...** button.</span></span><br /><span data-ttu-id="142bc-126">4.  En el **las rutas de acceso de referencia** diálogo cuadro, escriba el nombre del directorio en el **carpeta:** cuadro.</span><span class="sxs-lookup"><span data-stu-id="142bc-126">4.  In the **Reference Paths** dialog box, enter the directory name in the **Folder:** box.</span></span><br /><span data-ttu-id="142bc-127">5.  Haga clic en **Agregar carpeta**.</span><span class="sxs-lookup"><span data-stu-id="142bc-127">5.  Click **Add Folder**.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="142bc-128">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="142bc-128">Example</span></span>  
 <span data-ttu-id="142bc-129">El siguiente código compila `T2.vb` para crear un archivo .exe.</span><span class="sxs-lookup"><span data-stu-id="142bc-129">The following code compiles `T2.vb` to create an .exe file.</span></span> <span data-ttu-id="142bc-130">El compilador busca en el directorio de trabajo, en el directorio raíz de la unidad C: y en el directorio nuevos ensamblados de la unidad C: de referencias de ensamblado.</span><span class="sxs-lookup"><span data-stu-id="142bc-130">The compiler looks in the working directory, in the root directory of the C: drive, and in the New Assemblies directory of the C: drive for assembly references.</span></span>  
  
```console  
vbc -libpath:c:\;"c:\New Assemblies" -reference:t2.dll t2.vb  
```  
  
## <a name="see-also"></a><span data-ttu-id="142bc-131">Vea también</span><span class="sxs-lookup"><span data-stu-id="142bc-131">See also</span></span>
- [<span data-ttu-id="142bc-132">Ensamblados de .NET</span><span class="sxs-lookup"><span data-stu-id="142bc-132">Assemblies in .NET</span></span>](../../../standard/assembly/index.md)
- [<span data-ttu-id="142bc-133">Compilador de línea de comandos de Visual Basic</span><span class="sxs-lookup"><span data-stu-id="142bc-133">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)
- [<span data-ttu-id="142bc-134">Líneas de comandos de compilación de ejemplo</span><span class="sxs-lookup"><span data-stu-id="142bc-134">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
