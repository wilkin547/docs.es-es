---
title: -libpath
ms.date: 03/10/2018
helpviewer_keywords:
- libpath compiler option [Visual Basic]
- /libpath compiler option [Visual Basic]
- -libpath compiler option [Visual Basic]
ms.assetid: 5f1c26c9-3455-4e89-bdf3-b12d6c2e655b
ms.openlocfilehash: 9a5822a097828f818da020735c3822e86eb3236b
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/07/2020
ms.locfileid: "75716634"
---
# <a name="-libpath"></a><span data-ttu-id="e361d-102">-libpath</span><span class="sxs-lookup"><span data-stu-id="e361d-102">-libpath</span></span>
<span data-ttu-id="e361d-103">Especifica la ubicación de los ensamblados a los que se hace referencia.</span><span class="sxs-lookup"><span data-stu-id="e361d-103">Specifies the location of referenced assemblies.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e361d-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="e361d-104">Syntax</span></span>  
  
```console  
-libpath:dirList  
```  
  
## <a name="arguments"></a><span data-ttu-id="e361d-105">Argumentos</span><span class="sxs-lookup"><span data-stu-id="e361d-105">Arguments</span></span>  
  
|<span data-ttu-id="e361d-106">Término</span><span class="sxs-lookup"><span data-stu-id="e361d-106">Term</span></span>|<span data-ttu-id="e361d-107">Definición</span><span class="sxs-lookup"><span data-stu-id="e361d-107">Definition</span></span>|  
|---|---|  
|`dirList`|<span data-ttu-id="e361d-108">Obligatorio.</span><span class="sxs-lookup"><span data-stu-id="e361d-108">Required.</span></span> <span data-ttu-id="e361d-109">Lista delimitada por punto y coma de directorios para que el compilador busque un ensamblado al que se hace referencia si no lo encuentra en el directorio de trabajo actual (el directorio desde el que se invoca al compilador) o en el directorio del sistema de Common Language Runtime.</span><span class="sxs-lookup"><span data-stu-id="e361d-109">Semicolon-delimited list of directories for the compiler to look in if a referenced assembly is not found in either the current working directory (the directory from which you are invoking the compiler) or the common language runtime's system directory.</span></span> <span data-ttu-id="e361d-110">Si el nombre del directorio contiene un espacio, escríbalo entre comillas (" ").</span><span class="sxs-lookup"><span data-stu-id="e361d-110">If the directory name contains a space, enclose the name in quotation marks (" ").</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e361d-111">Comentarios</span><span class="sxs-lookup"><span data-stu-id="e361d-111">Remarks</span></span>  
 <span data-ttu-id="e361d-112">La opción `-libpath` especifica la ubicación de los ensamblados a los que se hace referencia con la opción [-reference](../../../visual-basic/reference/command-line-compiler/reference.md).</span><span class="sxs-lookup"><span data-stu-id="e361d-112">The `-libpath` option specifies the location of assemblies referenced by the [-reference](../../../visual-basic/reference/command-line-compiler/reference.md) option.</span></span>  
  
 <span data-ttu-id="e361d-113">El compilador busca referencias a ensamblados que no presentan la ruta completa en el siguiente orden:</span><span class="sxs-lookup"><span data-stu-id="e361d-113">The compiler searches for assembly references that are not fully qualified in the following order:</span></span>  
  
1. <span data-ttu-id="e361d-114">Directorio de trabajo actual.</span><span class="sxs-lookup"><span data-stu-id="e361d-114">Current working directory.</span></span> <span data-ttu-id="e361d-115">Es el directorio desde donde se invoca al compilador.</span><span class="sxs-lookup"><span data-stu-id="e361d-115">This is the directory from which the compiler is invoked.</span></span>  
  
2. <span data-ttu-id="e361d-116">El directorio del sistema de Common Language Runtime.</span><span class="sxs-lookup"><span data-stu-id="e361d-116">The common language runtime system directory.</span></span>  
  
3. <span data-ttu-id="e361d-117">Directorios especificados por `-libpath`.</span><span class="sxs-lookup"><span data-stu-id="e361d-117">Directories specified by `-libpath`.</span></span>  
  
