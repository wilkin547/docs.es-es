---
title: Obtener un valor único de una base de datos
description: Obtenga información sobre cómo devolver un valor único en ADO.NET. Este código de ejemplo devuelve el valor de la columna de identidad para un registro insertado.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: b38526cd-a62a-48cb-822a-e91dfa68e02d
ms.openlocfilehash: a6f268f72f8b8a09ae48ba3cad6254323cb95a20
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/02/2020
ms.locfileid: "84286707"
---
# <a name="obtaining-a-single-value-from-a-database"></a><span data-ttu-id="2e086-104">Obtener un valor único de una base de datos</span><span class="sxs-lookup"><span data-stu-id="2e086-104">Obtaining a Single Value from a Database</span></span>
<span data-ttu-id="2e086-105">En ocasiones se debe devolver información de bases de datos consistente en un único valor, en lugar de una tabla o un flujo de datos.</span><span class="sxs-lookup"><span data-stu-id="2e086-105">You may need to return database information that is simply a single value rather than in the form of a table or data stream.</span></span> <span data-ttu-id="2e086-106">Por ejemplo, puede que desee devolver el resultado de una función de agregado como COUNT ( \* ), SUM (Price) o AVG (quantity).</span><span class="sxs-lookup"><span data-stu-id="2e086-106">For example, you may want to return the result of an aggregate function such as COUNT(\*), SUM(Price), or AVG(Quantity).</span></span> <span data-ttu-id="2e086-107">El objeto **Command** proporciona la capacidad de devolver valores únicos mediante el método **ExecuteScalar** .</span><span class="sxs-lookup"><span data-stu-id="2e086-107">The **Command** object provides the capability to return single values using the **ExecuteScalar** method.</span></span> <span data-ttu-id="2e086-108">El método **ExecuteScalar** devuelve, como un valor escalar, el valor de la primera columna de la primera fila del conjunto de resultados.</span><span class="sxs-lookup"><span data-stu-id="2e086-108">The **ExecuteScalar** method returns, as a scalar value, the value of the first column of the first row of the result set.</span></span>  
  
 <span data-ttu-id="2e086-109">El ejemplo de código siguiente inserta un valor nuevo en la base de datos utilizando <xref:System.Data.SqlClient.SqlCommand>.</span><span class="sxs-lookup"><span data-stu-id="2e086-109">The following code example inserts a new value in the database using a <xref:System.Data.SqlClient.SqlCommand>.</span></span> <span data-ttu-id="2e086-110">El método <xref:System.Data.SqlClient.SqlCommand.ExecuteScalar%2A> se utiliza para devolver el valor de columna de identidad para el registro insertado.</span><span class="sxs-lookup"><span data-stu-id="2e086-110">The <xref:System.Data.SqlClient.SqlCommand.ExecuteScalar%2A> method is used to return the identity column value for the inserted record.</span></span>  
  
 [!code-csharp[DataWorks SqlCommand.ExecuteScalar#1](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks SqlCommand.ExecuteScalar/CS/source.cs#1)]
 [!code-vb[DataWorks SqlCommand.ExecuteScalar#1](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks SqlCommand.ExecuteScalar/VB/source.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="2e086-111">Consulte también</span><span class="sxs-lookup"><span data-stu-id="2e086-111">See also</span></span>

- [<span data-ttu-id="2e086-112">Comandos y parámetros</span><span class="sxs-lookup"><span data-stu-id="2e086-112">Commands and Parameters</span></span>](commands-and-parameters.md)
- [<span data-ttu-id="2e086-113">Ejecutar un comando</span><span class="sxs-lookup"><span data-stu-id="2e086-113">Executing a Command</span></span>](executing-a-command.md)
- [<span data-ttu-id="2e086-114">DbConnection, DbCommand y DbException</span><span class="sxs-lookup"><span data-stu-id="2e086-114">DbConnection, DbCommand and DbException</span></span>](dbconnection-dbcommand-and-dbexception.md)
- [<span data-ttu-id="2e086-115">Información general de ADO.NET</span><span class="sxs-lookup"><span data-stu-id="2e086-115">ADO.NET Overview</span></span>](ado-net-overview.md)
