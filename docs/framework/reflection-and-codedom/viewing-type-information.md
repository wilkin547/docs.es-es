---
title: Ver información de tipos
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- types, viewing type information
- Type object
- viewing type information
- reflection, viewing type information
ms.assetid: 7e7303a9-4064-4738-b4e7-b75974ed70d2
ms.openlocfilehash: bf119ff547df59cd369d688fd81ab058893614f2
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73130013"
---
# <a name="viewing-type-information"></a><span data-ttu-id="84d67-102">Ver información de tipos</span><span class="sxs-lookup"><span data-stu-id="84d67-102">Viewing Type Information</span></span>
<span data-ttu-id="84d67-103">La clase <xref:System.Type?displayProperty=nameWithType> es fundamental para la reflexión.</span><span class="sxs-lookup"><span data-stu-id="84d67-103">The <xref:System.Type?displayProperty=nameWithType> class is central to reflection.</span></span> <span data-ttu-id="84d67-104">Common Language Runtime crea el objeto **Type** para un tipo cargado cuando lo solicita la reflexión.</span><span class="sxs-lookup"><span data-stu-id="84d67-104">The common language runtime creates the **Type** for a loaded type when reflection requests it.</span></span> <span data-ttu-id="84d67-105">Puede usar los métodos, los campos, las propiedades y las clases anidadas de un objeto **Type** para averiguarlo todo sobre dicho tipo.</span><span class="sxs-lookup"><span data-stu-id="84d67-105">You can use a **Type** object's methods, fields, properties, and nested classes to find out everything about that type.</span></span>  
  
 <span data-ttu-id="84d67-106">Use <xref:System.Reflection.Assembly.GetType%2A?displayProperty=nameWithType> o <xref:System.Reflection.Assembly.GetTypes%2A?displayProperty=nameWithType> para obtener objetos **Type** de ensamblados no cargados y pasar el nombre de los tipos que quiera.</span><span class="sxs-lookup"><span data-stu-id="84d67-106">Use <xref:System.Reflection.Assembly.GetType%2A?displayProperty=nameWithType> or <xref:System.Reflection.Assembly.GetTypes%2A?displayProperty=nameWithType> to obtain **Type** objects from assemblies that have not been loaded, passing in the name of the type or types you want.</span></span> <span data-ttu-id="84d67-107">Use <xref:System.Type.GetType%2A?displayProperty=nameWithType> para obtener objetos **Type** de un ensamblado que ya está cargado.</span><span class="sxs-lookup"><span data-stu-id="84d67-107">Use <xref:System.Type.GetType%2A?displayProperty=nameWithType> to get the **Type** objects from an assembly that is already loaded.</span></span> <span data-ttu-id="84d67-108">Use <xref:System.Reflection.Module.GetType%2A?displayProperty=nameWithType> y <xref:System.Reflection.Module.GetTypes%2A?displayProperty=nameWithType> para obtener objetos **Type** de módulo.</span><span class="sxs-lookup"><span data-stu-id="84d67-108">Use <xref:System.Reflection.Module.GetType%2A?displayProperty=nameWithType> and <xref:System.Reflection.Module.GetTypes%2A?displayProperty=nameWithType> to obtain module **Type** objects.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="84d67-109">Si quiere examinar y manipular tipos y métodos genéricos, vea la información adicional proporcionada en [Reflexión y tipos genéricos](reflection-and-generic-types.md) y [Cómo: Examinar y crear instancias de tipos genéricos mediante la reflexión](how-to-examine-and-instantiate-generic-types-with-reflection.md).</span><span class="sxs-lookup"><span data-stu-id="84d67-109">If you want to examine and manipulate generic types and methods, please see the additional information provided in [Reflection and Generic Types](reflection-and-generic-types.md) and [How to: Examine and Instantiate Generic Types with Reflection](how-to-examine-and-instantiate-generic-types-with-reflection.md).</span></span>  
  
 <span data-ttu-id="84d67-110">En el ejemplo siguiente se muestra la sintaxis necesaria para obtener el objeto <xref:System.Reflection.Assembly> y el módulo de un ensamblado.</span><span class="sxs-lookup"><span data-stu-id="84d67-110">The following example shows the syntax necessary to get the <xref:System.Reflection.Assembly> object and module for an assembly.</span></span>  
  
 [!code-cpp[Conceptual.Types.ViewInfo#6](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.types.viewinfo/cpp/source5.cpp#6)]
 [!code-csharp[Conceptual.Types.ViewInfo#6](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.types.viewinfo/cs/source5.cs#6)]
 [!code-vb[Conceptual.Types.ViewInfo#6](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.types.viewinfo/vb/source5.vb#6)]  
  
 <span data-ttu-id="84d67-111">En el ejemplo siguiente se muestra cómo obtener objetos **Type** de un ensamblado cargado.</span><span class="sxs-lookup"><span data-stu-id="84d67-111">The following example demonstrates getting **Type** objects from a loaded assembly.</span></span>  
  
 [!code-cpp[Conceptual.Types.ViewInfo#7](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.types.viewinfo/cpp/source5.cpp#7)]
 [!code-csharp[Conceptual.Types.ViewInfo#7](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.types.viewinfo/cs/source5.cs#7)]
 [!code-vb[Conceptual.Types.ViewInfo#7](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.types.viewinfo/vb/source5.vb#7)]  
  
 <span data-ttu-id="84d67-112">Una vez que obtenga un objeto **Type**, hay muchas maneras de obtener información sobre los miembros de dicho tipo.</span><span class="sxs-lookup"><span data-stu-id="84d67-112">Once you obtain a **Type**, there are many ways you can discover information about the members of that type.</span></span> <span data-ttu-id="84d67-113">Por ejemplo, puede obtener información sobre todos los miembros del tipo. Para ello, llame al método <xref:System.Type.GetMembers%2A?displayProperty=nameWithType>, que obtiene una matriz de objetos <xref:System.Reflection.MemberInfo> que describen cada uno de los miembros del tipo actual.</span><span class="sxs-lookup"><span data-stu-id="84d67-113">For example, you can find out about all the type's members by calling the <xref:System.Type.GetMembers%2A?displayProperty=nameWithType> method, which obtains an array of <xref:System.Reflection.MemberInfo> objects describing each of the members of the current type.</span></span>  
  
 <span data-ttu-id="84d67-114">También puede usar métodos en la clase **Type** para recuperar información sobre uno o más constructores, métodos, eventos, campos o propiedades especificados por nombre.</span><span class="sxs-lookup"><span data-stu-id="84d67-114">You can also use methods on the **Type** class to retrieve information about one or more constructors, methods, events, fields, or properties that you specify by name.</span></span> <span data-ttu-id="84d67-115">Por ejemplo, <xref:System.Type.GetConstructor%2A?displayProperty=nameWithType> encapsula un constructor específico de la clase actual.</span><span class="sxs-lookup"><span data-stu-id="84d67-115">For example, <xref:System.Type.GetConstructor%2A?displayProperty=nameWithType> encapsulates a specific constructor of the current class.</span></span>  
  
 <span data-ttu-id="84d67-116">Si tiene un objeto **Type**, puede usar la propiedad <xref:System.Type.Module%2A?displayProperty=nameWithType> para obtener un objeto que encapsule el módulo que contiene dicho tipo.</span><span class="sxs-lookup"><span data-stu-id="84d67-116">If you have a **Type**, you can use the <xref:System.Type.Module%2A?displayProperty=nameWithType> property to obtain an object that encapsulates the module containing that type.</span></span> <span data-ttu-id="84d67-117">Use la propiedad <xref:System.Reflection.Module.Assembly%2A?displayProperty=nameWithType> para buscar un objeto que encapsule el ensamblado que contiene el módulo.</span><span class="sxs-lookup"><span data-stu-id="84d67-117">Use the <xref:System.Reflection.Module.Assembly%2A?displayProperty=nameWithType> property to locate an object that encapsulates the assembly containing the module.</span></span> <span data-ttu-id="84d67-118">Puede obtener el ensamblado que encapsula el tipo directamente mediante la propiedad <xref:System.Type.Assembly%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="84d67-118">You can obtain the assembly that encapsulates the type directly by using the <xref:System.Type.Assembly%2A?displayProperty=nameWithType> property.</span></span>  
  
## <a name="systemtype-and-constructorinfo"></a><span data-ttu-id="84d67-119">System.Type y ConstructorInfo</span><span class="sxs-lookup"><span data-stu-id="84d67-119">System.Type and ConstructorInfo</span></span>  
 <span data-ttu-id="84d67-120">En el ejemplo siguiente se muestra cómo enumerar los constructores de una clase, en este caso, la clase <xref:System.String>.</span><span class="sxs-lookup"><span data-stu-id="84d67-120">The following example shows how to list the constructors for a class, in this case, the <xref:System.String> class.</span></span>  
  
 [!code-cpp[Conceptual.Types.ViewInfo#1](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.types.viewinfo/cpp/source1.cpp#1)]
 [!code-csharp[Conceptual.Types.ViewInfo#1](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.types.viewinfo/cs/source1.cs#1)]
 [!code-vb[Conceptual.Types.ViewInfo#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.types.viewinfo/vb/source1.vb#1)]  
  
## <a name="memberinfo-methodinfo-fieldinfo-and-propertyinfo"></a><span data-ttu-id="84d67-121">MemberInfo, MethodInfo, FieldInfo y PropertyInfo</span><span class="sxs-lookup"><span data-stu-id="84d67-121">MemberInfo, MethodInfo, FieldInfo, and PropertyInfo</span></span>  
 <span data-ttu-id="84d67-122">Obtenga información sobre los métodos, las propiedades, los eventos y los campos del tipo mediante los objetos <xref:System.Reflection.MemberInfo>, <xref:System.Reflection.MethodInfo>, <xref:System.Reflection.FieldInfo> o <xref:System.Reflection.PropertyInfo>.</span><span class="sxs-lookup"><span data-stu-id="84d67-122">Obtain information about the type's methods, properties, events, and fields using <xref:System.Reflection.MemberInfo>, <xref:System.Reflection.MethodInfo>, <xref:System.Reflection.FieldInfo>, or <xref:System.Reflection.PropertyInfo> objects.</span></span>  
  
 <span data-ttu-id="84d67-123">En el ejemplo siguiente se usa **MemberInfo** para mostrar el número de miembros en la clase **System.IO.File** y se usa la propiedad <xref:System.Type.IsPublic%2A> para determinar la visibilidad de la clase.</span><span class="sxs-lookup"><span data-stu-id="84d67-123">The following example uses **MemberInfo** to list the number of members in the **System.IO.File** class and uses the <xref:System.Type.IsPublic%2A> property to determine the visibility of the class.</span></span>  
  
 [!code-cpp[Conceptual.Types.ViewInfo#2](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.types.viewinfo/cpp/source2.cpp#2)]
 [!code-csharp[Conceptual.Types.ViewInfo#2](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.types.viewinfo/cs/source2.cs#2)]
 [!code-vb[Conceptual.Types.ViewInfo#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.types.viewinfo/vb/source2.vb#2)]  
  
 <span data-ttu-id="84d67-124">En el ejemplo siguiente se investiga el tipo del miembro especificado.</span><span class="sxs-lookup"><span data-stu-id="84d67-124">The following example investigates the type of the specified member.</span></span> <span data-ttu-id="84d67-125">Se realiza la reflexión en un miembro de la clase **MemberInfo** y se muestra su tipo.</span><span class="sxs-lookup"><span data-stu-id="84d67-125">It performs reflection on a member of the **MemberInfo** class, and lists its type.</span></span>  
  
 [!code-cpp[Conceptual.Types.ViewInfo#3](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.types.viewinfo/cpp/source3.cpp#3)]
 [!code-csharp[Conceptual.Types.ViewInfo#3](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.types.viewinfo/cs/source3.cs#3)]
 [!code-vb[Conceptual.Types.ViewInfo#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.types.viewinfo/vb/source3.vb#3)]  
  
 <span data-ttu-id="84d67-126">En el ejemplo siguiente se usan todas las clases **\*Info** de reflexión junto con <xref:System.Reflection.BindingFlags> para enumerar todos los miembros (constructores, campos, propiedades, eventos y métodos) de la clase especificada y dividir los miembros en categorías estáticas y de instancia.</span><span class="sxs-lookup"><span data-stu-id="84d67-126">The following example uses all the Reflection **\*Info** classes along with <xref:System.Reflection.BindingFlags> to list all the members (constructors, fields, properties, events, and methods) of the specified class, dividing the members into static and instance categories.</span></span>  
  
 [!code-cpp[Conceptual.Types.ViewInfo#4](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.types.viewinfo/cpp/source4.cpp#4)]
 [!code-csharp[Conceptual.Types.ViewInfo#4](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.types.viewinfo/cs/source4.cs#4)]
 [!code-vb[Conceptual.Types.ViewInfo#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.types.viewinfo/vb/source4.vb#4)]  
  
## <a name="see-also"></a><span data-ttu-id="84d67-127">Vea también</span><span class="sxs-lookup"><span data-stu-id="84d67-127">See also</span></span>

- <xref:System.Reflection.BindingFlags>
- <xref:System.Reflection.Assembly.GetType%2A?displayProperty=nameWithType>
- <xref:System.Reflection.Assembly.GetTypes%2A?displayProperty=nameWithType>
- <xref:System.Type.GetType%2A?displayProperty=nameWithType>
- <xref:System.Type.GetMembers%2A?displayProperty=nameWithType>
- <xref:System.Type.GetFields%2A?displayProperty=nameWithType>
- <xref:System.Reflection.Module.GetType%2A?displayProperty=nameWithType>
- <xref:System.Reflection.Module.GetTypes%2A?displayProperty=nameWithType>
- <xref:System.Reflection.MemberInfo>
- <xref:System.Reflection.ConstructorInfo>
- <xref:System.Reflection.MethodInfo>
- <xref:System.Reflection.FieldInfo>
- <xref:System.Reflection.EventInfo>
- <xref:System.Reflection.ParameterInfo>
- [<span data-ttu-id="84d67-128">Reflexión y tipos genéricos</span><span class="sxs-lookup"><span data-stu-id="84d67-128">Reflection and Generic Types</span></span>](reflection-and-generic-types.md)
