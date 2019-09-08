---
title: Funciones definidas por el usuario
ms.date: 03/30/2017
ms.assetid: 3304c9b2-5c7a-4a95-9d45-4f260dcb606e
ms.openlocfilehash: 40697da4fe678668f8f7ecda86abebf40da7b973
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/07/2019
ms.locfileid: "70792307"
---
# <a name="user-defined-functions"></a>Funciones definidas por el usuario
[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] utiliza los métodos de un modelo de objetos para representar las funciones definidas por el usuario. Los métodos se designan como funciones aplicando el atributo <xref:System.Data.Linq.Mapping.FunctionAttribute> y, si es necesario, el atributo <xref:System.Data.Linq.Mapping.ParameterAttribute>. Para obtener más información, vea [el LINQ to SQL modelo de objetos](the-linq-to-sql-object-model.md).  
  
 Para evitar que se inicie <xref:System.InvalidOperationException>, las funciones definidas por el usuario en [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] deben presentarse de una de las formas siguientes:  
  
- Una función ajustada como llamada a método que tiene los atributos de asignación correctos. Para obtener más información, consulte [asignación basada en atributos](attribute-based-mapping.md).  
  
- Un método SQL estático específico de [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)].  
  
- Función compatible con un método .NET Framework.  
  
 Los temas de esta sección muestran cómo formar estos métodos y cómo llamarlos en una aplicación si es usted quien escribe el código. Los desarrolladores que usan Visual Studio normalmente usarían el Object Relational Designer para asignar funciones definidas por el usuario.  
  
## <a name="in-this-section"></a>En esta sección  
 [Cómo: Usar funciones escalares definidas por el usuario](how-to-use-scalar-valued-user-defined-functions.md)  
 Describe cómo implementar una función que devuelve valores escalares.  
  
 [Procedimientos: Usar funciones definidas por el usuario con valores de tabla](how-to-use-table-valued-user-defined-functions.md)  
 Describe cómo implementar una función que devuelve valores de tabla.  
  
 [Procedimientos: Llamar a funciones alineadas definidas por el usuario](how-to-call-user-defined-functions-inline.md)  
 Describe cómo realizar llamadas en el código a funciones y cómo varía la ejecución en esos casos.
