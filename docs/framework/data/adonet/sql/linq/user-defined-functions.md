---
title: Funciones definidas por el usuario
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 3304c9b2-5c7a-4a95-9d45-4f260dcb606e
caps.latest.revision: "3"
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: ad269ddaa7d7c3995672398a24de06f57f7122e2
ms.sourcegitcommit: ed26cfef4e18f6d93ab822d8c29f902cff3519d1
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/17/2018
---
# <a name="user-defined-functions"></a>Funciones definidas por el usuario
[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] utiliza los métodos de un modelo de objetos para representar las funciones definidas por el usuario. Los métodos se designan como funciones aplicando el atributo <xref:System.Data.Linq.Mapping.FunctionAttribute> y, si es necesario, el atributo <xref:System.Data.Linq.Mapping.ParameterAttribute>. Para obtener más información, consulte [el modelo de LINQ to SQL objeto](../../../../../../docs/framework/data/adonet/sql/linq/the-linq-to-sql-object-model.md).  
  
 Para evitar que se inicie <xref:System.InvalidOperationException>, las funciones definidas por el usuario en [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] deben presentarse de una de las formas siguientes:  
  
-   Una función ajustada como llamada a método que tiene los atributos de asignación correctos. Para obtener más información, consulte [asignación basada en el atributo](../../../../../../docs/framework/data/adonet/sql/linq/attribute-based-mapping.md).  
  
-   Un método SQL estático específico de [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)].  
  
-   Una función admitida por un método [!INCLUDE[dnprdnshort](../../../../../../includes/dnprdnshort-md.md)].  
  
 Los temas de esta sección muestran cómo formar estos métodos y cómo llamarlos en una aplicación si es usted quien escribe el código. Los desarrolladores de [!INCLUDE[vs_current_short](../../../../../../includes/vs-current-short-md.md)] normalmente utilizarían el [!INCLUDE[vs_ordesigner_long](../../../../../../includes/vs-ordesigner-long-md.md)] para asignar funciones definidas por el usuario.  
  
## <a name="in-this-section"></a>En esta sección  
 [Uso de funciones escalares definidas por el usuario](../../../../../../docs/framework/data/adonet/sql/linq/how-to-use-scalar-valued-user-defined-functions.md)  
 Describe cómo implementar una función que devuelve valores escalares.  
  
 [Uso de funciones con valores de tabla definidas por el usuario](../../../../../../docs/framework/data/adonet/sql/linq/how-to-use-table-valued-user-defined-functions.md)  
 Describe cómo implementar una función que devuelve valores de tabla.  
  
 [Llamada a funciones alineadas definidas por el usuario](../../../../../../docs/framework/data/adonet/sql/linq/how-to-call-user-defined-functions-inline.md)  
 Describe cómo realizar llamadas en el código a funciones y cómo varía la ejecución en esos casos.
