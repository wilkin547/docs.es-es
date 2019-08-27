---
title: -refout (Opciones del compilador de C#)
ms.date: 08/08/2017
f1_keywords:
- /refout
helpviewer_keywords:
- refout compiler option [C#]
- /refout compiler option [C#]
- -refout compiler option [C#]
ms.openlocfilehash: 97cbf540527d0449387b71bb1d97df95b6a4aba4
ms.sourcegitcommit: 986f836f72ef10876878bd6217174e41464c145a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/19/2019
ms.locfileid: "69602501"
---
# <a name="-refout-c-compiler-options"></a><span data-ttu-id="59432-102">-refout (Opciones del compilador de C#)</span><span class="sxs-lookup"><span data-stu-id="59432-102">-refout (C# Compiler Options)</span></span>

<span data-ttu-id="59432-103">La opción **-refout** especifica una ruta de archivo donde el ensamblado de referencia debe mostrarse.</span><span class="sxs-lookup"><span data-stu-id="59432-103">The **-refout** option specifies a file path where the reference assembly should be output.</span></span> <span data-ttu-id="59432-104">Esto se traduce en `metadataPeStream` en la API de emisión.</span><span class="sxs-lookup"><span data-stu-id="59432-104">This translates to `metadataPeStream` in the Emit API.</span></span> <span data-ttu-id="59432-105">Esta opción corresponde a la propiedad de proyecto [ProduceReferenceAssembly](/visualstudio/msbuild/common-msbuild-project-properties) de MSBuild.</span><span class="sxs-lookup"><span data-stu-id="59432-105">This option corresponds to the [ProduceReferenceAssembly](/visualstudio/msbuild/common-msbuild-project-properties) project property of MSBuild.</span></span>

## <a name="syntax"></a><span data-ttu-id="59432-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="59432-106">Syntax</span></span>

```console
-refout:filepath
```

## <a name="arguments"></a><span data-ttu-id="59432-107">Argumentos</span><span class="sxs-lookup"><span data-stu-id="59432-107">Arguments</span></span>

 <span data-ttu-id="59432-108">`filepath` La ruta de archivo del ensamblado de referencia.</span><span class="sxs-lookup"><span data-stu-id="59432-108">`filepath` The filepath for the reference assembly.</span></span> <span data-ttu-id="59432-109">Generalmente debe coincidir con el ensamblado principal.</span><span class="sxs-lookup"><span data-stu-id="59432-109">It should generally match that of the primary assembly.</span></span> <span data-ttu-id="59432-110">La convención recomendada (que se usa por MSBuild) es colocar el ensamblado de referencia en una subcarpeta "ref/" con relación al ensamblado principal.</span><span class="sxs-lookup"><span data-stu-id="59432-110">The recommended convention (used by MSBuild) is to place the reference assembly in a "ref/" sub-folder relative to the primary assembly.</span></span>

## <a name="remarks"></a><span data-ttu-id="59432-111">Comentarios</span><span class="sxs-lookup"><span data-stu-id="59432-111">Remarks</span></span>

<span data-ttu-id="59432-112">Los ensamblados de solo metadatos tienen sus cuerpos de métodos reemplazados por un cuerpo `throw null` único, pero incluyen todos los miembros excepto los tipos anónimos.</span><span class="sxs-lookup"><span data-stu-id="59432-112">Metadata-only assemblies have their method bodies replaced with a single `throw null` body, but include all members except anonymous types.</span></span> <span data-ttu-id="59432-113">El motivo de usar cuerpos `throw null` (en lugar de no usar ningún cuerpo) es que PEVerify pueda ejecutar y pasar (por lo tanto, validar la integridad de los metadatos).</span><span class="sxs-lookup"><span data-stu-id="59432-113">The reason for using `throw null` bodies (as opposed to no bodies) is so that PEVerify could run and pass (thus validating the completeness of the metadata).</span></span>

<span data-ttu-id="59432-114">Los ensamblados de referencia incluyen un atributo `ReferenceAssembly` de nivel de ensamblado.</span><span class="sxs-lookup"><span data-stu-id="59432-114">Reference assemblies include an assembly-level `ReferenceAssembly` attribute.</span></span> <span data-ttu-id="59432-115">Este atributo puede especificarse en el origen (por lo tanto, el compilador no necesitará sintetizarlo).</span><span class="sxs-lookup"><span data-stu-id="59432-115">This attribute may be specified in source (then the compiler won't need to synthesize it).</span></span> <span data-ttu-id="59432-116">Debido a este atributo, los tiempos de ejecución rechazarán cargar ensamblados de referencia para su ejecución (pero todavía pueden cargarse en modo de solo reflexión).</span><span class="sxs-lookup"><span data-stu-id="59432-116">Because of this attribute, runtimes will refuse to load reference assemblies for execution (but they can still be loaded in reflection-only mode).</span></span> <span data-ttu-id="59432-117">Las herramientas que se reflejan en ensamblados necesitan asegurarse de que cargan ensamblados de referencia en el modo de solo reflexión, de otro modo, recibirán un error typeload del runtime.</span><span class="sxs-lookup"><span data-stu-id="59432-117">Tools that reflect on assemblies need to ensure they load reference assemblies as reflection-only, otherwise they will receive a typeload error from the runtime.</span></span>

<span data-ttu-id="59432-118">Los ensamblados de referencia también quitan los metadatos (miembros privados) de los ensamblados de solo metadatos:</span><span class="sxs-lookup"><span data-stu-id="59432-118">Reference assemblies further remove metadata (private members) from metadata-only assemblies:</span></span>

- <span data-ttu-id="59432-119">Un ensamblado de referencia solo tiene referencias para lo que necesita en la superficie de la API.</span><span class="sxs-lookup"><span data-stu-id="59432-119">A reference assembly only has references for what it needs in the API surface.</span></span> <span data-ttu-id="59432-120">El ensamblado real puede tener referencias adicionales relacionadas con las implementaciones específicas.</span><span class="sxs-lookup"><span data-stu-id="59432-120">The real assembly may have additional references related to specific implementations.</span></span> <span data-ttu-id="59432-121">Por ejemplo, el ensamblado de referencia de `class C { private void M() { dynamic d = 1; ... } }` no hace referencia a ningún tipo necesario para `dynamic`.</span><span class="sxs-lookup"><span data-stu-id="59432-121">For instance, the reference assembly for `class C { private void M() { dynamic d = 1; ... } }` does not reference any types required for `dynamic`.</span></span>
- <span data-ttu-id="59432-122">Los miembros de función privados (métodos, propiedades y eventos) se quitan en los casos donde su retirada no afecta a la compilación de manera visible.</span><span class="sxs-lookup"><span data-stu-id="59432-122">Private function-members (methods, properties, and events) are removed in cases where their removal doesn't observably impact compilation.</span></span> <span data-ttu-id="59432-123">Si no hay ningún atributo <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute>, haga lo mismo para los miembros de función internos.</span><span class="sxs-lookup"><span data-stu-id="59432-123">If there are no <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> attributes, do the same for internal function-members.</span></span>
- <span data-ttu-id="59432-124">Pero todos los tipos (incluidos los tipos anidados o privados) se conservan en los ensamblados de referencia.</span><span class="sxs-lookup"><span data-stu-id="59432-124">But all types (including private or nested types) are kept in reference assemblies.</span></span> <span data-ttu-id="59432-125">Se conservan todos los atributos (incluso los internos).</span><span class="sxs-lookup"><span data-stu-id="59432-125">All attributes are kept (even internal ones).</span></span>
- <span data-ttu-id="59432-126">Se conservan todos los métodos virtuales.</span><span class="sxs-lookup"><span data-stu-id="59432-126">All virtual methods are kept.</span></span> <span data-ttu-id="59432-127">Se mantienen las implementaciones explícitas de interfaces.</span><span class="sxs-lookup"><span data-stu-id="59432-127">Explicit interface implementations are kept.</span></span> <span data-ttu-id="59432-128">Se conservan los eventos y propiedades que se han implementado explícitamente, ya que sus descriptores de acceso son virtuales (y por lo tanto se conservan).</span><span class="sxs-lookup"><span data-stu-id="59432-128">Explicitly implemented properties and events are kept, as their accessors are virtual (and are therefore kept).</span></span>
- <span data-ttu-id="59432-129">Se conservan todos los campos de un struct.</span><span class="sxs-lookup"><span data-stu-id="59432-129">All fields of a struct are kept.</span></span> <span data-ttu-id="59432-130">(Es un candidato para el refinamiento posterior de C#-7.1)</span><span class="sxs-lookup"><span data-stu-id="59432-130">(This is a candidate for post-C#-7.1 refinement)</span></span>

<span data-ttu-id="59432-131">Las opciones `-refout` y [`-refonly`](refonly-compiler-option.md) son mutuamente excluyentes.</span><span class="sxs-lookup"><span data-stu-id="59432-131">The `-refout` and [`-refonly`](refonly-compiler-option.md) options are mutually exclusive.</span></span>

## <a name="see-also"></a><span data-ttu-id="59432-132">Vea también</span><span class="sxs-lookup"><span data-stu-id="59432-132">See also</span></span>

- [<span data-ttu-id="59432-133">Opciones del compilador de C#</span><span class="sxs-lookup"><span data-stu-id="59432-133">C# Compiler Options</span></span>](./index.md)
- [<span data-ttu-id="59432-134">Administrar propiedades de soluciones y proyectos</span><span class="sxs-lookup"><span data-stu-id="59432-134">Managing Project and Solution Properties</span></span>](/visualstudio/ide/managing-project-and-solution-properties)
