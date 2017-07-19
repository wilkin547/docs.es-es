---
title: "Viewing Type Information | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
helpviewer_keywords: 
  - "types, viewing type information"
  - "Type object"
  - "viewing type information"
  - "reflection, viewing type information"
ms.assetid: 7e7303a9-4064-4738-b4e7-b75974ed70d2
caps.latest.revision: 13
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 12
---
# Viewing Type Information
La clase <xref:System.Type?displayProperty=fullName> es fundamental para la reflexión.  Common Language Runtime crea **Type** para un tipo cargado cuando lo solicita la reflexión.  Se pueden utilizar los métodos, campos, propiedades y clases anidadas de un objeto **Type** para averiguarlo todo sobre dicho tipo.  
  
 Utilice <xref:System.Reflection.Assembly.GetType%2A?displayProperty=fullName> o <xref:System.Reflection.Assembly.GetTypes%2A?displayProperty=fullName> para obtener objetos **Type** de los ensamblados que no han sido cargados, pasando el nombre de los tipos que desea.  Utilice <xref:System.Type.GetType%2A?displayProperty=fullName> para obtener los objetos **Type** de un ensamblado cargado.  Utilice <xref:System.Reflection.Module.GetType%2A?displayProperty=fullName> y <xref:System.Reflection.Module.GetTypes%2A?displayProperty=fullName> para obtener los objetos **Type** del módulo.  
  
