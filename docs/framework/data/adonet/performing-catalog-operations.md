---
description: 'Más información sobre: realización de operaciones de catálogo'
title: Realizar operaciones de catálogo
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: e60f542f-6271-495b-a9e4-48553481c2a3
ms.openlocfilehash: c484e3a56d846de66c6e13b374efe58430ab86b2
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99754347"
---
# <a name="performing-catalog-operations"></a><span data-ttu-id="aaf68-103">Realizar operaciones de catálogo</span><span class="sxs-lookup"><span data-stu-id="aaf68-103">Performing Catalog Operations</span></span>

<span data-ttu-id="aaf68-104">Para ejecutar un comando que modifique una base de datos o un catálogo, por ejemplo una instrucción CREATE TABLE o CREATE PROCEDURE, debe crear un objeto **Command** mediante las instrucciones SQL adecuadas y un objeto **Connection**.</span><span class="sxs-lookup"><span data-stu-id="aaf68-104">To execute a command to modify a database or catalog, such as the CREATE TABLE or CREATE PROCEDURE statement, create a **Command** object using the appropriate SQL statements and a **Connection** object.</span></span> <span data-ttu-id="aaf68-105">Ejecute el comando con el método **ExecuteNonQuery** del objeto **Command** .</span><span class="sxs-lookup"><span data-stu-id="aaf68-105">Execute the command with the **ExecuteNonQuery** method of the **Command** object.</span></span>  
  
 <span data-ttu-id="aaf68-106">En el ejemplo de código siguiente se crea un procedimiento almacenado en una base de datos de Microsoft SQL Server.</span><span class="sxs-lookup"><span data-stu-id="aaf68-106">The following code example creates a stored procedure in a Microsoft SQL Server database.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="aaf68-107">Vea también</span><span class="sxs-lookup"><span data-stu-id="aaf68-107">See also</span></span>

- [<span data-ttu-id="aaf68-108">Usar comandos para modificar datos</span><span class="sxs-lookup"><span data-stu-id="aaf68-108">Using Commands to Modify Data</span></span>](using-commands-to-modify-data.md)
- [<span data-ttu-id="aaf68-109">Comandos y parámetros</span><span class="sxs-lookup"><span data-stu-id="aaf68-109">Commands and Parameters</span></span>](commands-and-parameters.md)
- [<span data-ttu-id="aaf68-110">Información general de ADO.NET</span><span class="sxs-lookup"><span data-stu-id="aaf68-110">ADO.NET Overview</span></span>](ado-net-overview.md)
