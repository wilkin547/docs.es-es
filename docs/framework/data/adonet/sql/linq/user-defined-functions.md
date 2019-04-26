---
title: Funciones definidas por el usuario
ms.date: 03/30/2017
ms.assetid: 3304c9b2-5c7a-4a95-9d45-4f260dcb606e
ms.openlocfilehash: f1222d9332d365c9c3c6ca2aa28cbb48e92c04e0
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61917675"
---
# <a name="user-defined-functions"></a>Funciones definidas por el usuario
[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] utiliza los métodos de un modelo de objetos para representar las funciones definidas por el usuario. Los métodos se designan como funciones aplicando el atributo <xref:System.Data.Linq.Mapping.FunctionAttribute> y, si es necesario, el atributo <xref:System.Data.Linq.Mapping.ParameterAttribute>. Para obtener más información, consulte [el modelo LINQ to SQL objeto](../../../../../../docs/framework/data/adonet/sql/linq/the-linq-to-sql-object-model.md).  
  
 Para evitar que se inicie <xref:System.InvalidOperationException>, las funciones definidas por el usuario en [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] deben presentarse de una de las formas siguientes:  
  
-   Una función ajustada como llamada a método que tiene los atributos de asignación correctos. Para obtener más información, consulte [asignación basada en atributos](../../../../../../docs/framework/data/adonet/sql/linq/attribute-based-mapping.md).  
  
-   Un método SQL estático específico de [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)].  
  
-   Una función admitida por un método [!INCLUDE[dnprdnshort](../../../../../../includes/dnprdnshort-md.md)].  
  
 Los temas de esta sección muestran cómo formar estos métodos y cómo llamarlos en una aplicación si es usted quien escribe el código. Los desarrolladores que usan Visual Studio normalmente usaría el [!INCLUDE[vs_ordesigner_long](../../../../../../includes/vs-ordesigner-long-md.md)] para asignar funciones definidas por el usuario.  
  
## <a name="in-this-section"></a>En esta sección  
 [Cómo: Utilice las funciones escalares de definido por el usuario](../../../../../../docs/framework/data/adonet/sql/linq/how-to-use-scalar-valued-user-defined-functions.md)  
 Describe cómo implementar una función que devuelve valores escalares.  
  
 [Cómo: Usar las funciones con valores de tabla de definido por el usuario](../../../../../../docs/framework/data/adonet/sql/linq/how-to-use-table-valued-user-defined-functions.md)  
 Describe cómo implementar una función que devuelve valores de tabla.  
  
 [Cómo: Llamar a funciones alineadas definidas por usuario](../../../../../../docs/framework/data/adonet/sql/linq/how-to-call-user-defined-functions-inline.md)  
 Describe cómo realizar llamadas en el código a funciones y cómo varía la ejecución en esos casos.
