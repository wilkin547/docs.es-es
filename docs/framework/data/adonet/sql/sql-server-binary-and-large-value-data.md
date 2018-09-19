---
title: Datos binarios y datos de valores grandes de SQL Server
ms.date: 03/30/2017
ms.assetid: e00827b3-7511-4b2d-91d7-851ca86cc6b5
ms.openlocfilehash: 9ebbe23dfbcac7825ce449dd40f62b921d13ab4a
ms.sourcegitcommit: 5bbfe34a9a14e4ccb22367e57b57585c208cf757
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/18/2018
ms.locfileid: "45998947"
---
# <a name="sql-server-binary-and-large-value-data"></a><span data-ttu-id="c9b86-102">Datos binarios y datos de valores grandes de SQL Server</span><span class="sxs-lookup"><span data-stu-id="c9b86-102">SQL Server Binary and Large-Value Data</span></span>
<span data-ttu-id="c9b86-103">SQL Server proporciona el especificador `max`, que amplía la capacidad de almacenamiento de los tipos de datos `varchar`, `nvarchar` y `varbinary`.</span><span class="sxs-lookup"><span data-stu-id="c9b86-103">SQL Server provides the `max` specifier, which expands the storage capacity of the `varchar`, `nvarchar`, and `varbinary` data types.</span></span> <span data-ttu-id="c9b86-104">`varchar(max)`, `nvarchar(max)`, y `varbinary(max)` se denominan colectivamente *tipos de datos de valores grandes*.</span><span class="sxs-lookup"><span data-stu-id="c9b86-104">`varchar(max)`, `nvarchar(max)`, and `varbinary(max)` are collectively called *large-value data types*.</span></span> <span data-ttu-id="c9b86-105">Puede utilizar los tipos de datos de valores grandes para almacenar hasta 2^31-1 bytes de datos.</span><span class="sxs-lookup"><span data-stu-id="c9b86-105">You can use the large-value data types to store up to 2^31-1 bytes of data.</span></span>  
  
 <span data-ttu-id="c9b86-106">SQL Server 2008 incorpora el atributo FILESTREAM, que no es un tipo de datos, sino un atributo que se puede definir en una columna, y permite almacenar datos de valores grandes en el sistema de archivos en lugar de almacenarlos en la base de datos.</span><span class="sxs-lookup"><span data-stu-id="c9b86-106">SQL Server 2008 introduces the FILESTREAM attribute, which is not a data type, but rather an attribute that can be defined on a column, allowing large-value data to be stored on the file system instead of in the database.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="c9b86-107">En esta sección</span><span class="sxs-lookup"><span data-stu-id="c9b86-107">In This Section</span></span>  
 [<span data-ttu-id="c9b86-108">Modificación de datos de valores grandes (max) en ADO.NET</span><span class="sxs-lookup"><span data-stu-id="c9b86-108">Modifying Large-Value (max) Data in ADO.NET</span></span>](../../../../../docs/framework/data/adonet/sql/modifying-large-value-max-data.md)  
 <span data-ttu-id="c9b86-109">Describe cómo trabajar con tipos de datos de valores grandes.</span><span class="sxs-lookup"><span data-stu-id="c9b86-109">Describes how to work with the large-value data types.</span></span>  
  
 [<span data-ttu-id="c9b86-110">Datos FILESTREAM</span><span class="sxs-lookup"><span data-stu-id="c9b86-110">FILESTREAM Data</span></span>](../../../../../docs/framework/data/adonet/sql/filestream-data.md)  
 <span data-ttu-id="c9b86-111">Describe cómo trabajar con datos de valores grandes almacenados en SQL Server 2008 con el atributo FILESTREAM.</span><span class="sxs-lookup"><span data-stu-id="c9b86-111">Describes how to work with large-value data stored in SQL Server 2008 with the FILESTREAM attribute.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c9b86-112">Vea también</span><span class="sxs-lookup"><span data-stu-id="c9b86-112">See Also</span></span>  
 [<span data-ttu-id="c9b86-113">Tipos de datos de SQL Server y ADO.NET</span><span class="sxs-lookup"><span data-stu-id="c9b86-113">SQL Server Data Types and ADO.NET</span></span>](../../../../../docs/framework/data/adonet/sql/sql-server-data-types.md)  
 [<span data-ttu-id="c9b86-114">Operaciones de datos de SQL Server en ADO.NET</span><span class="sxs-lookup"><span data-stu-id="c9b86-114">SQL Server Data Operations in ADO.NET</span></span>](../../../../../docs/framework/data/adonet/sql/sql-server-data-operations.md)  
 [<span data-ttu-id="c9b86-115">Recuperar y modificar datos en ADO.NET</span><span class="sxs-lookup"><span data-stu-id="c9b86-115">Retrieving and Modifying Data in ADO.NET</span></span>](../../../../../docs/framework/data/adonet/retrieving-and-modifying-data.md)  
 [<span data-ttu-id="c9b86-116">Proveedores administrados de ADO.NET y Centro para desarrolladores de DataSet</span><span class="sxs-lookup"><span data-stu-id="c9b86-116">ADO.NET Managed Providers and DataSet Developer Center</span></span>](https://go.microsoft.com/fwlink/?LinkId=217917)
