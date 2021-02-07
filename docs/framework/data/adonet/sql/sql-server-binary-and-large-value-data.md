---
description: 'Más información acerca de: SQL Server datos binarios y de Large-Value'
title: Datos binarios y datos de valores grandes de SQL Server
ms.date: 03/30/2017
ms.assetid: e00827b3-7511-4b2d-91d7-851ca86cc6b5
ms.openlocfilehash: 8c7da5d504af0bc1beeea7e210a6fff4157fb090
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99767445"
---
# <a name="sql-server-binary-and-large-value-data"></a><span data-ttu-id="c5649-103">Datos binarios y datos de valores grandes de SQL Server</span><span class="sxs-lookup"><span data-stu-id="c5649-103">SQL Server Binary and Large-Value Data</span></span>

<span data-ttu-id="c5649-104">SQL Server proporciona el especificador `max`, que amplía la capacidad de almacenamiento de los tipos datos `varchar`, `nvarchar` y `varbinary`.</span><span class="sxs-lookup"><span data-stu-id="c5649-104">SQL Server provides the `max` specifier, which expands the storage capacity of the `varchar`, `nvarchar`, and `varbinary` data types.</span></span> <span data-ttu-id="c5649-105">`varchar(max)`, `nvarchar(max)` y `varbinary(max)` se denominan colectivamente *tipos de datos de valores grandes*.</span><span class="sxs-lookup"><span data-stu-id="c5649-105">`varchar(max)`, `nvarchar(max)`, and `varbinary(max)` are collectively called *large-value data types*.</span></span> <span data-ttu-id="c5649-106">Puede usar los tipos de datos de valores grandes para almacenar hasta 2^31-1 bytes de datos.</span><span class="sxs-lookup"><span data-stu-id="c5649-106">You can use the large-value data types to store up to 2^31-1 bytes of data.</span></span>  
  
 <span data-ttu-id="c5649-107">SQL Server 2008 presenta el atributo FILESTREAM, que no es un tipo de datos, sino un atributo que se puede definir en una columna, lo que permite almacenar datos de valores grandes en el sistema de archivos, en lugar de en la base de datos.</span><span class="sxs-lookup"><span data-stu-id="c5649-107">SQL Server 2008 introduces the FILESTREAM attribute, which is not a data type, but rather an attribute that can be defined on a column, allowing large-value data to be stored on the file system instead of in the database.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="c5649-108">En esta sección</span><span class="sxs-lookup"><span data-stu-id="c5649-108">In This Section</span></span>  

 [<span data-ttu-id="c5649-109">Modificación de datos de Large-Value (Max) en ADO.NET</span><span class="sxs-lookup"><span data-stu-id="c5649-109">Modifying Large-Value (max) Data in ADO.NET</span></span>](modifying-large-value-max-data.md)  
 <span data-ttu-id="c5649-110">Describe cómo trabajar con tipos de datos de valores grandes.</span><span class="sxs-lookup"><span data-stu-id="c5649-110">Describes how to work with the large-value data types.</span></span>  
  
 [<span data-ttu-id="c5649-111">Datos de FILESTREAM</span><span class="sxs-lookup"><span data-stu-id="c5649-111">FILESTREAM Data</span></span>](filestream-data.md)  
 <span data-ttu-id="c5649-112">Describe cómo trabajar con datos de valores grandes almacenados en SQL Server 2008 con el atributo FILESTREAM.</span><span class="sxs-lookup"><span data-stu-id="c5649-112">Describes how to work with large-value data stored in SQL Server 2008 with the FILESTREAM attribute.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c5649-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="c5649-113">See also</span></span>

- [<span data-ttu-id="c5649-114">Tipos de datos de SQL Server y ADO.NET</span><span class="sxs-lookup"><span data-stu-id="c5649-114">SQL Server Data Types and ADO.NET</span></span>](sql-server-data-types.md)
- [<span data-ttu-id="c5649-115">SQL Server operaciones de datos en ADO.NET</span><span class="sxs-lookup"><span data-stu-id="c5649-115">SQL Server Data Operations in ADO.NET</span></span>](sql-server-data-operations.md)
- [<span data-ttu-id="c5649-116">Recuperar y modificar datos en ADO.NET</span><span class="sxs-lookup"><span data-stu-id="c5649-116">Retrieving and Modifying Data in ADO.NET</span></span>](../retrieving-and-modifying-data.md)
- [<span data-ttu-id="c5649-117">Información general de ADO.NET</span><span class="sxs-lookup"><span data-stu-id="c5649-117">ADO.NET Overview</span></span>](../ado-net-overview.md)
