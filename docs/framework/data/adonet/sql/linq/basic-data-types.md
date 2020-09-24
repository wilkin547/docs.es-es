---
title: Tipos de datos básicos
ms.date: 03/30/2017
ms.assetid: eca2c472-9548-4800-bd31-5d8d9f11752b
ms.openlocfilehash: ae561bad3315977ba12dd0e12abda1da163ca456
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/24/2020
ms.locfileid: "91156022"
---
# <a name="basic-data-types"></a>Tipos de datos básicos

Como las consultas de LINQ to SQL se convierten a Transact-SQL antes de ejecutarlas en Microsoft SQL Server, LINQ to SQL admite una funcionalidad muy similar a la integrada en SQL Server para los tipos de datos básicos.  
  
## <a name="casting"></a>Conversión  

 Se habilitan las conversiones implícitas o explícitas de tipos CLR de origen a tipos CLR de destino si hay una conversión similar válida en SQL Server. Para obtener más información sobre la conversión de CLR, vea [función ctype](../../../../../visual-basic/language-reference/functions/ctype-function.md) (Visual Basic) y [operadores de prueba de tipos y conversión](../../../../../csharp/language-reference/operators/type-testing-and-cast.md). Después de la conversión, las conversiones de tipos cambian el comportamiento de las operaciones realizadas en una expresión CLR para coincidir con el comportamiento de otras expresiones CLR que tienen una asignación natural al tipo de destino. Las conversiones de tipos también se pueden convertir en el contexto de la asignación de herencia. Los tipos de los objetos se pueden convertir a subtipos de entidad más específicos de forma que se pueda tener acceso a los datos específicos de su subtipo.  
  
## <a name="equality-operators"></a>Operadores de igualdad  

 LINQ to SQL admite los siguientes operadores de igualdad en los tipos de datos básicos dentro de las consultas de LINQ to SQL:  
  
- Operador Equal y desigualdad: se admiten los operadores de igualdad y desigualdad para los tipos numéricos, <xref:System.Boolean> , <xref:System.DateTime> y <xref:System.TimeSpan> . Para obtener más información sobre los operadores de Visual Basic `=` y `<>` , vea [operadores de comparación](../../../../../visual-basic/language-reference/operators/comparison-operators.md). Para obtener más información sobre los operadores de comparación de C# `==` y `!=` , vea [operadores de igualdad](../../../../../csharp/language-reference/operators/equality-operators.md).
  
- Operador Is: el operador `IS` tiene un equivalente compatible cuando se utiliza la asignación de herencia. Se puede utilizar en lugar de probar directamente la columna discriminadora para determinar si un objeto es de un tipo de entidad concreto, y se convierte en una marca de verificación en la columna discriminadora. Para obtener más información acerca de los operadores Visual Basic y C# es, vea [is (operador](../../../../../visual-basic/language-reference/operators/is-operator.md) ) y [es](../../../../../csharp/language-reference/operators/type-testing-and-cast.md#is-operator).  
  
## <a name="see-also"></a>Vea también

- [Asignación de tipos entre CLR y SQL](sql-clr-type-mapping.md)
- [Tipos de datos y funciones](data-types-and-functions.md)
