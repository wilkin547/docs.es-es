---
title: Convertir tipos de datos (Visual Basic) | Documentos de Microsoft
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
ms.assetid: 9b0cf1ab-de48-4c6e-9f00-05b40fade46e
caps.latest.revision: 3
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 53d8ad292891a567e13ec8a5396bcc114b379351
ms.lasthandoff: 03/13/2017

---
# <a name="converting-data-types-visual-basic"></a>Convertir tipos de datos (Visual Basic)
Métodos de conversión cambian el tipo de objetos de entrada.  
  
 Operaciones de conversión en las consultas LINQ son útiles en una variedad de aplicaciones. Estos son algunos ejemplos:  
  
-   El <xref:System.Linq.Enumerable.AsEnumerable%2A?displayProperty=fullName>método se puede utilizar para ocultar la implementación personalizada de un tipo de operador de consulta estándar.</xref:System.Linq.Enumerable.AsEnumerable%2A?displayProperty=fullName>  
  
-   El <xref:System.Linq.Enumerable.OfType%2A?displayProperty=fullName>método puede utilizarse para habilitar las colecciones no parametrizadas para realizar consultas LINQ.</xref:System.Linq.Enumerable.OfType%2A?displayProperty=fullName>  
  
-   El <xref:System.Linq.Enumerable.ToArray%2A?displayProperty=fullName>, <xref:System.Linq.Enumerable.ToDictionary%2A?displayProperty=fullName>, <xref:System.Linq.Enumerable.ToList%2A?displayProperty=fullName>, y <xref:System.Linq.Enumerable.ToLookup%2A?displayProperty=fullName>métodos pueden usarse para forzar la ejecución inmediata de la consulta en lugar de aplaza hasta que se enumere la consulta.</xref:System.Linq.Enumerable.ToLookup%2A?displayProperty=fullName> </xref:System.Linq.Enumerable.ToList%2A?displayProperty=fullName> </xref:System.Linq.Enumerable.ToDictionary%2A?displayProperty=fullName> </xref:System.Linq.Enumerable.ToArray%2A?displayProperty=fullName>  
  
## <a name="methods"></a>Métodos  
 La tabla siguiente enumeran los métodos de operador de consulta estándar que realizan conversiones de tipo de datos.  
  
 Los métodos de conversión de esta tabla cuyos nombres comiencen por "As" cambian el tipo estático de la colección de origen, pero no lo enumeran. Escriba los métodos cuyos nombres empiezan por "A enumerar la colección de origen y colocar los elementos en la colección correspondiente".  
  
