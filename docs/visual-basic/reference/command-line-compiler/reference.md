---
description: Más información sobre -reference (Visual Basic)
title: -reference
ms.date: 03/13/2018
helpviewer_keywords:
- /reference compiler option [Visual Basic]
- r compiler option [Visual Basic]
- -reference compiler option [Visual Basic]
- /r compiler option [Visual Basic]
- reference compiler option [Visual Basic]
- -r compiler option [Visual Basic]
ms.assetid: 66bdfced-bbf6-43d1-a554-bc0990315737
ms.openlocfilehash: e84cdf447294a299c26a775327528a94ebba03da
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/14/2021
ms.locfileid: "100474153"
---
# <a name="-reference-visual-basic"></a><span data-ttu-id="19194-103">-reference (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="19194-103">-reference (Visual Basic)</span></span>

<span data-ttu-id="19194-104">Hace que el compilador facilite al proyecto que se está compilando información de tipos en los ensamblados especificados.</span><span class="sxs-lookup"><span data-stu-id="19194-104">Causes the compiler to make type information in the specified assemblies available to the project you are currently compiling.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="19194-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="19194-105">Syntax</span></span>  
  
```console  
-reference:fileList  
```

<span data-ttu-id="19194-106">o</span><span class="sxs-lookup"><span data-stu-id="19194-106">or</span></span>

```console
-r:fileList  
```  
  
## <a name="arguments"></a><span data-ttu-id="19194-107">Argumentos</span><span class="sxs-lookup"><span data-stu-id="19194-107">Arguments</span></span>  
  
|<span data-ttu-id="19194-108">Término</span><span class="sxs-lookup"><span data-stu-id="19194-108">Term</span></span>|<span data-ttu-id="19194-109">Definición</span><span class="sxs-lookup"><span data-stu-id="19194-109">Definition</span></span>|  
|---|---|  
|`fileList`|<span data-ttu-id="19194-110">Obligatorio.</span><span class="sxs-lookup"><span data-stu-id="19194-110">Required.</span></span> <span data-ttu-id="19194-111">Lista delimitada por comas de nombres de archivos de ensamblado.</span><span class="sxs-lookup"><span data-stu-id="19194-111">Comma-delimited list of assembly file names.</span></span> <span data-ttu-id="19194-112">Si el nombre de archivo contiene un espacio, escríbalo entre comillas.</span><span class="sxs-lookup"><span data-stu-id="19194-112">If the file name contains a space, enclose the name in quotation marks.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="19194-113">Comentarios</span><span class="sxs-lookup"><span data-stu-id="19194-113">Remarks</span></span>  

 <span data-ttu-id="19194-114">Los archivos que importe deben contener metadatos de ensamblado.</span><span class="sxs-lookup"><span data-stu-id="19194-114">The file(s) you import must contain assembly metadata.</span></span> <span data-ttu-id="19194-115">Solo los tipos públicos son visibles fuera del ensamblado.</span><span class="sxs-lookup"><span data-stu-id="19194-115">Only public types are visible outside the assembly.</span></span> <span data-ttu-id="19194-116">La opción [-addmodule](addmodule.md) importa metadatos de un módulo.</span><span class="sxs-lookup"><span data-stu-id="19194-116">The [-addmodule](addmodule.md) option imports metadata from a module.</span></span>  
  
 <span data-ttu-id="19194-117">Si hace referencia a un ensamblado (ensamblado A) que a su vez hace referencia a otro ensamblado (ensamblado B), debe hacer referencia al ensamblado B si:</span><span class="sxs-lookup"><span data-stu-id="19194-117">If you reference an assembly (Assembly A) which itself references another assembly (Assembly B), you need to reference Assembly B if:</span></span>  
  
- <span data-ttu-id="19194-118">Un tipo del ensamblado A hereda de un tipo o implementa una interfaz del ensamblado B.</span><span class="sxs-lookup"><span data-stu-id="19194-118">A type from Assembly A inherits from a type or implements an interface from Assembly B.</span></span>  
  
