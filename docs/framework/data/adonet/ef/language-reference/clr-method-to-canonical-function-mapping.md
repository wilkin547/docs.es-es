---
title: "Asignar m&#233;todo CLR a funci&#243;n can&#243;nica | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
ms.assetid: e3363261-2cb8-4b54-9555-2870be99b929
caps.latest.revision: 2
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 2
---
# Asignar m&#233;todo CLR a funci&#243;n can&#243;nica
Entity Framework proporciona un conjunto de funciones canónicas que implementan funcionalidad que es común en muchos sistemas de base de datos, como la manipulación de cadenas y las funciones matemáticas.  Esto permite a los programadores dirigir sus conocimientos a un amplio intervalo de sistemas de base de datos.  Cuando se invocan desde una tecnología de creación de consultas, como LINQ to Entities, estas funciones canónicas se convierten en la correspondiente función de almacenamiento correcta para ser utilizada por el proveedor.  Esto permite que las llamadas a funciones se expresen de forma común en los orígenes de datos, proporcionando una experiencia de consultas coherente en los citados orígenes de datos.  Los operadores bit a bit AND, OR, NOT y XOR también se asignan a funciones canónicas cuando el operando es un tipo numérico. En el caso de operandos booleanos, los operadores bit a bit AND, OR, NOT y XOR calculan las operaciones lógicas AND, OR, NOT y XOR de sus operandos.  Para obtener más información, consulta [Funciones canónicas](../../../../../../docs/framework/data/adonet/ef/language-reference/canonical-functions.md).  
  
 En los escenarios LINQ, las consultas en Entity Framework implican la asignación de ciertos métodos de CLR a métodos en el origen de datos subyacente a través de funciones canónicas.  Las llamadas a métodos en una consulta en LINQ to Entities no asignadas explícitamente a una función canónica harán que se lance una excepción <xref:System.NotSupportedException> en tiempo de ejecución.  
  
## Asignación del método System.String \(estático\)  
  
|Método System.String \(estático\)|Función canónica|  
|---------------------------------------|----------------------|  
|System.String Concat\(String `str0`, String `str1`\)|Concat\(`str0`, `str1`\)|  
|System.String Concat\(String `str0`, String `str1`, String `str2`\)|Concat\(Concat\(`str0`, `str1`\), `str2`\)|  
|System.String Concat\(String `str0`, String `str1`, String `str2`, String `str03`\)|Concat\(Concat\(Concat\(`str0`, `str1`\), `str2`\), `str3`\)|  
|Boolean Equals\(String `a`, String `b`\)|\= \(operador\)|  
|Boolean IsNullOrEmpty\(String `value`\)|\(IsNull\(`value`\)\) OR Length\(`value`\) \= 0|  
|Boolean op\_Equality\(String `a`, String `b`\)|\= \(operador\)|  
|Boolean op\_Inequality\(String `a` , String `b`\)|\!\= \(operador\)|  
|Microsoft.VisualBasic.Strings.Trim\(String `str`\)|Trim\(`str`\)|  
|Microsoft.VisualBasic.Strings.LTrim\(String `str`\)|Ltrim\(`str`\)|  
|Microsoft.VisualBasic.Strings.RTrim\(String `str`\)|Rtrim\(`str`\)|  
|Microsoft.VisualBasic.Strings.Len\(String `expression`\)|Length\(`expression`\)|  
|Microsoft.VisualBasic.Strings.Left\(String `str`, Int32 `Length`\)|Left\(`str`, `Length`\)|  
|Microsoft.VisualBasic.Strings.Mid\(String `str`, Int32 `Start`, Int32 `Length`\)|Substring\(`str`, `Start`, `Length`\)|  
|Microsoft.VisualBasic.Strings.Right\(String `str`, Int32 `Length`\)|Right\(`str`, `Length`\)|  
|Microsoft.VisualBasic.Strings.UCase\(String `Value`\)|ToUpper\(`Value`\)|  
|Microsoft.VisualBasic.Strings.LCase\(String Value\)|ToLower\(`Value`\)|  
  
## Asignación del método System.String \(instancia\)  
  
