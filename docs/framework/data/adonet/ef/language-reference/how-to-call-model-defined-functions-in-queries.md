---
description: 'Más información acerca de cómo: llamar a funciones de Model-Defined en las consultas'
title: Procedimiento para llamar a funciones definidas por el modelo en consultas
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 6c804e4d-f348-4afd-9f63-d3f0f24bc6a9
ms.openlocfilehash: d59ef6edeba1e4b00e0481f8578e9c04735831fa
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99748653"
---
# <a name="how-to-call-model-defined-functions-in-queries"></a>Procedimiento para llamar a funciones definidas por el modelo en consultas

En este tema se describe cómo llamar a las funciones definidas en el modelo conceptual desde LINQ to Entities consultas.  
  
 En el procedimiento siguiente se proporciona un esquema de alto nivel para llamar a una función definida por el modelo desde una consulta LINQ to Entities. El ejemplo que sigue proporciona más detalles sobre los pasos del procedimiento. El procedimiento da por hecho que se ha definido una función en el modelo conceptual. Para obtener más información, vea [Cómo: definir funciones personalizadas en el modelo conceptual](/previous-versions/dotnet/netframework-4.0/dd456812(v=vs.100)).  
  
### <a name="to-call-a-function-defined-in-the-conceptual-model"></a>Para llamar a una función definida en el modelo conceptual  
  
1. Agregue un método de Common Language Runtime (CLR) a su aplicación que se corresponda con la función definida en el modelo conceptual. Para asignar el método, debe aplicarle un atributo <xref:System.Data.Objects.DataClasses.EdmFunctionAttribute>. Tenga en cuenta que los parámetros <xref:System.Data.Objects.DataClasses.EdmFunctionAttribute.NamespaceName%2A> y <xref:System.Data.Objects.DataClasses.EdmFunctionAttribute.FunctionName%2A> del atributo son el nombre del espacio de nombres del modelo conceptual y el nombre de la función en el modelo conceptual, respectivamente. La resolución del nombre de la función para LINQ distingue entre mayúsculas y minúsculas.  
  
2. Llame a la función en una consulta LINQ to Entities.  
  
## <a name="example"></a>Ejemplo  

 En el ejemplo siguiente se muestra cómo llamar a una función que se define en el modelo conceptual desde una consulta LINQ to Entities. En el ejemplo se usa el modelo School. Para obtener información sobre el modelo School, vea [crear la base de datos de ejemplo School](/previous-versions/dotnet/netframework-4.0/bb399731(v=vs.100)) y [generar el archivo School. edmx](/previous-versions/dotnet/netframework-4.0/bb399739(v=vs.100)).  
  
 La siguiente función del modelo conceptual devuelve el número de años transcurridos desde que se contrató a un instructor. Para obtener información sobre cómo agregar la función a un modelo conceptual, vea [Cómo: definir funciones personalizadas en el modelo conceptual](/previous-versions/dotnet/netframework-4.0/dd456812(v=vs.100))).  
  
 [!code-xml[DP ConceptualModelFunctions#1](../../../../../../samples/snippets/xml/VS_Snippets_Data/dp conceptualmodelfunctions/xml/school.edmx#1)]
  
## <a name="example"></a>Ejemplo  

 A continuación, agregue el siguiente método a su aplicación y utilice un atributo <xref:System.Data.Objects.DataClasses.EdmFunctionAttribute> para asignarlo a la función del modelo conceptual:  
  
 [!code-csharp[DP ConceptualModelFunctions#2](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp conceptualmodelfunctions/cs/program.cs#2)]
 [!code-vb[DP ConceptualModelFunctions#2](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/dp conceptualmodelfunctions/vb/module1.vb#2)]  
  
## <a name="example"></a>Ejemplo  

 Ahora puede llamar a la función de modelo conceptual desde una consulta de LINQ to Entities. El siguiente código llama al método para mostrar todos los instructores que se contrataron hace más de diez años:  
  
 [!code-csharp[DP ConceptualModelFunctions#3](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp conceptualmodelfunctions/cs/program.cs#3)]
 [!code-vb[DP ConceptualModelFunctions#3](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/dp conceptualmodelfunctions/vb/module1.vb#3)]  
  
## <a name="see-also"></a>Vea también

- [.edmx, Información general sobre el archivo](/previous-versions/dotnet/netframework-4.0/cc982042(v=vs.100))
- [Consultas en LINQ to Entities](queries-in-linq-to-entities.md)
- [Llamar a funciones en consultas de LINQ to Entities](calling-functions-in-linq-to-entities-queries.md)
- [Procedimiento para llamar a funciones definidas por el modelo como métodos de objeto](how-to-call-model-defined-functions-as-object-methods.md)
