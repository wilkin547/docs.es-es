---
title: "Restricciones de esquema | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 73d2980e-e73c-4987-913a-8ddc93d09144
caps.latest.revision: 3
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 3
---
# Restricciones de esquema
El segundo parámetro opcional del método **GetSchema** son las restricciones que se utilizan para limitar la cantidad de información de esquema devuelta. Este parámetro se pasa al método **GetSchema** como una matriz de cadenas.  La posición en la matriz determina los valores que puede pasar, y es equivalente al número de restricciones.  
  
 Por ejemplo, en la tabla siguiente se describen las restricciones que admite la colección de esquemas "Tables" utilizando el proveedor de datos .NET Framework para SQL Server.  Las restricciones adicionales para las colecciones de esquemas de SQL Server se muestran al final de este tema.  
  
|Nombre de la restricción|Nombre de parámetro|Valor predeterminado de la restricción|Número de restricciones|  
|------------------------------|-------------------------|--------------------------------------------|-----------------------------|  
|Catálogo|@Catalog|TABLE\_CATALOG|1|  
|Propietario|@Owner|TABLE\_SCHEMA|2|  
|Tabla|@Name|TABLE\_NAME|3|  
|TableType|@TableType|TABLE\_TYPE|4|  
  
## Especificación de los valores de restricción  
 Para utilizar una de las restricciones de la colección de esquemas "Tables", basta con crear una matriz de cadenas con cuatro elementos y, después, colocar un valor en el elemento que coincida con el número de restricción.  Por ejemplo, para restringir las tablas devueltas por el método **GetSchema** a solo las del esquema "Sales", establezca el segundo elemento de la matriz en "Sales" antes de pasarlo al método **GetSchema**.  
  
> [!NOTE]
>  Las colecciones con restricciones para `SqlClient` y `OracleClient` tienen una columna `ParameterName` adicional.  La columna de valor predeterminado de restricción sigue ahí para la compatibilidad con versiones anteriores, pero actualmente se omite.  Para reducir el riesgo de un ataque de inyección de SQL al especificar valores de restricción, es necesario utilizar consultas parametrizadas en lugar de sustitución de cadenas.  
  
> [!NOTE]
>  El número de elementos de la matriz debe ser menor o igual que el número de restricciones admitidas en la colección de esquemas especificada o se iniciará una <xref:System.ArgumentException>.  Puede haber un número de restricciones inferior al máximo.  Se supone que las restricciones que faltan serán nulas \(sin restricciones\).  
  
 Puede consultar un proveedor administrado de .NET Framework para determinar la lista de restricciones admitidas mediante la llamada al método **GetSchema** con el nombre de la colección de esquemas con restricciones, que es "Restrictions".  Esto devolverá una <xref:System.Data.DataTable> con una lista de los nombres de colecciones, los nombres de restricciones, los valores predeterminados de restricción y los números de restricciones.  
  
### Ejemplo  
 En los ejemplos siguientes se muestra cómo utilizar el método <xref:System.Data.SqlClient.SqlConnection.GetSchema%2A> del proveedor de datos .NET Framework para la clase <xref:System.Data.SqlClient.SqlConnection> de SQL Server para recuperar información de esquema de todas las tablas contenidas en la base de datos de ejemplo **AdventureWorks**, y para restringir la información devuelta a solo las tablas del esquema "Sales":  
  
 \[Visual Basic\]  
  