|Método System.String \(instancia\)|Función canónica|Notas|  
|----------------------------------------|----------------------|-----------|  
|Boolean Contains\(String `value`\)|`this` LIKE '%`value`%'|Si `value` no es una constante, asigna a IndexOf\(`this`, `value`\) \> 0.|  
|Boolean EndsWith\(String `value`\)|`this` LIKE `'`%`value`'|Si `value` no es una constante, entonces asigna a Right\(`this`, length\(`value`\)\) \= `value`.|  
|Boolean StartsWith\(String `value`\)|`this` LIKE '`value`%'|Si `value` no es una constante, entonces asigna a IndexOf\(`this`, `value`\) \= 1.|  
|Longitud|Length\(`this`\)||  
|Int32 IndexOf\(String `value`\)|IndexOf\(`this`, `value`\) \- 1||  
|System.String Insert\(Int32 `startIndex`, String `value`\)|Concat\(Concat\(Substring\(`this`, 1, `startIndex`\), `value`\), Substring\(`this`, `startIndex`\+1, Length\(`this`\) \- `startIndex`\)\)||  
|System.String Remove\(Int32 `startIndex`\)|Substring\(`this`, 1, `startIndex`\)||  
|System.String Remove\(Int32 `startIndex`, Int32 `count`\)|Concat\(Substring\(`this`, 1, `startIndex`\) , Substring\(`this`, `startIndex` \+ `count` \+1, Length\(`this`\) \- \(`startIndex` \+ `count`\)\)\)|Remove\(`startIndex`, `count`\) solo es compatible si `count` es un número entero mayor o igual que 0.|  
|System.String Replace\(String `oldValue`, String `newValue`\)|Replace\(`this`, `oldValue`, `newValue`\)||  
|System.String Substring\(Int32 `startIndex`\)|Substring\(`this`, `startIndex` \+1, Length\(`this`\) \- `startIndex`\)||  
|System.String Substring\(Int32 `startIndex`, Int32 `length`\)|Substring\(`this`, `startIndex` \+1, `length`\)||  
|System.String ToLower\(\)|ToLower\(`this`\)||  
|System.String ToUpper\(\)|ToUpper\(`this`\)||  
|System.String Trim\(\)|Trim\(`this`\)||  
|System.String TrimEnd\(Char\[\] `trimChars`\)|RTrim\(`this`\)||  
|System.String TrimStart\(Char\[\]`trimChars`\)|LTrim\(`this`\)||  
|Boolean Equals\(String `value`\)|\= \(operador\)||  
  
## Asignación del método System.DateTime \(estático\)  
  
|Método System.DateTime \(estático\)|Función canónica|Notas|  
|-----------------------------------------|----------------------|-----------|  
|Boolean Equals\(DateTime `t1`, DateTime `t2`\)|\= \(operador\)||  
|System.DateTime.Now|CurrentDateTime\(\)||  
|System.DateTime.UtcNow|CurrentUtcDateTime\(\)||  
|Boolean op\_Equality\(DateTime `d1`, DateTime `d2`\)|\= \(operador\)||  
|Boolean op\_GreaterThan\(DateTime `t1`, DateTime `t2`\)|\> \(operador\)||  
|Boolean op\_GreaterThanOrEqual\(DateTime `t1`, DateTime `t2`\)|\>\= \(operador\)||  
|Boolean op\_Inequality\(DateTime `t1`, DateTime `t2`\)|\!\= \(operador\)||  
|Boolean op\_LessThan\(DateTime `t1`, DateTime `t2`\)|\< \(operador\)||  
|Boolean op\_LessThanOrEqual\(DateTime `t1`, DateTime `t2`\)|\<\= \(operador\)||  
|Microsoft.VisualBasic.DateAndTime.DatePart\( \_<br /><br /> ByVal `Interval` As DateInterval, \_<br /><br /> ByVal `DateValue` As DateTime, \_<br /><br /> Optional ByVal `FirstDayOfWeekValue` As FirstDayOfWeek \= VbSunday, \_<br /><br /> Optional ByVal `FirstWeekOfYearValue` As FirstWeekOfYear \= VbFirstJan1 \_<br /><br /> \) As Integer||Para obtener más información, consulte la sección Función DatePart.|  
|Microsoft.VisualBasic.DateAndTime.Now|CurrentDateTime\(\)||  
|Microsoft.VisualBasic.DateAndTime.Year\(DateTime `TimeValue`\)|Year\(\)||  
|Microsoft.VisualBasic.DateAndTime.Month\(DateTime `TimeValue`\)|Month\(\)||  
|Microsoft.VisualBasic.DateAndTime.Day\(DateTime `TimeValue`\)|Day\(\)||  
|Microsoft.VisualBasic.DateAndTime.Hour\(DateTime `TimeValue`\)|Hour\(\)||  
|Microsoft.VisualBasic.DateAndTime.Minute\(DateTime `TimeValue`\)|Minute\(\)||  
|Microsoft.VisualBasic.DateAndTime.Second\(DateTime `TimeValue`\)|Second\(\)||  
  
