---
title: 'private protected: Referencia de C#'
ms.date: 11/15/2017
f1_keywords:
- privateprotected_CSharpKeyword
author: sputier
ms.openlocfilehash: 94ef55d7e13841f81b036f52659b215e22a3a0d7
ms.sourcegitcommit: 6f58a5f75ceeb936f8ee5b786e9adb81a9a3bee9
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/28/2020
ms.locfileid: "87301806"
---
# <a name="private-protected-c-reference"></a><span data-ttu-id="290ca-102">private protected (Referencia de C#)</span><span class="sxs-lookup"><span data-stu-id="290ca-102">private protected (C# Reference)</span></span>

<span data-ttu-id="290ca-103">La combinación de palabras claves `private protected` es un modificador de acceso de miembro.</span><span class="sxs-lookup"><span data-stu-id="290ca-103">The `private protected` keyword combination is a member access modifier.</span></span> <span data-ttu-id="290ca-104">Los miembros private protected están accesibles para los tipos que se deriven de la clase contenedora, pero solo desde dentro del ensamblado correspondiente que lo contenga.</span><span class="sxs-lookup"><span data-stu-id="290ca-104">A private protected member is accessible by types derived from the containing class, but only within its containing assembly.</span></span> <span data-ttu-id="290ca-105">Para obtener una comparación de `private protected` con los demás modificadores de acceso, vea [Niveles de accesibilidad](accessibility-levels.md).</span><span class="sxs-lookup"><span data-stu-id="290ca-105">For a comparison of `private protected` with the other access modifiers, see [Accessibility Levels](accessibility-levels.md).</span></span>

> [!NOTE]
> <span data-ttu-id="290ca-106">El modificador de acceso `private protected` es válido en C# versión 7.2 y versiones posteriores.</span><span class="sxs-lookup"><span data-stu-id="290ca-106">The `private protected` access modifier is valid in C# version 7.2 and later.</span></span>

## <a name="example"></a><span data-ttu-id="290ca-107">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="290ca-107">Example</span></span>

<span data-ttu-id="290ca-108">Se puede tener acceso a un miembro private protected de una clase base desde tipos derivados en el ensamblado que lo contiene solo si el tipo estático de la variable es el tipo de clase derivada.</span><span class="sxs-lookup"><span data-stu-id="290ca-108">A private protected member of a base class is accessible from derived types in its containing assembly only if the static type of the variable is the derived class type.</span></span> <span data-ttu-id="290ca-109">Por ejemplo, vea el siguiente segmento de código:</span><span class="sxs-lookup"><span data-stu-id="290ca-109">For example, consider the following code segment:</span></span>

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

<span data-ttu-id="290ca-110">Este ejemplo contiene dos archivos, `Assembly1.cs` y `Assembly2.cs`.</span><span class="sxs-lookup"><span data-stu-id="290ca-110">This example contains two files, `Assembly1.cs` and `Assembly2.cs`.</span></span>
<span data-ttu-id="290ca-111">El primer archivo contiene una clase base pública, `BaseClass`, y un tipo derivado de ella, `DerivedClass1`.</span><span class="sxs-lookup"><span data-stu-id="290ca-111">The first file contains a public base class, `BaseClass`, and a type derived from it, `DerivedClass1`.</span></span> <span data-ttu-id="290ca-112">`BaseClass` posee un miembro private protected, `myValue`, al que `DerivedClass1` intenta tener acceso de dos maneras.</span><span class="sxs-lookup"><span data-stu-id="290ca-112">`BaseClass` owns a private protected member, `myValue`, which `DerivedClass1` tries to access in two ways.</span></span> <span data-ttu-id="290ca-113">El primer intento de acceso a `myValue` a través de una instancia de `BaseClass` generará un error.</span><span class="sxs-lookup"><span data-stu-id="290ca-113">The first attempt to access `myValue` through an instance of `BaseClass` will produce an error.</span></span> <span data-ttu-id="290ca-114">En cambio, el intento de usarlo como un miembro heredado en `DerivedClass1` se realizará correctamente.</span><span class="sxs-lookup"><span data-stu-id="290ca-114">However, the attempt to use it as an inherited member in `DerivedClass1` will succeed.</span></span>

