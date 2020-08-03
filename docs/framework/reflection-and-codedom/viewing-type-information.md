---
title: Ver información de tipos
description: Vea información de tipos mediante System.Type, algo fundamental para la reflexión en .NET. Revise ConstructorInfo, MemberInfo, MethodInfo, FieldInfo y PropertyInfo.
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
ms.openlocfilehash: cd74021e1f1a79626e171db13def98e546cd51df
ms.sourcegitcommit: 3d84eac0818099c9949035feb96bbe0346358504
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/21/2020
ms.locfileid: "86865208"
---
# <a name="viewing-type-information"></a>Ver información de tipos
La clase <xref:System.Type?displayProperty=nameWithType> es fundamental para la reflexión. Common Language Runtime crea el objeto **Type** para un tipo cargado cuando lo solicita la reflexión. Puede usar los métodos, los campos, las propiedades y las clases anidadas de un objeto **Type** para averiguarlo todo sobre dicho tipo.  
  
 Use <xref:System.Reflection.Assembly.GetType%2A?displayProperty=nameWithType> o <xref:System.Reflection.Assembly.GetTypes%2A?displayProperty=nameWithType> para obtener objetos **Type** de ensamblados no cargados y pasar el nombre de los tipos que quiera. Use <xref:System.Type.GetType%2A?displayProperty=nameWithType> para obtener objetos **Type** de un ensamblado que ya está cargado. Use <xref:System.Reflection.Module.GetType%2A?displayProperty=nameWithType> y <xref:System.Reflection.Module.GetTypes%2A?displayProperty=nameWithType> para obtener objetos **Type** de módulo.  
  
> [!NOTE]
> Si quiere examinar y manipular tipos y métodos genéricos, vea la información adicional proporcionada en [Reflexión y tipos genéricos](reflection-and-generic-types.md) y [Cómo: Examinar y crear instancias de tipos genéricos mediante la reflexión](how-to-examine-and-instantiate-generic-types-with-reflection.md).  
  
 En el ejemplo siguiente se muestra la sintaxis necesaria para obtener el objeto <xref:System.Reflection.Assembly> y el módulo de un ensamblado.  
  
 [!code-cpp[Conceptual.Types.ViewInfo#6](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.types.viewinfo/cpp/source5.cpp#6)]
 [!code-csharp[Conceptual.Types.ViewInfo#6](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.types.viewinfo/cs/source5.cs#6)]
 [!code-vb[Conceptual.Types.ViewInfo#6](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.types.viewinfo/vb/source5.vb#6)]  
  
 En el ejemplo siguiente se muestra cómo obtener objetos **Type** de un ensamblado cargado.  
  
 [!code-cpp[Conceptual.Types.ViewInfo#7](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.types.viewinfo/cpp/source5.cpp#7)]
 [!code-csharp[Conceptual.Types.ViewInfo#7](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.types.viewinfo/cs/source5.cs#7)]
 [!code-vb[Conceptual.Types.ViewInfo#7](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.types.viewinfo/vb/source5.vb#7)]  
  
 Una vez que obtenga un objeto **Type**, hay muchas maneras de obtener información sobre los miembros de dicho tipo. Por ejemplo, puede obtener información sobre todos los miembros del tipo. Para ello, llame al método <xref:System.Type.GetMembers%2A?displayProperty=nameWithType>, que obtiene una matriz de objetos <xref:System.Reflection.MemberInfo> que describen cada uno de los miembros del tipo actual.  
  
 También puede usar métodos en la clase **Type** para recuperar información sobre uno o más constructores, métodos, eventos, campos o propiedades especificados por nombre. Por ejemplo, <xref:System.Type.GetConstructor%2A?displayProperty=nameWithType> encapsula un constructor específico de la clase actual.  
  
 Si tiene un objeto **Type**, puede usar la propiedad <xref:System.Type.Module%2A?displayProperty=nameWithType> para obtener un objeto que encapsule el módulo que contiene dicho tipo. Use la propiedad <xref:System.Reflection.Module.Assembly%2A?displayProperty=nameWithType> para buscar un objeto que encapsule el ensamblado que contiene el módulo. Puede obtener el ensamblado que encapsula el tipo directamente mediante la propiedad <xref:System.Type.Assembly%2A?displayProperty=nameWithType>.  
  
## <a name="systemtype-and-constructorinfo"></a>System.Type y ConstructorInfo  
 En el ejemplo siguiente se muestra cómo enumerar los constructores de una clase, en este caso, la clase <xref:System.String>.  
  
 [!code-cpp[Conceptual.Types.ViewInfo#1](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.types.viewinfo/cpp/source1.cpp#1)]
 [!code-csharp[Conceptual.Types.ViewInfo#1](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.types.viewinfo/cs/source1.cs#1)]
 [!code-vb[Conceptual.Types.ViewInfo#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.types.viewinfo/vb/source1.vb#1)]  
  
## <a name="memberinfo-methodinfo-fieldinfo-and-propertyinfo"></a>MemberInfo, MethodInfo, FieldInfo y PropertyInfo  
 Obtenga información sobre los métodos, las propiedades, los eventos y los campos del tipo mediante los objetos <xref:System.Reflection.MemberInfo>, <xref:System.Reflection.MethodInfo>, <xref:System.Reflection.FieldInfo> o <xref:System.Reflection.PropertyInfo>.  
  
 En el ejemplo siguiente se usa **MemberInfo** para mostrar el número de miembros en la clase **System.IO.File** y se usa la propiedad <xref:System.Type.IsPublic%2A> para determinar la visibilidad de la clase.  
  
 [!code-cpp[Conceptual.Types.ViewInfo#2](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.types.viewinfo/cpp/source2.cpp#2)]
 [!code-csharp[Conceptual.Types.ViewInfo#2](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.types.viewinfo/cs/source2.cs#2)]
 [!code-vb[Conceptual.Types.ViewInfo#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.types.viewinfo/vb/source2.vb#2)]  
  
 En el ejemplo siguiente se investiga el tipo del miembro especificado. Se realiza la reflexión en un miembro de la clase **MemberInfo** y se muestra su tipo.  
  
 [!code-cpp[Conceptual.Types.ViewInfo#3](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.types.viewinfo/cpp/source3.cpp#3)]
 [!code-csharp[Conceptual.Types.ViewInfo#3](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.types.viewinfo/cs/source3.cs#3)]
 [!code-vb[Conceptual.Types.ViewInfo#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.types.viewinfo/vb/source3.vb#3)]  
  
 En el ejemplo siguiente se usan todas las clases **\*Info** de reflexión junto con <xref:System.Reflection.BindingFlags> para enumerar todos los miembros (constructores, campos, propiedades, eventos y métodos) de la clase especificada y dividir los miembros en categorías estáticas y de instancia.  
  
 [!code-cpp[Conceptual.Types.ViewInfo#4](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.types.viewinfo/cpp/source4.cpp#4)]
 [!code-csharp[Conceptual.Types.ViewInfo#4](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.types.viewinfo/cs/source4.cs#4)]
 [!code-vb[Conceptual.Types.ViewInfo#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.types.viewinfo/vb/source4.vb#4)]  
  
## <a name="see-also"></a>Vea también

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
- [Reflexión y tipos genéricos](reflection-and-generic-types.md)
