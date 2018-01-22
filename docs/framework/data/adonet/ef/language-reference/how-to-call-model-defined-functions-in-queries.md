---
title: "Cómo: Llamar a funciones definidas por el modelo en consultas"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
ms.assetid: 6c804e4d-f348-4afd-9f63-d3f0f24bc6a9
caps.latest.revision: "3"
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: ec20542ad452bcefbe2b6d286e68ad8bbfb5adb9
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/19/2018
---
# <a name="how-to-call-model-defined-functions-in-queries"></a>Cómo: Llamar a funciones definidas por el modelo en consultas
En este tema se describe cómo llamar a las funciones definidas en el modelo conceptual desde consultas [!INCLUDE[linq_entities](../../../../../../includes/linq-entities-md.md)].  
  
 El siguiente procedimiento proporciona un esquema de alto nivel para llamar a una función definida por el modelo desde una consulta [!INCLUDE[linq_entities](../../../../../../includes/linq-entities-md.md)]. El ejemplo que sigue proporciona más detalles sobre los pasos del procedimiento. El procedimiento da por hecho que se ha definido una función en el modelo conceptual. Para obtener más información, consulte [Cómo: definir funciones personalizadas en el modelo Conceptual](http://msdn.microsoft.com/library/0dad7b8b-58f6-4271-b238-f34810d68e5f).  
  
### <a name="to-call-a-function-defined-in-the-conceptual-model"></a>Para llamar a una función definida en el modelo conceptual  
  
1.  Agregue un método de Common Language Runtime (CLR) a su aplicación que se corresponda con la función definida en el modelo conceptual. Para asignar el método, debe aplicarle un atributo <xref:System.Data.Objects.DataClasses.EdmFunctionAttribute>. Tenga en cuenta que los parámetros <xref:System.Data.Objects.DataClasses.EdmFunctionAttribute.NamespaceName%2A> y <xref:System.Data.Objects.DataClasses.EdmFunctionAttribute.FunctionName%2A> del atributo son el nombre del espacio de nombres del modelo conceptual y el nombre de la función en el modelo conceptual, respectivamente. La resolución del nombre de la función para LINQ distingue entre mayúsculas y minúsculas.  
  
2.  Llame a la función en una consulta [!INCLUDE[linq_entities](../../../../../../includes/linq-entities-md.md)].  
  
## <a name="example"></a>Ejemplo  
 En el siguiente ejemplo se muestra cómo llamar a una función que se define en el modelo conceptual desde una consulta [!INCLUDE[linq_entities](../../../../../../includes/linq-entities-md.md)]. En el ejemplo se usa el modelo School. Para obtener información sobre el modelo School, vea [crear la base de datos de ejemplo School](http://msdn.microsoft.com/library/c1bec483-a0ea-4660-aa0b-7b0a8b68fed0) y [generar el archivo .edmx de School](http://msdn.microsoft.com/library/c48b3907-a8be-4fe6-884c-e95af1852758).  
  
 La siguiente función del modelo conceptual devuelve el número de años transcurridos desde que se contrató a un instructor. Para obtener información acerca de cómo agregar la función a un modelo conceptual, consulte [Cómo: definir funciones personalizadas en el modelo Conceptual](http://msdn.microsoft.com/library/0dad7b8b-58f6-4271-b238-f34810d68e5f).)  
  
 [!code-xml[DP ConceptualModelFunctions#1](../../../../../../samples/snippets/xml/VS_Snippets_Data/dp conceptualmodelfunctions/xml/school.edmx#1)]
  
## <a name="example"></a>Ejemplo  
 A continuación, agregue el siguiente método a su aplicación y utilice un atributo <xref:System.Data.Objects.DataClasses.EdmFunctionAttribute> para asignarlo a la función del modelo conceptual:  
  
 [!code-csharp[DP ConceptualModelFunctions#2](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp conceptualmodelfunctions/cs/program.cs#2)]
 [!code-vb[DP ConceptualModelFunctions#2](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/dp conceptualmodelfunctions/vb/module1.vb#2)]  
  
## <a name="example"></a>Ejemplo  
 Ahora puede llamar a la función del modelo conceptual desde una consulta [!INCLUDE[linq_entities](../../../../../../includes/linq-entities-md.md)]. El siguiente código llama al método para mostrar todos los instructores que se contrataron hace más de diez años:  
  
 [!code-csharp[DP ConceptualModelFunctions#3](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp conceptualmodelfunctions/cs/program.cs#3)]
 [!code-vb[DP ConceptualModelFunctions#3](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/dp conceptualmodelfunctions/vb/module1.vb#3)]  
  
## <a name="see-also"></a>Vea también  
 [información general de archivo .edmx](http://msdn.microsoft.com/library/f4c8e7ce-1db6-417e-9759-15f8b55155d4)  
 [Consultas en LINQ to Entities](../../../../../../docs/framework/data/adonet/ef/language-reference/queries-in-linq-to-entities.md)  
 [Llamada a funciones en consultas de LINQ to Entities](../../../../../../docs/framework/data/adonet/ef/language-reference/calling-functions-in-linq-to-entities-queries.md)  
 [Llamada a funciones definidas por el modelo como métodos de objeto](../../../../../../docs/framework/data/adonet/ef/language-reference/how-to-call-model-defined-functions-as-object-methods.md)
