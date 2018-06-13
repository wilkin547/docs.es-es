---
title: -referencia (Visual Basic)
ms.date: 03/13/2018
helpviewer_keywords:
- /reference compiler option [Visual Basic]
- r compiler option [Visual Basic]
- -reference compiler option [Visual Basic]
- /r compiler option [Visual Basic]
- reference compiler option [Visual Basic]
- -r compiler option [Visual Basic]
ms.assetid: 66bdfced-bbf6-43d1-a554-bc0990315737
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: cb5d3b4c50a9c22880bdcc8406835cf51481e3cd
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33654374"
---
# <a name="-reference-visual-basic"></a><span data-ttu-id="feb67-102">-referencia (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="feb67-102">-reference (Visual Basic)</span></span>
<span data-ttu-id="feb67-103">Hace que el compilador para que estén disponibles para el proyecto que se está compilando la información de tipo en los ensamblados especificados.</span><span class="sxs-lookup"><span data-stu-id="feb67-103">Causes the compiler to make type information in the specified assemblies available to the project you are currently compiling.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="feb67-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="feb67-104">Syntax</span></span>  
  
```  
-reference:fileList  
' -or-  
-r:fileList  
```  
  
## <a name="arguments"></a><span data-ttu-id="feb67-105">Argumentos</span><span class="sxs-lookup"><span data-stu-id="feb67-105">Arguments</span></span>  
  
|<span data-ttu-id="feb67-106">Término</span><span class="sxs-lookup"><span data-stu-id="feb67-106">Term</span></span>|<span data-ttu-id="feb67-107">Definición</span><span class="sxs-lookup"><span data-stu-id="feb67-107">Definition</span></span>|  
|---|---|  
|`fileList`|<span data-ttu-id="feb67-108">Requerido.</span><span class="sxs-lookup"><span data-stu-id="feb67-108">Required.</span></span> <span data-ttu-id="feb67-109">Lista delimitada por comas de nombres de archivos de ensamblado.</span><span class="sxs-lookup"><span data-stu-id="feb67-109">Comma-delimited list of assembly file names.</span></span> <span data-ttu-id="feb67-110">Si el nombre de archivo contiene un espacio, escríbalo entre comillas.</span><span class="sxs-lookup"><span data-stu-id="feb67-110">If the file name contains a space, enclose the name in quotation marks.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="feb67-111">Comentarios</span><span class="sxs-lookup"><span data-stu-id="feb67-111">Remarks</span></span>  
 <span data-ttu-id="feb67-112">Los archivos importados deben contener metadatos de ensamblado.</span><span class="sxs-lookup"><span data-stu-id="feb67-112">The file(s) you import must contain assembly metadata.</span></span> <span data-ttu-id="feb67-113">Solo los tipos públicos son visibles fuera del ensamblado.</span><span class="sxs-lookup"><span data-stu-id="feb67-113">Only public types are visible outside the assembly.</span></span> <span data-ttu-id="feb67-114">El [/addmodule](../../../visual-basic/reference/command-line-compiler/addmodule.md) opción importa los metadatos de un módulo.</span><span class="sxs-lookup"><span data-stu-id="feb67-114">The [/addmodule](../../../visual-basic/reference/command-line-compiler/addmodule.md) option imports metadata from a module.</span></span>  
  
 <span data-ttu-id="feb67-115">Si hace referencia a un ensamblado (A) que hiciera referencia a otro ensamblado (ensamblado B), debe hacer referencia al ensamblado B si:</span><span class="sxs-lookup"><span data-stu-id="feb67-115">If you reference an assembly (Assembly A) which itself references another assembly (Assembly B), you need to reference Assembly B if:</span></span>  
  
-   <span data-ttu-id="feb67-116">Un tipo del ensamblado A hereda de un tipo o implementa una interfaz del ensamblado B.</span><span class="sxs-lookup"><span data-stu-id="feb67-116">A type from Assembly A inherits from a type or implements an interface from Assembly B.</span></span>  
  
