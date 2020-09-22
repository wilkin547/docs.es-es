---
description: 'private protected: Referencia de C#'
title: 'private protected: Referencia de C#'
ms.date: 11/15/2017
f1_keywords:
- privateprotected_CSharpKeyword
author: sputier
ms.openlocfilehash: e7ef6d691b43abd3d07321adfc0c166629ce9098
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/15/2020
ms.locfileid: "90537306"
---
# <a name="private-protected-c-reference"></a><span data-ttu-id="f3b82-103">private protected (Referencia de C#)</span><span class="sxs-lookup"><span data-stu-id="f3b82-103">private protected (C# Reference)</span></span>

<span data-ttu-id="f3b82-104">La combinación de palabras claves `private protected` es un modificador de acceso de miembro.</span><span class="sxs-lookup"><span data-stu-id="f3b82-104">The `private protected` keyword combination is a member access modifier.</span></span> <span data-ttu-id="f3b82-105">Los miembros private protected están accesibles para los tipos que se deriven de la clase contenedora, pero solo desde dentro del ensamblado correspondiente que lo contenga.</span><span class="sxs-lookup"><span data-stu-id="f3b82-105">A private protected member is accessible by types derived from the containing class, but only within its containing assembly.</span></span> <span data-ttu-id="f3b82-106">Para obtener una comparación de `private protected` con los demás modificadores de acceso, vea [Niveles de accesibilidad](accessibility-levels.md).</span><span class="sxs-lookup"><span data-stu-id="f3b82-106">For a comparison of `private protected` with the other access modifiers, see [Accessibility Levels](accessibility-levels.md).</span></span>

> [!NOTE]
> <span data-ttu-id="f3b82-107">El modificador de acceso `private protected` es válido en C# versión 7.2 y versiones posteriores.</span><span class="sxs-lookup"><span data-stu-id="f3b82-107">The `private protected` access modifier is valid in C# version 7.2 and later.</span></span>

## <a name="example"></a><span data-ttu-id="f3b82-108">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="f3b82-108">Example</span></span>

<span data-ttu-id="f3b82-109">Se puede tener acceso a un miembro private protected de una clase base desde tipos derivados en el ensamblado que lo contiene solo si el tipo estático de la variable es el tipo de clase derivada.</span><span class="sxs-lookup"><span data-stu-id="f3b82-109">A private protected member of a base class is accessible from derived types in its containing assembly only if the static type of the variable is the derived class type.</span></span> <span data-ttu-id="f3b82-110">Por ejemplo, vea el siguiente segmento de código:</span><span class="sxs-lookup"><span data-stu-id="f3b82-110">For example, consider the following code segment:</span></span>

```csharp
public class BaseClass
{
    private protected int myValue = 0;
}

public class DerivedClass1 : BaseClass
{
    void Access()
    {
        var baseObject = new BaseClass();

        // Error CS1540, because myValue can only be accessed by
        // classes derived from BaseClass.
        // baseObject.myValue = 5;

        // OK, accessed through the current derived class instance
        myValue = 5;
    }
}
```

```csharp
// Assembly2.cs
// Compile with: /reference:Assembly1.dll
class DerivedClass2 : BaseClass
{
    void Access()
    {
        // Error CS0122, because myValue can only be
        // accessed by types in Assembly1
        // myValue = 10;
    }
}
```

<span data-ttu-id="f3b82-111">Este ejemplo contiene dos archivos, `Assembly1.cs` y `Assembly2.cs`.</span><span class="sxs-lookup"><span data-stu-id="f3b82-111">This example contains two files, `Assembly1.cs` and `Assembly2.cs`.</span></span>
<span data-ttu-id="f3b82-112">El primer archivo contiene una clase base pública, `BaseClass`, y un tipo derivado de ella, `DerivedClass1`.</span><span class="sxs-lookup"><span data-stu-id="f3b82-112">The first file contains a public base class, `BaseClass`, and a type derived from it, `DerivedClass1`.</span></span> <span data-ttu-id="f3b82-113">`BaseClass` posee un miembro private protected, `myValue`, al que `DerivedClass1` intenta tener acceso de dos maneras.</span><span class="sxs-lookup"><span data-stu-id="f3b82-113">`BaseClass` owns a private protected member, `myValue`, which `DerivedClass1` tries to access in two ways.</span></span> <span data-ttu-id="f3b82-114">El primer intento de acceso a `myValue` a través de una instancia de `BaseClass` generará un error.</span><span class="sxs-lookup"><span data-stu-id="f3b82-114">The first attempt to access `myValue` through an instance of `BaseClass` will produce an error.</span></span> <span data-ttu-id="f3b82-115">En cambio, el intento de usarlo como un miembro heredado en `DerivedClass1` se realizará correctamente.</span><span class="sxs-lookup"><span data-stu-id="f3b82-115">However, the attempt to use it as an inherited member in `DerivedClass1` will succeed.</span></span>

