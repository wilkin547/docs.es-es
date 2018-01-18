---
title: Llamar a funciones en consultas de LINQ to Entities
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 12a525a9-727c-4464-a0c7-71a0ef541792
caps.latest.revision: "3"
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: dd81543f3a89f4f673f999b1fa80575de6d64654
ms.sourcegitcommit: ed26cfef4e18f6d93ab822d8c29f902cff3519d1
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/17/2018
---
# <a name="calling-functions-in-linq-to-entities-queries"></a>Llamar a funciones en consultas de LINQ to Entities
Los temas de esta sección describen cómo realizar llamadas a funciones en consultas de LINQ to Entities.  
  
 Las clases <xref:System.Data.Objects.EntityFunctions> y <xref:System.Data.Objects.SqlClient.SqlFunctions> proporcionan acceso a funciones canónicas y de base de datos como parte de Entity Framework. Para obtener más información, consulte [Cómo: llamar a funciones canónicas](../../../../../../docs/framework/data/adonet/ef/language-reference/how-to-call-canonical-functions.md) y [Cómo: llamar a funciones de base de datos](../../../../../../docs/framework/data/adonet/ef/language-reference/how-to-call-database-functions.md).  
  
 El proceso para llamar a una función personalizada requiere tres pasos básicos:  
  
1.  Defina una función en su modelo conceptual o declare una función en su modelo de almacenamiento.  
  
2.  Agregue un método a su aplicación y asígnelo a la función del modelo con un <xref:System.Data.Objects.DataClasses.EdmFunctionAttribute>.  
  
3.  Llame a la función en una consulta LINQ to Entities.  
  
 Para obtener más información, vea los temas de esta sección.  
  
## <a name="in-this-section"></a>En esta sección  
 [Llamada a funciones canónicas](../../../../../../docs/framework/data/adonet/ef/language-reference/how-to-call-canonical-functions.md)  
  
 [Llamada a funciones de base de datos](../../../../../../docs/framework/data/adonet/ef/language-reference/how-to-call-database-functions.md)  
  
 [Llamada a funciones de base de datos personalizadas](../../../../../../docs/framework/data/adonet/ef/language-reference/how-to-call-custom-database-functions.md)  
  
 [Llamada a funciones definidas por el modelo en consultas](../../../../../../docs/framework/data/adonet/ef/language-reference/how-to-call-model-defined-functions-in-queries.md)  
  
 [Llamada a funciones definidas por el modelo como métodos de objeto](../../../../../../docs/framework/data/adonet/ef/language-reference/how-to-call-model-defined-functions-as-object-methods.md)  
  
## <a name="see-also"></a>Vea también  
 [Consultas en LINQ to Entities](../../../../../../docs/framework/data/adonet/ef/language-reference/queries-in-linq-to-entities.md)  
 [Funciones canónicas](../../../../../../docs/framework/data/adonet/ef/language-reference/canonical-functions.md)  
 [información general de archivo .edmx](http://msdn.microsoft.com/en-us/f4c8e7ce-1db6-417e-9759-15f8b55155d4)  
 [Cómo: definir funciones personalizadas en el modelo Conceptual](http://msdn.microsoft.com/en-us/0dad7b8b-58f6-4271-b238-f34810d68e5f)
