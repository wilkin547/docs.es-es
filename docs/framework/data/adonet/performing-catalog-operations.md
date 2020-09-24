---
title: Realizar operaciones de catálogo
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: e60f542f-6271-495b-a9e4-48553481c2a3
ms.openlocfilehash: 802762592a63a2046abcde8ed83ac67be47faf96
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/24/2020
ms.locfileid: "91161651"
---
# <a name="performing-catalog-operations"></a>Realizar operaciones de catálogo

Para ejecutar un comando para modificar una base de datos o un catálogo, como la instrucción CREATE TABLE o CREATE PROCEDURE, cree un objeto **Command** con las instrucciones SQL adecuadas y un objeto **Connection** . Ejecute el comando con el método **ExecuteNonQuery** del objeto **Command** .  
  
 En el ejemplo de código siguiente se crea un procedimiento almacenado en una base de datos de Microsoft SQL Server.  
  
```vb  
' Assumes connection is a valid SqlConnection.  
Dim queryString As String = "CREATE PROCEDURE InsertCategory " & _  
    "@CategoryName nchar(15), " & _  
    "@Identity int OUT " & _  
    "AS " & _  
    "INSERT INTO Categories (CategoryName) VALUES(@CategoryName) " & _  
    "SET @Identity = @@Identity " & _  
    "RETURN @@ROWCOUNT"  
  
Dim command As SqlCommand = New SqlCommand(queryString, connection)  
command.ExecuteNonQuery()  
```  
  
```csharp  
// Assumes connection is a valid SqlConnection.  
string queryString = "CREATE PROCEDURE InsertCategory  " +
    "@CategoryName nchar(15), " +  
    "@Identity int OUT " +  
    "AS " +
    "INSERT INTO Categories (CategoryName) VALUES(@CategoryName) " +
    "SET @Identity = @@Identity " +  
    "RETURN @@ROWCOUNT";  
  
SqlCommand command = new SqlCommand(queryString, connection);  
command.ExecuteNonQuery();  
```  
  
## <a name="see-also"></a>Consulte también

- [Usar comandos para modificar datos](using-commands-to-modify-data.md)
- [Comandos y parámetros](commands-and-parameters.md)
- [Información general de ADO.NET](ado-net-overview.md)
