---
title: Usar comandos para modificar datos
ms.date: 03/30/2017
ms.assetid: f4160389-b9ff-4b74-b655-437c76dcd586
ms.openlocfilehash: f2e3d162bfbdcb79cfecefa4ddc8e6a0dc46ee3c
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61875958"
---
# <a name="using-commands-to-modify-data"></a><span data-ttu-id="52492-102">Usar comandos para modificar datos</span><span class="sxs-lookup"><span data-stu-id="52492-102">Using Commands to Modify Data</span></span>
<span data-ttu-id="52492-103">Mediante un proveedor de datos .NET Framework puede ejecutar procedimientos almacenados o instrucciones de lenguaje de definición de datos, como CREATE TABLE y ALTER COLUMN, para manipular los esquemas de una base de datos o catálogo.</span><span class="sxs-lookup"><span data-stu-id="52492-103">Using a .NET Framework data provider, you can execute stored procedures or data definition language statements (for example, CREATE TABLE and ALTER COLUMN) to perform schema manipulation on a database or catalog.</span></span> <span data-ttu-id="52492-104">Estos comandos no devuelven filas como haría con una consulta, por lo que la **comando** objeto proporciona un **ExecuteNonQuery** para procesarlos.</span><span class="sxs-lookup"><span data-stu-id="52492-104">These commands do not return rows as a query would, so the **Command** object provides an **ExecuteNonQuery** to process them.</span></span>  
  
 <span data-ttu-id="52492-105">Además de usar **ExecuteNonQuery** para modificar el esquema, también puede usar este método para procesar instrucciones SQL que modifican datos sin que no devuelven filas, como INSERT, UPDATE y DELETE.</span><span class="sxs-lookup"><span data-stu-id="52492-105">In addition to using **ExecuteNonQuery** to modify schema, you can also use this method to process SQL statements that modify data but that do not return rows, such as INSERT, UPDATE, and DELETE.</span></span>  
  
 <span data-ttu-id="52492-106">Aunque no se devuelven filas por la **ExecuteNonQuery** pueden pasar y devolver a través de los parámetros de método de entrada y salida y valores devueltos del **parámetros** colección de la **comando**  objeto.</span><span class="sxs-lookup"><span data-stu-id="52492-106">Although rows are not returned by the **ExecuteNonQuery** method, input and output parameters and return values can be passed and returned via the **Parameters** collection of the **Command** object.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="52492-107">En esta sección</span><span class="sxs-lookup"><span data-stu-id="52492-107">In This Section</span></span>  
 [<span data-ttu-id="52492-108">Actualización de datos de un origen de datos</span><span class="sxs-lookup"><span data-stu-id="52492-108">Updating Data in a Data Source</span></span>](../../../../docs/framework/data/adonet/updating-data-in-a-data-source.md)  
 <span data-ttu-id="52492-109">Describe la forma de ejecutar comandos o procedimientos almacenados que modifican datos en una base de datos.</span><span class="sxs-lookup"><span data-stu-id="52492-109">Describes how to execute commands or stored procedures that modify data in a database.</span></span>  
  
 [<span data-ttu-id="52492-110">Realización de operaciones de catálogo</span><span class="sxs-lookup"><span data-stu-id="52492-110">Performing Catalog Operations</span></span>](../../../../docs/framework/data/adonet/performing-catalog-operations.md)  
 <span data-ttu-id="52492-111">Describe la forma de ejecutar comandos que modifican esquemas de la base de datos.</span><span class="sxs-lookup"><span data-stu-id="52492-111">Describes how to execute commands that modify database schema.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="52492-112">Vea también</span><span class="sxs-lookup"><span data-stu-id="52492-112">See also</span></span>

- [<span data-ttu-id="52492-113">Recuperar y modificar datos en ADO.NET</span><span class="sxs-lookup"><span data-stu-id="52492-113">Retrieving and Modifying Data in ADO.NET</span></span>](../../../../docs/framework/data/adonet/retrieving-and-modifying-data.md)
- [<span data-ttu-id="52492-114">Comandos y parámetros</span><span class="sxs-lookup"><span data-stu-id="52492-114">Commands and Parameters</span></span>](../../../../docs/framework/data/adonet/commands-and-parameters.md)
- [<span data-ttu-id="52492-115">Proveedores administrados de ADO.NET y Centro para desarrolladores de DataSet</span><span class="sxs-lookup"><span data-stu-id="52492-115">ADO.NET Managed Providers and DataSet Developer Center</span></span>](https://go.microsoft.com/fwlink/?LinkId=217917)
