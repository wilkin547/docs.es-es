---
title: Usar comandos para modificar datos
ms.date: 03/30/2017
ms.assetid: f4160389-b9ff-4b74-b655-437c76dcd586
ms.openlocfilehash: e2f61dbf74f28d026ae91a2bc8f5bb78530ffeac
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/24/2020
ms.locfileid: "91177259"
---
# <a name="using-commands-to-modify-data"></a><span data-ttu-id="a00f7-102">Usar comandos para modificar datos</span><span class="sxs-lookup"><span data-stu-id="a00f7-102">Using Commands to Modify Data</span></span>

<span data-ttu-id="a00f7-103">Mediante un proveedor de datos .NET Framework puede ejecutar procedimientos almacenados o instrucciones de lenguaje de definición de datos, como CREATE TABLE y ALTER COLUMN, para manipular los esquemas de una base de datos o catálogo.</span><span class="sxs-lookup"><span data-stu-id="a00f7-103">Using a .NET Framework data provider, you can execute stored procedures or data definition language statements (for example, CREATE TABLE and ALTER COLUMN) to perform schema manipulation on a database or catalog.</span></span> <span data-ttu-id="a00f7-104">Estos comandos no devuelven filas como lo haría una consulta, por lo que el objeto de **comando** proporciona un **ExecuteNonQuery** para procesarlos.</span><span class="sxs-lookup"><span data-stu-id="a00f7-104">These commands do not return rows as a query would, so the **Command** object provides an **ExecuteNonQuery** to process them.</span></span>  
  
 <span data-ttu-id="a00f7-105">Además de usar **ExecuteNonQuery** para modificar el esquema, también puede utilizar este método para procesar instrucciones SQL que modifican datos pero que no devuelven filas, como INSERT, Update y DELETE.</span><span class="sxs-lookup"><span data-stu-id="a00f7-105">In addition to using **ExecuteNonQuery** to modify schema, you can also use this method to process SQL statements that modify data but that do not return rows, such as INSERT, UPDATE, and DELETE.</span></span>  
  
 <span data-ttu-id="a00f7-106">Aunque el método **ExecuteNonQuery** no devuelve las filas, los parámetros de entrada y salida y los valores devueltos se pueden pasar y devolver a través de la colección **Parameters** del objeto **Command** .</span><span class="sxs-lookup"><span data-stu-id="a00f7-106">Although rows are not returned by the **ExecuteNonQuery** method, input and output parameters and return values can be passed and returned via the **Parameters** collection of the **Command** object.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="a00f7-107">En esta sección</span><span class="sxs-lookup"><span data-stu-id="a00f7-107">In This Section</span></span>  

 [<span data-ttu-id="a00f7-108">Actualizar datos de un origen de datos</span><span class="sxs-lookup"><span data-stu-id="a00f7-108">Updating Data in a Data Source</span></span>](updating-data-in-a-data-source.md)  
 <span data-ttu-id="a00f7-109">Describe la forma de ejecutar comandos o procedimientos almacenados que modifican datos en una base de datos.</span><span class="sxs-lookup"><span data-stu-id="a00f7-109">Describes how to execute commands or stored procedures that modify data in a database.</span></span>  
  
 [<span data-ttu-id="a00f7-110">Realizar operaciones de catálogo</span><span class="sxs-lookup"><span data-stu-id="a00f7-110">Performing Catalog Operations</span></span>](performing-catalog-operations.md)  
 <span data-ttu-id="a00f7-111">Describe la forma de ejecutar comandos que modifican esquemas de la base de datos.</span><span class="sxs-lookup"><span data-stu-id="a00f7-111">Describes how to execute commands that modify database schema.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a00f7-112">Consulte también</span><span class="sxs-lookup"><span data-stu-id="a00f7-112">See also</span></span>

- [<span data-ttu-id="a00f7-113">Recuperar y modificar datos en ADO.NET</span><span class="sxs-lookup"><span data-stu-id="a00f7-113">Retrieving and Modifying Data in ADO.NET</span></span>](retrieving-and-modifying-data.md)
- [<span data-ttu-id="a00f7-114">Comandos y parámetros</span><span class="sxs-lookup"><span data-stu-id="a00f7-114">Commands and Parameters</span></span>](commands-and-parameters.md)
- [<span data-ttu-id="a00f7-115">Información general de ADO.NET</span><span class="sxs-lookup"><span data-stu-id="a00f7-115">ADO.NET Overview</span></span>](ado-net-overview.md)
