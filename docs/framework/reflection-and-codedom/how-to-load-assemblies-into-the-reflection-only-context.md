---
title: "How to: Load Assemblies into the Reflection-Only Context | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "reflection, reflection-only loader context"
  - "assemblies [.NET Framework], loading for reflection"
  - "attributes [.NET Framework], retrieving"
  - "assemblies [.NET Framework], reflection-only loader context"
  - "reflection-only loader context"
ms.assetid: 9818b660-52f5-423d-a9af-e75163aa7068
caps.latest.revision: 8
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 8
---
# How to: Load Assemblies into the Reflection-Only Context
El contexto de sólo reflexión le permite examinar ensamblados compilados para otras plataformas o para otras versiones de .NET Framework.  El código cargado en este contexto sólo se puede examinar; no puede ejecutarse.  Esto significa que no se pueden crear objetos, porque no se pueden ejecutar los constructores.  Dado que no se puede ejecutar el código, las dependencias no se cargan automáticamente.  Si necesita examinarlos, debe cargarlas manualmente.  
  
### Para cargar un ensamblado en un contexto de sólo reflexión  
  
1.  Utilice la sobrecarga del método <xref:System.Reflection.Assembly.ReflectionOnlyLoad%28System.String%29> para cargar el ensamblado dando su nombre para mostrar o el método <xref:System.Reflection.Assembly.ReflectionOnlyLoadFrom%2A> para cargar el ensamblado proporcionando su ruta de acceso.  Si el ensamblado es una imagen binaria, utilice la sobrecarga del método [ReflectionOnlyLoad\(Byte\<xref:System.Reflection.Assembly.ReflectionOnlyLoad%28System.Byte%5B%5D%29>.  
  
    > [!NOTE]
    >  No se puede utilizar el contexto de sólo reflexión para cargar una versión de .dll desde una versión de .NET Framework distinta a la versión usada en el contexto de ejecución.  
  
2.  Si el ensamblado tiene dependencias, el método <xref:System.Reflection.Assembly.ReflectionOnlyLoad%2A> no las carga.  Si necesita examinarlas, debe cargarlas manualmente.  
  
3.  Determine si un ensamblado está cargado en el contexto de sólo reflexión utilizando la propiedad <xref:System.Reflection.Assembly.ReflectionOnly%2A> del ensamblado.  
  
4.  Si se han aplicado atributos al ensamblado o a tipos del ensamblado, examine esos atributos utilizando la clase <xref:System.Reflection.CustomAttributeData> para garantizar que no se intenta ejecutar código en el contexto de sólo reflexión.  Utilice la sobrecarga adecuada del método <xref:System.Reflection.CustomAttributeData.GetCustomAttributes%2A?displayProperty=fullName> para obtener objetos <xref:System.Reflection.CustomAttributeData> que representan los atributos aplicados a un ensamblado, miembro, módulo o parámetro.  
  
    > [!NOTE]
    >  Los atributos aplicados al ensamblado o a su contenido podrían estar definidos en el ensamblado o bien en otro ensamblado cargado en el contexto de sólo reflexión.  No hay ninguna manera de saber de antemano dónde se definen los atributos.  
  
## Ejemplo  
 El ejemplo de código siguiente muestra cómo examinar los atributos aplicados a un ensamblado cargado en el contexto de sólo reflexión.  
  
 El ejemplo de código define un atributo personalizado con dos constructores y una propiedad.  El atributo se aplica al ensamblado, a un tipo de prueba declarado en el ensamblado, a un método del tipo y a un parámetro del método.  Cuando se ejecuta, el ensamblado se carga en el contexto de sólo reflexión y muestra información sobre los atributos personalizados que se le aplicaron y a los tipos y miembros que contiene.  
  
> [!NOTE]
>  Para simplificar el ejemplo de código, el ensamblado se carga y se examina a sí mismo.  Normalmente, no es de esperar encontrar el mismo ensamblado cargado tanto en el contexto de ejecución como en el contexto de sólo reflexión.  
  
 [!code-cpp[CustomAttributeData#1](../../../samples/snippets/cpp/VS_Snippets_CLR/CustomAttributeData/CPP/source.cpp#1)]
 [!code-csharp[CustomAttributeData#1](../../../samples/snippets/csharp/VS_Snippets_CLR/CustomAttributeData/CS/source.cs#1)]
 [!code-vb[CustomAttributeData#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/CustomAttributeData/VB/source.vb#1)]  
  
## Vea también  
 <xref:System.Reflection.Assembly.ReflectionOnlyLoad%2A>   
 <xref:System.Reflection.Assembly.ReflectionOnly%2A>   
 <xref:System.Reflection.CustomAttributeData>