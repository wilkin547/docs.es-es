---
title: Obtener un valor único de una base de datos
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: b38526cd-a62a-48cb-822a-e91dfa68e02d
ms.openlocfilehash: b7ad989dce39a8e9a0ed7b6cd988e06304e7b40f
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/03/2018
ms.locfileid: "32764936"
---
# <a name="obtaining-a-single-value-from-a-database"></a><span data-ttu-id="2ce9c-102">Obtener un valor único de una base de datos</span><span class="sxs-lookup"><span data-stu-id="2ce9c-102">Obtaining a Single Value from a Database</span></span>
<span data-ttu-id="2ce9c-103">En ocasiones se debe devolver información de bases de datos consistente en un único valor, en lugar de una tabla o un flujo de datos.</span><span class="sxs-lookup"><span data-stu-id="2ce9c-103">You may need to return database information that is simply a single value rather than in the form of a table or data stream.</span></span> <span data-ttu-id="2ce9c-104">Por ejemplo, puede que desee devolver el resultado de una función de agregado como COUNT (\*), SUM (price) o AVG (Quantity).</span><span class="sxs-lookup"><span data-stu-id="2ce9c-104">For example, you may want to return the result of an aggregate function such as COUNT(\*), SUM(Price), or AVG(Quantity).</span></span> <span data-ttu-id="2ce9c-105">El **comando** objeto proporciona la capacidad de devolver valores únicos mediante el **ExecuteScalar** método.</span><span class="sxs-lookup"><span data-stu-id="2ce9c-105">The **Command** object provides the capability to return single values using the **ExecuteScalar** method.</span></span> <span data-ttu-id="2ce9c-106">El **ExecuteScalar** método devuelve, como un valor escalar, el valor de la primera columna de la primera fila del conjunto de resultados.</span><span class="sxs-lookup"><span data-stu-id="2ce9c-106">The **ExecuteScalar** method returns, as a scalar value, the value of the first column of the first row of the result set.</span></span>  
  
 <span data-ttu-id="2ce9c-107">El ejemplo de código siguiente inserta un valor nuevo en la base de datos utilizando <xref:System.Data.SqlClient.SqlCommand>.</span><span class="sxs-lookup"><span data-stu-id="2ce9c-107">The following code example inserts a new value in the database using a <xref:System.Data.SqlClient.SqlCommand>.</span></span> <span data-ttu-id="2ce9c-108">El método <xref:System.Data.SqlClient.SqlCommand.ExecuteScalar%2A> se utiliza para devolver el valor de columna de identidad para el registro insertado.</span><span class="sxs-lookup"><span data-stu-id="2ce9c-108">The <xref:System.Data.SqlClient.SqlCommand.ExecuteScalar%2A> method is used to return the identity column value for the inserted record.</span></span>  
  
 [!code-csharp[DataWorks SqlCommand.ExecuteScalar#1](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks SqlCommand.ExecuteScalar/CS/source.cs#1)]
 [!code-vb[DataWorks SqlCommand.ExecuteScalar#1](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks SqlCommand.ExecuteScalar/VB/source.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="2ce9c-109">Vea también</span><span class="sxs-lookup"><span data-stu-id="2ce9c-109">See Also</span></span>  
 [<span data-ttu-id="2ce9c-110">Comandos y parámetros</span><span class="sxs-lookup"><span data-stu-id="2ce9c-110">Commands and Parameters</span></span>](../../../../docs/framework/data/adonet/commands-and-parameters.md)  
 [<span data-ttu-id="2ce9c-111">Ejecución de un comando</span><span class="sxs-lookup"><span data-stu-id="2ce9c-111">Executing a Command</span></span>](../../../../docs/framework/data/adonet/executing-a-command.md)  
 [<span data-ttu-id="2ce9c-112">DbConnection, DbCommand y DbException</span><span class="sxs-lookup"><span data-stu-id="2ce9c-112">DbConnection, DbCommand and DbException</span></span>](../../../../docs/framework/data/adonet/dbconnection-dbcommand-and-dbexception.md)  
 [<span data-ttu-id="2ce9c-113">Proveedores administrados de ADO.NET y Centro para desarrolladores de DataSet</span><span class="sxs-lookup"><span data-stu-id="2ce9c-113">ADO.NET Managed Providers and DataSet Developer Center</span></span>](http://go.microsoft.com/fwlink/?LinkId=217917)
