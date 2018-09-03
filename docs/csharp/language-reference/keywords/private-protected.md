---
title: private protected (Referencia de C#)
ms.date: 11/15/2017
author: sputier
ms.openlocfilehash: 4a4ee999fe932674e854b1428ab33b33bc71d2ad
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/03/2018
ms.locfileid: "43419539"
---
# <a name="private-protected-c-reference"></a><span data-ttu-id="2c08d-102">private protected (Referencia de C#)</span><span class="sxs-lookup"><span data-stu-id="2c08d-102">private protected (C# Reference)</span></span>

<span data-ttu-id="2c08d-103">La combinación de palabras claves `private protected` es un modificador de acceso de miembro.</span><span class="sxs-lookup"><span data-stu-id="2c08d-103">The `private protected` keyword combination is a member access modifier.</span></span> <span data-ttu-id="2c08d-104">Los miembros private protected están accesibles para los tipos que se deriven de la clase contenedora, pero solo desde dentro del ensamblado correspondiente que lo contenga.</span><span class="sxs-lookup"><span data-stu-id="2c08d-104">A private protected member is accessible by types derived from the containing class, but only within its containing assembly.</span></span> <span data-ttu-id="2c08d-105">Para obtener una comparación de `private protected` con los demás modificadores de acceso, vea [Niveles de accesibilidad](accessibility-levels.md).</span><span class="sxs-lookup"><span data-stu-id="2c08d-105">For a comparison of `private protected` with the other access modifiers, see [Accessibility Levels](accessibility-levels.md).</span></span>

> [!NOTE]
> <span data-ttu-id="2c08d-106">El modificador de acceso `private protected` es válido en C# versión 7.2 y versiones posteriores.</span><span class="sxs-lookup"><span data-stu-id="2c08d-106">The `private protected` access modifier is valid in C# version 7.2 and later.</span></span>

## <a name="example"></a><span data-ttu-id="2c08d-107">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="2c08d-107">Example</span></span>

<span data-ttu-id="2c08d-108">Se puede tener acceso a un miembro private protected de una clase base desde tipos derivados en el ensamblado que lo contiene solo si el tipo estático de la variable es el tipo de clase derivada.</span><span class="sxs-lookup"><span data-stu-id="2c08d-108">A private protected member of a base class is accessible from derived types in its containing assembly only if the static type of the variable is the derived class type.</span></span> <span data-ttu-id="2c08d-109">Por ejemplo, vea el siguiente segmento de código:</span><span class="sxs-lookup"><span data-stu-id="2c08d-109">For example, consider the following code segment:</span></span>  

```csharp
// Assembly1.cs  
// Compile with: /target:library  
public class BaseClass
{
    private protected int myValue = 0;
}

public class DerivedClass1 : BaseClass
{
    void Access()
    {
        BaseClass baseObject = new BaseClass();

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

<span data-ttu-id="2c08d-110">Este ejemplo contiene dos archivos, `Assembly1.cs` y `Assembly2.cs`.</span><span class="sxs-lookup"><span data-stu-id="2c08d-110">This example contains two files, `Assembly1.cs` and `Assembly2.cs`.</span></span>
<span data-ttu-id="2c08d-111">El primer archivo contiene una clase base pública, `BaseClass`, y un tipo derivado de ella, `DerivedClass1`.</span><span class="sxs-lookup"><span data-stu-id="2c08d-111">The first file contains a public base class, `BaseClass`, and a type derived from it, `DerivedClass1`.</span></span> <span data-ttu-id="2c08d-112">`BaseClass` posee un miembro private protected, `myValue`, al que `DerivedClass1` intenta tener acceso de dos maneras.</span><span class="sxs-lookup"><span data-stu-id="2c08d-112">`BaseClass` owns a private protected member, `myValue`, which `DerivedClass1` tries to access in two ways.</span></span> <span data-ttu-id="2c08d-113">El primer intento de acceso a `myValue` a través de una instancia de `BaseClass` generará un error.</span><span class="sxs-lookup"><span data-stu-id="2c08d-113">The first attempt to access `myValue` through an instance of `BaseClass` will produce an error.</span></span> <span data-ttu-id="2c08d-114">En cambio, el intento de usarlo como un miembro heredado en `DerivedClass1` se realizará correctamente.</span><span class="sxs-lookup"><span data-stu-id="2c08d-114">However, the attempt to use it as an inherited member in `DerivedClass1` will succeed.</span></span>
<span data-ttu-id="2c08d-115">En el segundo archivo, un intento de tener acceso a `myValue` como un miembro heredado de `DerivedClass2` generará un error, ya que solo está accesible para los tipos derivados en Assembly1.</span><span class="sxs-lookup"><span data-stu-id="2c08d-115">In the second file, an attempt to access `myValue` as an inherited member of `DerivedClass2` will produce an error, as it is only accessible by derived types in Assembly1.</span></span>

<span data-ttu-id="2c08d-116">Los miembros de struct no pueden ser `private protected`, porque los structs no se heredan.</span><span class="sxs-lookup"><span data-stu-id="2c08d-116">Struct members cannot be `private protected` because the struct cannot be inherited.</span></span>  

## <a name="c-language-specification"></a><span data-ttu-id="2c08d-117">especificación del lenguaje C#</span><span class="sxs-lookup"><span data-stu-id="2c08d-117">C# language specification</span></span>

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  

## <a name="see-also"></a><span data-ttu-id="2c08d-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="2c08d-118">See also</span></span>

- [<span data-ttu-id="2c08d-119">Referencia de C#</span><span class="sxs-lookup"><span data-stu-id="2c08d-119">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="2c08d-120">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="2c08d-120">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="2c08d-121">Palabras clave de C#</span><span class="sxs-lookup"><span data-stu-id="2c08d-121">C# Keywords</span></span>](index.md)
- [<span data-ttu-id="2c08d-122">Modificadores de acceso</span><span class="sxs-lookup"><span data-stu-id="2c08d-122">Access Modifiers</span></span>](access-modifiers.md)
- [<span data-ttu-id="2c08d-123">Niveles de accesibilidad</span><span class="sxs-lookup"><span data-stu-id="2c08d-123">Accessibility Levels</span></span>](accessibility-levels.md)
- [<span data-ttu-id="2c08d-124">Modificadores</span><span class="sxs-lookup"><span data-stu-id="2c08d-124">Modifiers</span></span>](modifiers.md)
- [<span data-ttu-id="2c08d-125">public</span><span class="sxs-lookup"><span data-stu-id="2c08d-125">public</span></span>](public.md)
- [<span data-ttu-id="2c08d-126">private</span><span class="sxs-lookup"><span data-stu-id="2c08d-126">private</span></span>](private.md)
- [<span data-ttu-id="2c08d-127">internal</span><span class="sxs-lookup"><span data-stu-id="2c08d-127">internal</span></span>](internal.md)
- <span data-ttu-id="2c08d-128">[Security concerns for internal virtual keywords](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/heyd8kky(v=vs.100)) (Problemas de seguridad de palabras clave virtuales internas)</span><span class="sxs-lookup"><span data-stu-id="2c08d-128">[Security concerns for internal virtual keywords](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/heyd8kky(v=vs.100))</span></span>