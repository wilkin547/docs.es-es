---
title: Procedimiento para cargar ensamblados en el contexto de solo reflexión
description: Vea un ejemplo de cómo cargar ensamblados en el contexto de solo reflexión de .NET. Examine ensamblados compilados para otras plataformas o versiones de .NET.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- reflection, reflection-only loader context
- assemblies [.NET Framework], loading for reflection
- attributes [.NET Framework], retrieving
- assemblies [.NET Framework], reflection-only loader context
- reflection-only loader context
ms.assetid: 9818b660-52f5-423d-a9af-e75163aa7068
ms.openlocfilehash: 92f847f6c61ba39bf8621af6080baccfdabe514a
ms.sourcegitcommit: 3d84eac0818099c9949035feb96bbe0346358504
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/21/2020
ms.locfileid: "86865078"
---
# <a name="how-to-load-assemblies-into-the-reflection-only-context"></a><span data-ttu-id="90e62-104">Procedimiento para cargar ensamblados en el contexto de solo reflexión</span><span class="sxs-lookup"><span data-stu-id="90e62-104">How to: Load Assemblies into the Reflection-Only Context</span></span>

<span data-ttu-id="90e62-105">El contexto de carga de solo reflexión permite examinar ensamblados compilados para otras plataformas o para otras versiones de .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="90e62-105">The reflection-only load context allows you to examine assemblies compiled for other platforms or for other versions of the .NET Framework.</span></span> <span data-ttu-id="90e62-106">El código cargado en este contexto solo se puede examinar; no se puede ejecutar.</span><span class="sxs-lookup"><span data-stu-id="90e62-106">Code loaded into this context can only be examined; it cannot be executed.</span></span> <span data-ttu-id="90e62-107">Esto significa que no se pueden crear objetos, porque no se pueden ejecutar constructores.</span><span class="sxs-lookup"><span data-stu-id="90e62-107">This means that objects cannot be created, because constructors cannot be executed.</span></span> <span data-ttu-id="90e62-108">Dado que no se puede ejecutar el código, las dependencias no se cargan automáticamente.</span><span class="sxs-lookup"><span data-stu-id="90e62-108">Because the code cannot be executed, dependencies are not automatically loaded.</span></span> <span data-ttu-id="90e62-109">Si necesita examinarlas, tiene que cargarlas manualmente.</span><span class="sxs-lookup"><span data-stu-id="90e62-109">If you need to examine them, you must load them yourself.</span></span>

## <a name="to-load-an-assembly-into-the-reflection-only-load-context"></a><span data-ttu-id="90e62-110">Para cargar un ensamblado en el contexto de carga de solo reflexión</span><span class="sxs-lookup"><span data-stu-id="90e62-110">To load an assembly into the reflection-only load context</span></span>

1. <span data-ttu-id="90e62-111">Use la sobrecarga del método <xref:System.Reflection.Assembly.ReflectionOnlyLoad%28System.String%29> para cargar el ensamblado a partir de su nombre para mostrar, o el método <xref:System.Reflection.Assembly.ReflectionOnlyLoadFrom%2A> para cargar el ensamblado a partir de su ruta de acceso.</span><span class="sxs-lookup"><span data-stu-id="90e62-111">Use the <xref:System.Reflection.Assembly.ReflectionOnlyLoad%28System.String%29> method overload to load the assembly given its display name, or the <xref:System.Reflection.Assembly.ReflectionOnlyLoadFrom%2A> method to load the assembly given its path.</span></span> <span data-ttu-id="90e62-112">Si el ensamblado es una imagen binaria, use la sobrecarga del método <xref:System.Reflection.Assembly.ReflectionOnlyLoad%28System.Byte%5B%5D%29>.</span><span class="sxs-lookup"><span data-stu-id="90e62-112">If the assembly is a binary image, use the <xref:System.Reflection.Assembly.ReflectionOnlyLoad%28System.Byte%5B%5D%29> method overload.</span></span>

    > [!NOTE]
    > <span data-ttu-id="90e62-113">No puede usar el contexto de solo reflexión para cargar una versión de mscorlib.dll desde una versión de .NET Framework que no sea la versión del contexto de ejecución.</span><span class="sxs-lookup"><span data-stu-id="90e62-113">You cannot use the reflection-only context to load a version of mscorlib.dll from a version of the .NET Framework other than the version in the execution context.</span></span>

2. <span data-ttu-id="90e62-114">Si el ensamblado tiene dependencias, el método <xref:System.Reflection.Assembly.ReflectionOnlyLoad%2A> no las carga.</span><span class="sxs-lookup"><span data-stu-id="90e62-114">If the assembly has dependencies, the <xref:System.Reflection.Assembly.ReflectionOnlyLoad%2A> method does not load them.</span></span> <span data-ttu-id="90e62-115">Si necesita examinarlas, tiene que cargarlas manualmente.</span><span class="sxs-lookup"><span data-stu-id="90e62-115">If you need to examine them, you must load them yourself.</span></span>

