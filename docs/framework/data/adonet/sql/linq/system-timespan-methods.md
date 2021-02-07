---
description: 'Más información sobre: métodos System. TimeSpan'
title: System.TimeSpan (Métodos)
ms.date: 03/30/2017
ms.assetid: 9333fee8-1454-4374-855b-8c14c002f48f
ms.openlocfilehash: fa3192d18a59e589f2c7510776f8510b2c12cac4
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99681193"
---
# <a name="systemtimespan-methods"></a>System.TimeSpan (Métodos)

La compatibilidad de miembros con <xref:System.TimeSpan?displayProperty=nameWithType> depende en gran medida de las versiones de .NET Framework y Microsoft SQL Server que use.  
  
 Si no se admite un método, operador o propiedad, significa que LINQ to SQL no puede traducir el miembro para la ejecución en SQL Server. Todavía puede usar estos miembros en el código. No obstante, deben evaluarse antes de traducir la consulta a Transact-SQL o después de recuperar los resultados de la base de datos.  
  
## <a name="previous-limitations"></a>Limitaciones anteriores  

 Al usar LINQ to SQL con versiones de .NET Framework anteriores a .NET Framework 3.5 Service Pack 1, no puede asignar campos de base de datos de SQL Server a <xref:System.TimeSpan?displayProperty=nameWithType>. Sin embargo, se admiten las operaciones en <xref:System.TimeSpan> porque se pueden devolver valores <xref:System.TimeSpan> a partir de la sustracción de <xref:System.DateTime> o se pueden incluir en una expresión como una variable literal o una variable enlazada.  
  
## <a name="supported-systemtimespan-member-support"></a>Compatibilidad con miembros System. TimeSpan admitidos

 Los métodos, operadores y propiedades siguientes admitidos en LINQ to SQL, están disponibles para su uso en las consultas de LINQ to SQL. Una vez asignado en el modelo de objetos o en el archivo de asignación externo, LINQ to SQL permite llamar a muchos de los miembros de <xref:System.TimeSpan?displayProperty=nameWithType> dentro de las consultas de LINQ to SQL.  
  
|Métodos <xref:System.TimeSpan> compatibles|Operadores <xref:System.TimeSpan> compatibles|Propiedades <xref:System.TimeSpan> admitidas|  
|------------------------------------------------------------------------------------------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------|  
|<xref:System.TimeSpan.Compare%2A>|<xref:System.TimeSpan.op_Equality%2A>|<xref:System.TimeSpan.Days%2A>|  
|<xref:System.TimeSpan.CompareTo%28System.TimeSpan%29>|<xref:System.TimeSpan.op_GreaterThan%2A>|<xref:System.TimeSpan.Hours%2A>|  
|<xref:System.TimeSpan.Duration%2A>|<xref:System.TimeSpan.op_GreaterThanOrEqual%2A>|<xref:System.TimeSpan.MaxValue>|  
|<xref:System.TimeSpan.Equals%28System.TimeSpan%2CSystem.TimeSpan%29>|<xref:System.TimeSpan.op_Inequality%2A>|<xref:System.TimeSpan.Milliseconds%2A>|  
|<xref:System.TimeSpan.Equals%28System.TimeSpan%29>|<xref:System.TimeSpan.op_LessThan%2A>|<xref:System.TimeSpan.Minutes%2A>|  
||<xref:System.TimeSpan.op_LessThanOrEqual%2A>|<xref:System.TimeSpan.MinValue>|  
  
> [!NOTE]
> La capacidad para asignar <xref:System.TimeSpan?displayProperty=nameWithType> a una columna `TIME` de SQL con LINQ to SQL requiere .NET Framework 3.5 Service Pack 1 y posteriores. El tipo de datos `TIME` de SQL está disponible solo en Microsoft SQL Server 2008 y posteriores.  
  
### <a name="addition-and-subtraction"></a>Suma y resta  

 Aunque el tipo <xref:System.TimeSpan?displayProperty=nameWithType> de CLR admite la suma y resta, el tipo `TIME` de SQL no. Debido a esto, las consultas de LINQ to SQL generarán errores si intentan realizar operaciones de suma o resta cuando se asignan al tipo `TIME` de SQL. Puede encontrar otras consideraciones para trabajar con tipos de fecha y hora SQL en [la asignación de tipos SQL-CLR](sql-clr-type-mapping.md).  
  
## <a name="see-also"></a>Vea también

- [Conceptos sobre consultas](query-concepts.md)
- [Crear el modelo de objetos](creating-the-object-model.md)
- [Asignación de tipos entre CLR y SQL](sql-clr-type-mapping.md)
- [Tipos de datos y funciones](data-types-and-functions.md)