<span data-ttu-id="290ca-115">En el segundo archivo, un intento de tener acceso a `myValue` como un miembro heredado de `DerivedClass2` generará un error, ya que solo está accesible para los tipos derivados en Assembly1.</span><span class="sxs-lookup"><span data-stu-id="290ca-115">In the second file, an attempt to access `myValue` as an inherited member of `DerivedClass2` will produce an error, as it is only accessible by derived types in Assembly1.</span></span>

<span data-ttu-id="290ca-116">Si `Assembly1.cs` contiene un elemento <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> que asigna un nombre a `Assembly2`, la clase derivada `DerivedClass1` tendrá acceso a los miembros `private protected` declarados en `BaseClass`.</span><span class="sxs-lookup"><span data-stu-id="290ca-116">If `Assembly1.cs` contains an <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> that names `Assembly2`, the derived class `DerivedClass1` will have access to `private protected` members declared in `BaseClass`.</span></span> <span data-ttu-id="290ca-117">`InternalsVisibleTo` hace que los miembros `private protected` sean visibles para las clases derivadas en otros ensamblados.</span><span class="sxs-lookup"><span data-stu-id="290ca-117">`InternalsVisibleTo` makes `private protected` members visible to derived classes in other assemblies.</span></span>

<span data-ttu-id="290ca-118">Los miembros de struct no pueden ser `private protected`, porque los structs no se heredan.</span><span class="sxs-lookup"><span data-stu-id="290ca-118">Struct members cannot be `private protected` because the struct cannot be inherited.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="290ca-119">Especificación del lenguaje C#</span><span class="sxs-lookup"><span data-stu-id="290ca-119">C# language specification</span></span>

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a><span data-ttu-id="290ca-120">Vea también</span><span class="sxs-lookup"><span data-stu-id="290ca-120">See also</span></span>

- [<span data-ttu-id="290ca-121">Referencia de C#</span><span class="sxs-lookup"><span data-stu-id="290ca-121">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="290ca-122">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="290ca-122">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="290ca-123">Palabras clave de C#</span><span class="sxs-lookup"><span data-stu-id="290ca-123">C# Keywords</span></span>](index.md)
- [<span data-ttu-id="290ca-124">Modificadores de acceso</span><span class="sxs-lookup"><span data-stu-id="290ca-124">Access Modifiers</span></span>](access-modifiers.md)
- [<span data-ttu-id="290ca-125">Niveles de accesibilidad</span><span class="sxs-lookup"><span data-stu-id="290ca-125">Accessibility Levels</span></span>](accessibility-levels.md)
- [<span data-ttu-id="290ca-126">Modificadores</span><span class="sxs-lookup"><span data-stu-id="290ca-126">Modifiers</span></span>](index.md)
- [<span data-ttu-id="290ca-127">public</span><span class="sxs-lookup"><span data-stu-id="290ca-127">public</span></span>](public.md)
- [<span data-ttu-id="290ca-128">private</span><span class="sxs-lookup"><span data-stu-id="290ca-128">private</span></span>](private.md)
- [<span data-ttu-id="290ca-129">internal</span><span class="sxs-lookup"><span data-stu-id="290ca-129">internal</span></span>](internal.md)
- <span data-ttu-id="290ca-130">[Security concerns for internal virtual keywords](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/heyd8kky(v=vs.100)) (Problemas de seguridad de palabras clave virtuales internas)</span><span class="sxs-lookup"><span data-stu-id="290ca-130">[Security concerns for internal virtual keywords](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/heyd8kky(v=vs.100))</span></span>