|Nombre del método|Descripción|Sintaxis de expresiones de consulta de Visual Basic|Más información|  
|-----------------|-----------------|------------------------------------------|----------------------|  
|AsEnumerable|Devuelve la entrada tipificada como <xref:System.Collections.Generic.IEnumerable%601>.</xref:System.Collections.Generic.IEnumerable%601>|No es aplicable.|<xref:System.Linq.Enumerable.AsEnumerable%2A?displayProperty=fullName></xref:System.Linq.Enumerable.AsEnumerable%2A?displayProperty=fullName>|  
|AsQueryable|Convierte un (genérico) <xref:System.Collections.IEnumerable>a <xref:System.Linq.IQueryable>.</xref:System.Linq.IQueryable> (genérico)</xref:System.Collections.IEnumerable>|No es aplicable.|<xref:System.Linq.Queryable.AsQueryable%2A?displayProperty=fullName></xref:System.Linq.Queryable.AsQueryable%2A?displayProperty=fullName>|  
|Conversión de tipos explícita|Convierte los elementos de una colección a un tipo especificado.|`From … As …`|<xref:System.Linq.Enumerable.Cast%2A?displayProperty=fullName></xref:System.Linq.Enumerable.Cast%2A?displayProperty=fullName><br /><br /> <xref:System.Linq.Queryable.Cast%2A?displayProperty=fullName></xref:System.Linq.Queryable.Cast%2A?displayProperty=fullName>|  
|OfType|Filtra valores en función de su capacidad para convertirse en un tipo especificado.|No es aplicable.|<xref:System.Linq.Enumerable.OfType%2A?displayProperty=fullName></xref:System.Linq.Enumerable.OfType%2A?displayProperty=fullName><br /><br /> <xref:System.Linq.Queryable.OfType%2A?displayProperty=fullName></xref:System.Linq.Queryable.OfType%2A?displayProperty=fullName>|  
|ToArray|Convierte una colección en una matriz. Este método fuerza la ejecución de la consulta.|No es aplicable.|<xref:System.Linq.Enumerable.ToArray%2A?displayProperty=fullName></xref:System.Linq.Enumerable.ToArray%2A?displayProperty=fullName>|  
|ToDictionary|Coloca los elementos en una <xref:System.Collections.Generic.Dictionary%602>según una función del selector de claves.</xref:System.Collections.Generic.Dictionary%602> Este método fuerza la ejecución de la consulta.|No es aplicable.|<xref:System.Linq.Enumerable.ToDictionary%2A?displayProperty=fullName></xref:System.Linq.Enumerable.ToDictionary%2A?displayProperty=fullName>|  
|ToList|Convierte una colección a un <xref:System.Collections.Generic.List%601>.</xref:System.Collections.Generic.List%601> Este método fuerza la ejecución de la consulta.|No es aplicable.|<xref:System.Linq.Enumerable.ToList%2A?displayProperty=fullName></xref:System.Linq.Enumerable.ToList%2A?displayProperty=fullName>|  
|ToLookup|Coloca los elementos en una <xref:System.Linq.Lookup%602>(diccionario uno a varios) según una función del selector de claves.</xref:System.Linq.Lookup%602> Este método fuerza la ejecución de la consulta.|No es aplicable.|<xref:System.Linq.Enumerable.ToLookup%2A?displayProperty=fullName></xref:System.Linq.Enumerable.ToLookup%2A?displayProperty=fullName>|  
  
## <a name="query-expression-syntax-example"></a>Ejemplo de sintaxis de expresiones de consulta  
 El siguiente ejemplo de código utiliza el `From As` cláusula para convertir un tipo en un subtipo antes de obtener acceso a un miembro que solo está disponible en el subtipo.  
  
```vb  
Class Plant  
    Public Property Name As String  
End Class  
  
Class CarnivorousPlant  
    Inherits Plant  
    Public Property TrapType As String  
End Class  
  
Sub Cast()  
  
    Dim plants() As Plant = {   
        New CarnivorousPlant With {.Name = "Venus Fly Trap", .TrapType = "Snap Trap"},   
        New CarnivorousPlant With {.Name = "Pitcher Plant", .TrapType = "Pitfall Trap"},   
        New CarnivorousPlant With {.Name = "Sundew", .TrapType = "Flypaper Trap"},   
        New CarnivorousPlant With {.Name = "Waterwheel Plant", .TrapType = "Snap Trap"}}  
  
    Dim query = From plant As CarnivorousPlant In plants   
                Where plant.TrapType = "Snap Trap"   
                Select plant  
  
    Dim sb As New System.Text.StringBuilder()  
    For Each plant In query  
        sb.AppendLine(plant.Name)  
    Next  
  
    ' Display the results.  
    MsgBox(sb.ToString())  
  
    ' This code produces the following output:  
  
    ' Venus Fly Trap  
    ' Waterwheel Plant  
  
End Sub  
```  
  
## <a name="see-also"></a>Vea también  
 <xref:System.Linq></xref:System.Linq>   
 [Información general sobre operadores de consulta estándar (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/standard-query-operators-overview.md)   
 [FROM (cláusula)](../../../../visual-basic/language-reference/queries/from-clause.md)   
 [Cómo: consultar un objeto ArrayList con LINQ (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/how-to-query-an-arraylist-with-linq.md)