-   <span data-ttu-id="feb67-117">Se invoca a un campo, una propiedad, un evento o un método que tiene un tipo de parámetro o un tipo de valor devuelto del ensamblado B.</span><span class="sxs-lookup"><span data-stu-id="feb67-117">A field, property, event, or method that has a return type or parameter type from Assembly B is invoked.</span></span>  
  
 <span data-ttu-id="feb67-118">Use [- libpath](../../../visual-basic/reference/command-line-compiler/libpath.md) para especificar el directorio en el que se encuentran una o varias de las referencias de ensamblado.</span><span class="sxs-lookup"><span data-stu-id="feb67-118">Use [-libpath](../../../visual-basic/reference/command-line-compiler/libpath.md) to specify the directory in which one or more of your assembly references is located.</span></span>  
  
 <span data-ttu-id="feb67-119">Para que el compilador reconozca un tipo en un ensamblado (no un módulo), debe forzarse para resolver el tipo.</span><span class="sxs-lookup"><span data-stu-id="feb67-119">For the compiler to recognize a type in an assembly (not a module), it must be forced to resolve the type.</span></span> <span data-ttu-id="feb67-120">Un ejemplo de cómo se puede hacer esto es definir una instancia del tipo.</span><span class="sxs-lookup"><span data-stu-id="feb67-120">One example of how you can do this is to define an instance of the type.</span></span> <span data-ttu-id="feb67-121">Otras maneras de están disponibles para resolver los nombres de tipo en un ensamblado para el compilador.</span><span class="sxs-lookup"><span data-stu-id="feb67-121">Other ways are available to resolve type names in an assembly for the compiler.</span></span> <span data-ttu-id="feb67-122">Por ejemplo, si se hereda de un tipo en un ensamblado, el nombre de tipo, a continuación, se convierte en el compilador conoce.</span><span class="sxs-lookup"><span data-stu-id="feb67-122">For example, if you inherit from a type in an assembly, the type name then becomes known to the compiler.</span></span>  
  
 <span data-ttu-id="feb67-123">El archivo de respuesta Vbc.rsp, que utiliza habitualmente referencias [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] ensamblados, se utiliza de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="feb67-123">The Vbc.rsp response file, which references commonly used [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] assemblies, is used by default.</span></span> <span data-ttu-id="feb67-124">Usar `-noconfig` si no desea que el compilador utilice Vbc.rsp.</span><span class="sxs-lookup"><span data-stu-id="feb67-124">Use `-noconfig` if you do not want the compiler to use Vbc.rsp.</span></span>  
  
 <span data-ttu-id="feb67-125">La forma abreviada de `-reference` es `/r`.</span><span class="sxs-lookup"><span data-stu-id="feb67-125">The short form of `-reference` is `/r`.</span></span>  
  
## <a name="example"></a><span data-ttu-id="feb67-126">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="feb67-126">Example</span></span>  
 <span data-ttu-id="feb67-127">El comando siguiente compila el archivo de código fuente `Input.vb` y hacer referencia a ensamblados de `Metad1.dll` y `Metad2.dll` para generar `Out.exe`.</span><span class="sxs-lookup"><span data-stu-id="feb67-127">The following command compiles source file `Input.vb` and reference assemblies from `Metad1.dll` and `Metad2.dll` to produce `Out.exe`.</span></span>  
  
```console
vbc -reference:metad1.dll,metad2.dll -out:out.exe input.vb  
```  
  
## <a name="see-also"></a><span data-ttu-id="feb67-128">Vea también</span><span class="sxs-lookup"><span data-stu-id="feb67-128">See Also</span></span>  
 [<span data-ttu-id="feb67-129">Compilador de línea de comandos de Visual Basic</span><span class="sxs-lookup"><span data-stu-id="feb67-129">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)  
 [<span data-ttu-id="feb67-130">-noconfig</span><span class="sxs-lookup"><span data-stu-id="feb67-130">-noconfig</span></span>](../../../visual-basic/reference/command-line-compiler/noconfig.md)  
 [<span data-ttu-id="feb67-131">-target (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="feb67-131">-target (Visual Basic)</span></span>](../../../visual-basic/reference/command-line-compiler/target.md)  
 [<span data-ttu-id="feb67-132">Public</span><span class="sxs-lookup"><span data-stu-id="feb67-132">Public</span></span>](../../../visual-basic/language-reference/modifiers/public.md)  
 [<span data-ttu-id="feb67-133">Líneas de comandos de compilación de ejemplo</span><span class="sxs-lookup"><span data-stu-id="feb67-133">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
