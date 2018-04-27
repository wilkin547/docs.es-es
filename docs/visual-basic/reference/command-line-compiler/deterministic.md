---
title: -determinista
ms.date: 04/11/2018
ms.prod: .net
ms.technology:
- devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- deterministic compiler option [Visual Basic]
- -deterministic compiler option [Visual Basic]
- -deterministic compiler option [Visual Basic]
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 273abf8811f04cd7f58599ce3421ca1f17c740d9
ms.sourcegitcommit: 2042de78fcdceebb6b8ac4b7a292b93e8782cbf5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/27/2018
---
# <a name="-deterministic"></a><span data-ttu-id="f920a-102">-determinista</span><span class="sxs-lookup"><span data-stu-id="f920a-102">-deterministic</span></span>

<span data-ttu-id="f920a-103">Hace que el compilador generar un ensamblado cuyo resultado byte a byte es idéntica en compilaciones para las mismas entradas.</span><span class="sxs-lookup"><span data-stu-id="f920a-103">Causes the compiler to produce an assembly whose byte-for-byte output is identical across compilations for identical inputs.</span></span> 

## <a name="syntax"></a><span data-ttu-id="f920a-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="f920a-104">Syntax</span></span>

```
-deterministic
```

## <a name="remarks"></a><span data-ttu-id="f920a-105">Comentarios</span><span class="sxs-lookup"><span data-stu-id="f920a-105">Remarks</span></span>

<span data-ttu-id="f920a-106">De forma predeterminada, resultados del compilador de un conjunto determinado de entradas es único, ya que el compilador agrega una marca de tiempo y un GUID que se genera a partir de números aleatorios.</span><span class="sxs-lookup"><span data-stu-id="f920a-106">By default, compiler output from a given set of inputs is unique, since the compiler adds a timestamp and a GUID that is generated from random numbers.</span></span> <span data-ttu-id="f920a-107">Usa el `-deterministic` opción para generar un *ensamblado determinista*, uno cuyo contenido binario es idéntico a través de las compilaciones, siempre y cuando la entrada sigue siendo el mismo.</span><span class="sxs-lookup"><span data-stu-id="f920a-107">You use the `-deterministic` option to produce a *deterministic assembly*, one whose binary content is identical across compilations as long as the input remains the same.</span></span>

<span data-ttu-id="f920a-108">El compilador considera que las entradas siguientes con el fin de determinismo:</span><span class="sxs-lookup"><span data-stu-id="f920a-108">The compiler considers the following inputs for the purpose of determinism:</span></span>

- <span data-ttu-id="f920a-109">La secuencia de parámetros de línea de comandos.</span><span class="sxs-lookup"><span data-stu-id="f920a-109">The sequence of command-line parameters.</span></span>
- <span data-ttu-id="f920a-110">El contenido del archivo de respuesta del compilador rsp.</span><span class="sxs-lookup"><span data-stu-id="f920a-110">The contents of the compiler's .rsp response file.</span></span>
- <span data-ttu-id="f920a-111">La versión exacta del compilador utilizada y sus ensamblados que se hace referencia.</span><span class="sxs-lookup"><span data-stu-id="f920a-111">The precise version of the compiler used, and its referenced assemblies.</span></span>
- <span data-ttu-id="f920a-112">La ruta del directorio actual.</span><span class="sxs-lookup"><span data-stu-id="f920a-112">The current directory path.</span></span>
- <span data-ttu-id="f920a-113">El contenido binario de todos los archivos explícitamente pasó al compilador directa o indirectamente, incluidos:</span><span class="sxs-lookup"><span data-stu-id="f920a-113">The binary contents of all files explicitly passed to the compiler either directly or indirectly, including:</span></span> 
    - <span data-ttu-id="f920a-114">Archivos de código fuente</span><span class="sxs-lookup"><span data-stu-id="f920a-114">Source files</span></span>
    - <span data-ttu-id="f920a-115">ensamblados de referencia</span><span class="sxs-lookup"><span data-stu-id="f920a-115">Referenced assemblies</span></span>
    - <span data-ttu-id="f920a-116">Módulos que se hace referencia</span><span class="sxs-lookup"><span data-stu-id="f920a-116">Referenced modules</span></span>
    - <span data-ttu-id="f920a-117">Recursos</span><span class="sxs-lookup"><span data-stu-id="f920a-117">Resources</span></span>
    - <span data-ttu-id="f920a-118">El archivo de clave de nombre seguro</span><span class="sxs-lookup"><span data-stu-id="f920a-118">The strong name key file</span></span>
    - <span data-ttu-id="f920a-119">@ archivos de respuesta</span><span class="sxs-lookup"><span data-stu-id="f920a-119">@ response files</span></span>
    - <span data-ttu-id="f920a-120">Analizadores</span><span class="sxs-lookup"><span data-stu-id="f920a-120">Analyzers</span></span>
    - <span data-ttu-id="f920a-121">Conjuntos de reglas</span><span class="sxs-lookup"><span data-stu-id="f920a-121">Rulesets</span></span>
    - <span data-ttu-id="f920a-122">Archivos adicionales que pueden utilizarse analizadores</span><span class="sxs-lookup"><span data-stu-id="f920a-122">Additional files that may be used by analyzers</span></span>
