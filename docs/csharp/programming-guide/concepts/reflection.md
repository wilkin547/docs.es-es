---
title: Reflexión (C#)
description: La reflexión proporciona objetos que describen los ensamblados, módulos y tipos en C#. Si el código incluye atributos, la reflexión le permite acceder a ellos.
ms.date: 07/20/2015
ms.assetid: f80a2362-953b-4e8e-9759-cd5f334190d4
ms.openlocfilehash: 4d4f4c082dd2d58e212bae53524e5dd4fd06fb75
ms.sourcegitcommit: 6f58a5f75ceeb936f8ee5b786e9adb81a9a3bee9
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/28/2020
ms.locfileid: "87302807"
---
# <a name="reflection-c"></a><span data-ttu-id="04eef-104">Reflexión (C#)</span><span class="sxs-lookup"><span data-stu-id="04eef-104">Reflection (C#)</span></span>

<span data-ttu-id="04eef-105">La reflexión proporciona objetos (de tipo <xref:System.Type>) que describen los ensamblados, módulos y tipos.</span><span class="sxs-lookup"><span data-stu-id="04eef-105">Reflection provides objects (of type <xref:System.Type>) that describe assemblies, modules, and types.</span></span> <span data-ttu-id="04eef-106">Puede usar la reflexión para crear dinámicamente una instancia de un tipo, enlazar el tipo a un objeto existente u obtener el tipo desde un objeto existente e invocar sus métodos, o acceder a sus campos y propiedades.</span><span class="sxs-lookup"><span data-stu-id="04eef-106">You can use reflection to dynamically create an instance of a type, bind the type to an existing object, or get the type from an existing object and invoke its methods or access its fields and properties.</span></span> <span data-ttu-id="04eef-107">Si usa atributos en el código, la reflexión le permite acceder a ellos.</span><span class="sxs-lookup"><span data-stu-id="04eef-107">If you are using attributes in your code, reflection enables you to access them.</span></span> <span data-ttu-id="04eef-108">Para obtener más información, consulte [Attributes](../../../standard/attributes/index.md) (Atributos).</span><span class="sxs-lookup"><span data-stu-id="04eef-108">For more information, see [Attributes](../../../standard/attributes/index.md).</span></span>

<span data-ttu-id="04eef-109">Este es un ejemplo simple de reflexión que usa el método <xref:System.Object.GetType>, heredado por todos los tipos de la clase base `Object`, para obtener el tipo de una variable:</span><span class="sxs-lookup"><span data-stu-id="04eef-109">Here's a simple example of reflection using the <xref:System.Object.GetType> method - inherited by all types from the `Object` base class - to obtain the type of a variable:</span></span>

> [!NOTE]
> <span data-ttu-id="04eef-110">Asegúrese de agregar `using System;` y `using System.Reflection;` en la parte superior del archivo de *.cs*.</span><span class="sxs-lookup"><span data-stu-id="04eef-110">Make sure you add `using System;` and `using System.Reflection;` at the top of your *.cs* file.</span></span>

```csharp
// Using GetType to obtain type information:
int i = 42;
Type type = i.GetType();
Console.WriteLine(type);
```

<span data-ttu-id="04eef-111">El resultado es `System.Int32`.</span><span class="sxs-lookup"><span data-stu-id="04eef-111">The output is: `System.Int32`.</span></span>

<span data-ttu-id="04eef-112">En el ejemplo siguiente se usa la reflexión para obtener el nombre completo del ensamblado cargado.</span><span class="sxs-lookup"><span data-stu-id="04eef-112">The following example uses reflection to obtain the full name of the loaded assembly.</span></span>

```csharp
// Using Reflection to get information of an Assembly:
Assembly info = typeof(int).Assembly;
Console.WriteLine(info);
```

<span data-ttu-id="04eef-113">El resultado es `System.Private.CoreLib, Version=4.0.0.0, Culture=neutral, PublicKeyToken=7cec85d7bea7798e`.</span><span class="sxs-lookup"><span data-stu-id="04eef-113">The output is: `System.Private.CoreLib, Version=4.0.0.0, Culture=neutral, PublicKeyToken=7cec85d7bea7798e`.</span></span>

> [!NOTE]
> <span data-ttu-id="04eef-114">Las palabras clave de C# `protected` y `internal` no tienen ningún significado en IL y no se usan en las API de reflexión.</span><span class="sxs-lookup"><span data-stu-id="04eef-114">The C# keywords `protected` and `internal` have no meaning in IL and are not used in the reflection APIs.</span></span> <span data-ttu-id="04eef-115">Los términos correspondientes en IL son *Family* y *Assembly*.</span><span class="sxs-lookup"><span data-stu-id="04eef-115">The corresponding terms in IL are *Family* and *Assembly*.</span></span> <span data-ttu-id="04eef-116">Para identificar un método `internal` con la reflexión, use la propiedad <xref:System.Reflection.MethodBase.IsAssembly%2A>.</span><span class="sxs-lookup"><span data-stu-id="04eef-116">To identify an `internal` method using reflection, use the <xref:System.Reflection.MethodBase.IsAssembly%2A> property.</span></span> <span data-ttu-id="04eef-117">Para identificar un método `protected internal`, use <xref:System.Reflection.MethodBase.IsFamilyOrAssembly%2A>.</span><span class="sxs-lookup"><span data-stu-id="04eef-117">To identify a `protected internal` method, use the <xref:System.Reflection.MethodBase.IsFamilyOrAssembly%2A>.</span></span>

## <a name="reflection-overview"></a><span data-ttu-id="04eef-118">Información general de la reflexión</span><span class="sxs-lookup"><span data-stu-id="04eef-118">Reflection overview</span></span>

<span data-ttu-id="04eef-119">La reflexión resulta útil en las siguientes situaciones:</span><span class="sxs-lookup"><span data-stu-id="04eef-119">Reflection is useful in the following situations:</span></span>

- <span data-ttu-id="04eef-120">Cuando tenga que acceder a atributos en los metadatos del programa.</span><span class="sxs-lookup"><span data-stu-id="04eef-120">When you have to access attributes in your program's metadata.</span></span> <span data-ttu-id="04eef-121">Para obtener más información, consulte [Recuperar información almacenada en atributos](../../../standard/attributes/retrieving-information-stored-in-attributes.md).</span><span class="sxs-lookup"><span data-stu-id="04eef-121">For more information, see [Retrieving Information Stored in Attributes](../../../standard/attributes/retrieving-information-stored-in-attributes.md).</span></span>
- <span data-ttu-id="04eef-122">Para examinar y crear instancias de tipos en un ensamblado.</span><span class="sxs-lookup"><span data-stu-id="04eef-122">For examining and instantiating types in an assembly.</span></span>
- <span data-ttu-id="04eef-123">Para generar nuevos tipos en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="04eef-123">For building new types at runtime.</span></span> <span data-ttu-id="04eef-124">Usar clases en <xref:System.Reflection.Emit>.</span><span class="sxs-lookup"><span data-stu-id="04eef-124">Use classes in <xref:System.Reflection.Emit>.</span></span>
- <span data-ttu-id="04eef-125">Para llevar a cabo métodos de acceso de enlace en tiempo de ejecución en tipos creados en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="04eef-125">For performing late binding, accessing methods on types created at run time.</span></span> <span data-ttu-id="04eef-126">Consulte el tema [Cargar y utilizar tipos dinámicamente](../../../framework/reflection-and-codedom/dynamically-loading-and-using-types.md).</span><span class="sxs-lookup"><span data-stu-id="04eef-126">See the topic [Dynamically Loading and Using Types](../../../framework/reflection-and-codedom/dynamically-loading-and-using-types.md).</span></span>

## <a name="related-sections"></a><span data-ttu-id="04eef-127">Secciones relacionadas</span><span class="sxs-lookup"><span data-stu-id="04eef-127">Related sections</span></span>

<span data-ttu-id="04eef-128">Para obtener más información:</span><span class="sxs-lookup"><span data-stu-id="04eef-128">For more information:</span></span>

- [<span data-ttu-id="04eef-129">Reflexión</span><span class="sxs-lookup"><span data-stu-id="04eef-129">Reflection</span></span>](../../../framework/reflection-and-codedom/reflection.md)
- [<span data-ttu-id="04eef-130">Ver información tipos</span><span class="sxs-lookup"><span data-stu-id="04eef-130">Viewing Type Information</span></span>](../../../framework/reflection-and-codedom/viewing-type-information.md)
- [<span data-ttu-id="04eef-131">Reflexión y tipos genéricos</span><span class="sxs-lookup"><span data-stu-id="04eef-131">Reflection and Generic Types</span></span>](../../../framework/reflection-and-codedom/reflection-and-generic-types.md)
- <xref:System.Reflection.Emit>
- [<span data-ttu-id="04eef-132">Recuperar la información almacenada en atributos</span><span class="sxs-lookup"><span data-stu-id="04eef-132">Retrieving Information Stored in Attributes</span></span>](../../../standard/attributes/retrieving-information-stored-in-attributes.md)

## <a name="see-also"></a><span data-ttu-id="04eef-133">Consulte también</span><span class="sxs-lookup"><span data-stu-id="04eef-133">See also</span></span>

- [<span data-ttu-id="04eef-134">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="04eef-134">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="04eef-135">Ensamblados de .NET</span><span class="sxs-lookup"><span data-stu-id="04eef-135">Assemblies in .NET</span></span>](../../../standard/assembly/index.md)
