---
title: Datos binarios y datos de valores grandes de SQL Server
ms.date: 03/30/2017
ms.assetid: e00827b3-7511-4b2d-91d7-851ca86cc6b5
ms.openlocfilehash: a9296e83b0f4e4352423470433670bb2cbe5a248
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/24/2020
ms.locfileid: "91183044"
---
# <a name="sql-server-binary-and-large-value-data"></a><span data-ttu-id="0b319-102">Datos binarios y datos de valores grandes de SQL Server</span><span class="sxs-lookup"><span data-stu-id="0b319-102">SQL Server Binary and Large-Value Data</span></span>

<span data-ttu-id="0b319-103">SQL Server proporciona el especificador `max`, que amplía la capacidad de almacenamiento de los tipos datos `varchar`, `nvarchar` y `varbinary`.</span><span class="sxs-lookup"><span data-stu-id="0b319-103">SQL Server provides the `max` specifier, which expands the storage capacity of the `varchar`, `nvarchar`, and `varbinary` data types.</span></span> <span data-ttu-id="0b319-104">`varchar(max)`, `nvarchar(max)` y `varbinary(max)` se denominan colectivamente *tipos de datos de valores grandes*.</span><span class="sxs-lookup"><span data-stu-id="0b319-104">`varchar(max)`, `nvarchar(max)`, and `varbinary(max)` are collectively called *large-value data types*.</span></span> <span data-ttu-id="0b319-105">Puede usar los tipos de datos de valores grandes para almacenar hasta 2^31-1 bytes de datos.</span><span class="sxs-lookup"><span data-stu-id="0b319-105">You can use the large-value data types to store up to 2^31-1 bytes of data.</span></span>  
  
 <span data-ttu-id="0b319-106">SQL Server 2008 presenta el atributo FILESTREAM, que no es un tipo de datos, sino un atributo que se puede definir en una columna, lo que permite almacenar datos de valores grandes en el sistema de archivos, en lugar de en la base de datos.</span><span class="sxs-lookup"><span data-stu-id="0b319-106">SQL Server 2008 introduces the FILESTREAM attribute, which is not a data type, but rather an attribute that can be defined on a column, allowing large-value data to be stored on the file system instead of in the database.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="0b319-107">En esta sección</span><span class="sxs-lookup"><span data-stu-id="0b319-107">In This Section</span></span>  

 [<span data-ttu-id="0b319-108">Modificación de datos de valores grandes (Max) en ADO.NET</span><span class="sxs-lookup"><span data-stu-id="0b319-108">Modifying Large-Value (max) Data in ADO.NET</span></span>](modifying-large-value-max-data.md)  
 <span data-ttu-id="0b319-109">Describe cómo trabajar con tipos de datos de valores grandes.</span><span class="sxs-lookup"><span data-stu-id="0b319-109">Describes how to work with the large-value data types.</span></span>  
  
 [<span data-ttu-id="0b319-110">Datos FILESTREAM</span><span class="sxs-lookup"><span data-stu-id="0b319-110">FILESTREAM Data</span></span>](filestream-data.md)  
 <span data-ttu-id="0b319-111">Describe cómo trabajar con datos de valores grandes almacenados en SQL Server 2008 con el atributo FILESTREAM.</span><span class="sxs-lookup"><span data-stu-id="0b319-111">Describes how to work with large-value data stored in SQL Server 2008 with the FILESTREAM attribute.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0b319-112">Consulte también</span><span class="sxs-lookup"><span data-stu-id="0b319-112">See also</span></span>

- [<span data-ttu-id="0b319-113">Tipos de datos de SQL Server y ADO.NET</span><span class="sxs-lookup"><span data-stu-id="0b319-113">SQL Server Data Types and ADO.NET</span></span>](sql-server-data-types.md)
- [<span data-ttu-id="0b319-114">SQL Server operaciones de datos en ADO.NET</span><span class="sxs-lookup"><span data-stu-id="0b319-114">SQL Server Data Operations in ADO.NET</span></span>](sql-server-data-operations.md)
- [<span data-ttu-id="0b319-115">Recuperar y modificar datos en ADO.NET</span><span class="sxs-lookup"><span data-stu-id="0b319-115">Retrieving and Modifying Data in ADO.NET</span></span>](../retrieving-and-modifying-data.md)
- [<span data-ttu-id="0b319-116">Información general de ADO.NET</span><span class="sxs-lookup"><span data-stu-id="0b319-116">ADO.NET Overview</span></span>](../ado-net-overview.md)
