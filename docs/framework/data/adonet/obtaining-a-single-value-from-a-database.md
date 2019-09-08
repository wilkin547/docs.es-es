---
title: Obtener un valor único de una base de datos
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: b38526cd-a62a-48cb-822a-e91dfa68e02d
ms.openlocfilehash: fb43d21546a0e98e87aab23db9213309b62320b9
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/07/2019
ms.locfileid: "70794750"
---
# <a name="obtaining-a-single-value-from-a-database"></a><span data-ttu-id="3fce6-102">Obtener un valor único de una base de datos</span><span class="sxs-lookup"><span data-stu-id="3fce6-102">Obtaining a Single Value from a Database</span></span>
<span data-ttu-id="3fce6-103">En ocasiones se debe devolver información de bases de datos consistente en un único valor, en lugar de una tabla o un flujo de datos.</span><span class="sxs-lookup"><span data-stu-id="3fce6-103">You may need to return database information that is simply a single value rather than in the form of a table or data stream.</span></span> <span data-ttu-id="3fce6-104">Por ejemplo, puede que desee devolver el resultado de una función de agregado como Count (\*), SUM (Price) o AVG (quantity).</span><span class="sxs-lookup"><span data-stu-id="3fce6-104">For example, you may want to return the result of an aggregate function such as COUNT(\*), SUM(Price), or AVG(Quantity).</span></span> <span data-ttu-id="3fce6-105">El objeto **Command** proporciona la capacidad de devolver valores únicos mediante el método **ExecuteScalar** .</span><span class="sxs-lookup"><span data-stu-id="3fce6-105">The **Command** object provides the capability to return single values using the **ExecuteScalar** method.</span></span> <span data-ttu-id="3fce6-106">El método **ExecuteScalar** devuelve, como un valor escalar, el valor de la primera columna de la primera fila del conjunto de resultados.</span><span class="sxs-lookup"><span data-stu-id="3fce6-106">The **ExecuteScalar** method returns, as a scalar value, the value of the first column of the first row of the result set.</span></span>  
  
 <span data-ttu-id="3fce6-107">El ejemplo de código siguiente inserta un valor nuevo en la base de datos utilizando <xref:System.Data.SqlClient.SqlCommand>.</span><span class="sxs-lookup"><span data-stu-id="3fce6-107">The following code example inserts a new value in the database using a <xref:System.Data.SqlClient.SqlCommand>.</span></span> <span data-ttu-id="3fce6-108">El método <xref:System.Data.SqlClient.SqlCommand.ExecuteScalar%2A> se utiliza para devolver el valor de columna de identidad para el registro insertado.</span><span class="sxs-lookup"><span data-stu-id="3fce6-108">The <xref:System.Data.SqlClient.SqlCommand.ExecuteScalar%2A> method is used to return the identity column value for the inserted record.</span></span>  
  
 [!code-csharp[DataWorks SqlCommand.ExecuteScalar#1](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks SqlCommand.ExecuteScalar/CS/source.cs#1)]
 [!code-vb[DataWorks SqlCommand.ExecuteScalar#1](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks SqlCommand.ExecuteScalar/VB/source.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="3fce6-109">Vea también</span><span class="sxs-lookup"><span data-stu-id="3fce6-109">See also</span></span>

- [<span data-ttu-id="3fce6-110">Comandos y parámetros</span><span class="sxs-lookup"><span data-stu-id="3fce6-110">Commands and Parameters</span></span>](commands-and-parameters.md)
- [<span data-ttu-id="3fce6-111">Ejecución de un comando</span><span class="sxs-lookup"><span data-stu-id="3fce6-111">Executing a Command</span></span>](executing-a-command.md)
- [<span data-ttu-id="3fce6-112">DbConnection, DbCommand y DbException</span><span class="sxs-lookup"><span data-stu-id="3fce6-112">DbConnection, DbCommand and DbException</span></span>](dbconnection-dbcommand-and-dbexception.md)
- [<span data-ttu-id="3fce6-113">Información general sobre ADO.NET</span><span class="sxs-lookup"><span data-stu-id="3fce6-113">ADO.NET Overview</span></span>](ado-net-overview.md)