- <span data-ttu-id="f920a-123">La referencia cultural actual (para el idioma en qué diagnósticos y las excepciones se producen mensajes).</span><span class="sxs-lookup"><span data-stu-id="f920a-123">The current culture (for the language in which diagnostics and exception messages are produced).</span></span>
- <span data-ttu-id="f920a-124">La codificación predeterminada (o la página de códigos actual) si no se especifica la codificación.</span><span class="sxs-lookup"><span data-stu-id="f920a-124">The default encoding (or the current code page) if the encoding is not specified.</span></span>
- <span data-ttu-id="f920a-125">La existencia, la existencia no y el contenido de los archivos en las rutas de búsqueda del compilador (especificado, por ejemplo, `/lib` o `/recurse`).</span><span class="sxs-lookup"><span data-stu-id="f920a-125">The existence, non-existence, and contents of files on the compiler's search paths (specified, for example, by `/lib` or `/recurse`).</span></span>
- <span data-ttu-id="f920a-126">La plataforma CLR en el que se ejecuta el compilador.</span><span class="sxs-lookup"><span data-stu-id="f920a-126">The CLR platform on which the compiler is run.</span></span>
- <span data-ttu-id="f920a-127">El valor de `%LIBPATH%`, que pueden afectar a la carga de la dependencia de analizador.</span><span class="sxs-lookup"><span data-stu-id="f920a-127">The value of `%LIBPATH%`, which can affect analyzer dependency loading.</span></span>

<span data-ttu-id="f920a-128">Cuando los orígenes disponibles públicamente, compilación determinista puede usarse para establecer si se compila un archivo binario de una fuente confiable.</span><span class="sxs-lookup"><span data-stu-id="f920a-128">When sources are publicly available, deterministic compilation can be used for establishing whether a binary is compiled from a trusted source.</span></span> <span data-ttu-id="f920a-129">También puede ser útil en un sistema de compilación continua para determinar si deben ejecutar pasos de compilación que dependen de los cambios en un archivo binario.</span><span class="sxs-lookup"><span data-stu-id="f920a-129">It can also be useful in a continuous build system for determining whether build steps that are dependent on changes to a binary need to be executed.</span></span> 

## <a name="see-also"></a><span data-ttu-id="f920a-130">Vea también</span><span class="sxs-lookup"><span data-stu-id="f920a-130">See Also</span></span>
[<span data-ttu-id="f920a-131">Compilador de línea de comandos de Visual Basic</span><span class="sxs-lookup"><span data-stu-id="f920a-131">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)  
[<span data-ttu-id="f920a-132">Líneas de comandos de compilación de ejemplo</span><span class="sxs-lookup"><span data-stu-id="f920a-132">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