## Asignación del método System.DateTime \(instancia\)  
  
|Método System.DateTime \(instancia\)|Función canónica|  
|------------------------------------------|----------------------|  
|Boolean Equals\(DateTime `value`\)|\= \(operador\)|  
|Day|Day\(`this`\)|  
|Hour|Hour\(`this`\)|  
|Millisecond|Millisecond\(`this`\)|  
|Minute|Minute\(`this`\)|  
|Mes|Month\(`this`\)|  
|Second|Second\(`this`\)|  
|Year|Year\(`this`\)|  
  
## Asignación del método System.DateTimeOffset \(instancia\)  
 La asignación mostrada para los métodos `get` sobre las propiedades enumeradas.  
  
|Método System.DateTimeOffset \(instancia\)|Función canónica|Notas|  
|------------------------------------------------|----------------------|-----------|  
|Day|Day\(`this`\)|No se admite en SQL Server 2005.|  
|Hour|Hour\(`this`\)|No se admite en SQL Server 2005.|  
|Millisecond|Millisecond\(`this`\)|No se admite en SQL Server 2005.|  
|Minute|Minute\(`this`\)|No se admite en SQL Server 2005.|  
|Mes|Month\(`this`\)|No se admite en SQL Server 2005.|  
|Second|Second\(`this`\)|No se admite en SQL Server 2005.|  
|Year|Year\(`this`\)|No se admite en SQL Server 2005.|  
  
> [!NOTE]
>  El método <xref:System.DateTimeOffset.Equals%2A> devuelve `true` si los objetos <xref:System.DateTimeOffset> comparados son iguales; de lo contrario, devuelve `false`.  El método <xref:System.DateTimeOffset.CompareTo%2A> devuelve 0, 1 o \-1 dependiendo de si el objeto <xref:System.DateTimeOffset> comparado es igual, mayor que, o menor que, respectivamente.  
  
## Asignación del método System.DateTimeOffset \(estático\)  
 La asignación mostrada para los métodos `get` sobre las propiedades enumeradas.  
  
|Método System.DateTimeOffset \(estático\)|Función canónica|Notas|  
|-----------------------------------------------|----------------------|-----------|  
|System.DateTimeOffset.Now\(\)|CurrentDateTimeOffset\(\)|No se admite en SQL Server 2005.|  
  
## Asignación del método System.TimeSpan \(instancia\)  
 La asignación mostrada para los métodos `get` sobre las propiedades enumeradas.  
  
|Método System.TimeSpan \(instancia\)|Función canónica|Notas|  
|------------------------------------------|----------------------|-----------|  
|Horas|Hour\(`this`\)|No se admite en SQL Server 2005.|  
|Milliseconds|Millisecond\(`this`\)|No se admite en SQL Server 2005.|  
|Minutos|Minute\(`this`\)|No se admite en SQL Server 2005.|  
|Seconds|Second\(`this`\)|No se admite en SQL Server 2005.|  
  
> [!NOTE]
>  El método <xref:System.TimeSpan.Equals%2A> devuelve `true` si los objetos <xref:System.TimeSpan> comparados son iguales; de lo contrario, devuelve `false`.  El método <xref:System.TimeSpan.CompareTo%2A> devuelve 0, 1 o \-1 dependiendo de si el objeto <xref:System.TimeSpan> comparado es igual, mayor que, o menor que, respectivamente.  
  
### Función DatePart  
 La función `DatePart` está asignada a una función canónica de entre un grupo, según el valor de `Interval`.  En la tabla siguiente, se muestra la asignación de la función canónica para los valores compatibles de `Interval`:  
  
|Valor del intervalo|Función canónica|  
|-------------------------|----------------------|  
|DateInterval.Year|Year\(\)|  
|DateInterval.Month|Month\(\)|  
|DateInterval.Day|Day\(\)|  
|DateInterval.Hour|Hour\(\)|  
|DateInterval.Minute|Minute\(\)|  
|DateInterval.Second|Second\(\)|  
  
## Asignación de funciones matemáticas  
  
