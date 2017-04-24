---
title: "C&#243;mo: Llamar a funciones definidas por el modelo en consultas | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 6c804e4d-f348-4afd-9f63-d3f0f24bc6a9
caps.latest.revision: 3
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 3
---
# C&#243;mo: Llamar a funciones definidas por el modelo en consultas
En este tema se describe cómo llamar a las funciones definidas en el modelo conceptual desde consultas [!INCLUDE[linq_entities](../../../../../../includes/linq-entities-md.md)].  
  
 El siguiente procedimiento proporciona un esquema de alto nivel para llamar a una función definida por el modelo desde una consulta [!INCLUDE[linq_entities](../../../../../../includes/linq-entities-md.md)].  El ejemplo que sigue proporciona más detalles sobre los pasos del procedimiento.  El procedimiento da por hecho que se ha definido una función en el modelo conceptual.  Para obtener más información, consulta [How to: Define Custom Functions in the Conceptual Model](http://msdn.microsoft.com/es-es/0dad7b8b-58f6-4271-b238-f34810d68e5f).  
  
### Para llamar a una función definida en el modelo conceptual  
  
1.  Agregue un método de Common Language Runtime \(CLR\) a su aplicación que se corresponda con la función definida en el modelo conceptual.  Para asignar el método, debe aplicarle un atributo <xref:System.Data.Objects.DataClasses.EdmFunctionAttribute>.  Tenga en cuenta que los parámetros <xref:System.Data.Objects.DataClasses.EdmFunctionAttribute.NamespaceName%2A> y <xref:System.Data.Objects.DataClasses.EdmFunctionAttribute.FunctionName%2A> del atributo son el nombre del espacio de nombres del modelo conceptual y el nombre de la función en el modelo conceptual, respectivamente.  La resolución del nombre de la función para LINQ distingue entre mayúsculas y minúsculas.  
  
2.  Llame a la función en una consulta [!INCLUDE[linq_entities](../../../../../../includes/linq-entities-md.md)].  
  
## Ejemplo  
 En el siguiente ejemplo se muestra cómo llamar a una función que se define en el modelo conceptual desde una consulta [!INCLUDE[linq_entities](../../../../../../includes/linq-entities-md.md)].  En el ejemplo se usa el modelo School.  Para obtener información sobre el modelo School, vea [Creating the School Sample Database](http://msdn.microsoft.com/es-es/c1bec483-a0ea-4660-aa0b-7b0a8b68fed0) y [Generating the School .edmx File](http://msdn.microsoft.com/es-es/c48b3907-a8be-4fe6-884c-e95af1852758).  
  
 La siguiente función del modelo conceptual devuelve el número de años transcurridos desde que se contrató a un instructor.  Para obtener información sobre cómo agregar la función a un modelo conceptual, vea [How to: Define Custom Functions in the Conceptual Model](http://msdn.microsoft.com/es-es/0dad7b8b-58f6-4271-b238-f34810d68e5f).  
  
 [!code-xml[DP ConceptualModelFunctions#1](../../../../../../samples/snippets/xml/VS_Snippets_Data/dp conceptualmodelfunctions/xml/school.edmx#1)]
 <!-- TODO: review snippet reference [!code-xml[DP ConceptualModelFunctions#1](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp conceptualmodelfunctions/cs/obj/debug/edmxresourcestoembed/school.csdl#1)]  -->  
  
## Ejemplo  
 A continuación, agregue el siguiente método a su aplicación y utilice un atributo <xref:System.Data.Objects.DataClasses.EdmFunctionAttribute> para asignarlo a la función del modelo conceptual:  
  
 [!code-csharp[DP ConceptualModelFunctions#2](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp conceptualmodelfunctions/cs/program.cs#2)]
 [!code-vb[DP ConceptualModelFunctions#2](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/dp conceptualmodelfunctions/vb/module1.vb#2)]  
  
## Ejemplo  
 Ahora puede llamar a la función del modelo conceptual desde una consulta [!INCLUDE[linq_entities](../../../../../../includes/linq-entities-md.md)].  El siguiente código llama al método para mostrar todos los instructores que se contrataron hace más de diez años:  
  
 [!code-csharp[DP ConceptualModelFunctions#3](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp conceptualmodelfunctions/cs/program.cs#3)]
 [!code-vb[DP ConceptualModelFunctions#3](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/dp conceptualmodelfunctions/vb/module1.vb#3)]  
  
## Vea también  
 [.edmx File Overview](http://msdn.microsoft.com/es-es/f4c8e7ce-1db6-417e-9759-15f8b55155d4)   
 [Consultas en LINQ to Entities](../../../../../../docs/framework/data/adonet/ef/language-reference/queries-in-linq-to-entities.md)   
 [Llamar a funciones en consultas de LINQ to Entities](../../../../../../docs/framework/data/adonet/ef/language-reference/calling-functions-in-linq-to-entities-queries.md)   
 [Cómo: Llamar a funciones definidas por el modelo como métodos de objeto](../../../../../../docs/framework/data/adonet/ef/language-reference/how-to-call-model-defined-functions-as-object-methods.md)