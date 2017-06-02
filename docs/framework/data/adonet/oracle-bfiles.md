---
title: "Tipos de datos BFILE de Oracle | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 341bbf84-4734-4d44-8723-ccedee954e21
caps.latest.revision: 3
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 3
---
# Tipos de datos BFILE de Oracle
El proveedor de datos .NET Framework para Oracle incluye la clase <xref:System.Data.OracleClient.OracleBFile>, que se utiliza para trabajar con el tipo de datos <xref:System.Data.OracleClient.OracleType> de Oracle.  
  
 El tipo de datos **BFILE** de Oracle es un tipo de datos **LOB** de Oracle que contiene una referencia a datos binarios con un tamaño máximo de 4 gigabytes.  El tipo de datos **BFILE** se diferencia de otros tipos de datos **LOB** de Oracle en que sus datos se almacenan en un archivo físico en el sistema operativo en lugar de en el servidor.  Tenga en cuenta que el tipo de datos **BFILE** proporciona acceso de solo lectura a los datos.  
  
 Otras características del tipo de datos **BFILE** que lo distinguen del tipo de datos **LOB** son que:  
  
-   contiene datos no estructurados.  
  
-   admite el troceo en el servidor.  
  
-   utiliza semántica de copia de referencia.  Por ejemplo, si realiza una operación de copia en un **BFILE**, solo se copia el localizador de **BFILE** \(que es una referencia al archivo\).  Los datos del archivo no se copian.  
  
 El tipo de datos **BFILE** se debe utilizar para hacer referencia a los LOB que son de gran tamaño y que, por lo tanto, no resultan prácticos para almacenarse en la base de datos.  El uso de un tipo de datos **BFILE** comparado con un tipo de datos **LOB** implica una mayor sobrecarga en el cliente, el servidor y la comunicación.  El acceso a un **BFILE** es más eficiente si solo necesita obtener una pequeña cantidad de datos.  En cambio, si necesita obtener el objeto entero, es más eficiente tener acceso a los LOB residentes en la base de datos.  
  
 Cada objeto **OracleBFile** no NULL está asociado con dos entidades que definen la ubicación del archivo físico subyacente:  
  
1.  Un objeto DIRECTORY de Oracle, que es un alias de base de datos de un directorio del sistema de archivos, y  
  
2.  el nombre de archivo del archivo físico subyacente, que se encuentra en el directorio asociado con el objeto DIRECTORY.  
  
## Ejemplo  
 En el siguiente ejemplo con C\# se muestra cómo puede crear un **BFILE** en una tabla de Oracle y, a continuación, recuperarlo en forma de un objeto **OracleBFile**.  Además, se demuestra el uso del objeto <xref:System.Data.OracleClient.OracleDataReader> y de los métodos **Seek** y**Read** de **OracleBFile**.  Tenga en cuenta que para utilizar este ejemplo, primero debe crear un directorio llamado "c:\\\\bfiles" y un archivo llamado "MyFile.jpg" en el servidor Oracle.  
  
```csharp  
using System;  
using System.IO;  
using System.Data;  
using System.Data.OracleClient;  
  
public class Sample  
{  
   public static void Main(string[] args)  
   {  
      OracleConnection connection = new OracleConnection(  
        "Data Source=Oracle8i;Integrated Security=yes");  
      connection.Open();  
  
      OracleCommand command = connection.CreateCommand();  
      command.CommandText =   
        "CREATE or REPLACE DIRECTORY MyDir as 'c:\\bfiles'";  
      command.ExecuteNonQuery();  
      command.CommandText =   
        "DROP TABLE MyBFileTable";  
      try {  
        command.ExecuteNonQuery();  
      }  
      catch {  
      }  
      command.CommandText =   
        "CREATE TABLE MyBFileTable(col1 number, col2 BFILE)";  
      command.ExecuteNonQuery();  
      command.CommandText =   
        "INSERT INTO MyBFileTable values ('2', BFILENAME('MyDir', " +  
        "'MyFile.jpg'))";  
      command.ExecuteNonQuery();  
      command.CommandText = "SELECT * FROM MyBFileTable";  
  
        byte[] buffer = new byte[100];  
  
      OracleDataReader reader = command.ExecuteReader();  
      using (reader) {  
          if (reader.Read()) {  
                OracleBFile bFile = reader.GetOracleBFile(1);  
                using (bFile) {  
                  bFile.Seek(0, SeekOrigin.Begin);  
                  bFile.Read(buffer, 0, 100);  
              }  
          }  
      }  
  
      connection.Close();  
   }  
  
}  
```  
  
## Vea también  
 [Oracle y ADO.NET](../../../../docs/framework/data/adonet/oracle-and-adonet.md)   
 [Proveedores administrados de ADO.NET y centro de desarrolladores de conjuntos de datos](http://go.microsoft.com/fwlink/?LinkId=217917)