<span data-ttu-id="f3b82-116">En el segundo archivo, un intento de tener acceso a `myValue` como un miembro heredado de `DerivedClass2` generará un error, ya que solo está accesible para los tipos derivados en Assembly1.</span><span class="sxs-lookup"><span data-stu-id="f3b82-116">In the second file, an attempt to access `myValue` as an inherited member of `DerivedClass2` will produce an error, as it is only accessible by derived types in Assembly1.</span></span>

<span data-ttu-id="f3b82-117">Si `Assembly1.cs` contiene un elemento <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> que asigna un nombre a `Assembly2`, la clase derivada `DerivedClass1` tendrá acceso a los miembros `private protected` declarados en `BaseClass`.</span><span class="sxs-lookup"><span data-stu-id="f3b82-117">If `Assembly1.cs` contains an <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> that names `Assembly2`, the derived class `DerivedClass1` will have access to `private protected` members declared in `BaseClass`.</span></span> <span data-ttu-id="f3b82-118">`InternalsVisibleTo` hace que los miembros `private protected` sean visibles para las clases derivadas en otros ensamblados.</span><span class="sxs-lookup"><span data-stu-id="f3b82-118">`InternalsVisibleTo` makes `private protected` members visible to derived classes in other assemblies.</span></span>

<span data-ttu-id="f3b82-119">Los miembros de struct no pueden ser `private protected`, porque los structs no se heredan.</span><span class="sxs-lookup"><span data-stu-id="f3b82-119">Struct members cannot be `private protected` because the struct cannot be inherited.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="f3b82-120">Especificación del lenguaje C#</span><span class="sxs-lookup"><span data-stu-id="f3b82-120">C# language specification</span></span>

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a><span data-ttu-id="f3b82-121">Vea también</span><span class="sxs-lookup"><span data-stu-id="f3b82-121">See also</span></span>

- [<span data-ttu-id="f3b82-122">Referencia de C#</span><span class="sxs-lookup"><span data-stu-id="f3b82-122">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="f3b82-123">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="f3b82-123">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="f3b82-124">Palabras clave de C#</span><span class="sxs-lookup"><span data-stu-id="f3b82-124">C# Keywords</span></span>](index.md)
- [<span data-ttu-id="f3b82-125">Modificadores de acceso</span><span class="sxs-lookup"><span data-stu-id="f3b82-125">Access Modifiers</span></span>](access-modifiers.md)
- [<span data-ttu-id="f3b82-126">Niveles de accesibilidad</span><span class="sxs-lookup"><span data-stu-id="f3b82-126">Accessibility Levels</span></span>](accessibility-levels.md)
- [<span data-ttu-id="f3b82-127">Modificadores</span><span class="sxs-lookup"><span data-stu-id="f3b82-127">Modifiers</span></span>](index.md)
- [<span data-ttu-id="f3b82-128">public</span><span class="sxs-lookup"><span data-stu-id="f3b82-128">public</span></span>](public.md)
- [<span data-ttu-id="f3b82-129">private</span><span class="sxs-lookup"><span data-stu-id="f3b82-129">private</span></span>](private.md)
- [<span data-ttu-id="f3b82-130">internal</span><span class="sxs-lookup"><span data-stu-id="f3b82-130">internal</span></span>](internal.md)
- <span data-ttu-id="f3b82-131">[Security concerns for internal virtual keywords](/previous-versions/dotnet/netframework-4.0/heyd8kky(v=vs.100)) (Problemas de seguridad de palabras clave virtuales internas)</span><span class="sxs-lookup"><span data-stu-id="f3b82-131">[Security concerns for internal virtual keywords](/previous-versions/dotnet/netframework-4.0/heyd8kky(v=vs.100))</span></span>