|Método CLR|Función canónica|  
|----------------|----------------------|  
|System.Decimal.Ceiling\(Decimal `d`\)|Ceiling\(`d`\)|  
|System.Decimal.Floor\(Decimal `d`\)|Floor\(`d`\)|  
|System.Decimal.Round\(Decimal `d`\)|Round\(`d`\)|  
|System.Math.Ceiling\(Decimal `d`\)|Ceiling\(`d`\)|  
|System.Math.Floor\(Decimal `d`\)|Floor\(`d`\)|  
|System.Math.Round\(Decimal `d`\)|Round\(`d`\)|  
|System.Math.Ceiling\(Double `a`\)|Ceiling\(`a`\)|  
|System.Math.Floor\(Double `a`\)|Floor\(`a`\)|  
|System.Math.Round\(Double `a`\)|Round\(`a`\)|  
|System.Math.Round\(valor Double, dígitos Int16\)|Round\(valor, dígitos\)|  
|System.Math.Round\(valor Double, dígitos Int32\)|Round\(valor, dígitos\)|  
|System.Math.Round\(valor decimal, dígitos Int16\)|Round\(valor, dígitos\)|  
|System.Math.Round\(valor decimal, dígitos Int32\)|Round\(valor, dígitos\)|  
|System.Math.Abs\(valor Int16\)|Abs\(valor\)|  
|System.Math.Abs\(valor Int32\)|Abs\(valor\)|  
|System.Math.Abs\(valor Int64\)|Abs\(valor\)|  
|System.Math.Abs\(valor Byte\)|Abs\(valor\)|  
|System.Math.Abs\(valor Single\)|Abs\(valor\)|  
|System.Math.Abs\(valor Double\)|Abs\(valor\)|  
|System.Math.Abs\(valor decimal\)|Abs\(valor\)|  
|System.Math.Truncate\(valor Double, dígitos Int16\)|Truncate\(valor, dígitos\)|  
|System.Math.Truncate\(valor Double, dígitos Int32\)|Truncate\(valor, dígitos\)|  
|System.Math.Truncate\(valor Decimal, dígitos Int16\)|Truncate\(valor, dígitos\)|  
|System.Math.Truncate\(valor Decimal, dígitos Int32\)|Truncate\(valor, dígitos\)|  
|System.Math.Power\(valor Int32, exponente Int64\)|Power\(valor, exponente\)|  
|System.Math.Power\(valor Int32, exponente Double\)|Power\(valor, exponente\)|  
|System.Math.Power\(valor Int32, exponente Decimal\)|Power\(valor, exponente\)|  
|System.Math.Power\(valor Int64, exponente Int64\)|Power\(valor, exponente\)|  
|System.Math.Power\(valor Int64, exponente Double\)|Power\(valor, exponente\)|  
|System.Math.Power\(valor Int64, exponente Decimal\)|Power\(valor, exponente\)|  
|System.Math.Power\(valor Double, exponente Int64\)|Power\(valor, exponente\)|  
|System.Math.Power\(valor Double, exponente Double\)|Power\(valor, exponente\)|  
|System.Math.Power\(valor Double, exponente Decimal\)|Power\(valor, exponente\)|  
|System.Math.Power\(valor Decimal, exponente Int64\)|Power\(valor, exponente\)|  
|System.Math.Power\(valor Decimal, exponente Double\)|Power\(valor, exponente\)|  
|System.Math.Power\(valor Decimal, exponente Decimal\)|Power\(valor, exponente\)|  
  
## Asignación de operadores bit a bit  
  
|Operador bit a bit|Función canónica para operandos no booleanos|Función canónica para operandos booleanos|  
|------------------------|--------------------------------------------------|-----------------------------------------------|  
|Operador AND bit a bit|BitWiseAnd|op1 AND op2|  
|Operador OR bit a bit|BitWiseOr|op1 OR op2|  
|Operador NOT bit a bit|BitWiseNot|NOT\(op\)|  
|Operador XOR bit a bit|BitWiseXor|\(\(op1 AND NOT\(op2\)\) OR \(NOT\(op1\) AND op2\)\)|  
  
## Otra asignación  
  
|Método|Función canónica|  
|------------|----------------------|  
|Guid.NewGuid \(\)|NewGuid\(\)|  
  
## Vea también  
 [LINQ to Entities](../../../../../../docs/framework/data/adonet/ef/language-reference/linq-to-entities.md)