```  
Imports System.Data.SqlClient  
  
Module Module1  
Sub Main()  
  Dim connectionString As String = _  
    "Data Source=(local);Database=AdventureWorks;" & _  
       "Integrated Security=true;";  
  
  Dim restrictions(3) As String  
  Using connection As New SqlConnection(connectionString)  
    connection.Open()  
  
    'Specify the restrictions.  
    restrictions(1) = "Sales"  
    Dim table As DataTable = connection.GetSchema("Tables", _  
       restrictions)  
  
    ' Display the contents of the table.  
      For Each row As DataRow In table.Rows  
         For Each col As DataColumn In table.Columns  
            Console.WriteLine("{0} = {1}", col.ColumnName, row(col))  
         Next  
         Console.WriteLine("============================")  
      Next  
    Console.WriteLine("Press any key to continue.")  
    Console.ReadKey()  
  End Using  
End Sub  
End Module  
```  
  
 \[C\#\]  
  
```  
using System;  
using System.Data;  
using System.Data.SqlClient;  
  
class Program  
{  
  static void Main()  
  {  
    string connectionString =   
       "Data Source=(local);Database=AdventureWorks;" +  
       "Integrated Security=true;";  
    using (SqlConnection connection =  
       new SqlConnection(connectionString))  
    {  
        connection.Open();  
  
        // Specify the restrictions.  
        string[] restrictions = new string[4];  
        restrictions[1] = "Sales";  
        System.Data.DataTable table = connection.GetSchema(  
          "Tables", restrictions);  
  
        // Display the contents of the table.  
        foreach (System.Data.DataRow row in table.Rows)  
        {  
            foreach (System.Data.DataColumn col in table.Columns)  
            {  
                Console.WriteLine("{0} = {1}",   
                  col.ColumnName, row[col]);  
            }  
            Console.WriteLine("============================");  
        }  
        Console.WriteLine("Press any key to continue.");  
        Console.ReadKey();  
    }  
  }  
  
  private static string GetConnectionString()  
  {  
     // To avoid storing the connection string in your code,  
     // you can retrieve it from a configuration file.  
     return "Data Source=(local);Database=AdventureWorks;" +  
        "Integrated Security=true;";  
  }  
  
  private static void DisplayData(System.Data.DataTable table)  
  {  
     foreach (System.Data.DataRow row in table.Rows)  
     {  
        foreach (System.Data.DataColumn col in table.Columns)  
        {  
           Console.WriteLine("{0} = {1}", col.ColumnName, row[col]);  
        }  
     Console.WriteLine("============================");  
     }  
  }  
}  
```  
  
## Restricciones de esquema de SQL Server  
 En la tabla siguiente se muestran las restricciones de las colecciones de esquemas de SQL Server.  
  
### Usuarios  
  
|Nombre de la restricción|Nombre de parámetro|Valor predeterminado de la restricción|Número de restricciones|  
|------------------------------|-------------------------|--------------------------------------------|-----------------------------|  
|User\_Name|@Name|name|1|  
  
### Bases de datos  
  
|Nombre de la restricción|Nombre de parámetro|Valor predeterminado de la restricción|Número de restricciones|  
|------------------------------|-------------------------|--------------------------------------------|-----------------------------|  
|Name|@Name|Name|1|  
  
### Tablas  
  
|Nombre de la restricción|Nombre de parámetro|Valor predeterminado de la restricción|Número de restricciones|  
|------------------------------|-------------------------|--------------------------------------------|-----------------------------|  
|Catálogo|@Catalog|TABLE\_CATALOG|1|  
|Propietario|@Owner|TABLE\_SCHEMA|2|  
|Tabla|@Name|TABLE\_NAME|3|  
|TableType|@TableType|TABLE\_TYPE|4|  
  
### Columnas  
  
|Nombre de la restricción|Nombre de parámetro|Valor predeterminado de la restricción|Número de restricciones|  
|------------------------------|-------------------------|--------------------------------------------|-----------------------------|  
|Catálogo|@Catalog|TABLE\_CATALOG|1|  
|Propietario|@Owner|TABLE\_SCHEMA|2|  
|Tabla|@Table|TABLE\_NAME|3|  
|Columna|@Column|COLUMN\_NAME|4|  
  
### StructuredTypeMembers  
  
|Nombre de la restricción|Nombre de parámetro|Valor predeterminado de la restricción|Número de restricciones|  
|------------------------------|-------------------------|--------------------------------------------|-----------------------------|  
|Catálogo|@Catalog|TABLE\_CATALOG|1|  
|Propietario|@Owner|TABLE\_SCHEMA|2|  
|Tabla|@Table|TABLE\_NAME|3|  
|Columna|@Column|COLUMN\_NAME|4|  
  
### Vistas  
  
|Nombre de la restricción|Nombre de parámetro|Valor predeterminado de la restricción|Número de restricciones|  
|------------------------------|-------------------------|--------------------------------------------|-----------------------------|  
|Catálogo|@Catalog|TABLE\_CATALOG|1|  
|Propietario|@Owner|TABLE\_SCHEMA|2|  
|Tabla|@Table|TABLE\_NAME|3|  
  
### ViewColumns  
  
|Nombre de la restricción|Nombre de parámetro|Valor predeterminado de la restricción|Número de restricciones|  
|------------------------------|-------------------------|--------------------------------------------|-----------------------------|  
|Catálogo|@Catalog|VIEW\_CATALOG|1|  
|Propietario|@Owner|VIEW\_SCHEMA|2|  
|Tabla|@Table|VIEW\_NAME|3|  
|Columna|@Column|COLUMN\_NAME|4|  
  
### ProcedureParameters  
  
|Nombre de la restricción|Nombre de parámetro|Valor predeterminado de la restricción|Número de restricciones|  
|------------------------------|-------------------------|--------------------------------------------|-----------------------------|  
|Catálogo|@Catalog|SPECIFIC\_CATALOG|1|  
|Propietario|@Owner|SPECIFIC\_SCHEMA|2|  
|Name|@Name|SPECIFIC\_NAME|3|  
|Parámetro|@Parameter|PARAMETER\_NAME|4|  
  
### Procedimientos  
  
|Nombre de la restricción|Nombre de parámetro|Valor predeterminado de la restricción|Número de restricciones|  
|------------------------------|-------------------------|--------------------------------------------|-----------------------------|  
|Catálogo|@Catalog|SPECIFIC\_CATALOG|1|  
|Propietario|@Owner|SPECIFIC\_SCHEMA|2|  
|Name|@Name|SPECIFIC\_NAME|3|  
|Tipo|@Type|ROUTINE\_TYPE|4|  
  
### IndexColumns  
  
|Nombre de la restricción|Nombre de parámetro|Valor predeterminado de la restricción|Número de restricciones|  
|------------------------------|-------------------------|--------------------------------------------|-----------------------------|  
|Catálogo|@Catalog|db\_name\(\)|1|  
|Propietario|@Owner|user\_name\(\)|2|  
|Tabla|@Table|o.  name|3|  
|ConstraintName|@ConstraintName|x.  name|4|  
|Columna|@Column|c.  name|5|  
  
### Índices  
  
|Nombre de la restricción|Nombre de parámetro|Valor predeterminado de la restricción|Número de restricciones|  
|------------------------------|-------------------------|--------------------------------------------|-----------------------------|  
|Catálogo|@Catalog|db\_name\(\)|1|  
|Propietario|@Owner|user\_name\(\)|2|  
|Tabla|@Table|o.  name|3|  
  
### UserDefinedTypes  
  
|Nombre de la restricción|Nombre de parámetro|Valor predeterminado de la restricción|Número de restricciones|  
|------------------------------|-------------------------|--------------------------------------------|-----------------------------|  
|assembly\_name|@AssemblyName|ensamblados.  name|1|  
|udt\_name|@UDTName|types.assembly\_class|2|  
  
### ForeignKeys  
  
|Nombre de la restricción|Nombre de parámetro|Valor predeterminado de la restricción|Número de restricciones|  
|------------------------------|-------------------------|--------------------------------------------|-----------------------------|  
|Catálogo|@Catalog|CONSTRAINT\_CATALOG|1|  
|Propietario|@Owner|CONSTRAINT\_SCHEMA|2|  
|Tabla|@Table|TABLE\_NAME|3|  
|Name|@Name|CONSTRAINT\_NAME|4|  
  
## Restricciones de esquema de SQL Server 2008  
 En la tabla siguiente se muestran las restricciones de las colecciones de esquemas de SQL Server 2008.  Estas restricciones son válidas a partir de la versión 3.5 SP1 de .NET Framework y SQL Server 2008.  No se admiten en versiones anteriores de .NET Framework y SQL Server.  
  
### ColumnSetColumns  
  
|Nombre de la restricción|Nombre de parámetro|Valor predeterminado de la restricción|Número de restricciones|  
|------------------------------|-------------------------|--------------------------------------------|-----------------------------|  
|Catálogo|@Catalog|TABLE\_CATALOG|1|  
|Propietario|@Owner|TABLE\_SCHEMA|2|  
|Tabla|@Table|TABLE\_NAME|3|  
  
### AllColumns  
  
|Nombre de la restricción|Nombre de parámetro|Valor predeterminado de la restricción|Número de restricciones|  
|------------------------------|-------------------------|--------------------------------------------|-----------------------------|  
|Catálogo|@Catalog|TABLE\_CATALOG|1|  
|Propietario|@Owner|TABLE\_SCHEMA|2|  
|Tabla|@Table|TABLE\_NAME|3|  
|Columna|@Column|COLUMN\_NAME|4|  
  
## Vea también  
 [Proveedores administrados de ADO.NET y centro de desarrolladores de conjuntos de datos](http://go.microsoft.com/fwlink/?LinkId=217917)