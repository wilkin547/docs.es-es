---
title: -Reference (Visual Basic)
ms.date: 03/13/2018
helpviewer_keywords:
- /reference compiler option [Visual Basic]
- r compiler option [Visual Basic]
- -reference compiler option [Visual Basic]
- /r compiler option [Visual Basic]
- reference compiler option [Visual Basic]
- -r compiler option [Visual Basic]
ms.assetid: 66bdfced-bbf6-43d1-a554-bc0990315737
ms.openlocfilehash: 552fbcf920be609de83708a995a87761f6080220
ms.sourcegitcommit: eff6adb61852369ab690f3f047818c90580e7eb1
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/07/2019
ms.locfileid: "72005272"
---
# <a name="-reference-visual-basic"></a><span data-ttu-id="66eb1-102">-Reference (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="66eb1-102">-reference (Visual Basic)</span></span>
<span data-ttu-id="66eb1-103">Hace que el compilador haga que la información de tipo de los ensamblados especificados esté disponible para el proyecto que se está compilando actualmente.</span><span class="sxs-lookup"><span data-stu-id="66eb1-103">Causes the compiler to make type information in the specified assemblies available to the project you are currently compiling.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="66eb1-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="66eb1-104">Syntax</span></span>  
  
```console  
-reference:fileList  
```

<span data-ttu-id="66eb1-105">o</span><span class="sxs-lookup"><span data-stu-id="66eb1-105">or</span></span>

```console
-r:fileList  
```  
  
## <a name="arguments"></a><span data-ttu-id="66eb1-106">Argumentos</span><span class="sxs-lookup"><span data-stu-id="66eb1-106">Arguments</span></span>  
  
|<span data-ttu-id="66eb1-107">Término</span><span class="sxs-lookup"><span data-stu-id="66eb1-107">Term</span></span>|<span data-ttu-id="66eb1-108">Definición</span><span class="sxs-lookup"><span data-stu-id="66eb1-108">Definition</span></span>|  
|---|---|  
|`fileList`|<span data-ttu-id="66eb1-109">Obligatorio.</span><span class="sxs-lookup"><span data-stu-id="66eb1-109">Required.</span></span> <span data-ttu-id="66eb1-110">Lista delimitada por comas de nombres de archivos de ensamblado.</span><span class="sxs-lookup"><span data-stu-id="66eb1-110">Comma-delimited list of assembly file names.</span></span> <span data-ttu-id="66eb1-111">Si el nombre de archivo contiene un espacio, escríbalo entre comillas.</span><span class="sxs-lookup"><span data-stu-id="66eb1-111">If the file name contains a space, enclose the name in quotation marks.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="66eb1-112">Comentarios</span><span class="sxs-lookup"><span data-stu-id="66eb1-112">Remarks</span></span>  
 <span data-ttu-id="66eb1-113">Los archivos que importe deben contener metadatos de ensamblado.</span><span class="sxs-lookup"><span data-stu-id="66eb1-113">The file(s) you import must contain assembly metadata.</span></span> <span data-ttu-id="66eb1-114">Solo los tipos públicos son visibles fuera del ensamblado.</span><span class="sxs-lookup"><span data-stu-id="66eb1-114">Only public types are visible outside the assembly.</span></span> <span data-ttu-id="66eb1-115">La opción [/AddModule](../../../visual-basic/reference/command-line-compiler/addmodule.md) importa los metadatos de un módulo.</span><span class="sxs-lookup"><span data-stu-id="66eb1-115">The [/addmodule](../../../visual-basic/reference/command-line-compiler/addmodule.md) option imports metadata from a module.</span></span>  
  
 <span data-ttu-id="66eb1-116">Si hace referencia a un ensamblado (ensamblado A) que a su vez hace referencia a otro ensamblado (ensamblado B), debe hacer referencia al ensamblado B si:</span><span class="sxs-lookup"><span data-stu-id="66eb1-116">If you reference an assembly (Assembly A) which itself references another assembly (Assembly B), you need to reference Assembly B if:</span></span>  
  
- <span data-ttu-id="66eb1-117">Un tipo del ensamblado A hereda de un tipo o implementa una interfaz del ensamblado B.</span><span class="sxs-lookup"><span data-stu-id="66eb1-117">A type from Assembly A inherits from a type or implements an interface from Assembly B.</span></span>  
  
