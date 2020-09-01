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
ms.openlocfilehash: 9d0bcc2957e5a666c21cdc2ce61e74fc90fe3530
ms.sourcegitcommit: d579fb5e4b46745fd0f1f8874c94c6469ce58604
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/30/2020
ms.locfileid: "89125831"
---
# <a name="-deterministic"></a><span data-ttu-id="22ec9-103">-deterministic</span><span class="sxs-lookup"><span data-stu-id="22ec9-103">-deterministic</span></span>

<span data-ttu-id="22ec9-104">Hace que el compilador genere un ensamblado cuya salida byte a byte es idéntica en todas las compilaciones para las entradas idénticas.</span><span class="sxs-lookup"><span data-stu-id="22ec9-104">Causes the compiler to produce an assembly whose byte-for-byte output is identical across compilations for identical inputs.</span></span>

## <a name="syntax"></a><span data-ttu-id="22ec9-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="22ec9-105">Syntax</span></span>

```console
-deterministic
```

## <a name="remarks"></a><span data-ttu-id="22ec9-106">Comentarios</span><span class="sxs-lookup"><span data-stu-id="22ec9-106">Remarks</span></span>

<span data-ttu-id="22ec9-107">De forma predeterminada, la salida del compilador para un conjunto determinado de entradas es única, ya que el compilador agrega una marca de tiempo y un GUID que se genera a partir de números aleatorios.</span><span class="sxs-lookup"><span data-stu-id="22ec9-107">By default, compiler output from a given set of inputs is unique, since the compiler adds a timestamp and a GUID that is generated from random numbers.</span></span> <span data-ttu-id="22ec9-108">Use la opción `-deterministic` para generar un *ensamblado determinista*, cuyo contenido binario es idéntico en todas las compilaciones, siempre y cuando la entrada siga siendo la misma.</span><span class="sxs-lookup"><span data-stu-id="22ec9-108">You use the `-deterministic` option to produce a *deterministic assembly*, one whose binary content is identical across compilations as long as the input remains the same.</span></span>

<span data-ttu-id="22ec9-109">El compilador tiene en cuenta las entradas siguientes con el fin de garantizar el determinismo:</span><span class="sxs-lookup"><span data-stu-id="22ec9-109">The compiler considers the following inputs for the purpose of determinism:</span></span>

- <span data-ttu-id="22ec9-110">La secuencia de parámetros de la línea de comandos.</span><span class="sxs-lookup"><span data-stu-id="22ec9-110">The sequence of command-line parameters.</span></span>
- <span data-ttu-id="22ec9-111">El contenido del archivo de respuesta .rsp del compilador.</span><span class="sxs-lookup"><span data-stu-id="22ec9-111">The contents of the compiler's .rsp response file.</span></span>
- <span data-ttu-id="22ec9-112">La versión exacta del compilador que se usa y los ensamblados a los que se hace referencia.</span><span class="sxs-lookup"><span data-stu-id="22ec9-112">The precise version of the compiler used, and its referenced assemblies.</span></span>
- <span data-ttu-id="22ec9-113">La ruta de acceso del directorio actual.</span><span class="sxs-lookup"><span data-stu-id="22ec9-113">The current directory path.</span></span>
- <span data-ttu-id="22ec9-114">El contenido binario de todos los archivos pasados explícitamente al compilador, ya sea de manera directa o indirecta, incluidos los siguientes:</span><span class="sxs-lookup"><span data-stu-id="22ec9-114">The binary contents of all files explicitly passed to the compiler either directly or indirectly, including:</span></span>
  - <span data-ttu-id="22ec9-115">Archivos de código fuente</span><span class="sxs-lookup"><span data-stu-id="22ec9-115">Source files</span></span>
  - <span data-ttu-id="22ec9-116">Ensamblados a los que se hace referencia</span><span class="sxs-lookup"><span data-stu-id="22ec9-116">Referenced assemblies</span></span>
  - <span data-ttu-id="22ec9-117">Módulos a los que se hace referencia</span><span class="sxs-lookup"><span data-stu-id="22ec9-117">Referenced modules</span></span>
  - <span data-ttu-id="22ec9-118">Recursos</span><span class="sxs-lookup"><span data-stu-id="22ec9-118">Resources</span></span>
  - <span data-ttu-id="22ec9-119">Archivo de clave de nombre seguro</span><span class="sxs-lookup"><span data-stu-id="22ec9-119">The strong name key file</span></span>
  - <span data-ttu-id="22ec9-120">Archivos de respuesta @</span><span class="sxs-lookup"><span data-stu-id="22ec9-120">@ response files</span></span>
  - <span data-ttu-id="22ec9-121">Analizadores</span><span class="sxs-lookup"><span data-stu-id="22ec9-121">Analyzers</span></span>
  - <span data-ttu-id="22ec9-122">Conjuntos de reglas</span><span class="sxs-lookup"><span data-stu-id="22ec9-122">Rulesets</span></span>
  - <span data-ttu-id="22ec9-123">Archivos adicionales que podrían usar los analizadores</span><span class="sxs-lookup"><span data-stu-id="22ec9-123">Additional files that may be used by analyzers</span></span>
