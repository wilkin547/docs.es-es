---
title: Usar comandos para modificar datos
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: f4160389-b9ff-4b74-b655-437c76dcd586
caps.latest.revision: "4"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.workload: dotnet
ms.openlocfilehash: 5c574a5e880dd838397b35df48138079cb58e2cf
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="using-commands-to-modify-data"></a><span data-ttu-id="e8b80-102">Usar comandos para modificar datos</span><span class="sxs-lookup"><span data-stu-id="e8b80-102">Using Commands to Modify Data</span></span>
<span data-ttu-id="e8b80-103">Mediante un proveedor de datos .NET Framework puede ejecutar procedimientos almacenados o instrucciones de lenguaje de definición de datos, como CREATE TABLE y ALTER COLUMN, para manipular los esquemas de una base de datos o catálogo.</span><span class="sxs-lookup"><span data-stu-id="e8b80-103">Using a .NET Framework data provider, you can execute stored procedures or data definition language statements (for example, CREATE TABLE and ALTER COLUMN) to perform schema manipulation on a database or catalog.</span></span> <span data-ttu-id="e8b80-104">Estos comandos no devuelven filas tal y como haría una consulta y, por lo que la **comando** objeto proporciona un **ExecuteNonQuery** para procesarlos.</span><span class="sxs-lookup"><span data-stu-id="e8b80-104">These commands do not return rows as a query would, so the **Command** object provides an **ExecuteNonQuery** to process them.</span></span>  
  
 <span data-ttu-id="e8b80-105">Además de usar **ExecuteNonQuery** para modificar el esquema, también puede utilizar este método para procesar instrucciones SQL que modifican datos sin que no devuelven filas, como INSERT, UPDATE y DELETE.</span><span class="sxs-lookup"><span data-stu-id="e8b80-105">In addition to using **ExecuteNonQuery** to modify schema, you can also use this method to process SQL statements that modify data but that do not return rows, such as INSERT, UPDATE, and DELETE.</span></span>  
  
 <span data-ttu-id="e8b80-106">Aunque no se devuelven filas por la **ExecuteNonQuery** parámetros de entrada y salida de método y valores devueltos pueden pasar y devolver a través de la **parámetros** colección de la **comando**  objeto.</span><span class="sxs-lookup"><span data-stu-id="e8b80-106">Although rows are not returned by the **ExecuteNonQuery** method, input and output parameters and return values can be passed and returned via the **Parameters** collection of the **Command** object.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="e8b80-107">En esta sección</span><span class="sxs-lookup"><span data-stu-id="e8b80-107">In This Section</span></span>  
 [<span data-ttu-id="e8b80-108">Actualización de datos de un origen de datos</span><span class="sxs-lookup"><span data-stu-id="e8b80-108">Updating Data in a Data Source</span></span>](../../../../docs/framework/data/adonet/updating-data-in-a-data-source.md)  
 <span data-ttu-id="e8b80-109">Describe la forma de ejecutar comandos o procedimientos almacenados que modifican datos en una base de datos.</span><span class="sxs-lookup"><span data-stu-id="e8b80-109">Describes how to execute commands or stored procedures that modify data in a database.</span></span>  
  
 [<span data-ttu-id="e8b80-110">Realización de operaciones de catálogo</span><span class="sxs-lookup"><span data-stu-id="e8b80-110">Performing Catalog Operations</span></span>](../../../../docs/framework/data/adonet/performing-catalog-operations.md)  
 <span data-ttu-id="e8b80-111">Describe la forma de ejecutar comandos que modifican esquemas de la base de datos.</span><span class="sxs-lookup"><span data-stu-id="e8b80-111">Describes how to execute commands that modify database schema.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e8b80-112">Vea también</span><span class="sxs-lookup"><span data-stu-id="e8b80-112">See Also</span></span>  
 [<span data-ttu-id="e8b80-113">Recuperar y modificar datos en ADO.NET</span><span class="sxs-lookup"><span data-stu-id="e8b80-113">Retrieving and Modifying Data in ADO.NET</span></span>](../../../../docs/framework/data/adonet/retrieving-and-modifying-data.md)  
 [<span data-ttu-id="e8b80-114">Comandos y parámetros</span><span class="sxs-lookup"><span data-stu-id="e8b80-114">Commands and Parameters</span></span>](../../../../docs/framework/data/adonet/commands-and-parameters.md)  
 [<span data-ttu-id="e8b80-115">Proveedores administrados de ADO.NET y Centro para desarrolladores de DataSet</span><span class="sxs-lookup"><span data-stu-id="e8b80-115">ADO.NET Managed Providers and DataSet Developer Center</span></span>](http://go.microsoft.com/fwlink/?LinkId=217917)
