---
title: Reflexión (C#)
ms.date: 07/20/2015
ms.assetid: f80a2362-953b-4e8e-9759-cd5f334190d4
ms.openlocfilehash: d04fb15add465d0a04ac6b38b1c47aa408c81eaa
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/04/2018
ms.locfileid: "43521677"
---
# <a name="reflection-c"></a><span data-ttu-id="2ff25-102">Reflexión (C#)</span><span class="sxs-lookup"><span data-stu-id="2ff25-102">Reflection (C#)</span></span>
<span data-ttu-id="2ff25-103">La reflexión proporciona objetos (de tipo <xref:System.Type>) que describen los ensamblados, módulos y tipos.</span><span class="sxs-lookup"><span data-stu-id="2ff25-103">Reflection provides objects (of type <xref:System.Type>) that describe assemblies, modules and types.</span></span> <span data-ttu-id="2ff25-104">Puede usar la reflexión para crear dinámicamente una instancia de un tipo, enlazar el tipo a un objeto existente u obtener el tipo desde un objeto existente e invocar sus métodos, o acceder a sus campos y propiedades.</span><span class="sxs-lookup"><span data-stu-id="2ff25-104">You can use reflection to dynamically create an instance of a type, bind the type to an existing object, or get the type from an existing object and invoke its methods or access its fields and properties.</span></span> <span data-ttu-id="2ff25-105">Si usa atributos en el código, la reflexión le permite acceder a ellos.</span><span class="sxs-lookup"><span data-stu-id="2ff25-105">If you are using attributes in your code, reflection enables you to access them.</span></span> <span data-ttu-id="2ff25-106">Para obtener más información, consulte [Attributes](../../../../docs/standard/attributes/index.md) (Atributos).</span><span class="sxs-lookup"><span data-stu-id="2ff25-106">For more information, see [Attributes](../../../../docs/standard/attributes/index.md).</span></span>  
  
 <span data-ttu-id="2ff25-107">Este es un ejemplo simple de reflexión que usa el método estático `GetType`, heredado por todos los tipos de la clase base `Object`, para obtener el tipo de una variable:</span><span class="sxs-lookup"><span data-stu-id="2ff25-107">Here's a simple example of reflection using the static method `GetType` - inherited by all types from the `Object` base class - to obtain the type of a variable:</span></span>  
  
```csharp  
// Using GetType to obtain type information:  
int i = 42;  
System.Type type = i.GetType();  
System.Console.WriteLine(type);  
```  
  
 <span data-ttu-id="2ff25-108">El resultado es el siguiente:</span><span class="sxs-lookup"><span data-stu-id="2ff25-108">The output is:</span></span>  
  
 `System.Int32`  
  
 <span data-ttu-id="2ff25-109">En el ejemplo siguiente se usa la reflexión para obtener el nombre completo del ensamblado cargado.</span><span class="sxs-lookup"><span data-stu-id="2ff25-109">The following example uses reflection to obtain the full name of the loaded assembly.</span></span>  
  
```csharp  
// Using Reflection to get information from an Assembly:  
System.Reflection.Assembly info = typeof(System.Int32).Assembly;  
System.Console.WriteLine(info);  
```  
  
 <span data-ttu-id="2ff25-110">El resultado es el siguiente:</span><span class="sxs-lookup"><span data-stu-id="2ff25-110">The output is:</span></span>  
  
 `mscorlib, Version=2.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089`  
  
> [!NOTE]
>  <span data-ttu-id="2ff25-111">Las palabras clave de C# `protected` y `internal` no tienen ningún significado en IL y no se usan en las API de reflexión.</span><span class="sxs-lookup"><span data-stu-id="2ff25-111">The C# keywords `protected` and `internal` have no meaning in IL and are not used in the reflection APIs.</span></span> <span data-ttu-id="2ff25-112">Los términos correspondientes en IL son *Family* y *Assembly*.</span><span class="sxs-lookup"><span data-stu-id="2ff25-112">The corresponding terms in IL are *Family* and *Assembly*.</span></span> <span data-ttu-id="2ff25-113">Para identificar un método `internal` con la reflexión, use la propiedad <xref:System.Reflection.MethodBase.IsAssembly%2A>.</span><span class="sxs-lookup"><span data-stu-id="2ff25-113">To identify an `internal` method using reflection, use the <xref:System.Reflection.MethodBase.IsAssembly%2A> property.</span></span> <span data-ttu-id="2ff25-114">Para identificar un método `protected internal`, use <xref:System.Reflection.MethodBase.IsFamilyOrAssembly%2A>.</span><span class="sxs-lookup"><span data-stu-id="2ff25-114">To identify a `protected internal` method, use the <xref:System.Reflection.MethodBase.IsFamilyOrAssembly%2A>.</span></span>  
  
## <a name="reflection-overview"></a><span data-ttu-id="2ff25-115">Información general de la reflexión</span><span class="sxs-lookup"><span data-stu-id="2ff25-115">Reflection Overview</span></span>  
 <span data-ttu-id="2ff25-116">La reflexión resulta útil en las siguientes situaciones:</span><span class="sxs-lookup"><span data-stu-id="2ff25-116">Reflection is useful in the following situations:</span></span>  
  
-   <span data-ttu-id="2ff25-117">Cuando tenga que acceder a atributos en los metadatos del programa.</span><span class="sxs-lookup"><span data-stu-id="2ff25-117">When you have to access attributes in your program's metadata.</span></span> <span data-ttu-id="2ff25-118">Para obtener más información, consulte [Retrieving Information Stored in Attributes](../../../standard/attributes/retrieving-information-stored-in-attributes.md) (Recuperar la información almacenada en atributos).</span><span class="sxs-lookup"><span data-stu-id="2ff25-118">For more information, see [Retrieving Information Stored in Attributes](../../../standard/attributes/retrieving-information-stored-in-attributes.md).</span></span>  
  
-   <span data-ttu-id="2ff25-119">Para examinar y crear instancias de tipos en un ensamblado.</span><span class="sxs-lookup"><span data-stu-id="2ff25-119">For examining and instantiating types in an assembly.</span></span>  
  
-   <span data-ttu-id="2ff25-120">Para generar nuevos tipos en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="2ff25-120">For building new types at runtime.</span></span> <span data-ttu-id="2ff25-121">Usar clases en <xref:System.Reflection.Emit>.</span><span class="sxs-lookup"><span data-stu-id="2ff25-121">Use classes in <xref:System.Reflection.Emit>.</span></span>  
  
-   <span data-ttu-id="2ff25-122">Para llevar a cabo métodos de acceso de enlace en tiempo de ejecución en tipos creados en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="2ff25-122">For performing late binding, accessing methods on types created at run time.</span></span> <span data-ttu-id="2ff25-123">Consulte el tema [Dynamically Loading and Using Types](../../../framework/reflection-and-codedom/dynamically-loading-and-using-types.md) (Cargar y usar tipos dinámicamente).</span><span class="sxs-lookup"><span data-stu-id="2ff25-123">See the topic [Dynamically Loading and Using Types](../../../framework/reflection-and-codedom/dynamically-loading-and-using-types.md).</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="2ff25-124">Secciones relacionadas</span><span class="sxs-lookup"><span data-stu-id="2ff25-124">Related Sections</span></span>  
 <span data-ttu-id="2ff25-125">Para obtener más información:</span><span class="sxs-lookup"><span data-stu-id="2ff25-125">For more information:</span></span>  
  
-   [<span data-ttu-id="2ff25-126">Reflexión</span><span class="sxs-lookup"><span data-stu-id="2ff25-126">Reflection</span></span>](../../../framework/reflection-and-codedom/reflection.md)  
  
-   <span data-ttu-id="2ff25-127">[Viewing Type Information](../../../framework/reflection-and-codedom/viewing-type-information.md) (Ver información tipos)</span><span class="sxs-lookup"><span data-stu-id="2ff25-127">[Viewing Type Information](../../../framework/reflection-and-codedom/viewing-type-information.md)</span></span>  
  
-   <span data-ttu-id="2ff25-128">[Reflection and Generic Types](../../../framework/reflection-and-codedom/reflection-and-generic-types.md) (Reflexión y tipos genéricos)</span><span class="sxs-lookup"><span data-stu-id="2ff25-128">[Reflection and Generic Types](../../../framework/reflection-and-codedom/reflection-and-generic-types.md)</span></span>  
  
-   <xref:System.Reflection.Emit>  
  
-   <span data-ttu-id="2ff25-129">[Retrieving Information Stored in Attributes](../../../standard/attributes/retrieving-information-stored-in-attributes.md) (Recuperar la información almacenada en atributos)</span><span class="sxs-lookup"><span data-stu-id="2ff25-129">[Retrieving Information Stored in Attributes](../../../standard/attributes/retrieving-information-stored-in-attributes.md)</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2ff25-130">Vea también</span><span class="sxs-lookup"><span data-stu-id="2ff25-130">See Also</span></span>

- [<span data-ttu-id="2ff25-131">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="2ff25-131">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
- [<span data-ttu-id="2ff25-132">Ensamblados en Common Language Runtime</span><span class="sxs-lookup"><span data-stu-id="2ff25-132">Assemblies in the Common Language Runtime</span></span>](../../../../docs/framework/app-domains/assemblies-in-the-common-language-runtime.md)
