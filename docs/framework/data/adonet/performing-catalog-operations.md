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
# <a name="performing-catalog-operations"></a><span data-ttu-id="65ab6-102">Realizar operaciones de catálogo</span><span class="sxs-lookup"><span data-stu-id="65ab6-102">Performing Catalog Operations</span></span>

<span data-ttu-id="65ab6-103">Para ejecutar un comando para modificar una base de datos o un catálogo, como la instrucción CREATE TABLE o CREATE PROCEDURE, cree un objeto **Command** con las instrucciones SQL adecuadas y un objeto **Connection** .</span><span class="sxs-lookup"><span data-stu-id="65ab6-103">To execute a command to modify a database or catalog, such as the CREATE TABLE or CREATE PROCEDURE statement, create a **Command** object using the appropriate SQL statements and a **Connection** object.</span></span> <span data-ttu-id="65ab6-104">Ejecute el comando con el método **ExecuteNonQuery** del objeto **Command** .</span><span class="sxs-lookup"><span data-stu-id="65ab6-104">Execute the command with the **ExecuteNonQuery** method of the **Command** object.</span></span>  
  
 <span data-ttu-id="65ab6-105">En el ejemplo de código siguiente se crea un procedimiento almacenado en una base de datos de Microsoft SQL Server.</span><span class="sxs-lookup"><span data-stu-id="65ab6-105">The following code example creates a stored procedure in a Microsoft SQL Server database.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="65ab6-106">Consulte también</span><span class="sxs-lookup"><span data-stu-id="65ab6-106">See also</span></span>

- [<span data-ttu-id="65ab6-107">Usar comandos para modificar datos</span><span class="sxs-lookup"><span data-stu-id="65ab6-107">Using Commands to Modify Data</span></span>](using-commands-to-modify-data.md)
- [<span data-ttu-id="65ab6-108">Comandos y parámetros</span><span class="sxs-lookup"><span data-stu-id="65ab6-108">Commands and Parameters</span></span>](commands-and-parameters.md)
- [<span data-ttu-id="65ab6-109">Información general de ADO.NET</span><span class="sxs-lookup"><span data-stu-id="65ab6-109">ADO.NET Overview</span></span>](ado-net-overview.md)
