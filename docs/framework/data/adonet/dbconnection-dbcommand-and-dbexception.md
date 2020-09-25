---
title: DbConnection, DbCommand y DbException
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 58aab611-7e6f-4749-b983-28ab7ae87dbe
ms.openlocfilehash: 3075999c15fccc3a41c191297a146c362b3638e8
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/24/2020
ms.locfileid: "91183330"
---
# <a name="dbconnection-dbcommand-and-dbexception"></a>DbConnection, DbCommand y DbException

Después de crear un objeto <xref:System.Data.Common.DbProviderFactory> y un objeto <xref:System.Data.Common.DbConnection>, puede trabajar con comandos y lectores de datos para recuperar datos del origen de datos.  
  
## <a name="retrieving-data-example"></a>Ejemplo de recuperación de datos  

 En este ejemplo se utiliza un objeto `DbConnection` como argumento. Se crea un objeto <xref:System.Data.Common.DbCommand> para seleccionar datos de la tabla Categories mediante el establecimiento de <xref:System.Data.Common.DbCommand.CommandText%2A> en una instrucción SELECT de SQL. El código asume que la tabla Categories existe en el origen de datos. Se abre la conexión y los datos se recuperan mediante <xref:System.Data.Common.DbDataReader>.  
  
 [!code-csharp[DataWorks DbProviderFactories.DbCommandData#1](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks DbProviderFactories.DbCommandData/CS/source.cs#1)]
 [!code-vb[DataWorks DbProviderFactories.DbCommandData#1](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks DbProviderFactories.DbCommandData/VB/source.vb#1)]  
  
## <a name="executing-a-command-example"></a>Ejemplo de ejecución de un comando  

 En este ejemplo se utiliza un objeto `DbConnection` como argumento. Si el objeto `DbConnection` es válido, se abre la conexión y, a continuación, se crea y se ejecuta un objeto <xref:System.Data.Common.DbCommand>. <xref:System.Data.Common.DbCommand.CommandText%2A> se establece en una instrucción INSERT de SQL que realiza una inserción en la tabla Categories de la base de datos Northwind. El código a sume que la base de datos Northwind existe en el origen de datos y que la sintaxis de SQL usada en la instrucción INSERT es válida en el proveedor especificado. El bloque de código <xref:System.Data.Common.DbException> controla los errores que se producen en el origen de datos y el bloque <xref:System.Exception> controla todas las demás excepciones.  
  
 [!code-csharp[DataWorks DbProviderFactories.DbCommand#1](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks DbProviderFactories.DbCommand/CS/source.cs#1)]
 [!code-vb[DataWorks DbProviderFactories.DbCommand#1](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks DbProviderFactories.DbCommand/VB/source.vb#1)]  
  
## <a name="handling-data-errors-with-dbexception"></a>Controlar errores de datos con DbException  

 La clase <xref:System.Data.Common.DbException> es la clase base para todas las excepciones que se producen por cuenta del origen de datos. Puede usarla en el código de control de excepciones para controlar las excepciones que inician diferentes proveedores sin necesidad de hacer referencia a una clase de excepción específica. En el fragmento de código siguiente se muestra cómo utilizar <xref:System.Data.Common.DbException>para mostrar la información de error que devuelve el origen de datos mediante las propiedades <xref:System.Exception.GetType%2A>, <xref:System.Exception.Source%2A>, <xref:System.Runtime.InteropServices.ExternalException.ErrorCode%2A> y <xref:System.Exception.Message%2A>. El resultado mostrará el tipo de error, el origen que indica el nombre de proveedor, un código de error y el mensaje asociado al error.  
  
```vb  
Try  
    ' Do work here.  
Catch ex As DbException  
    ' Display information about the exception.  
    Console.WriteLine("GetType: {0}", ex.GetType())  
    Console.WriteLine("Source: {0}", ex.Source)  
    Console.WriteLine("ErrorCode: {0}", ex.ErrorCode)  
    Console.WriteLine("Message: {0}", ex.Message)  
Finally  
    ' Perform cleanup here.  
End Try  
```  
  
```csharp  
try  
{  
    // Do work here.  
}  
catch (DbException ex)  
{  
    // Display information about the exception.  
    Console.WriteLine("GetType: {0}", ex.GetType());  
    Console.WriteLine("Source: {0}", ex.Source);  
    Console.WriteLine("ErrorCode: {0}", ex.ErrorCode);  
    Console.WriteLine("Message: {0}", ex.Message);  
}  
finally  
{  
    // Perform cleanup here.  
}  
```  
  
## <a name="see-also"></a>Consulte también

- [Objetos DbProviderFactory](dbproviderfactories.md)
- [Obtener un objeto DbProviderFactory](obtaining-a-dbproviderfactory.md)
- [Modificar datos con un objeto DbDataAdapter](modifying-data-with-a-dbdataadapter.md)
- [Información general de ADO.NET](ado-net-overview.md)
