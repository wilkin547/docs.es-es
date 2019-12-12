---
title: Reflexión (C#)
ms.date: 07/20/2015
ms.assetid: f80a2362-953b-4e8e-9759-cd5f334190d4
ms.openlocfilehash: a56fb24b63e4d80dbb67b079466b67cd11672023
ms.sourcegitcommit: 5fb5b6520b06d7f5e6131ec2ad854da302a28f2e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/03/2019
ms.locfileid: "74711660"
---
# <a name="reflection-c"></a><span data-ttu-id="1218e-102">Reflexión (C#)</span><span class="sxs-lookup"><span data-stu-id="1218e-102">Reflection (C#)</span></span>

<span data-ttu-id="1218e-103">La reflexión proporciona objetos (de tipo <xref:System.Type>) que describen los ensamblados, módulos y tipos.</span><span class="sxs-lookup"><span data-stu-id="1218e-103">Reflection provides objects (of type <xref:System.Type>) that describe assemblies, modules, and types.</span></span> <span data-ttu-id="1218e-104">Puede usar la reflexión para crear dinámicamente una instancia de un tipo, enlazar el tipo a un objeto existente u obtener el tipo desde un objeto existente e invocar sus métodos, o acceder a sus campos y propiedades.</span><span class="sxs-lookup"><span data-stu-id="1218e-104">You can use reflection to dynamically create an instance of a type, bind the type to an existing object, or get the type from an existing object and invoke its methods or access its fields and properties.</span></span> <span data-ttu-id="1218e-105">Si usa atributos en el código, la reflexión le permite acceder a ellos.</span><span class="sxs-lookup"><span data-stu-id="1218e-105">If you are using attributes in your code, reflection enables you to access them.</span></span> <span data-ttu-id="1218e-106">Para obtener más información, consulte [Attributes](../../../standard/attributes/index.md) (Atributos).</span><span class="sxs-lookup"><span data-stu-id="1218e-106">For more information, see [Attributes](../../../standard/attributes/index.md).</span></span>

<span data-ttu-id="1218e-107">Este es un ejemplo simple de reflexión que usa el método <xref:System.Object.GetType>, heredado por todos los tipos de la clase base `Object`, para obtener el tipo de una variable:</span><span class="sxs-lookup"><span data-stu-id="1218e-107">Here's a simple example of reflection using the <xref:System.Object.GetType> method - inherited by all types from the `Object` base class - to obtain the type of a variable:</span></span>

> [!NOTE]
> <span data-ttu-id="1218e-108">Asegúrese de agregar `using System;` y `using System.Reflection;` en la parte superior del archivo de *.cs*.</span><span class="sxs-lookup"><span data-stu-id="1218e-108">Make sure you add `using System;` and `using System.Reflection;` at the top of your *.cs* file.</span></span>

```csharp
// Using GetType to obtain type information:
int i = 42;
Type type = i.GetType();
Console.WriteLine(type);
```

<span data-ttu-id="1218e-109">El resultado es `System.Int32`.</span><span class="sxs-lookup"><span data-stu-id="1218e-109">The output is: `System.Int32`.</span></span>

<span data-ttu-id="1218e-110">En el ejemplo siguiente se usa la reflexión para obtener el nombre completo del ensamblado cargado.</span><span class="sxs-lookup"><span data-stu-id="1218e-110">The following example uses reflection to obtain the full name of the loaded assembly.</span></span>

```csharp
// Using Reflection to get information of an Assembly:
Assembly info = typeof(int).Assembly;
Console.WriteLine(info);
```

<span data-ttu-id="1218e-111">El resultado es `System.Private.CoreLib, Version=4.0.0.0, Culture=neutral, PublicKeyToken=7cec85d7bea7798e`.</span><span class="sxs-lookup"><span data-stu-id="1218e-111">The output is: `System.Private.CoreLib, Version=4.0.0.0, Culture=neutral, PublicKeyToken=7cec85d7bea7798e`.</span></span>

> [!NOTE]
> <span data-ttu-id="1218e-112">Las palabras clave de C# `protected` y `internal` no tienen ningún significado en IL y no se usan en las API de reflexión.</span><span class="sxs-lookup"><span data-stu-id="1218e-112">The C# keywords `protected` and `internal` have no meaning in IL and are not used in the reflection APIs.</span></span> <span data-ttu-id="1218e-113">Los términos correspondientes en IL son *Family* y *Assembly*.</span><span class="sxs-lookup"><span data-stu-id="1218e-113">The corresponding terms in IL are *Family* and *Assembly*.</span></span> <span data-ttu-id="1218e-114">Para identificar un método `internal` con la reflexión, use la propiedad <xref:System.Reflection.MethodBase.IsAssembly%2A>.</span><span class="sxs-lookup"><span data-stu-id="1218e-114">To identify an `internal` method using reflection, use the <xref:System.Reflection.MethodBase.IsAssembly%2A> property.</span></span> <span data-ttu-id="1218e-115">Para identificar un método `protected internal`, use <xref:System.Reflection.MethodBase.IsFamilyOrAssembly%2A>.</span><span class="sxs-lookup"><span data-stu-id="1218e-115">To identify a `protected internal` method, use the <xref:System.Reflection.MethodBase.IsFamilyOrAssembly%2A>.</span></span>

## <a name="reflection-overview"></a><span data-ttu-id="1218e-116">Información general de la reflexión</span><span class="sxs-lookup"><span data-stu-id="1218e-116">Reflection overview</span></span>

<span data-ttu-id="1218e-117">La reflexión resulta útil en las siguientes situaciones:</span><span class="sxs-lookup"><span data-stu-id="1218e-117">Reflection is useful in the following situations:</span></span>

- <span data-ttu-id="1218e-118">Cuando tenga que acceder a atributos en los metadatos del programa.</span><span class="sxs-lookup"><span data-stu-id="1218e-118">When you have to access attributes in your program's metadata.</span></span> <span data-ttu-id="1218e-119">Para obtener más información, consulte [Retrieving Information Stored in Attributes](../../../standard/attributes/retrieving-information-stored-in-attributes.md) (Recuperar la información almacenada en atributos).</span><span class="sxs-lookup"><span data-stu-id="1218e-119">For more information, see [Retrieving Information Stored in Attributes](../../../standard/attributes/retrieving-information-stored-in-attributes.md).</span></span>
- <span data-ttu-id="1218e-120">Para examinar y crear instancias de tipos en un ensamblado.</span><span class="sxs-lookup"><span data-stu-id="1218e-120">For examining and instantiating types in an assembly.</span></span>
- <span data-ttu-id="1218e-121">Para generar nuevos tipos en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="1218e-121">For building new types at runtime.</span></span> <span data-ttu-id="1218e-122">Usar clases en <xref:System.Reflection.Emit>.</span><span class="sxs-lookup"><span data-stu-id="1218e-122">Use classes in <xref:System.Reflection.Emit>.</span></span>
- <span data-ttu-id="1218e-123">Para llevar a cabo métodos de acceso de enlace en tiempo de ejecución en tipos creados en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="1218e-123">For performing late binding, accessing methods on types created at run time.</span></span> <span data-ttu-id="1218e-124">Consulte el tema [Dynamically Loading and Using Types](../../../framework/reflection-and-codedom/dynamically-loading-and-using-types.md) (Cargar y usar tipos dinámicamente).</span><span class="sxs-lookup"><span data-stu-id="1218e-124">See the topic [Dynamically Loading and Using Types](../../../framework/reflection-and-codedom/dynamically-loading-and-using-types.md).</span></span>

## <a name="related-sections"></a><span data-ttu-id="1218e-125">Secciones relacionadas</span><span class="sxs-lookup"><span data-stu-id="1218e-125">Related sections</span></span>

<span data-ttu-id="1218e-126">Para obtener más información:</span><span class="sxs-lookup"><span data-stu-id="1218e-126">For more information:</span></span>

- [<span data-ttu-id="1218e-127">Reflexión</span><span class="sxs-lookup"><span data-stu-id="1218e-127">Reflection</span></span>](../../../framework/reflection-and-codedom/reflection.md)
- <span data-ttu-id="1218e-128">[Viewing Type Information](../../../framework/reflection-and-codedom/viewing-type-information.md) (Ver información tipos)</span><span class="sxs-lookup"><span data-stu-id="1218e-128">[Viewing Type Information](../../../framework/reflection-and-codedom/viewing-type-information.md)</span></span>
- <span data-ttu-id="1218e-129">[Reflection and Generic Types](../../../framework/reflection-and-codedom/reflection-and-generic-types.md) (Reflexión y tipos genéricos)</span><span class="sxs-lookup"><span data-stu-id="1218e-129">[Reflection and Generic Types](../../../framework/reflection-and-codedom/reflection-and-generic-types.md)</span></span>
- <xref:System.Reflection.Emit>
- <span data-ttu-id="1218e-130">[Retrieving Information Stored in Attributes](../../../standard/attributes/retrieving-information-stored-in-attributes.md) (Recuperar la información almacenada en atributos)</span><span class="sxs-lookup"><span data-stu-id="1218e-130">[Retrieving Information Stored in Attributes](../../../standard/attributes/retrieving-information-stored-in-attributes.md)</span></span>

## <a name="see-also"></a><span data-ttu-id="1218e-131">Vea también</span><span class="sxs-lookup"><span data-stu-id="1218e-131">See also</span></span>

- [<span data-ttu-id="1218e-132">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="1218e-132">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="1218e-133">Ensamblados de .NET</span><span class="sxs-lookup"><span data-stu-id="1218e-133">Assemblies in .NET</span></span>](../../../standard/assembly/index.md)
