---
description: -deterministic (opciones del compilador de C#)
title: -deterministic (opciones del compilador de C#)
ms.date: 04/12/2018
f1_keywords:
- /deterministic
helpviewer_keywords:
- -deterministic compiler option [C#]
- deterministic compiler option [C#]
- /deterministic compiler option [C#]
ms.openlocfilehash: d64f4d4b0d4e9b5ed2cc1ee40662dc669fc6660d
ms.sourcegitcommit: 4f5f1855849cb02c3b610c7006ac21d7429f3348
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/15/2021
ms.locfileid: "98235331"
---
# <a name="-deterministic"></a><span data-ttu-id="640e2-103">-deterministic</span><span class="sxs-lookup"><span data-stu-id="640e2-103">-deterministic</span></span>

<span data-ttu-id="640e2-104">Hace que el compilador genere un ensamblado cuya salida byte a byte es idéntica en todas las compilaciones para las entradas idénticas.</span><span class="sxs-lookup"><span data-stu-id="640e2-104">Causes the compiler to produce an assembly whose byte-for-byte output is identical across compilations for identical inputs.</span></span>

## <a name="syntax"></a><span data-ttu-id="640e2-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="640e2-105">Syntax</span></span>

```console
-deterministic
```

## <a name="remarks"></a><span data-ttu-id="640e2-106">Comentarios</span><span class="sxs-lookup"><span data-stu-id="640e2-106">Remarks</span></span>

<span data-ttu-id="640e2-107">De forma predeterminada, la salida del compilador de un conjunto determinado de entradas es única, ya que el compilador agrega una marca de tiempo y un MVID que se genera a partir de números aleatorios.</span><span class="sxs-lookup"><span data-stu-id="640e2-107">By default, compiler output from a given set of inputs is unique, since the compiler adds a timestamp and a MVID that is generated from random numbers.</span></span> <span data-ttu-id="640e2-108">Use la opción `-deterministic` para generar un *ensamblado determinista*, cuyo contenido binario es idéntico en todas las compilaciones, siempre y cuando la entrada siga siendo la misma.</span><span class="sxs-lookup"><span data-stu-id="640e2-108">You use the `-deterministic` option to produce a *deterministic assembly*, one whose binary content is identical across compilations as long as the input remains the same.</span></span> <span data-ttu-id="640e2-109">En este tipo de compilación, los campos timestamp y MVID se reemplazarán por los valores derivados de un hash de todas las entradas de la compilación.</span><span class="sxs-lookup"><span data-stu-id="640e2-109">In such a build, the timestamp and MVID fields will be replaced with values derived from a hash of all the compilation inputs.</span></span>

<span data-ttu-id="640e2-110">El compilador tiene en cuenta las entradas siguientes con el fin de garantizar el determinismo:</span><span class="sxs-lookup"><span data-stu-id="640e2-110">The compiler considers the following inputs for the purpose of determinism:</span></span>

- <span data-ttu-id="640e2-111">La secuencia de parámetros de la línea de comandos.</span><span class="sxs-lookup"><span data-stu-id="640e2-111">The sequence of command-line parameters.</span></span>
- <span data-ttu-id="640e2-112">El contenido del archivo de respuesta .rsp del compilador.</span><span class="sxs-lookup"><span data-stu-id="640e2-112">The contents of the compiler's .rsp response file.</span></span>
- <span data-ttu-id="640e2-113">La versión exacta del compilador que se usa y los ensamblados a los que se hace referencia.</span><span class="sxs-lookup"><span data-stu-id="640e2-113">The precise version of the compiler used, and its referenced assemblies.</span></span>
- <span data-ttu-id="640e2-114">La ruta de acceso del directorio actual.</span><span class="sxs-lookup"><span data-stu-id="640e2-114">The current directory path.</span></span>
- <span data-ttu-id="640e2-115">El contenido binario de todos los archivos pasados explícitamente al compilador, ya sea de manera directa o indirecta, incluidos los siguientes:</span><span class="sxs-lookup"><span data-stu-id="640e2-115">The binary contents of all files explicitly passed to the compiler either directly or indirectly, including:</span></span>
  - <span data-ttu-id="640e2-116">Archivos de código fuente</span><span class="sxs-lookup"><span data-stu-id="640e2-116">Source files</span></span>
  - <span data-ttu-id="640e2-117">Ensamblados a los que se hace referencia</span><span class="sxs-lookup"><span data-stu-id="640e2-117">Referenced assemblies</span></span>
  - <span data-ttu-id="640e2-118">Módulos a los que se hace referencia</span><span class="sxs-lookup"><span data-stu-id="640e2-118">Referenced modules</span></span>
  - <span data-ttu-id="640e2-119">Recursos</span><span class="sxs-lookup"><span data-stu-id="640e2-119">Resources</span></span>
  - <span data-ttu-id="640e2-120">Archivo de clave de nombre seguro</span><span class="sxs-lookup"><span data-stu-id="640e2-120">The strong name key file</span></span>
  - <span data-ttu-id="640e2-121">Archivos de respuesta @</span><span class="sxs-lookup"><span data-stu-id="640e2-121">@ response files</span></span>
  - <span data-ttu-id="640e2-122">Analizadores</span><span class="sxs-lookup"><span data-stu-id="640e2-122">Analyzers</span></span>
  - <span data-ttu-id="640e2-123">Conjuntos de reglas</span><span class="sxs-lookup"><span data-stu-id="640e2-123">Rulesets</span></span>
  - <span data-ttu-id="640e2-124">Archivos adicionales que podrían usar los analizadores</span><span class="sxs-lookup"><span data-stu-id="640e2-124">Additional files that may be used by analyzers</span></span>
- <span data-ttu-id="640e2-125">La referencia cultural actual (para el idioma en el que se producen los diagnósticos y los mensajes de excepción).</span><span class="sxs-lookup"><span data-stu-id="640e2-125">The current culture (for the language in which diagnostics and exception messages are produced).</span></span>
- <span data-ttu-id="640e2-126">La codificación predeterminada (o página de códigos actual) si no se especifica la codificación.</span><span class="sxs-lookup"><span data-stu-id="640e2-126">The default encoding (or the current code page) if the encoding is not specified.</span></span>
- <span data-ttu-id="640e2-127">La existencia (o la inexistencia) de archivos y su contenido en las rutas de búsqueda del compilador (especificada, por ejemplo, mediante `-lib` o `-recurse`).</span><span class="sxs-lookup"><span data-stu-id="640e2-127">The existence, non-existence, and contents of files on the compiler's search paths (specified, for example, by `-lib` or `-recurse`).</span></span>
- <span data-ttu-id="640e2-128">La plataforma CLR en la que se ejecuta el compilador.</span><span class="sxs-lookup"><span data-stu-id="640e2-128">The CLR platform on which the compiler is run.</span></span>
- <span data-ttu-id="640e2-129">El valor de `%LIBPATH%`, que pueden afectar a la carga de dependencias del analizador.</span><span class="sxs-lookup"><span data-stu-id="640e2-129">The value of `%LIBPATH%`, which can affect analyzer dependency loading.</span></span>

<span data-ttu-id="640e2-130">Cuando los orígenes están disponibles públicamente, se puede usar la compilación determinista para establecer si un archivo binario se compila a partir de una fuente de confianza.</span><span class="sxs-lookup"><span data-stu-id="640e2-130">When sources are publicly available, deterministic compilation can be used for establishing whether a binary is compiled from a trusted source.</span></span> <span data-ttu-id="640e2-131">También puede ser útil en un sistema de compilación continua para determinar si es necesario ejecutar pasos de compilación que dependen de los cambios realizados en un archivo binario.</span><span class="sxs-lookup"><span data-stu-id="640e2-131">It can also be useful in a continuous build system for determining whether build steps that are dependent on changes to a binary need to be executed.</span></span>

## <a name="see-also"></a><span data-ttu-id="640e2-132">Vea también</span><span class="sxs-lookup"><span data-stu-id="640e2-132">See also</span></span>

- [<span data-ttu-id="640e2-133">Opciones del compilador de C#</span><span class="sxs-lookup"><span data-stu-id="640e2-133">C# Compiler Options</span></span>](./index.md)
- [<span data-ttu-id="640e2-134">Administrar propiedades de soluciones y proyectos</span><span class="sxs-lookup"><span data-stu-id="640e2-134">Managing Project and Solution Properties</span></span>](/visualstudio/ide/managing-project-and-solution-properties)
