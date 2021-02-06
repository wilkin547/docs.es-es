---
description: 'Más información acerca de: DbProviderFactories'
title: Objetos DbProviderFactory
ms.date: 03/30/2017
ms.assetid: 2a8e2640-3a49-42a1-a3a9-b43026907ae1
ms.openlocfilehash: 735c78a846fc8df31a922acf90e587c6d96f4995
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99651267"
---
# <a name="dbproviderfactories"></a><span data-ttu-id="b79b5-103">Objetos DbProviderFactory</span><span class="sxs-lookup"><span data-stu-id="b79b5-103">DbProviderFactories</span></span>

<span data-ttu-id="b79b5-104">El espacio de nombres <xref:System.Data.Common> proporciona clases para la creación de instancias <xref:System.Data.Common.DbProviderFactory> que permiten trabajar con orígenes de datos específicos.</span><span class="sxs-lookup"><span data-stu-id="b79b5-104">The <xref:System.Data.Common> namespace provides classes for creating <xref:System.Data.Common.DbProviderFactory> instances to work with specific data sources.</span></span> <span data-ttu-id="b79b5-105">Cuando crea una instancia <xref:System.Data.Common.DbProviderFactory> y le pasa información acerca del proveedor de datos, la instancia `DbProviderFactory` puede determinar el objeto fuertemente tipado correcto que debe devolver en función de la información que se ha proporcionado.</span><span class="sxs-lookup"><span data-stu-id="b79b5-105">When you create a <xref:System.Data.Common.DbProviderFactory> instance and pass it information about the data provider, the `DbProviderFactory` can determine the correct, strongly typed connection object to return based on the information it has been provided.</span></span>  
  
 <span data-ttu-id="b79b5-106">Comenzando con la versión 4 de .NET Framework , los proveedores de datos como <xref:System.Data.Odbc>, <xref:System.Data.OleDb>, <xref:System.Data.SqlClient> y <xref:System.Data.OracleClient> ya no aparecen en el archivo machine.config; sin embargo, sí aparecerán los proveedores personalizados.</span><span class="sxs-lookup"><span data-stu-id="b79b5-106">Beginning in the .NET Framework version 4, data providers such as <xref:System.Data.Odbc>, <xref:System.Data.OleDb>, <xref:System.Data.SqlClient>, and <xref:System.Data.OracleClient> are no longer listed in machine.config file, but custom providers will continue to be listed there.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="b79b5-107">En esta sección</span><span class="sxs-lookup"><span data-stu-id="b79b5-107">In This Section</span></span>  

 [<span data-ttu-id="b79b5-108">Información general sobre el modelo de fábrica</span><span class="sxs-lookup"><span data-stu-id="b79b5-108">Factory Model Overview</span></span>](factory-model-overview.md)  
 <span data-ttu-id="b79b5-109">Proporciona una introducción al patrón de diseño de generadores y a la interfaz de programación.</span><span class="sxs-lookup"><span data-stu-id="b79b5-109">Provides an overview of the factory design pattern and programming interface.</span></span>  
  
 [<span data-ttu-id="b79b5-110">Obtener un objeto DbProviderFactory</span><span class="sxs-lookup"><span data-stu-id="b79b5-110">Obtaining a DbProviderFactory</span></span>](obtaining-a-dbproviderfactory.md)  
 <span data-ttu-id="b79b5-111">Muestra cómo enumerar los proveedores de datos instalados y cómo crear una clase <xref:System.Data.Common.DbConnection> a partir de `DbProviderFactory`.</span><span class="sxs-lookup"><span data-stu-id="b79b5-111">Demonstrates how to list the installed data providers and create a <xref:System.Data.Common.DbConnection> from a `DbProviderFactory`.</span></span>  
  
 [<span data-ttu-id="b79b5-112">DbConnection, DbCommand y DbException</span><span class="sxs-lookup"><span data-stu-id="b79b5-112">DbConnection, DbCommand and DbException</span></span>](dbconnection-dbcommand-and-dbexception.md)  
 <span data-ttu-id="b79b5-113">Muestra cómo crear objetos <xref:System.Data.Common.DbCommand> y <xref:System.Data.Common.DbDataReader>, y cómo controlar los errores de datos con <xref:System.Data.Common.DbException>.</span><span class="sxs-lookup"><span data-stu-id="b79b5-113">Demonstrates how to create a <xref:System.Data.Common.DbCommand> and <xref:System.Data.Common.DbDataReader>, and how to handle data errors using <xref:System.Data.Common.DbException>.</span></span>  
  
 [<span data-ttu-id="b79b5-114">Modificar datos con un objeto DbDataAdapter</span><span class="sxs-lookup"><span data-stu-id="b79b5-114">Modifying Data with a DbDataAdapter</span></span>](modifying-data-with-a-dbdataadapter.md)  
 <span data-ttu-id="b79b5-115">Muestra cómo usar un objeto <xref:System.Data.Common.DbCommandBuilder> con <xref:System.Data.Common.DbDataAdapter> para recuperar y modificar datos.</span><span class="sxs-lookup"><span data-stu-id="b79b5-115">Demonstrates how to use a <xref:System.Data.Common.DbCommandBuilder> with a <xref:System.Data.Common.DbDataAdapter> to retrieve and modify data.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b79b5-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="b79b5-116">See also</span></span>

- [<span data-ttu-id="b79b5-117">Recuperar y modificar datos en ADO.NET</span><span class="sxs-lookup"><span data-stu-id="b79b5-117">Retrieving and Modifying Data in ADO.NET</span></span>](retrieving-and-modifying-data.md)
- [<span data-ttu-id="b79b5-118">Información general de ADO.NET</span><span class="sxs-lookup"><span data-stu-id="b79b5-118">ADO.NET Overview</span></span>](ado-net-overview.md)
