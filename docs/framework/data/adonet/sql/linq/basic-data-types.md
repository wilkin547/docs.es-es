---
title: Tipos de datos básicos
ms.date: 03/30/2017
ms.assetid: eca2c472-9548-4800-bd31-5d8d9f11752b
ms.openlocfilehash: b05bc69bdd6eea15806b8d928487da2c3f6503b5
ms.sourcegitcommit: 4a8c2b8d0df44142728b68ebc842575840476f6d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2019
ms.locfileid: "58545707"
---
# <a name="basic-data-types"></a>Tipos de datos básicos
Como las consultas de LINQ to SQL se convierten a Transact-SQL antes de ejecutarlas en Microsoft SQL Server, LINQ to SQL admite una funcionalidad muy similar a la integrada en SQL Server para los tipos de datos básicos.  
  
## <a name="casting"></a>Conversión  
 Se habilitan las conversiones implícitas o explícitas de tipos CLR de origen a tipos CLR de destino si hay una conversión similar válida en SQL Server. Para obtener más información acerca de la conversión de CLR, vea [CType Function](~/docs/visual-basic/language-reference/functions/ctype-function.md) (Visual Basic) y [como](~/docs/csharp/language-reference/keywords/as.md). Después de la conversión, las conversiones de tipos cambian el comportamiento de las operaciones realizadas en una expresión CLR para coincidir con el comportamiento de otras expresiones CLR que tienen una asignación natural al tipo de destino. Las conversiones de tipos también se pueden convertir en el contexto de la asignación de herencia. Los tipos de los objetos se pueden convertir a subtipos de entidad más específicos de forma que se pueda tener acceso a los datos específicos de su subtipo.  
  
## <a name="equality-operators"></a>Operadores de igualdad  
 LINQ to SQL admite los siguientes operadores de igualdad en los tipos de datos básicos dentro de las consultas de LINQ to SQL:  
  
-   Igual y el operador de desigualdad: Se admiten los operadores de igualdad y desigualdad numérico, <xref:System.Boolean>, <xref:System.DateTime>, y <xref:System.TimeSpan> tipos. Para obtener más información acerca de los operadores de Visual Basic `=` y `<>`, consulte [operadores de comparación](~/docs/visual-basic/language-reference/operators/comparison-operators.md). Para obtener más información acerca de C# operadores de comparación `==` y `!=`, consulte [operadores de igualdad](~/docs/csharp/language-reference/operators/equality-operators.md).
  
-   Es el operador: El `IS` operador tiene un equivalente compatible cuando se utiliza la asignación de herencia. Se puede utilizar en lugar de probar directamente la columna discriminadora para determinar si un objeto es de un tipo de entidad concreto, y se convierte en una marca de verificación en la columna discriminadora. Para obtener más información acerca de Visual Basic y C# es operadores, vea [operador Is](~/docs/visual-basic/language-reference/operators/is-operator.md) y [es](~/docs/csharp/language-reference/keywords/is.md).  
  
## <a name="see-also"></a>Vea también
- [Asignación de tipos entre CLR y SQL](../../../../../../docs/framework/data/adonet/sql/linq/sql-clr-type-mapping.md)
- [Tipos de datos y funciones](../../../../../../docs/framework/data/adonet/sql/linq/data-types-and-functions.md)
