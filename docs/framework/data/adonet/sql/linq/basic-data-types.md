---
title: Tipos de datos básicos
ms.date: 03/30/2017
ms.assetid: eca2c472-9548-4800-bd31-5d8d9f11752b
ms.openlocfilehash: b01a49afa99fc7ecdb7a113a5056e37d901527a1
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "69964064"
---
# <a name="basic-data-types"></a>Tipos de datos básicos
Como las consultas de LINQ to SQL se convierten a Transact-SQL antes de ejecutarlas en Microsoft SQL Server, LINQ to SQL admite una funcionalidad muy similar a la integrada en SQL Server para los tipos de datos básicos.  
  
## <a name="casting"></a>Conversión  
 Se habilitan las conversiones implícitas o explícitas de tipos CLR de origen a tipos CLR de destino si hay una conversión similar válida en SQL Server. Para obtener más información sobre la conversión de CLR, vea [función ctype](../../../../../visual-basic/language-reference/functions/ctype-function.md) (Visual Basic) y [operadores de prueba de tipos y conversión](../../../../../csharp/language-reference/operators/type-testing-and-cast.md). Después de la conversión, las conversiones de tipos cambian el comportamiento de las operaciones realizadas en una expresión CLR para coincidir con el comportamiento de otras expresiones CLR que tienen una asignación natural al tipo de destino. Las conversiones de tipos también se pueden convertir en el contexto de la asignación de herencia. Los tipos de los objetos se pueden convertir a subtipos de entidad más específicos de forma que se pueda tener acceso a los datos específicos de su subtipo.  
  
## <a name="equality-operators"></a>Operadores de igualdad  
 LINQ to SQL admite los siguientes operadores de igualdad en los tipos de datos básicos dentro de las consultas de LINQ to SQL:  
  
- Operador de igualdad y desigualdad: Los operadores de igualdad y desigualdad se admiten para <xref:System.Boolean>los <xref:System.DateTime>tipos numéricos,, y <xref:System.TimeSpan> . Para obtener más información sobre `=` los `<>`operadores de Visual Basic y, vea [operadores de comparación](../../../../../visual-basic/language-reference/operators/comparison-operators.md). Para obtener más información C# sobre los `==` operadores `!=`de comparación y, vea [operadores de igualdad](../../../../../csharp/language-reference/operators/equality-operators.md).
  
- Operador is: El `IS` operador tiene una traducción compatible cuando se utiliza la asignación de herencia. Se puede utilizar en lugar de probar directamente la columna discriminadora para determinar si un objeto es de un tipo de entidad concreto, y se convierte en una marca de verificación en la columna discriminadora. Para obtener más información acerca de los C# operadores Visual Basic y is, vea [is (operador](../../../../../visual-basic/language-reference/operators/is-operator.md) ) y [es](../../../../../csharp/language-reference/operators/type-testing-and-cast.md#is-operator).  
  
## <a name="see-also"></a>Vea también

- [Asignación de tipos entre CLR y SQL](../../../../../../docs/framework/data/adonet/sql/linq/sql-clr-type-mapping.md)
- [Tipos de datos y funciones](../../../../../../docs/framework/data/adonet/sql/linq/data-types-and-functions.md)