- <span data-ttu-id="22ec9-124">La referencia cultural actual (para el idioma en el que se producen los diagnósticos y los mensajes de excepción).</span><span class="sxs-lookup"><span data-stu-id="22ec9-124">The current culture (for the language in which diagnostics and exception messages are produced).</span></span>
- <span data-ttu-id="22ec9-125">La codificación predeterminada (o página de códigos actual) si no se especifica la codificación.</span><span class="sxs-lookup"><span data-stu-id="22ec9-125">The default encoding (or the current code page) if the encoding is not specified.</span></span>
- <span data-ttu-id="22ec9-126">La existencia (o la inexistencia) de archivos y su contenido en las rutas de búsqueda del compilador (especificada, por ejemplo, mediante `-lib` o `-recurse`).</span><span class="sxs-lookup"><span data-stu-id="22ec9-126">The existence, non-existence, and contents of files on the compiler's search paths (specified, for example, by `-lib` or `-recurse`).</span></span>
- <span data-ttu-id="22ec9-127">La plataforma CLR en la que se ejecuta el compilador.</span><span class="sxs-lookup"><span data-stu-id="22ec9-127">The CLR platform on which the compiler is run.</span></span>
- <span data-ttu-id="22ec9-128">El valor de `%LIBPATH%`, que pueden afectar a la carga de dependencias del analizador.</span><span class="sxs-lookup"><span data-stu-id="22ec9-128">The value of `%LIBPATH%`, which can affect analyzer dependency loading.</span></span>

<span data-ttu-id="22ec9-129">Cuando los orígenes están disponibles públicamente, se puede usar la compilación determinista para establecer si un archivo binario se compila a partir de una fuente de confianza.</span><span class="sxs-lookup"><span data-stu-id="22ec9-129">When sources are publicly available, deterministic compilation can be used for establishing whether a binary is compiled from a trusted source.</span></span> <span data-ttu-id="22ec9-130">También puede ser útil en un sistema de compilación continua para determinar si es necesario ejecutar pasos de compilación que dependen de los cambios realizados en un archivo binario.</span><span class="sxs-lookup"><span data-stu-id="22ec9-130">It can also be useful in a continuous build system for determining whether build steps that are dependent on changes to a binary need to be executed.</span></span>

## <a name="see-also"></a><span data-ttu-id="22ec9-131">Vea también</span><span class="sxs-lookup"><span data-stu-id="22ec9-131">See also</span></span>

- [<span data-ttu-id="22ec9-132">Opciones del compilador de C#</span><span class="sxs-lookup"><span data-stu-id="22ec9-132">C# Compiler Options</span></span>](./index.md)
- [<span data-ttu-id="22ec9-133">Administrar propiedades de soluciones y proyectos</span><span class="sxs-lookup"><span data-stu-id="22ec9-133">Managing Project and Solution Properties</span></span>](/visualstudio/ide/managing-project-and-solution-properties)
