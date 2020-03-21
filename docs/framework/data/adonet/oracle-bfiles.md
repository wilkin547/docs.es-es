---
title: Objetos BFILE de Oracle
ms.date: 03/30/2017
ms.assetid: 341bbf84-4734-4d44-8723-ccedee954e21
ms.openlocfilehash: 40060a7ea8576e08140d972072d086606d640366
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79149445"
---
# <a name="oracle-bfiles"></a>Objetos BFILE de Oracle
El proveedor de datos .NET Framework para Oracle incluye la clase <xref:System.Data.OracleClient.OracleBFile>, que se utiliza para trabajar con el tipo de datos <xref:System.Data.OracleClient.OracleType.BFile> de Oracle.  
  
 El tipo de datos **BFILE** de Oracle es un tipo de datos **LOB** de Oracle que contiene una referencia a datos binarios con un tamaño máximo de 4 gigabytes. Un **BFILE** de Oracle difiere de otros tipos de datos **LOB** de Oracle en que sus datos se almacenan en un archivo físico en el sistema operativo en lugar de en el servidor. Tenga en cuenta que el tipo de datos **BFILE** proporciona acceso de solo lectura a los datos.  
  
 Otras características de un tipo de datos **BFILE** que lo distinguen de un tipo de datos **LOB** son que:  
  
- contiene datos no estructurados.  
  
- admite el troceo en el servidor.  
  
- utiliza semántica de copia de referencia. Por ejemplo, si realiza una operación de copia en un **archivo BFILE**, solo se copia el localizador **BFILE** (que es una referencia al archivo). Los datos del archivo no se copian.  
  
 El tipo de datos **BFILE** se debe usar para hacer referencia a LOB que son de gran tamaño y, por lo tanto, no es práctico almacenar en la base de datos. Más sobrecarga de cliente, servidor y comunicación implica cuando se usa un tipo de datos **BFILE** en comparación con el tipo de datos **LOB.** Es más eficaz acceder a un **Archivo BFILE** si solo necesita obtener una pequeña cantidad de datos. En cambio, si necesita obtener el objeto entero, es más eficiente tener acceso a los LOB residentes en la base de datos.  
  
 Cada objeto **OracleBFile** no NULL está asociado a dos entidades que definen la ubicación del archivo físico subyacente:  
  
1. Un objeto DIRECTORY de Oracle, que es un alias de base de datos de un directorio del sistema de archivos, y  
  
2. el nombre de archivo del archivo físico subyacente, que se encuentra en el directorio asociado con el objeto DIRECTORY.  
  
## <a name="example"></a>Ejemplo  
 En el siguiente ejemplo de C- se muestra cómo crear un **archivo BFILE** en una tabla de Oracle y, a continuación, recuperarlo en forma de un **OracleBFile** objeto. En el ejemplo <xref:System.Data.OracleClient.OracleDataReader> se muestra cómo utilizar el objeto y los métodos **OracleBFile** **Seek** y **Read.** Tenga en cuenta que para utilizar este ejemplo, primero\\debe crear un directorio denominado "c: .bfiles" y el archivo denominado "MyFile.jpg" en el servidor de Oracle.  
  
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
  
## <a name="see-also"></a>Consulte también

- [Oracle y ADO.NET](oracle-and-adonet.md)
- [Información general de ADO.NET](ado-net-overview.md)
