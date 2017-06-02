---
title: "System.TimeSpan (M&#233;todos) | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 9333fee8-1454-4374-855b-8c14c002f48f
caps.latest.revision: 2
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 2
---
# System.TimeSpan (M&#233;todos)
La compatibilidad de miembros con <xref:System.TimeSpan?displayProperty=fullName> depende en gran medida de las versiones de .NET Framework y Microsoft SQL Server que use.  
  
 Si no se admite un método, operador o propiedad, significa que LINQ to SQL no puede traducir el miembro para la ejecución en SQL Server.  Todavía puede usar estos miembros en el código.  No obstante, deben evaluarse antes de traducir la consulta a Transact\-SQL o después de recuperar los resultados de la base de datos.  
  
## Limitaciones anteriores  
 Al usar LINQ to SQL con versiones de .NET Framework anteriores a .NET Framework 3.5 Service Pack 1, no puede asignar campos de base de datos de SQL Server a <xref:System.TimeSpan?displayProperty=fullName>.  Sin embargo, se admiten las operaciones en <xref:System.TimeSpan> porque se pueden devolver valores <xref:System.TimeSpan> a partir de la sustracción de <xref:System.DateTime> o se pueden incluir en una expresión como una variable literal o una variable enlazada.  
  
## Compatibilidad con el método System.TimeSpan admitido  
 Los métodos, operadores y propiedades siguientes admitidos en LINQ to SQL, están disponibles para su uso en las consultas de LINQ to SQL.  Una vez asignado en el modelo de objetos o en el archivo de asignación externo, LINQ to SQL permite llamar a muchos de los miembros de <xref:System.TimeSpan?displayProperty=fullName> dentro de las consultas de LINQ to SQL.  
  
|Métodos <xref:System.TimeSpan> compatibles|Operadores <xref:System.TimeSpan> compatibles|Propiedades <xref:System.TimeSpan> admitidas|  
|--------------------------------------------------------------------------------------------------------------------------------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------|  
|<xref:System.TimeSpan.Compare%2A>|<xref:System.TimeSpan.op_Equality%2A>|<xref:System.TimeSpan.Days%2A>|  
|<xref:System.TimeSpan.CompareTo%28System.TimeSpan%29>|<xref:System.TimeSpan.op_GreaterThan%2A>|<xref:System.TimeSpan.Hours%2A>|  
|<xref:System.TimeSpan.Duration%2A>|<xref:System.TimeSpan.op_GreaterThanOrEqual%2A>|<xref:System.TimeSpan.MaxValue>|  
|<xref:System.TimeSpan.Equals%28System.TimeSpan%2CSystem.TimeSpan%29>|<xref:System.TimeSpan.op_Inequality%2A>|<xref:System.TimeSpan.Milliseconds%2A>|  
|<xref:System.TimeSpan.Equals%28System.TimeSpan%29>|<xref:System.TimeSpan.op_LessThan%2A>|<xref:System.TimeSpan.Minutes%2A>|  
||<xref:System.TimeSpan.op_LessThanOrEqual%2A>|<xref:System.TimeSpan.MinValue%2A>|  
  
> [!NOTE]
>  La capacidad para asignar <xref:System.TimeSpan?displayProperty=fullName> a una columna `TIME` de SQL con LINQ to SQL requiere .NET Framework 3.5 Service Pack 1 y posteriores.  El tipo de datos `TIME` de SQL está disponible solo en Microsoft SQL Server 2008 y posteriores.  
  
### Suma y resta  
 Aunque el tipo <xref:System.TimeSpan?displayProperty=fullName> de CLR admite la suma y resta, el tipo `TIME` de SQL no.  Debido a esto, las consultas de LINQ to SQL generarán errores si intentan realizar operaciones de suma o resta cuando se asignan al tipo `TIME` de SQL.  Puede encontrar otras consideraciones para trabajar con tipos de fecha y hora de SQL en [Correspondencia de tipos SQL\-CLR](../../../../../../docs/framework/data/adonet/sql/linq/sql-clr-type-mapping.md).  
  
## Vea también  
 [Conceptos de consulta](../../../../../../docs/framework/data/adonet/sql/linq/query-concepts.md)   
 [Crear el modelo de objetos](../../../../../../docs/framework/data/adonet/sql/linq/creating-the-object-model.md)   
 [Correspondencia de tipos SQL\-CLR](../../../../../../docs/framework/data/adonet/sql/linq/sql-clr-type-mapping.md)   
 [Funciones y tipos de datos](../../../../../../docs/framework/data/adonet/sql/linq/data-types-and-functions.md)