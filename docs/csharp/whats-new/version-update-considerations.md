---
title: Consideraciones sobre versiones y actualizaciones para desarrolladores de C#
description: La incorporación de nuevas características de lenguajes en la biblioteca puede afectar al código que la utiliza.
ms.date: 09/19/2018
ms.openlocfilehash: 3ffe2f6fd64a391fddf28233dccb022c95851884
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/14/2020
ms.locfileid: "79398152"
---
# <a name="version-and-update-considerations-for-c-developers"></a><span data-ttu-id="5a362-103">Consideraciones sobre versiones y actualizaciones para desarrolladores de C#</span><span class="sxs-lookup"><span data-stu-id="5a362-103">Version and update considerations for C# developers</span></span>

<span data-ttu-id="5a362-104">La compatibilidad es un objetivo muy importante cuando se agregan nuevas características al lenguaje C#.</span><span class="sxs-lookup"><span data-stu-id="5a362-104">Compatibility is a very important goal as new features are added to the C# language.</span></span> <span data-ttu-id="5a362-105">En la mayoría de los casos, se puede volver a compilar el código existente con una nueva versión de compilador sin ningún problema.</span><span class="sxs-lookup"><span data-stu-id="5a362-105">In almost all cases, existing code can be recompiled with a new compiler version without any issue.</span></span>

<span data-ttu-id="5a362-106">Al adoptar nuevas características del lenguaje en una biblioteca, puede requerirse más atención.</span><span class="sxs-lookup"><span data-stu-id="5a362-106">More care may be required when you adopt new language features in a library.</span></span> <span data-ttu-id="5a362-107">Puede crear una biblioteca con características que se encuentran en la última versión y necesita asegurarse de que las aplicaciones creadas con versiones anteriores del compilador pueden usarla.</span><span class="sxs-lookup"><span data-stu-id="5a362-107">You may be creating a new library with features found in the latest version and need to ensure apps built using previous versions of the compiler can use it.</span></span> <span data-ttu-id="5a362-108">O bien puede actualizar una biblioteca existente, con la posibilidad de que muchos de los usuarios aún no tengan versiones actualizadas.</span><span class="sxs-lookup"><span data-stu-id="5a362-108">Or you may be upgrading an existing library and many of your users may not have upgraded versions yet.</span></span> <span data-ttu-id="5a362-109">Cuando tome decisiones sobre la adopción de nuevas características, se deberán tener en cuenta dos variaciones de compatibilidad: compatibilidad binaria y compatibilidad con el origen.</span><span class="sxs-lookup"><span data-stu-id="5a362-109">As you make decisions on adopting new features, you'll need to consider two variations of compatibility: source compatible and binary compatible.</span></span>

## <a name="binary-compatible-changes"></a><span data-ttu-id="5a362-110">Cambios compatibles con elementos binarios</span><span class="sxs-lookup"><span data-stu-id="5a362-110">Binary compatible changes</span></span>

<span data-ttu-id="5a362-111">Los cambios en la biblioteca son **compatibles con elementos binarios** cuando se puede utilizar la biblioteca actualizada sin tener que volver a crear aplicaciones y bibliotecas que la usan.</span><span class="sxs-lookup"><span data-stu-id="5a362-111">Changes to your library are **binary compatible** when your updated library can be used without rebuilding applications and libraries that use it.</span></span> <span data-ttu-id="5a362-112">No es necesario volver a compilar ensamblados dependientes ni realizar ningún cambio en el código fuente.</span><span class="sxs-lookup"><span data-stu-id="5a362-112">Dependent assemblies are not required to be rebuilt, nor are any source code changes required.</span></span> <span data-ttu-id="5a362-113">Los cambios compatibles con los elementos binarios también son compatibles con el origen.</span><span class="sxs-lookup"><span data-stu-id="5a362-113">Binary compatible changes are also source compatible changes.</span></span>

## <a name="source-compatible-changes"></a><span data-ttu-id="5a362-114">Cambios compatibles con el origen</span><span class="sxs-lookup"><span data-stu-id="5a362-114">Source compatible changes</span></span>

<span data-ttu-id="5a362-115">Los cambios en la biblioteca son **compatibles con el origen** cuando las aplicaciones y bibliotecas que usan la biblioteca no requieren cambios de código fuente, pero el origen debe volver a compilarse con la nueva versión para que funcione correctamente.</span><span class="sxs-lookup"><span data-stu-id="5a362-115">Changes to your library are **source compatible** when applications and libraries that use your library do not require source code changes, but the source must be recompiled against the new version to work correctly.</span></span>

