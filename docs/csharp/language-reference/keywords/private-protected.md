---
description: 'private protected: Referencia de C#'
title: 'private protected: Referencia de C#'
ms.date: 11/15/2017
f1_keywords:
- privateprotected_CSharpKeyword
author: sputier
ms.openlocfilehash: d83fd2a570b735a029bd2a79ad24e30d235dc5fb
ms.sourcegitcommit: d579fb5e4b46745fd0f1f8874c94c6469ce58604
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/30/2020
ms.locfileid: "89117966"
---
# <a name="private-protected-c-reference"></a><span data-ttu-id="f9f60-103">private protected (Referencia de C#)</span><span class="sxs-lookup"><span data-stu-id="f9f60-103">private protected (C# Reference)</span></span>

<span data-ttu-id="f9f60-104">La combinación de palabras claves `private protected` es un modificador de acceso de miembro.</span><span class="sxs-lookup"><span data-stu-id="f9f60-104">The `private protected` keyword combination is a member access modifier.</span></span> <span data-ttu-id="f9f60-105">Los miembros private protected están accesibles para los tipos que se deriven de la clase contenedora, pero solo desde dentro del ensamblado correspondiente que lo contenga.</span><span class="sxs-lookup"><span data-stu-id="f9f60-105">A private protected member is accessible by types derived from the containing class, but only within its containing assembly.</span></span> <span data-ttu-id="f9f60-106">Para obtener una comparación de `private protected` con los demás modificadores de acceso, vea [Niveles de accesibilidad](accessibility-levels.md).</span><span class="sxs-lookup"><span data-stu-id="f9f60-106">For a comparison of `private protected` with the other access modifiers, see [Accessibility Levels](accessibility-levels.md).</span></span>

> [!NOTE]
> <span data-ttu-id="f9f60-107">El modificador de acceso `private protected` es válido en C# versión 7.2 y versiones posteriores.</span><span class="sxs-lookup"><span data-stu-id="f9f60-107">The `private protected` access modifier is valid in C# version 7.2 and later.</span></span>

## <a name="example"></a><span data-ttu-id="f9f60-108">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="f9f60-108">Example</span></span>

<span data-ttu-id="f9f60-109">Se puede tener acceso a un miembro private protected de una clase base desde tipos derivados en el ensamblado que lo contiene solo si el tipo estático de la variable es el tipo de clase derivada.</span><span class="sxs-lookup"><span data-stu-id="f9f60-109">A private protected member of a base class is accessible from derived types in its containing assembly only if the static type of the variable is the derived class type.</span></span> <span data-ttu-id="f9f60-110">Por ejemplo, vea el siguiente segmento de código:</span><span class="sxs-lookup"><span data-stu-id="f9f60-110">For example, consider the following code segment:</span></span>

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

<span data-ttu-id="f9f60-111">Este ejemplo contiene dos archivos, `Assembly1.cs` y `Assembly2.cs`.</span><span class="sxs-lookup"><span data-stu-id="f9f60-111">This example contains two files, `Assembly1.cs` and `Assembly2.cs`.</span></span>
<span data-ttu-id="f9f60-112">El primer archivo contiene una clase base pública, `BaseClass`, y un tipo derivado de ella, `DerivedClass1`.</span><span class="sxs-lookup"><span data-stu-id="f9f60-112">The first file contains a public base class, `BaseClass`, and a type derived from it, `DerivedClass1`.</span></span> <span data-ttu-id="f9f60-113">`BaseClass` posee un miembro private protected, `myValue`, al que `DerivedClass1` intenta tener acceso de dos maneras.</span><span class="sxs-lookup"><span data-stu-id="f9f60-113">`BaseClass` owns a private protected member, `myValue`, which `DerivedClass1` tries to access in two ways.</span></span> <span data-ttu-id="f9f60-114">El primer intento de acceso a `myValue` a través de una instancia de `BaseClass` generará un error.</span><span class="sxs-lookup"><span data-stu-id="f9f60-114">The first attempt to access `myValue` through an instance of `BaseClass` will produce an error.</span></span> <span data-ttu-id="f9f60-115">En cambio, el intento de usarlo como un miembro heredado en `DerivedClass1` se realizará correctamente.</span><span class="sxs-lookup"><span data-stu-id="f9f60-115">However, the attempt to use it as an inherited member in `DerivedClass1` will succeed.</span></span>

