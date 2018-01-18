---
title: Objetos BFILE de Oracle
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 341bbf84-4734-4d44-8723-ccedee954e21
caps.latest.revision: "3"
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: 7e7b7d438abb5a7e14a55f30447d291d3c8ee286
ms.sourcegitcommit: ed26cfef4e18f6d93ab822d8c29f902cff3519d1
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/17/2018
---
# <a name="oracle-bfiles"></a>Objetos BFILE de Oracle
El proveedor de datos .NET Framework para Oracle incluye la clase <xref:System.Data.OracleClient.OracleBFile>, que se utiliza para trabajar con el tipo de datos <xref:System.Data.OracleClient.OracleType.BFile> de Oracle.  
  
 Oracle **BFILE** es de tipo de datos de Oracle **LOB** tipo de datos que contiene una referencia a datos binarios con un tamaño máximo de 4 gigabytes. Oracle **BFILE** difiere de otro Oracle **LOB** tipos de datos en que sus datos se almacenan en un archivo físico en el sistema operativo en lugar de en el servidor. Tenga en cuenta que la **BFILE** tipo de datos proporciona acceso de solo lectura a los datos.  
  
 Otras características de un **BFILE** tipo de datos que distinguirla de una **LOB** tipo de datos son que:  
  
-   contiene datos no estructurados.  
  
-   admite el troceo en el servidor.  
  
-   utiliza semántica de copia de referencia. Por ejemplo, si realiza una operación de copia en un **BFILE**, solo el **BFILE** se copia el localizador (que es una referencia al archivo). Los datos del archivo no se copian.  
  
 El **BFILE** tipo de datos se debe utilizar para hacer referencia a los LOB que son de gran tamaño y por lo tanto, no resultan prácticos para almacenarse en la base de datos. Más sobrecarga de cliente y servidor, la comunicación está implicada cuando se usa un **BFILE** tipo de datos en comparación con el **LOB** tipo de datos. Resulta más eficaz para tener acceso a un **BFILE** si solo necesita obtener una pequeña cantidad de datos. En cambio, si necesita obtener el objeto entero, es más eficiente tener acceso a los LOB residentes en la base de datos.  
  
 Cada usuario que no sea NULL **OracleBFile** objeto está asociado a dos entidades que definen la ubicación del archivo físico subyacente:  
  
1.  Un objeto DIRECTORY de Oracle, que es un alias de base de datos de un directorio del sistema de archivos, y  
  
2.  el nombre de archivo del archivo físico subyacente, que se encuentra en el directorio asociado con el objeto DIRECTORY.  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo de C# siguiente se muestra cómo puede crear un **BFILE** de Oracle de la tabla y, a continuación, recuperarlo en forma de un **OracleBFile** objeto. En el ejemplo se muestra cómo utilizar el <xref:System.Data.OracleClient.OracleDataReader> objeto y el **OracleBFile** **Seek** y **lectura** métodos. Tenga en cuenta que para utilizar este ejemplo, primero debe crear un directorio denominado "c:\\\bfiles" y un archivo llamado "MyFile.jpg" en el servidor Oracle.  
  
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
  
## <a name="see-also"></a>Vea también  
 [Oracle y ADO.NET](../../../../docs/framework/data/adonet/oracle-and-adonet.md)  
 [Proveedores administrados de ADO.NET y Centro para desarrolladores de DataSet](http://go.microsoft.com/fwlink/?LinkId=217917)
