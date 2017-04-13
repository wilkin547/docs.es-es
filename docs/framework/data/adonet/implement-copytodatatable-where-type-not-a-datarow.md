---
title: "C&#243;mo implementar CopyToDataTable&lt;T&gt; donde el tipo gen&#233;rico T no es un objeto DataRow | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: b27b52cf-6172-485f-a75c-70ff9c5a2bd4
caps.latest.revision: 2
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 2
---
# C&#243;mo implementar CopyToDataTable&lt;T&gt; donde el tipo gen&#233;rico T no es un objeto DataRow
El objeto <xref:System.Data.DataTable> se suele utilizar para el enlace de datos.  El método <xref:System.Data.DataTableExtensions.CopyToDataTable%2A> toma los resultados de una consulta y copia los datos en un objeto <xref:System.Data.DataTable> que puede utilizarse después para el enlace de datos.  Sin embargo, los métodos <xref:System.Data.DataTableExtensions.CopyToDataTable%2A> solo funcionan en un origen <xref:System.Collections.Generic.IEnumerable%601> en el que el parámetro genérico `T` es de tipo <xref:System.Data.DataRow>.  Aunque esto es útil, no permite la creación de tablas a partir de una secuencia de tipos escalares, a partir de consultas que proyectan tipos anónimos, o a partir de consultas que realizan combinaciones de tablas.  
  
 En este tema se describe cómo se implementan dos métodos de extensión `CopyToDataTable<T>` personalizados que aceptan un parámetro genérico `T` de un tipo distinto de <xref:System.Data.DataRow>.  La lógica para crear un objeto <xref:System.Data.DataTable> desde un origen <xref:System.Collections.Generic.IEnumerable%601> está contenida en la clase `ObjectShredder<T>`, que se incluye después en dos métodos de extensión `CopyToDataTable<T>` sobrecargados.  El método `Shred` de la clase `ObjectShredder<T>` devuelve el objeto <xref:System.Data.DataTable> relleno y acepta tres parámetros de entrada: un origen <xref:System.Collections.Generic.IEnumerable%601>, un objeto <xref:System.Data.DataTable> y una enumeración <xref:System.Data.LoadOption>.  El esquema inicial del objeto <xref:System.Data.DataTable> devuelto está basado en el esquema del tipo `T`.  Si se proporciona una tabla existente como entrada, el esquema debe ser coherente con el esquema del tipo `T`.  Cada propiedad y campo públicos del tipo `T` se convierten a un objeto <xref:System.Data.DataColumn> en la tabla devuelta.  Si la secuencia de origen contiene un tipo derivado de `T`, el esquema de la tabla devuelta se expande para las propiedades o campos públicos adicionales.  
  
 Para obtener ejemplos sobre el uso de los métodos `CopyToDataTable<T>` personalizados, vea [Crear DataTable desde una consulta](../../../../docs/framework/data/adonet/creating-a-datatable-from-a-query-linq-to-dataset.md).  
  
### Para implementar los métodos CopyToDataTable\<T\> personalizados en la aplicación  
  
1.  Implemente la clase `ObjectShredder<T>` para crear un objeto <xref:System.Data.DataTable> desde un origen <xref:System.Collections.Generic.IEnumerable%601>:  
  
     [!code-csharp[DP Custom CopyToDataTable Examples#ObjectShredderClass](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP Custom CopyToDataTable Examples/CS/Program.cs#objectshredderclass)]
     [!code-vb[DP Custom CopyToDataTable Examples#ObjectShredderClass](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP Custom CopyToDataTable Examples/VB/Module1.vb#objectshredderclass)]  
  
2.  Implemente los métodos de extensión `CopyToDataTable<T>` personalizados en una clase:  
  
     [!code-csharp[DP Custom CopyToDataTable Examples#CustomCopyToDataTableMethods](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP Custom CopyToDataTable Examples/CS/Program.cs#customcopytodatatablemethods)]
     [!code-vb[DP Custom CopyToDataTable Examples#CustomCopyToDataTableMethods](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP Custom CopyToDataTable Examples/VB/Module1.vb#customcopytodatatablemethods)]  
  
3.  Agregue la clase `ObjectShredder<T>` y los métodos de extensión `CopyToDataTable<T>` a la aplicación.  
  
    ```vb  
    Module Module1  
        Sub Main()  
        ' Your application code using CopyToDataTable<T>.  
        End Sub  
    End Module  
  
    Public Module CustomLINQtoDataSetMethods  
    …  
    End Module  
  
    Public Class ObjectShredder(Of T)  
    …  
    End Class  
    ```  
  
4.  ```c#  
    class Program  
    {  
            static void Main(string[] args)  
            {  
               // Your application code using CopyToDataTable<T>.  
            }  
    }  
    public static class CustomLINQtoDataSetMethods  
    {  
    …  
    }  
    public class ObjectShredder<T>  
    {  
    …  
    }  
    ```  
  
## Vea también  
 [Crear DataTable desde una consulta](../../../../docs/framework/data/adonet/creating-a-datatable-from-a-query-linq-to-dataset.md)   
 [Guía de programación](../../../../docs/framework/data/adonet/programming-guide-linq-to-dataset.md)