<span data-ttu-id="f9f60-116">En el segundo archivo, un intento de tener acceso a `myValue` como un miembro heredado de `DerivedClass2` generará un error, ya que solo está accesible para los tipos derivados en Assembly1.</span><span class="sxs-lookup"><span data-stu-id="f9f60-116">In the second file, an attempt to access `myValue` as an inherited member of `DerivedClass2` will produce an error, as it is only accessible by derived types in Assembly1.</span></span>

<span data-ttu-id="f9f60-117">Si `Assembly1.cs` contiene un elemento <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> que asigna un nombre a `Assembly2`, la clase derivada `DerivedClass1` tendrá acceso a los miembros `private protected` declarados en `BaseClass`.</span><span class="sxs-lookup"><span data-stu-id="f9f60-117">If `Assembly1.cs` contains an <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> that names `Assembly2`, the derived class `DerivedClass1` will have access to `private protected` members declared in `BaseClass`.</span></span> <span data-ttu-id="f9f60-118">`InternalsVisibleTo` hace que los miembros `private protected` sean visibles para las clases derivadas en otros ensamblados.</span><span class="sxs-lookup"><span data-stu-id="f9f60-118">`InternalsVisibleTo` makes `private protected` members visible to derived classes in other assemblies.</span></span>

<span data-ttu-id="f9f60-119">Los miembros de struct no pueden ser `private protected`, porque los structs no se heredan.</span><span class="sxs-lookup"><span data-stu-id="f9f60-119">Struct members cannot be `private protected` because the struct cannot be inherited.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="f9f60-120">Especificación del lenguaje C#</span><span class="sxs-lookup"><span data-stu-id="f9f60-120">C# language specification</span></span>

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a><span data-ttu-id="f9f60-121">Vea también</span><span class="sxs-lookup"><span data-stu-id="f9f60-121">See also</span></span>

- [<span data-ttu-id="f9f60-122">Referencia de C#</span><span class="sxs-lookup"><span data-stu-id="f9f60-122">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="f9f60-123">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="f9f60-123">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="f9f60-124">Palabras clave de C#</span><span class="sxs-lookup"><span data-stu-id="f9f60-124">C# Keywords</span></span>](index.md)
- [<span data-ttu-id="f9f60-125">Modificadores de acceso</span><span class="sxs-lookup"><span data-stu-id="f9f60-125">Access Modifiers</span></span>](access-modifiers.md)
- [<span data-ttu-id="f9f60-126">Niveles de accesibilidad</span><span class="sxs-lookup"><span data-stu-id="f9f60-126">Accessibility Levels</span></span>](accessibility-levels.md)
- [<span data-ttu-id="f9f60-127">Modificadores</span><span class="sxs-lookup"><span data-stu-id="f9f60-127">Modifiers</span></span>](index.md)
- [<span data-ttu-id="f9f60-128">public</span><span class="sxs-lookup"><span data-stu-id="f9f60-128">public</span></span>](public.md)
- [<span data-ttu-id="f9f60-129">private</span><span class="sxs-lookup"><span data-stu-id="f9f60-129">private</span></span>](private.md)
- [<span data-ttu-id="f9f60-130">internal</span><span class="sxs-lookup"><span data-stu-id="f9f60-130">internal</span></span>](internal.md)
- <span data-ttu-id="f9f60-131">[Security concerns for internal virtual keywords](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/heyd8kky(v=vs.100)) (Problemas de seguridad de palabras clave virtuales internas)</span><span class="sxs-lookup"><span data-stu-id="f9f60-131">[Security concerns for internal virtual keywords](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/heyd8kky(v=vs.100))</span></span>
