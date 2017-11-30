---
title: /libpath
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- libpath compiler option [Visual Basic]
- /libpath compiler option [Visual Basic]
- -libpath compiler option [Visual Basic]
ms.assetid: 5f1c26c9-3455-4e89-bdf3-b12d6c2e655b
caps.latest.revision: "16"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 2be2c460fddf2e8ea4fe1239ec073f208c072d34
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="libpath"></a><span data-ttu-id="3bb97-102">/libpath</span><span class="sxs-lookup"><span data-stu-id="3bb97-102">/libpath</span></span>
<span data-ttu-id="3bb97-103">Especifica la ubicación de los ensamblados que se hace referencia.</span><span class="sxs-lookup"><span data-stu-id="3bb97-103">Specifies the location of referenced assemblies.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3bb97-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="3bb97-104">Syntax</span></span>  
  
```  
/libpath:dirList  
```  
  
## <a name="arguments"></a><span data-ttu-id="3bb97-105">Argumentos</span><span class="sxs-lookup"><span data-stu-id="3bb97-105">Arguments</span></span>  
  
|<span data-ttu-id="3bb97-106">Término</span><span class="sxs-lookup"><span data-stu-id="3bb97-106">Term</span></span>|<span data-ttu-id="3bb97-107">Definición</span><span class="sxs-lookup"><span data-stu-id="3bb97-107">Definition</span></span>|  
|---|---|  
|`dirList`|<span data-ttu-id="3bb97-108">Obligatorio.</span><span class="sxs-lookup"><span data-stu-id="3bb97-108">Required.</span></span> <span data-ttu-id="3bb97-109">Lista delimitada por punto y coma de directorios para que el compilador buscar en caso de un ensamblado de referencia no se encuentra en el directorio de trabajo actual (el directorio desde el que se invoca el compilador) o el directorio del sistema de common language runtime.</span><span class="sxs-lookup"><span data-stu-id="3bb97-109">Semicolon-delimited list of directories for the compiler to look in if a referenced assembly is not found in either the current working directory (the directory from which you are invoking the compiler) or the common language runtime's system directory.</span></span> <span data-ttu-id="3bb97-110">Si el nombre del directorio contiene un espacio, ponga el nombre entre comillas ("").</span><span class="sxs-lookup"><span data-stu-id="3bb97-110">If the directory name contains a space, enclose the name in quotation marks (" ").</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="3bb97-111">Comentarios</span><span class="sxs-lookup"><span data-stu-id="3bb97-111">Remarks</span></span>  
 <span data-ttu-id="3bb97-112">El `/libpath` opción especifica la ubicación de ensamblados al que hace referencia el [/reference](../../../visual-basic/reference/command-line-compiler/reference.md) opción.</span><span class="sxs-lookup"><span data-stu-id="3bb97-112">The `/libpath` option specifies the location of assemblies referenced by the [/reference](../../../visual-basic/reference/command-line-compiler/reference.md) option.</span></span>  
  
 <span data-ttu-id="3bb97-113">El compilador busca referencias a ensamblados que no presentan la ruta completa en el siguiente orden:</span><span class="sxs-lookup"><span data-stu-id="3bb97-113">The compiler searches for assembly references that are not fully qualified in the following order:</span></span>  
  
1.  <span data-ttu-id="3bb97-114">Directorio de trabajo actual.</span><span class="sxs-lookup"><span data-stu-id="3bb97-114">Current working directory.</span></span> <span data-ttu-id="3bb97-115">Es el directorio desde donde se invoca al compilador.</span><span class="sxs-lookup"><span data-stu-id="3bb97-115">This is the directory from which the compiler is invoked.</span></span>  
  
2.  <span data-ttu-id="3bb97-116">El directorio del sistema de Common Language Runtime.</span><span class="sxs-lookup"><span data-stu-id="3bb97-116">The common language runtime system directory.</span></span>  
  
3.  <span data-ttu-id="3bb97-117">Directorios especificados por `/libpath`.</span><span class="sxs-lookup"><span data-stu-id="3bb97-117">Directories specified by `/libpath`.</span></span>  
  