4. <span data-ttu-id="e361d-118">Directorios especificados por la variable de entorno LIB.</span><span class="sxs-lookup"><span data-stu-id="e361d-118">Directories specified by the LIB environment variable.</span></span>  
  
 <span data-ttu-id="e361d-119">La opción `-libpath` es sumatoria; si se especifica más de una vez, se anexa a valores ya existentes.</span><span class="sxs-lookup"><span data-stu-id="e361d-119">The `-libpath` option is additive; specifying it more than once appends to any prior values.</span></span>  
  
 <span data-ttu-id="e361d-120">Use `-reference` para especificar una referencia a un ensamblado.</span><span class="sxs-lookup"><span data-stu-id="e361d-120">Use `-reference` to specify an assembly reference.</span></span>  
  
|<span data-ttu-id="e361d-121">Para establecer -libpath en el entorno de desarrollo integrado de Visual Studio</span><span class="sxs-lookup"><span data-stu-id="e361d-121">To set -libpath in the Visual Studio integrated development environment</span></span>|  
|---|  
|<span data-ttu-id="e361d-122">1.  Seleccione un proyecto en el **Explorador de soluciones**.</span><span class="sxs-lookup"><span data-stu-id="e361d-122">1.  Have a project selected in **Solution Explorer**.</span></span> <span data-ttu-id="e361d-123">En el menú **Proyecto**, haga clic en **Propiedades**.</span><span class="sxs-lookup"><span data-stu-id="e361d-123">On the **Project** menu, click **Properties**.</span></span> <br /><span data-ttu-id="e361d-124">2.  Haga clic en la pestaña **Referencias**.</span><span class="sxs-lookup"><span data-stu-id="e361d-124">2.  Click the **References** tab.</span></span><br /><span data-ttu-id="e361d-125">3.  Haga clic en el botón **Rutas de acceso de referencia...** .</span><span class="sxs-lookup"><span data-stu-id="e361d-125">3.  Click the **Reference Paths...** button.</span></span><br /><span data-ttu-id="e361d-126">4.  En el cuadro de diálogo **Rutas de acceso de referencia**, escriba el nombre del directorio en el cuadro **Carpeta:** .</span><span class="sxs-lookup"><span data-stu-id="e361d-126">4.  In the **Reference Paths** dialog box, enter the directory name in the **Folder:** box.</span></span><br /><span data-ttu-id="e361d-127">5.  Haga clic en **Agregar carpeta**.</span><span class="sxs-lookup"><span data-stu-id="e361d-127">5.  Click **Add Folder**.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="e361d-128">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="e361d-128">Example</span></span>  
 <span data-ttu-id="e361d-129">El código siguiente compila `T2.vb` para crear un archivo. exe.</span><span class="sxs-lookup"><span data-stu-id="e361d-129">The following code compiles `T2.vb` to create an .exe file.</span></span> <span data-ttu-id="e361d-130">El compilador busca las referencias de ensamblado en el directorio de trabajo, en el directorio raíz de la unidad C:, y en el directorio New Assemblies (Ensamblados nuevos) de la unidad C:.</span><span class="sxs-lookup"><span data-stu-id="e361d-130">The compiler looks in the working directory, in the root directory of the C: drive, and in the New Assemblies directory of the C: drive for assembly references.</span></span>  
  
```console  
vbc -libpath:c:\;"c:\New Assemblies" -reference:t2.dll t2.vb  
```  
  
## <a name="see-also"></a><span data-ttu-id="e361d-131">Vea también</span><span class="sxs-lookup"><span data-stu-id="e361d-131">See also</span></span>

- [<span data-ttu-id="e361d-132">Ensamblados de .NET</span><span class="sxs-lookup"><span data-stu-id="e361d-132">Assemblies in .NET</span></span>](../../../standard/assembly/index.md)
- [<span data-ttu-id="e361d-133">Compilador de línea de comandos de Visual Basic</span><span class="sxs-lookup"><span data-stu-id="e361d-133">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)
- [<span data-ttu-id="e361d-134">Líneas de comandos de compilación de ejemplo</span><span class="sxs-lookup"><span data-stu-id="e361d-134">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