- <span data-ttu-id="66eb1-118">Se invoca a un campo, una propiedad, un evento o un método que tiene un tipo de parámetro o un tipo de valor devuelto del ensamblado B.</span><span class="sxs-lookup"><span data-stu-id="66eb1-118">A field, property, event, or method that has a return type or parameter type from Assembly B is invoked.</span></span>  
  
 <span data-ttu-id="66eb1-119">Use [-LIBPATH](../../../visual-basic/reference/command-line-compiler/libpath.md) para especificar el directorio en el que se encuentran una o varias de las referencias de ensamblado.</span><span class="sxs-lookup"><span data-stu-id="66eb1-119">Use [-libpath](../../../visual-basic/reference/command-line-compiler/libpath.md) to specify the directory in which one or more of your assembly references is located.</span></span>  
  
 <span data-ttu-id="66eb1-120">Para que el compilador reconozca un tipo de un ensamblado (no de un módulo), se debe forzar la resolución del tipo.</span><span class="sxs-lookup"><span data-stu-id="66eb1-120">For the compiler to recognize a type in an assembly (not a module), it must be forced to resolve the type.</span></span> <span data-ttu-id="66eb1-121">Un ejemplo de cómo puede hacerlo es definir una instancia del tipo.</span><span class="sxs-lookup"><span data-stu-id="66eb1-121">One example of how you can do this is to define an instance of the type.</span></span> <span data-ttu-id="66eb1-122">Existen otras formas de resolver nombres de tipos en un ensamblado para el compilador.</span><span class="sxs-lookup"><span data-stu-id="66eb1-122">Other ways are available to resolve type names in an assembly for the compiler.</span></span> <span data-ttu-id="66eb1-123">Por ejemplo, si se hereda de un tipo de un ensamblado, el compilador hace que el nombre del tipo sea conocido.</span><span class="sxs-lookup"><span data-stu-id="66eb1-123">For example, if you inherit from a type in an assembly, the type name then becomes known to the compiler.</span></span>  
  
 <span data-ttu-id="66eb1-124">De forma predeterminada, se utiliza el archivo de respuesta VBC. RSP, que hace referencia a los ensamblados .NET Framework utilizados habitualmente.</span><span class="sxs-lookup"><span data-stu-id="66eb1-124">The Vbc.rsp response file, which references commonly used .NET Framework assemblies, is used by default.</span></span> <span data-ttu-id="66eb1-125">Use `-noconfig` si no desea que el compilador use VBC. rsp.</span><span class="sxs-lookup"><span data-stu-id="66eb1-125">Use `-noconfig` if you do not want the compiler to use Vbc.rsp.</span></span>  
  
 <span data-ttu-id="66eb1-126">La forma abreviada de `-reference` es `/r`.</span><span class="sxs-lookup"><span data-stu-id="66eb1-126">The short form of `-reference` is `/r`.</span></span>  
  
## <a name="example"></a><span data-ttu-id="66eb1-127">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="66eb1-127">Example</span></span>  
 <span data-ttu-id="66eb1-128">El comando siguiente compila el archivo de código fuente `Input.vb` y los ensamblados de referencia de `Metad1.dll` y `Metad2.dll` para generar `Out.exe`.</span><span class="sxs-lookup"><span data-stu-id="66eb1-128">The following command compiles source file `Input.vb` and reference assemblies from `Metad1.dll` and `Metad2.dll` to produce `Out.exe`.</span></span>  
  
```console
vbc -reference:metad1.dll,metad2.dll -out:out.exe input.vb  
```  
  
## <a name="see-also"></a><span data-ttu-id="66eb1-129">Vea también</span><span class="sxs-lookup"><span data-stu-id="66eb1-129">See also</span></span>

- [<span data-ttu-id="66eb1-130">Compilador de línea de comandos de Visual Basic</span><span class="sxs-lookup"><span data-stu-id="66eb1-130">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)
- [<span data-ttu-id="66eb1-131">-noconfig</span><span class="sxs-lookup"><span data-stu-id="66eb1-131">-noconfig</span></span>](../../../visual-basic/reference/command-line-compiler/noconfig.md)
- [<span data-ttu-id="66eb1-132">-Target (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="66eb1-132">-target (Visual Basic)</span></span>](../../../visual-basic/reference/command-line-compiler/target.md)
- [<span data-ttu-id="66eb1-133">Public</span><span class="sxs-lookup"><span data-stu-id="66eb1-133">Public</span></span>](../../../visual-basic/language-reference/modifiers/public.md)
- [<span data-ttu-id="66eb1-134">Líneas de comandos de compilación de ejemplo</span><span class="sxs-lookup"><span data-stu-id="66eb1-134">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
