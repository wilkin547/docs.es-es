---
title: -deterministic (opciones del compilador de C#)
ms.date: 04/12/2018
f1_keywords:
- /deterministic
helpviewer_keywords:
- -deterministic compiler option [C#]
- deterministic compiler option [C#]
- /deterministic compiler option [C#]
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 7c6d0c7128becb154955664cfdcf96d020de9369
ms.sourcegitcommit: 859b2ba0c74a1a5a4ad0d59a3c3af23450995981
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/11/2019
ms.locfileid: "59480669"
---
# <a name="-deterministic"></a><span data-ttu-id="128a9-102">-deterministic</span><span class="sxs-lookup"><span data-stu-id="128a9-102">-deterministic</span></span>

<span data-ttu-id="128a9-103">Hace que el compilador genere un ensamblado cuya salida byte a byte es idéntica en todas las compilaciones para las entradas idénticas.</span><span class="sxs-lookup"><span data-stu-id="128a9-103">Causes the compiler to produce an assembly whose byte-for-byte output is identical across compilations for identical inputs.</span></span>

## <a name="syntax"></a><span data-ttu-id="128a9-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="128a9-104">Syntax</span></span>

```
-deterministic
```

## <a name="remarks"></a><span data-ttu-id="128a9-105">Comentarios</span><span class="sxs-lookup"><span data-stu-id="128a9-105">Remarks</span></span>

<span data-ttu-id="128a9-106">De forma predeterminada, la salida del compilador para un conjunto determinado de entradas es única, ya que el compilador agrega una marca de tiempo y un GUID que se genera a partir de números aleatorios.</span><span class="sxs-lookup"><span data-stu-id="128a9-106">By default, compiler output from a given set of inputs is unique, since the compiler adds a timestamp and a GUID that is generated from random numbers.</span></span> <span data-ttu-id="128a9-107">Use la opción `-deterministic` para generar un *ensamblado determinista*, cuyo contenido binario es idéntico en todas las compilaciones, siempre y cuando la entrada siga siendo la misma.</span><span class="sxs-lookup"><span data-stu-id="128a9-107">You use the `-deterministic` option to produce a *deterministic assembly*, one whose binary content is identical across compilations as long as the input remains the same.</span></span>

<span data-ttu-id="128a9-108">El compilador tiene en cuenta las entradas siguientes con el fin de garantizar el determinismo:</span><span class="sxs-lookup"><span data-stu-id="128a9-108">The compiler considers the following inputs for the purpose of determinism:</span></span>

- <span data-ttu-id="128a9-109">La secuencia de parámetros de la línea de comandos.</span><span class="sxs-lookup"><span data-stu-id="128a9-109">The sequence of command-line parameters.</span></span>
- <span data-ttu-id="128a9-110">El contenido del archivo de respuesta .rsp del compilador.</span><span class="sxs-lookup"><span data-stu-id="128a9-110">The contents of the compiler's .rsp response file.</span></span>
- <span data-ttu-id="128a9-111">La versión exacta del compilador que se usa y los ensamblados a los que se hace referencia.</span><span class="sxs-lookup"><span data-stu-id="128a9-111">The precise version of the compiler used, and its referenced assemblies.</span></span>
- <span data-ttu-id="128a9-112">La ruta de acceso del directorio actual.</span><span class="sxs-lookup"><span data-stu-id="128a9-112">The current directory path.</span></span>
- <span data-ttu-id="128a9-113">El contenido binario de todos los archivos pasados explícitamente al compilador, ya sea de manera directa o indirecta, incluidos los siguientes:</span><span class="sxs-lookup"><span data-stu-id="128a9-113">The binary contents of all files explicitly passed to the compiler either directly or indirectly, including:</span></span>
  - <span data-ttu-id="128a9-114">Archivos de código fuente</span><span class="sxs-lookup"><span data-stu-id="128a9-114">Source files</span></span>
  - <span data-ttu-id="128a9-115">Ensamblados a los que se hace referencia</span><span class="sxs-lookup"><span data-stu-id="128a9-115">Referenced assemblies</span></span>
  - <span data-ttu-id="128a9-116">Módulos a los que se hace referencia</span><span class="sxs-lookup"><span data-stu-id="128a9-116">Referenced modules</span></span>
  - <span data-ttu-id="128a9-117">Recursos</span><span class="sxs-lookup"><span data-stu-id="128a9-117">Resources</span></span>
  - <span data-ttu-id="128a9-118">Archivo de clave de nombre seguro</span><span class="sxs-lookup"><span data-stu-id="128a9-118">The strong name key file</span></span>
  - <span data-ttu-id="128a9-119">Archivos de respuesta @</span><span class="sxs-lookup"><span data-stu-id="128a9-119">@ response files</span></span>
  - <span data-ttu-id="128a9-120">Analizadores</span><span class="sxs-lookup"><span data-stu-id="128a9-120">Analyzers</span></span>
  - <span data-ttu-id="128a9-121">Conjuntos de reglas</span><span class="sxs-lookup"><span data-stu-id="128a9-121">Rulesets</span></span>
  - <span data-ttu-id="128a9-122">Archivos adicionales que podrían usar los analizadores</span><span class="sxs-lookup"><span data-stu-id="128a9-122">Additional files that may be used by analyzers</span></span>
- <span data-ttu-id="128a9-123">La referencia cultural actual (para el idioma en el que se producen los diagnósticos y los mensajes de excepción).</span><span class="sxs-lookup"><span data-stu-id="128a9-123">The current culture (for the language in which diagnostics and exception messages are produced).</span></span>
- <span data-ttu-id="128a9-124">La codificación predeterminada (o página de códigos actual) si no se especifica la codificación.</span><span class="sxs-lookup"><span data-stu-id="128a9-124">The default encoding (or the current code page) if the encoding is not specified.</span></span>
- <span data-ttu-id="128a9-125">La existencia (o la inexistencia) de archivos y su contenido en las rutas de búsqueda del compilador (especificada, por ejemplo, mediante `/lib` o `/recurse`).</span><span class="sxs-lookup"><span data-stu-id="128a9-125">The existence, non-existence, and contents of files on the compiler's search paths (specified, for example, by `/lib` or `/recurse`).</span></span>
- <span data-ttu-id="128a9-126">La plataforma CLR en la que se ejecuta el compilador.</span><span class="sxs-lookup"><span data-stu-id="128a9-126">The CLR platform on which the compiler is run.</span></span>
- <span data-ttu-id="128a9-127">El valor de `%LIBPATH%`, que pueden afectar a la carga de dependencias del analizador.</span><span class="sxs-lookup"><span data-stu-id="128a9-127">The value of `%LIBPATH%`, which can affect analyzer dependency loading.</span></span>

<span data-ttu-id="128a9-128">Cuando los orígenes están disponibles públicamente, se puede usar la compilación determinista para establecer si un archivo binario se compila a partir de una fuente de confianza.</span><span class="sxs-lookup"><span data-stu-id="128a9-128">When sources are publicly available, deterministic compilation can be used for establishing whether a binary is compiled from a trusted source.</span></span> <span data-ttu-id="128a9-129">También puede ser útil en un sistema de compilación continua para determinar si es necesario ejecutar pasos de compilación que dependen de los cambios realizados en un archivo binario.</span><span class="sxs-lookup"><span data-stu-id="128a9-129">It can also be useful in a continuous build system for determining whether build steps that are dependent on changes to a binary need to be executed.</span></span>

## <a name="see-also"></a><span data-ttu-id="128a9-130">Vea también</span><span class="sxs-lookup"><span data-stu-id="128a9-130">See also</span></span>

- [<span data-ttu-id="128a9-131">Opciones del compilador de C#</span><span class="sxs-lookup"><span data-stu-id="128a9-131">C# Compiler Options</span></span>](../../../csharp/language-reference/compiler-options/index.md)
- [<span data-ttu-id="128a9-132">Administrar propiedades de soluciones y proyectos</span><span class="sxs-lookup"><span data-stu-id="128a9-132">Managing Project and Solution Properties</span></span>](/visualstudio/ide/managing-project-and-solution-properties)