4.  <span data-ttu-id="3bb97-118">Directorios especificados por la variable de entorno LIB.</span><span class="sxs-lookup"><span data-stu-id="3bb97-118">Directories specified by the LIB environment variable.</span></span>  
  
 <span data-ttu-id="3bb97-119">El `/libpath` opción es aditiva; especificando que más de una vez se anexa a los valores anteriores.</span><span class="sxs-lookup"><span data-stu-id="3bb97-119">The `/libpath` option is additive; specifying it more than once appends to any prior values.</span></span>  
  
 <span data-ttu-id="3bb97-120">Use `/reference` para especificar una referencia de ensamblado.</span><span class="sxs-lookup"><span data-stu-id="3bb97-120">Use `/reference` to specify an assembly reference.</span></span>  
  
|<span data-ttu-id="3bb97-121">Para establecer /libpath en Visual Studio integra el entorno de desarrollo</span><span class="sxs-lookup"><span data-stu-id="3bb97-121">To set /libpath in the Visual Studio integrated development environment</span></span>|  
|---|  
|<span data-ttu-id="3bb97-122">1.  Seleccione un proyecto en el **Explorador de soluciones**.</span><span class="sxs-lookup"><span data-stu-id="3bb97-122">1.  Have a project selected in **Solution Explorer**.</span></span> <span data-ttu-id="3bb97-123">En el menú **Proyecto**, haga clic en **Propiedades**.</span><span class="sxs-lookup"><span data-stu-id="3bb97-123">On the **Project** menu, click **Properties**.</span></span> <span data-ttu-id="3bb97-124">Para obtener más información, consulte [Introducción al Diseñador de proyectos](http://msdn.microsoft.com/en-us/898dd854-c98d-430c-ba1b-a913ce3c73d7).</span><span class="sxs-lookup"><span data-stu-id="3bb97-124">For more information, see [Introduction to the Project Designer](http://msdn.microsoft.com/en-us/898dd854-c98d-430c-ba1b-a913ce3c73d7).</span></span><br /><span data-ttu-id="3bb97-125">2.  Haga clic en la pestaña **Referencias**.</span><span class="sxs-lookup"><span data-stu-id="3bb97-125">2.  Click the **References** tab.</span></span><br /><span data-ttu-id="3bb97-126">3.  Haga clic en el **hacen referencia a las rutas de acceso...**  botón.</span><span class="sxs-lookup"><span data-stu-id="3bb97-126">3.  Click the **Reference Paths...** button.</span></span><br /><span data-ttu-id="3bb97-127">4.  En el **las rutas de acceso de referencia** diálogo cuadro, escriba el nombre del directorio en el **carpeta:** cuadro.</span><span class="sxs-lookup"><span data-stu-id="3bb97-127">4.  In the **Reference Paths** dialog box, enter the directory name in the **Folder:** box.</span></span><br /><span data-ttu-id="3bb97-128">5.  Haga clic en **Agregar carpeta**.</span><span class="sxs-lookup"><span data-stu-id="3bb97-128">5.  Click **Add Folder**.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="3bb97-129">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="3bb97-129">Example</span></span>  
 <span data-ttu-id="3bb97-130">El siguiente código compila `T2.vb` para crear un archivo .exe.</span><span class="sxs-lookup"><span data-stu-id="3bb97-130">The following code compiles `T2.vb` to create an .exe file.</span></span> <span data-ttu-id="3bb97-131">El compilador busca en el directorio de trabajo, en el directorio raíz de la unidad C: y en el directorio de nuevos ensamblados de la unidad C: de referencias de ensamblado.</span><span class="sxs-lookup"><span data-stu-id="3bb97-131">The compiler looks in the working directory, in the root directory of the C: drive, and in the New Assemblies directory of the C: drive for assembly references.</span></span>  
  
```  
vbc /libpath:c:\;"c:\New Assemblies" /reference:t2.dll t2.vb  
```  
  
## <a name="see-also"></a><span data-ttu-id="3bb97-132">Vea también</span><span class="sxs-lookup"><span data-stu-id="3bb97-132">See Also</span></span>  
 [<span data-ttu-id="3bb97-133">Ensamblados y Caché global de ensamblados</span><span class="sxs-lookup"><span data-stu-id="3bb97-133">Assemblies and the Global Assembly Cache</span></span>](../../../visual-basic/programming-guide/concepts/assemblies-gac/index.md)  
 [<span data-ttu-id="3bb97-134">Compilador de línea de comandos de Visual Basic</span><span class="sxs-lookup"><span data-stu-id="3bb97-134">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)  
 [<span data-ttu-id="3bb97-135">Líneas de comandos de compilación de ejemplo</span><span class="sxs-lookup"><span data-stu-id="3bb97-135">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