> [!NOTE]
>  Si desea examinar y manipular tipos y métodos genéricos, vea la información adicional que se proporciona en [Reflection and Generic Types](../../../docs/framework/reflection-and-codedom/reflection-and-generic-types.md) y en [How to: Examine and Instantiate Generic Types with Reflection](../../../docs/framework/reflection-and-codedom/how-to-examine-and-instantiate-generic-types-with-reflection.md).  
  
 En el ejemplo siguiente se muestra la sintaxis necesaria para obtener el objeto <xref:System.Reflection.Assembly> y el módulo de un ensamblado.  
  
 [!code-cpp[Conceptual.Types.ViewInfo#6](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.types.viewinfo/cpp/source5.cpp#6)]
 [!code-csharp[Conceptual.Types.ViewInfo#6](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.types.viewinfo/cs/source5.cs#6)]
 [!code-vb[Conceptual.Types.ViewInfo#6](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.types.viewinfo/vb/source5.vb#6)]  
  
 En el ejemplo siguiente se muestra cómo obtener los objetos **Type** de un ensamblado cargado.  
  
 [!code-cpp[Conceptual.Types.ViewInfo#7](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.types.viewinfo/cpp/source5.cpp#7)]
 [!code-csharp[Conceptual.Types.ViewInfo#7](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.types.viewinfo/cs/source5.cs#7)]
 [!code-vb[Conceptual.Types.ViewInfo#7](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.types.viewinfo/vb/source5.vb#7)]  
  
 Tras obtener un **Type**, existen varias maneras de detectar información sobre los miembros de dicho tipo.  Por ejemplo, para obtener información sobre todos los miembros del tipo, llame al método <xref:System.Type.GetMembers%2A?displayProperty=fullName>, que obtiene una matriz de objetos <xref:System.Reflection.MemberInfo> que describe cada uno de los miembros del tipo actual.  
  
 También se pueden utilizar métodos en la clase **Type** para recuperar información sobre uno o varios constructores, métodos, eventos, propiedades o campos especificados por su nombre.  Por ejemplo, <xref:System.Type.GetConstructor%2A?displayProperty=fullName> encapsula un constructor específico de la clase actual.  
  
 Si tiene **Type**, puede utilizar la propiedad <xref:System.Type.Module%2A?displayProperty=fullName> para obtener un objeto que encapsule el módulo que contiene dicho tipo.  Se utiliza la propiedad <xref:System.Reflection.Module.Assembly%2A?displayProperty=fullName> para buscar un objeto que encapsule el ensamblado que contiene el módulo.  Para obtener directamente el ensamblado que encapsula el tipo, utilice la propiedad <xref:System.Type.Assembly%2A?displayProperty=fullName>.  
  
## System.Type y ConstructorInfo  
 En el ejemplo siguiente se indica cómo enumerar los constructores de una clase; en este caso, la clase <xref:System.String>.  
  
 [!code-cpp[Conceptual.Types.ViewInfo#1](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.types.viewinfo/cpp/source1.cpp#1)]
 [!code-csharp[Conceptual.Types.ViewInfo#1](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.types.viewinfo/cs/source1.cs#1)]
 [!code-vb[Conceptual.Types.ViewInfo#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.types.viewinfo/vb/source1.vb#1)]  
  
## MemberInfo, MethodInfo, FieldInfo y PropertyInfo  
 Para obtener información sobre los métodos, propiedades, eventos y campos del tipo, utilice los objetos <xref:System.Reflection.MemberInfo>, <xref:System.Reflection.MethodInfo>, <xref:System.Reflection.FieldInfo> o <xref:System.Reflection.PropertyInfo>.  
  
 En el ejemplo siguiente, se utiliza **MemberInfo** para mostrar el número de miembros de la clase **System.IO.File** y se utiliza la propiedad [System.Type.IsPublic](frlrfSystemTypeClassIsPublicTopic) para determinar la visibilidad de la clase.  
  
 [!code-cpp[Conceptual.Types.ViewInfo#2](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.types.viewinfo/cpp/source2.cpp#2)]
 [!code-csharp[Conceptual.Types.ViewInfo#2](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.types.viewinfo/cs/source2.cs#2)]
 [!code-vb[Conceptual.Types.ViewInfo#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.types.viewinfo/vb/source2.vb#2)]  
  
 En el ejemplo siguiente se investiga el tipo del miembro especificado.  Realiza una reflexión en un miembro de la clase **MemberInfo** y muestra su tipo.  
  
 [!code-cpp[Conceptual.Types.ViewInfo#3](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.types.viewinfo/cpp/source3.cpp#3)]
 [!code-csharp[Conceptual.Types.ViewInfo#3](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.types.viewinfo/cs/source3.cs#3)]
 [!code-vb[Conceptual.Types.ViewInfo#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.types.viewinfo/vb/source3.vb#3)]  
  
 En el ejemplo siguiente se utilizan todas las clases **\*Info** de Reflection junto con <xref:System.Reflection.BindingFlags> para enumerar todos los miembros \(constructores, campos, propiedades, eventos y métodos\) de la clase especificada, dividiendo los miembros en las categorías de miembros estáticos y miembros de instancia.  
  
 [!code-cpp[Conceptual.Types.ViewInfo#4](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.types.viewinfo/cpp/source4.cpp#4)]
 [!code-csharp[Conceptual.Types.ViewInfo#4](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.types.viewinfo/cs/source4.cs#4)]
 [!code-vb[Conceptual.Types.ViewInfo#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.types.viewinfo/vb/source4.vb#4)]  
  
## Vea también  
 <xref:System.Reflection.BindingFlags>   
 <xref:System.Reflection.Assembly.GetType%2A?displayProperty=fullName>   
 <xref:System.Reflection.Assembly.GetTypes%2A?displayProperty=fullName>   
 <xref:System.Type.GetType%2A?displayProperty=fullName>   
 <xref:System.Type.GetMembers%2A?displayProperty=fullName>   
 <xref:System.Type.GetFields%2A?displayProperty=fullName>   
 <xref:System.Reflection.Module.GetType%2A?displayProperty=fullName>   
 <xref:System.Reflection.Module.GetTypes%2A?displayProperty=fullName>   
 <xref:System.Reflection.MemberInfo>   
 <xref:System.Reflection.ConstructorInfo>   
 <xref:System.Reflection.MethodInfo>   
 <xref:System.Reflection.FieldInfo>   
 <xref:System.Reflection.EventInfo>   
 <xref:System.Reflection.ParameterInfo>   
 [Reflection and Generic Types](../../../docs/framework/reflection-and-codedom/reflection-and-generic-types.md)