---
title: Llamar a funciones en consultas de LINQ to Entities
ms.date: 03/30/2017
ms.assetid: 12a525a9-727c-4464-a0c7-71a0ef541792
ms.openlocfilehash: 267bb393d9e75c66eb18139e8897da34bd86e159
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/04/2019
ms.locfileid: "70251265"
---
# <a name="calling-functions-in-linq-to-entities-queries"></a>Llamar a funciones en consultas de LINQ to Entities
Los temas de esta sección describen cómo realizar llamadas a funciones en consultas de LINQ to Entities.  
  
 Las clases <xref:System.Data.Objects.EntityFunctions> y <xref:System.Data.Objects.SqlClient.SqlFunctions> proporcionan acceso a funciones canónicas y de base de datos como parte de Entity Framework. Para obtener más información, consulte [Cómo Llamar a funciones](how-to-call-canonical-functions.md) canónicas y [cómo: Llamar a funciones](how-to-call-database-functions.md)de base de datos.  
  
 El proceso para llamar a una función personalizada requiere tres pasos básicos:  
  
1. Defina una función en su modelo conceptual o declare una función en su modelo de almacenamiento.  
  
2. Agregue un método a su aplicación y asígnelo a la función del modelo con un <xref:System.Data.Objects.DataClasses.EdmFunctionAttribute>.  
  
3. Llame a la función en una consulta LINQ to Entities.  
  
 Para obtener más información, vea los temas de esta sección.  
  
## <a name="in-this-section"></a>En esta sección  
 [Cómo: Llamar a funciones canónicas](how-to-call-canonical-functions.md)  
  
 [Cómo: Llamar a funciones de base de datos](how-to-call-database-functions.md)  
  
 [Procedimientos: Llamar a funciones de base de datos personalizadas](how-to-call-custom-database-functions.md)  
  
 [Cómo: Llamar a funciones definidas por el modelo en consultas](how-to-call-model-defined-functions-in-queries.md)  
  
 [Procedimientos: Llamar a funciones definidas por el modelo como métodos de objeto](how-to-call-model-defined-functions-as-object-methods.md)  
  
## <a name="see-also"></a>Vea también

- [Consultas en LINQ to Entities](queries-in-linq-to-entities.md)
- [Funciones canónicas](canonical-functions.md)
- [Información general sobre el archivo. edmx](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/cc982042(v=vs.100))
- [Procedimientos: Definir funciones personalizadas en el modelo conceptual](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/dd456812(v=vs.100))