3. <span data-ttu-id="90e62-116">Determine si un ensamblado se carga en el contexto de solo reflexión mediante la propiedad <xref:System.Reflection.Assembly.ReflectionOnly%2A> del ensamblado.</span><span class="sxs-lookup"><span data-stu-id="90e62-116">Determine whether an assembly is loaded into the reflection-only context by using the assembly's <xref:System.Reflection.Assembly.ReflectionOnly%2A> property.</span></span>

4. <span data-ttu-id="90e62-117">Si se han aplicado atributos al ensamblado o a tipos del ensamblado, examine esos atributos mediante la clase <xref:System.Reflection.CustomAttributeData> para asegurarse de que no se realice ningún intento de ejecutar código en el contexto de solo reflexión.</span><span class="sxs-lookup"><span data-stu-id="90e62-117">If attributes have been applied to the assembly or to types in the assembly, examine those attributes by using the <xref:System.Reflection.CustomAttributeData> class to ensure that no attempt is made to execute code in the reflection-only context.</span></span> <span data-ttu-id="90e62-118">Use la sobrecarga adecuada del método <xref:System.Reflection.CustomAttributeData.GetCustomAttributes%2A?displayProperty=nameWithType> para obtener objetos <xref:System.Reflection.CustomAttributeData> que representen a los atributos aplicados a un ensamblado, miembro, módulo o parámetro.</span><span class="sxs-lookup"><span data-stu-id="90e62-118">Use the appropriate overload of the <xref:System.Reflection.CustomAttributeData.GetCustomAttributes%2A?displayProperty=nameWithType> method to obtain <xref:System.Reflection.CustomAttributeData> objects representing the attributes applied to an assembly, member, module, or parameter.</span></span>

    > [!NOTE]
    > <span data-ttu-id="90e62-119">Los atributos aplicados al ensamblado o a su contenido podrían definirse en el ensamblado o en otro ensamblado cargado en el contexto de solo reflexión.</span><span class="sxs-lookup"><span data-stu-id="90e62-119">Attributes applied to the assembly or to its contents might be defined in the assembly, or they might be defined in another assembly loaded into the reflection-only context.</span></span> <span data-ttu-id="90e62-120">No hay forma de saber de antemano dónde se definen los atributos.</span><span class="sxs-lookup"><span data-stu-id="90e62-120">There is no way to tell in advance where the attributes are defined.</span></span>

## <a name="example"></a><span data-ttu-id="90e62-121">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="90e62-121">Example</span></span>

<span data-ttu-id="90e62-122">En el ejemplo de código siguiente se muestra cómo examinar los atributos aplicados a un ensamblado cargado en el contexto de solo reflexión.</span><span class="sxs-lookup"><span data-stu-id="90e62-122">The following code example shows how to examine the attributes applied to an assembly loaded into the reflection-only context.</span></span>

<span data-ttu-id="90e62-123">El ejemplo de código define un atributo personalizado con dos constructores y una propiedad.</span><span class="sxs-lookup"><span data-stu-id="90e62-123">The code example defines a custom attribute with two constructors and one property.</span></span> <span data-ttu-id="90e62-124">El atributo se aplica al ensamblado, a un tipo declarado en el ensamblado, a un método del tipo y a un parámetro del método.</span><span class="sxs-lookup"><span data-stu-id="90e62-124">The attribute is applied to the assembly, to a type declared in the assembly, to a method of the type, and to a parameter of the method.</span></span> <span data-ttu-id="90e62-125">Cuando se ejecuta, el ensamblado se carga automáticamente en el contexto de solo reflexión y muestra información sobre los atributos personalizados que se le aplicaron a él y a los tipos y miembros que contiene.</span><span class="sxs-lookup"><span data-stu-id="90e62-125">When executed, the assembly loads itself into the reflection-only context and displays information about the custom attributes that were applied to it and to the types and members it contains.</span></span>

> [!NOTE]
> <span data-ttu-id="90e62-126">Para simplificar el ejemplo de código, el ensamblado se carga y examina automáticamente.</span><span class="sxs-lookup"><span data-stu-id="90e62-126">To simplify the code example, the assembly loads and examines itself.</span></span> <span data-ttu-id="90e62-127">Normalmente no se esperaría encontrar el mismo ensamblado cargado tanto en el contexto de ejecución como en el contexto de solo reflexión.</span><span class="sxs-lookup"><span data-stu-id="90e62-127">Normally, you would not expect to find the same assembly loaded into both the execution context and the reflection-only context.</span></span>

[!code-cpp[CustomAttributeData#1](../../../samples/snippets/cpp/VS_Snippets_CLR/CustomAttributeData/CPP/source.cpp#1)]
[!code-csharp[CustomAttributeData#1](../../../samples/snippets/csharp/VS_Snippets_CLR/CustomAttributeData/CS/source.cs#1)]
[!code-vb[CustomAttributeData#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/CustomAttributeData/VB/source.vb#1)]

## <a name="see-also"></a><span data-ttu-id="90e62-128">Vea también</span><span class="sxs-lookup"><span data-stu-id="90e62-128">See also</span></span>

- <xref:System.Reflection.Assembly.ReflectionOnlyLoad%2A>
- <xref:System.Reflection.Assembly.ReflectionOnly%2A>
- <xref:System.Reflection.CustomAttributeData>
