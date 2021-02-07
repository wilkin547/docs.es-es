---
description: 'Más información sobre: usar comandos para modificar datos'
title: Usar comandos para modificar datos
ms.date: 03/30/2017
ms.assetid: f4160389-b9ff-4b74-b655-437c76dcd586
ms.openlocfilehash: 3addcb93850aa8e26fe441b5c859502779433bfb
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99766561"
---
# <a name="using-commands-to-modify-data"></a><span data-ttu-id="4b379-103">Usar comandos para modificar datos</span><span class="sxs-lookup"><span data-stu-id="4b379-103">Using Commands to Modify Data</span></span>

<span data-ttu-id="4b379-104">Mediante un proveedor de datos .NET Framework puede ejecutar procedimientos almacenados o instrucciones de lenguaje de definición de datos, como CREATE TABLE y ALTER COLUMN, para manipular los esquemas de una base de datos o catálogo.</span><span class="sxs-lookup"><span data-stu-id="4b379-104">Using a .NET Framework data provider, you can execute stored procedures or data definition language statements (for example, CREATE TABLE and ALTER COLUMN) to perform schema manipulation on a database or catalog.</span></span> <span data-ttu-id="4b379-105">Estos comandos no devuelven filas como lo haría una consulta, por lo que el objeto de **comando** proporciona un **ExecuteNonQuery** para procesarlos.</span><span class="sxs-lookup"><span data-stu-id="4b379-105">These commands do not return rows as a query would, so the **Command** object provides an **ExecuteNonQuery** to process them.</span></span>  
  
 <span data-ttu-id="4b379-106">Además de utilizar **ExecuteNonQuery** para modificar esquemas, este método se puede usar también para procesar instrucciones SQL que modifican datos sin devolver ninguna fila, como INSERT, UPDATE y DELETE.</span><span class="sxs-lookup"><span data-stu-id="4b379-106">In addition to using **ExecuteNonQuery** to modify schema, you can also use this method to process SQL statements that modify data but that do not return rows, such as INSERT, UPDATE, and DELETE.</span></span>  
  
 <span data-ttu-id="4b379-107">Aunque el método **ExecuteNonQuery** no devuelve ninguna fila, mediante la colección **Parameters** del objeto **Command** se pueden pasar y devolver parámetros de entrada y de salida, así como valores devueltos.</span><span class="sxs-lookup"><span data-stu-id="4b379-107">Although rows are not returned by the **ExecuteNonQuery** method, input and output parameters and return values can be passed and returned via the **Parameters** collection of the **Command** object.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="4b379-108">En esta sección</span><span class="sxs-lookup"><span data-stu-id="4b379-108">In This Section</span></span>  

 [<span data-ttu-id="4b379-109">Actualizar datos en un origen de datos</span><span class="sxs-lookup"><span data-stu-id="4b379-109">Updating Data in a Data Source</span></span>](updating-data-in-a-data-source.md)  
 <span data-ttu-id="4b379-110">Describe la forma de ejecutar comandos o procedimientos almacenados que modifican datos en una base de datos.</span><span class="sxs-lookup"><span data-stu-id="4b379-110">Describes how to execute commands or stored procedures that modify data in a database.</span></span>  
  
 [<span data-ttu-id="4b379-111">Realización de operaciones de catálogo</span><span class="sxs-lookup"><span data-stu-id="4b379-111">Performing Catalog Operations</span></span>](performing-catalog-operations.md)  
 <span data-ttu-id="4b379-112">Describe la forma de ejecutar comandos que modifican esquemas de la base de datos.</span><span class="sxs-lookup"><span data-stu-id="4b379-112">Describes how to execute commands that modify database schema.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4b379-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="4b379-113">See also</span></span>

- [<span data-ttu-id="4b379-114">Recuperar y modificar datos en ADO.NET</span><span class="sxs-lookup"><span data-stu-id="4b379-114">Retrieving and Modifying Data in ADO.NET</span></span>](retrieving-and-modifying-data.md)
- [<span data-ttu-id="4b379-115">Comandos y parámetros</span><span class="sxs-lookup"><span data-stu-id="4b379-115">Commands and Parameters</span></span>](commands-and-parameters.md)
- [<span data-ttu-id="4b379-116">Información general de ADO.NET</span><span class="sxs-lookup"><span data-stu-id="4b379-116">ADO.NET Overview</span></span>](ado-net-overview.md)
