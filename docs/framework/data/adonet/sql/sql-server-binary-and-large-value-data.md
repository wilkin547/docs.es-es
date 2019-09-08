---
title: Datos binarios y datos de valores grandes de SQL Server
ms.date: 03/30/2017
ms.assetid: e00827b3-7511-4b2d-91d7-851ca86cc6b5
ms.openlocfilehash: 4d941ad6b7865112b45fd8c20ad89e9236e17b9d
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/07/2019
ms.locfileid: "70791673"
---
# <a name="sql-server-binary-and-large-value-data"></a><span data-ttu-id="a3ccc-102">Datos binarios y datos de valores grandes de SQL Server</span><span class="sxs-lookup"><span data-stu-id="a3ccc-102">SQL Server Binary and Large-Value Data</span></span>
<span data-ttu-id="a3ccc-103">SQL Server proporciona el especificador `max`, que amplía la capacidad de almacenamiento de los tipos de datos `varchar`, `nvarchar` y `varbinary`.</span><span class="sxs-lookup"><span data-stu-id="a3ccc-103">SQL Server provides the `max` specifier, which expands the storage capacity of the `varchar`, `nvarchar`, and `varbinary` data types.</span></span> <span data-ttu-id="a3ccc-104">`varchar(max)`, `nvarchar(max)` y`varbinary(max)` se denominan colectivamente *tipos de datos de valores grandes*.</span><span class="sxs-lookup"><span data-stu-id="a3ccc-104">`varchar(max)`, `nvarchar(max)`, and `varbinary(max)` are collectively called *large-value data types*.</span></span> <span data-ttu-id="a3ccc-105">Puede utilizar los tipos de datos de valores grandes para almacenar hasta 2^31-1 bytes de datos.</span><span class="sxs-lookup"><span data-stu-id="a3ccc-105">You can use the large-value data types to store up to 2^31-1 bytes of data.</span></span>  
  
 <span data-ttu-id="a3ccc-106">SQL Server 2008 incorpora el atributo FILESTREAM, que no es un tipo de datos, sino un atributo que se puede definir en una columna, y permite almacenar datos de valores grandes en el sistema de archivos en lugar de almacenarlos en la base de datos.</span><span class="sxs-lookup"><span data-stu-id="a3ccc-106">SQL Server 2008 introduces the FILESTREAM attribute, which is not a data type, but rather an attribute that can be defined on a column, allowing large-value data to be stored on the file system instead of in the database.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="a3ccc-107">En esta sección</span><span class="sxs-lookup"><span data-stu-id="a3ccc-107">In This Section</span></span>  
 [<span data-ttu-id="a3ccc-108">Modificación de datos de valores grandes (max) en ADO.NET</span><span class="sxs-lookup"><span data-stu-id="a3ccc-108">Modifying Large-Value (max) Data in ADO.NET</span></span>](modifying-large-value-max-data.md)  
 <span data-ttu-id="a3ccc-109">Describe cómo trabajar con tipos de datos de valores grandes.</span><span class="sxs-lookup"><span data-stu-id="a3ccc-109">Describes how to work with the large-value data types.</span></span>  
  
 [<span data-ttu-id="a3ccc-110">Datos FILESTREAM</span><span class="sxs-lookup"><span data-stu-id="a3ccc-110">FILESTREAM Data</span></span>](filestream-data.md)  
 <span data-ttu-id="a3ccc-111">Describe cómo trabajar con datos de valores grandes almacenados en SQL Server 2008 con el atributo FILESTREAM.</span><span class="sxs-lookup"><span data-stu-id="a3ccc-111">Describes how to work with large-value data stored in SQL Server 2008 with the FILESTREAM attribute.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a3ccc-112">Vea también</span><span class="sxs-lookup"><span data-stu-id="a3ccc-112">See also</span></span>

- [<span data-ttu-id="a3ccc-113">Tipos de datos de SQL Server y ADO.NET</span><span class="sxs-lookup"><span data-stu-id="a3ccc-113">SQL Server Data Types and ADO.NET</span></span>](sql-server-data-types.md)
- [<span data-ttu-id="a3ccc-114">Operaciones de datos de SQL Server en ADO.NET</span><span class="sxs-lookup"><span data-stu-id="a3ccc-114">SQL Server Data Operations in ADO.NET</span></span>](sql-server-data-operations.md)
- [<span data-ttu-id="a3ccc-115">Recuperar y modificar datos en ADO.NET</span><span class="sxs-lookup"><span data-stu-id="a3ccc-115">Retrieving and Modifying Data in ADO.NET</span></span>](../retrieving-and-modifying-data.md)
- [<span data-ttu-id="a3ccc-116">Información general sobre ADO.NET</span><span class="sxs-lookup"><span data-stu-id="a3ccc-116">ADO.NET Overview</span></span>](../ado-net-overview.md)
