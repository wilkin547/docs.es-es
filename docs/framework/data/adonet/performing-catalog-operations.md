---
title: Realizar operaciones de catálogo
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: e60f542f-6271-495b-a9e4-48553481c2a3
ms.openlocfilehash: beb5d2db898df1c98662d53190ac1432acc746e7
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59141458"
---
# <a name="performing-catalog-operations"></a><span data-ttu-id="61a0f-102">Realizar operaciones de catálogo</span><span class="sxs-lookup"><span data-stu-id="61a0f-102">Performing Catalog Operations</span></span>
<span data-ttu-id="61a0f-103">Para ejecutar un comando que modifique una base de datos o catálogo, por ejemplo, la instrucción CREATE TABLE o CREATE PROCEDURE, debe crear un **comando** objeto mediante las instrucciones SQL adecuadas y un **conexión** objeto.</span><span class="sxs-lookup"><span data-stu-id="61a0f-103">To execute a command to modify a database or catalog, such as the CREATE TABLE or CREATE PROCEDURE statement, create a **Command** object using the appropriate SQL statements and a **Connection** object.</span></span> <span data-ttu-id="61a0f-104">Ejecute el comando con el **ExecuteNonQuery** método de la **comando** objeto.</span><span class="sxs-lookup"><span data-stu-id="61a0f-104">Execute the command with the **ExecuteNonQuery** method of the **Command** object.</span></span>  
  
 <span data-ttu-id="61a0f-105">En el ejemplo de código siguiente se crea un procedimiento almacenado en una base de datos de Microsoft SQL Server.</span><span class="sxs-lookup"><span data-stu-id="61a0f-105">The following code example creates a stored procedure in a Microsoft SQL Server database.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="61a0f-106">Vea también</span><span class="sxs-lookup"><span data-stu-id="61a0f-106">See also</span></span>

- [<span data-ttu-id="61a0f-107">Usar comandos para modificar datos</span><span class="sxs-lookup"><span data-stu-id="61a0f-107">Using Commands to Modify Data</span></span>](../../../../docs/framework/data/adonet/using-commands-to-modify-data.md)
- [<span data-ttu-id="61a0f-108">Comandos y parámetros</span><span class="sxs-lookup"><span data-stu-id="61a0f-108">Commands and Parameters</span></span>](../../../../docs/framework/data/adonet/commands-and-parameters.md)
- [<span data-ttu-id="61a0f-109">Proveedores administrados de ADO.NET y centro de desarrolladores de DataSet</span><span class="sxs-lookup"><span data-stu-id="61a0f-109">ADO.NET Managed Providers and DataSet Developer Center</span></span>](https://go.microsoft.com/fwlink/?LinkId=217917)
