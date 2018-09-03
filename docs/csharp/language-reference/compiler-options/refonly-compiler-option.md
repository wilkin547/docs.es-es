---
title: -refonly (Opciones del compilador de C#)
ms.date: 07/08/2017
f1_keywords:
- /refonly
helpviewer_keywords:
- /refonly compiler option [C#]
- -refonly compiler option [C#]
- refonly compiler option [C#]
ms.openlocfilehash: c15308d27b504f22b266e28f6db0caf837ae36c5
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/01/2018
ms.locfileid: "43421216"
---
# <a name="-refonly-c-compiler-options"></a><span data-ttu-id="95051-102">-refonly (Opciones del compilador de C#)</span><span class="sxs-lookup"><span data-stu-id="95051-102">-refonly (C# Compiler Options)</span></span>

<span data-ttu-id="95051-103">La opción **-refonly** indica que un ensamblado de referencia debe mostrarse en lugar de un ensamblado de implementación, como el resultado principal.</span><span class="sxs-lookup"><span data-stu-id="95051-103">The **-refonly** option indicates that a reference assembly should be output instead of an implementation assembly, as the primary output.</span></span> <span data-ttu-id="95051-104">El parámetro `-refonly` deshabilita de forma automática la generación de archivos PDB, ya que los ensamblados de referencia no pueden ejecutarse.</span><span class="sxs-lookup"><span data-stu-id="95051-104">The `-refonly` parameter silently disables outputting PDBs, as reference assemblies cannot be executed.</span></span>

## <a name="syntax"></a><span data-ttu-id="95051-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="95051-105">Syntax</span></span>

```console
-refonly
```

## <a name="remarks"></a><span data-ttu-id="95051-106">Comentarios</span><span class="sxs-lookup"><span data-stu-id="95051-106">Remarks</span></span>

<span data-ttu-id="95051-107">Los ensamblados de solo metadatos tienen sus cuerpos de métodos reemplazados por un cuerpo `throw null` único, pero incluyen todos los miembros excepto los tipos anónimos.</span><span class="sxs-lookup"><span data-stu-id="95051-107">Metadata-only assemblies have their method bodies replaced with a single `throw null` body, but include all members except anonymous types.</span></span> <span data-ttu-id="95051-108">El motivo de usar cuerpos `throw null` (en lugar de no usar ningún cuerpo) es que PEVerify pueda ejecutar y pasar (por lo tanto, validar la integridad de los metadatos).</span><span class="sxs-lookup"><span data-stu-id="95051-108">The reason for using `throw null` bodies (as opposed to no bodies) is so that PEVerify could run and pass (thus validating the completeness of the metadata).</span></span>

<span data-ttu-id="95051-109">Los ensamblados de referencia incluyen un atributo `ReferenceAssembly` de nivel de ensamblado.</span><span class="sxs-lookup"><span data-stu-id="95051-109">Reference assemblies include an assembly-level `ReferenceAssembly` attribute.</span></span> <span data-ttu-id="95051-110">Este atributo puede especificarse en el origen (por lo tanto, el compilador no necesitará sintetizarlo).</span><span class="sxs-lookup"><span data-stu-id="95051-110">This attribute may be specified in source (then the compiler won't need to synthesize it).</span></span> <span data-ttu-id="95051-111">Debido a este atributo, los tiempos de ejecución rechazarán cargar ensamblados de referencia para su ejecución (pero todavía pueden cargarse en modo de solo reflexión).</span><span class="sxs-lookup"><span data-stu-id="95051-111">Because of this attribute, runtimes will refuse to load reference assemblies for execution (but they can still be loaded in reflection-only mode).</span></span> <span data-ttu-id="95051-112">Las herramientas que se reflejan en ensamblados necesitan asegurarse de que cargan ensamblados de referencia en el modo de solo reflexión, de otro modo, recibirán un error typeload del runtime.</span><span class="sxs-lookup"><span data-stu-id="95051-112">Tools that reflect on assemblies need to ensure they load reference assemblies as reflection-only, otherwise they will receive a typeload error from the runtime.</span></span>

<span data-ttu-id="95051-113">Los ensamblados de referencia también quitan los metadatos (miembros privados) de los ensamblados de solo metadatos:</span><span class="sxs-lookup"><span data-stu-id="95051-113">Reference assemblies further remove metadata (private members) from metadata-only assemblies:</span></span>

- <span data-ttu-id="95051-114">Un ensamblado de referencia solo tiene referencias para lo que necesita en la superficie de la API.</span><span class="sxs-lookup"><span data-stu-id="95051-114">A reference assembly only has references for what it needs in the API surface.</span></span> <span data-ttu-id="95051-115">El ensamblado real puede tener referencias adicionales relacionadas con las implementaciones específicas.</span><span class="sxs-lookup"><span data-stu-id="95051-115">The real assembly may have additional references related to specific implementations.</span></span> <span data-ttu-id="95051-116">Por ejemplo, el ensamblado de referencia de `class C { private void M() { dynamic d = 1; ... } }` no hace referencia a ningún tipo necesario para `dynamic`.</span><span class="sxs-lookup"><span data-stu-id="95051-116">For instance, the reference assembly for `class C { private void M() { dynamic d = 1; ... } }` does not reference any types required for `dynamic`.</span></span>
- <span data-ttu-id="95051-117">Los miembros de función privados (métodos, propiedades y eventos) se quitan en los casos donde su retirada no afecta a la compilación de manera visible.</span><span class="sxs-lookup"><span data-stu-id="95051-117">Private function-members (methods, properties, and events) are removed in cases where their removal doesn't observably impact compilation.</span></span> <span data-ttu-id="95051-118">Si no hay ningún atributo `InternalsVisibleTo`, haga lo mismo para los miembros de función internos.</span><span class="sxs-lookup"><span data-stu-id="95051-118">If there are no `InternalsVisibleTo` attributes, do the same for internal function-members.</span></span>
- <span data-ttu-id="95051-119">Pero todos los tipos (incluidos los tipos anidados o privados) se conservan en los ensamblados de referencia.</span><span class="sxs-lookup"><span data-stu-id="95051-119">But all types (including private or nested types) are kept in reference assemblies.</span></span> <span data-ttu-id="95051-120">Se conservan todos los atributos (incluso los internos).</span><span class="sxs-lookup"><span data-stu-id="95051-120">All attributes are kept (even internal ones).</span></span>
- <span data-ttu-id="95051-121">Se conservan todos los métodos virtuales.</span><span class="sxs-lookup"><span data-stu-id="95051-121">All virtual methods are kept.</span></span> <span data-ttu-id="95051-122">Se mantienen las implementaciones explícitas de interfaces.</span><span class="sxs-lookup"><span data-stu-id="95051-122">Explicit interface implementations are kept.</span></span> <span data-ttu-id="95051-123">Se conservan los eventos y propiedades que se han implementado explícitamente, ya que sus descriptores de acceso son virtuales (y por lo tanto se conservan).</span><span class="sxs-lookup"><span data-stu-id="95051-123">Explicitly implemented properties and events are kept, as their accessors are virtual (and are therefore kept).</span></span>
- <span data-ttu-id="95051-124">Se conservan todos los campos de un struct.</span><span class="sxs-lookup"><span data-stu-id="95051-124">All fields of a struct are kept.</span></span> <span data-ttu-id="95051-125">(Es un candidato para el refinamiento posterior de C#-7.1)</span><span class="sxs-lookup"><span data-stu-id="95051-125">(This is a candidate for post-C#-7.1 refinement)</span></span>

<span data-ttu-id="95051-126">Las opciones `-refonly` y [`-refout`](refout-compiler-option.md) son mutuamente excluyentes.</span><span class="sxs-lookup"><span data-stu-id="95051-126">The `-refonly` and [`-refout`](refout-compiler-option.md) options are mutually exclusive.</span></span>

## <a name="see-also"></a><span data-ttu-id="95051-127">Vea también</span><span class="sxs-lookup"><span data-stu-id="95051-127">See also</span></span>

- [<span data-ttu-id="95051-128">Opciones del compilador de C#</span><span class="sxs-lookup"><span data-stu-id="95051-128">C# Compiler Options</span></span>](../../../csharp/language-reference/compiler-options/index.md)  
- [<span data-ttu-id="95051-129">Administrar propiedades de soluciones y proyectos</span><span class="sxs-lookup"><span data-stu-id="95051-129">Managing Project and Solution Properties</span></span>](/visualstudio/ide/managing-project-and-solution-properties)