## <a name="incompatible-changes"></a><span data-ttu-id="5a362-116">Cambios incompatibles</span><span class="sxs-lookup"><span data-stu-id="5a362-116">Incompatible changes</span></span>

<span data-ttu-id="5a362-117">Si un cambio no es **compatible con el origen** ni es **compatible con los elementos binarios**, se necesitan cambios del código junto con la recompilación en las bibliotecas y aplicaciones dependientes.</span><span class="sxs-lookup"><span data-stu-id="5a362-117">If a change is neither **source compatible** nor **binary compatible**, source code changes along with recompilation are required in dependent libraries and applications.</span></span>

## <a name="evaluate-your-library"></a><span data-ttu-id="5a362-118">Evaluar la biblioteca</span><span class="sxs-lookup"><span data-stu-id="5a362-118">Evaluate your library</span></span>

<span data-ttu-id="5a362-119">Estos conceptos de compatibilidad afectan a las declaraciones públicas y protegidas de la biblioteca, no a su implementación interna.</span><span class="sxs-lookup"><span data-stu-id="5a362-119">These compatibility concepts affect the public and protected declarations for your library, not its internal implementation.</span></span> <span data-ttu-id="5a362-120">La adopción interna de nuevas características siempre es **compatible con los elementos binarios**.</span><span class="sxs-lookup"><span data-stu-id="5a362-120">Adopting any new features internally are always **binary compatible**.</span></span>  

<span data-ttu-id="5a362-121">Los cambios **compatibles con los elementos binarios** proporcionan la nueva sintaxis que genera el mismo código compilado para las declaraciones públicas que la sintaxis anterior.</span><span class="sxs-lookup"><span data-stu-id="5a362-121">**Binary compatible** changes provide new syntax that generates the same compiled code for public declarations as the older syntax.</span></span> <span data-ttu-id="5a362-122">Por ejemplo, cambiar un método a un miembro con cuerpo de expresión es un **cambio compatible con un elemento binario**:</span><span class="sxs-lookup"><span data-stu-id="5a362-122">For example, changing a method to an expression-bodied member is a **binary compatible** change:</span></span>

<span data-ttu-id="5a362-123">Código original:</span><span class="sxs-lookup"><span data-stu-id="5a362-123">Original code:</span></span>

```csharp
public double CalculateSquare(double value)
{
    return value * value;
}
```

<span data-ttu-id="5a362-124">Nuevo código:</span><span class="sxs-lookup"><span data-stu-id="5a362-124">New code:</span></span>

```csharp
public double CalculateSquare(double value) => value * value;
```

<span data-ttu-id="5a362-125">Los cambios **compatibles con el origen** presentan la sintaxis que cambia el código compilado para un miembro público, pero de una forma compatible con los sitios de llamada existentes.</span><span class="sxs-lookup"><span data-stu-id="5a362-125">**Source compatible** changes introduce syntax that changes the compiled code for a public member, but in a way that is compatible with existing call sites.</span></span> <span data-ttu-id="5a362-126">Por ejemplo, cambiar una firma del método a partir de un parámetro de valor a `in` mediante un parámetro de referencia es compatible con el origen, pero no lo es con los elementos binarios:</span><span class="sxs-lookup"><span data-stu-id="5a362-126">For example, changing a method signature from a by value parameter to an `in` by reference parameter is source compatible, but not binary compatible:</span></span>

<span data-ttu-id="5a362-127">Código original:</span><span class="sxs-lookup"><span data-stu-id="5a362-127">Original code:</span></span>

```csharp
public double CalculateSquare(double value) => value * value;
```

<span data-ttu-id="5a362-128">Nuevo código:</span><span class="sxs-lookup"><span data-stu-id="5a362-128">New code:</span></span>

```csharp
public double CalculateSquare(in double value) => value * value;
```

<span data-ttu-id="5a362-129">En el artículo de [novedades](index.md), observe si la presentación de una característica que afecta a las declaraciones públicas es compatible con el origen o con los elementos binarios.</span><span class="sxs-lookup"><span data-stu-id="5a362-129">The [What's new](index.md) articles note if introducing a feature that affects public declarations is source compatible or binary compatible.</span></span>
