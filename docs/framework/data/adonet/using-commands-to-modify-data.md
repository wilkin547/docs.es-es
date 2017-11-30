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
ms.openlocfilehash: 853f8e4e75df3fffad4a2d5ecd4f7ae21b5d674f
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="using-commands-to-modify-data"></a><span data-ttu-id="64a15-102">Usar comandos para modificar datos</span><span class="sxs-lookup"><span data-stu-id="64a15-102">Using Commands to Modify Data</span></span>
<span data-ttu-id="64a15-103">Mediante un proveedor de datos .NET Framework puede ejecutar procedimientos almacenados o instrucciones de lenguaje de definición de datos, como CREATE TABLE y ALTER COLUMN, para manipular los esquemas de una base de datos o catálogo.</span><span class="sxs-lookup"><span data-stu-id="64a15-103">Using a .NET Framework data provider, you can execute stored procedures or data definition language statements (for example, CREATE TABLE and ALTER COLUMN) to perform schema manipulation on a database or catalog.</span></span> <span data-ttu-id="64a15-104">Estos comandos no devuelven filas tal y como haría una consulta y, por lo que la **comando** objeto proporciona un **ExecuteNonQuery** para procesarlos.</span><span class="sxs-lookup"><span data-stu-id="64a15-104">These commands do not return rows as a query would, so the **Command** object provides an **ExecuteNonQuery** to process them.</span></span>  
  
 <span data-ttu-id="64a15-105">Además de usar **ExecuteNonQuery** para modificar el esquema, también puede utilizar este método para procesar instrucciones SQL que modifican datos sin que no devuelven filas, como INSERT, UPDATE y DELETE.</span><span class="sxs-lookup"><span data-stu-id="64a15-105">In addition to using **ExecuteNonQuery** to modify schema, you can also use this method to process SQL statements that modify data but that do not return rows, such as INSERT, UPDATE, and DELETE.</span></span>  
  
 <span data-ttu-id="64a15-106">Aunque no se devuelven filas por la **ExecuteNonQuery** parámetros de entrada y salida de método y valores devueltos pueden pasar y devolver a través de la **parámetros** colección de la **comando**  objeto.</span><span class="sxs-lookup"><span data-stu-id="64a15-106">Although rows are not returned by the **ExecuteNonQuery** method, input and output parameters and return values can be passed and returned via the **Parameters** collection of the **Command** object.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="64a15-107">En esta sección</span><span class="sxs-lookup"><span data-stu-id="64a15-107">In This Section</span></span>  
 [<span data-ttu-id="64a15-108">Actualizar datos en un origen de datos</span><span class="sxs-lookup"><span data-stu-id="64a15-108">Updating Data in a Data Source</span></span>](../../../../docs/framework/data/adonet/updating-data-in-a-data-source.md)  
 <span data-ttu-id="64a15-109">Describe la forma de ejecutar comandos o procedimientos almacenados que modifican datos en una base de datos.</span><span class="sxs-lookup"><span data-stu-id="64a15-109">Describes how to execute commands or stored procedures that modify data in a database.</span></span>  
  
 [<span data-ttu-id="64a15-110">Realizar operaciones de catálogo</span><span class="sxs-lookup"><span data-stu-id="64a15-110">Performing Catalog Operations</span></span>](../../../../docs/framework/data/adonet/performing-catalog-operations.md)  
 <span data-ttu-id="64a15-111">Describe la forma de ejecutar comandos que modifican esquemas de la base de datos.</span><span class="sxs-lookup"><span data-stu-id="64a15-111">Describes how to execute commands that modify database schema.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="64a15-112">Vea también</span><span class="sxs-lookup"><span data-stu-id="64a15-112">See Also</span></span>  
 [<span data-ttu-id="64a15-113">Recuperar y modificar datos en ADO.NET</span><span class="sxs-lookup"><span data-stu-id="64a15-113">Retrieving and Modifying Data in ADO.NET</span></span>](../../../../docs/framework/data/adonet/retrieving-and-modifying-data.md)  
 [<span data-ttu-id="64a15-114">Comandos y parámetros</span><span class="sxs-lookup"><span data-stu-id="64a15-114">Commands and Parameters</span></span>](../../../../docs/framework/data/adonet/commands-and-parameters.md)  
 [<span data-ttu-id="64a15-115">Proveedores administrados de ADO.NET y Centro para desarrolladores de DataSet</span><span class="sxs-lookup"><span data-stu-id="64a15-115">ADO.NET Managed Providers and DataSet Developer Center</span></span>](http://go.microsoft.com/fwlink/?LinkId=217917)