- <span data-ttu-id="19194-119">Se invoca a un campo, una propiedad, un evento o un método que tiene un tipo de parámetro o un tipo de valor devuelto del ensamblado B.</span><span class="sxs-lookup"><span data-stu-id="19194-119">A field, property, event, or method that has a return type or parameter type from Assembly B is invoked.</span></span>  
  
 <span data-ttu-id="19194-120">Use [-libpath](libpath.md) para especificar el directorio en el que se encuentran una o varias de las referencias de ensamblado.</span><span class="sxs-lookup"><span data-stu-id="19194-120">Use [-libpath](libpath.md) to specify the directory in which one or more of your assembly references is located.</span></span>  
  
 <span data-ttu-id="19194-121">Para que el compilador reconozca un tipo en un ensamblado (no un módulo), se debe forzar la resolución del tipo.</span><span class="sxs-lookup"><span data-stu-id="19194-121">For the compiler to recognize a type in an assembly (not a module), it must be forced to resolve the type.</span></span> <span data-ttu-id="19194-122">Un ejemplo de cómo puede hacerse es definir una instancia del tipo.</span><span class="sxs-lookup"><span data-stu-id="19194-122">One example of how you can do this is to define an instance of the type.</span></span> <span data-ttu-id="19194-123">Existen otras formas de resolver nombres de tipo en un ensamblado para el compilador.</span><span class="sxs-lookup"><span data-stu-id="19194-123">Other ways are available to resolve type names in an assembly for the compiler.</span></span> <span data-ttu-id="19194-124">Por ejemplo, si se hereda de un tipo de un ensamblado, nombre del tipo pasa a ser conocido para el compilador.</span><span class="sxs-lookup"><span data-stu-id="19194-124">For example, if you inherit from a type in an assembly, the type name then becomes known to the compiler.</span></span>  
  
 <span data-ttu-id="19194-125">De forma predeterminada se usa el archivo de respuesta Vbc.rsp, que hace referencia a los ensamblados de .NET Framework usados habitualmente.</span><span class="sxs-lookup"><span data-stu-id="19194-125">The Vbc.rsp response file, which references commonly used .NET Framework assemblies, is used by default.</span></span> <span data-ttu-id="19194-126">Use `-noconfig` si no quiere que el compilador use Vbc.rsp.</span><span class="sxs-lookup"><span data-stu-id="19194-126">Use `-noconfig` if you do not want the compiler to use Vbc.rsp.</span></span>  
  
 <span data-ttu-id="19194-127">La forma abreviada de `-reference` es `-r`.</span><span class="sxs-lookup"><span data-stu-id="19194-127">The short form of `-reference` is `-r`.</span></span>  
  
## <a name="example"></a><span data-ttu-id="19194-128">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="19194-128">Example</span></span>  

 <span data-ttu-id="19194-129">El comando siguiente compila el archivo de código fuente `Input.vb` y hace referencia a ensamblados de `Metad1.dll` y `Metad2.dll` para generar `Out.exe`.</span><span class="sxs-lookup"><span data-stu-id="19194-129">The following command compiles source file `Input.vb` and reference assemblies from `Metad1.dll` and `Metad2.dll` to produce `Out.exe`.</span></span>  
  
```console
vbc -reference:metad1.dll,metad2.dll -out:out.exe input.vb  
```  
  
## <a name="see-also"></a><span data-ttu-id="19194-130">Vea también</span><span class="sxs-lookup"><span data-stu-id="19194-130">See also</span></span>

- [<span data-ttu-id="19194-131">Compilador de línea de comandos de Visual Basic</span><span class="sxs-lookup"><span data-stu-id="19194-131">Visual Basic Command-Line Compiler</span></span>](index.md)
- [<span data-ttu-id="19194-132">-noconfig</span><span class="sxs-lookup"><span data-stu-id="19194-132">-noconfig</span></span>](noconfig.md)
- [<span data-ttu-id="19194-133">-target (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="19194-133">-target (Visual Basic)</span></span>](target.md)
- [<span data-ttu-id="19194-134">Public</span><span class="sxs-lookup"><span data-stu-id="19194-134">Public</span></span>](../../language-reference/modifiers/public.md)
- [<span data-ttu-id="19194-135">Líneas de comandos de compilación de ejemplo</span><span class="sxs-lookup"><span data-stu-id="19194-135">Sample Compilation Command Lines</span></span>](sample-compilation-command-lines.md)
