---
title: Objetos DbProviderFactory
ms.date: 03/30/2017
ms.assetid: 2a8e2640-3a49-42a1-a3a9-b43026907ae1
ms.openlocfilehash: e3ea9e3d083314f8df25f9edadbd1a18f1227293
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/07/2019
ms.locfileid: "70784101"
---
# <a name="dbproviderfactories"></a><span data-ttu-id="88fe7-102">Objetos DbProviderFactory</span><span class="sxs-lookup"><span data-stu-id="88fe7-102">DbProviderFactories</span></span>
<span data-ttu-id="88fe7-103">El espacio de nombres <xref:System.Data.Common> proporciona clases para la creación de instancias <xref:System.Data.Common.DbProviderFactory> que permiten trabajar con orígenes de datos específicos.</span><span class="sxs-lookup"><span data-stu-id="88fe7-103">The <xref:System.Data.Common> namespace provides classes for creating <xref:System.Data.Common.DbProviderFactory> instances to work with specific data sources.</span></span> <span data-ttu-id="88fe7-104">Cuando crea una instancia <xref:System.Data.Common.DbProviderFactory> y le pasa información acerca del proveedor de datos, la instancia `DbProviderFactory` puede determinar el objeto fuertemente tipado correcto que debe devolver en función de la información que se ha proporcionado.</span><span class="sxs-lookup"><span data-stu-id="88fe7-104">When you create a <xref:System.Data.Common.DbProviderFactory> instance and pass it information about the data provider, the `DbProviderFactory` can determine the correct, strongly typed connection object to return based on the information it has been provided.</span></span>  
  
 <span data-ttu-id="88fe7-105">Comenzando con la versión 4 de .NET Framework , los proveedores de datos como <xref:System.Data.Odbc>, <xref:System.Data.OleDb>, <xref:System.Data.SqlClient> y <xref:System.Data.OracleClient> ya no aparecen en el archivo machine.config; sin embargo, sí aparecerán los proveedores personalizados.</span><span class="sxs-lookup"><span data-stu-id="88fe7-105">Beginning in the .NET Framework version 4, data providers such as <xref:System.Data.Odbc>, <xref:System.Data.OleDb>, <xref:System.Data.SqlClient>, and <xref:System.Data.OracleClient> are no longer listed in machine.config file, but custom providers will continue to be listed there.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="88fe7-106">En esta sección</span><span class="sxs-lookup"><span data-stu-id="88fe7-106">In This Section</span></span>  
 [<span data-ttu-id="88fe7-107">Información general sobre el modelo de fábrica</span><span class="sxs-lookup"><span data-stu-id="88fe7-107">Factory Model Overview</span></span>](factory-model-overview.md)  
 <span data-ttu-id="88fe7-108">Proporciona una introducción al patrón de diseño de generadores y a la interfaz de programación.</span><span class="sxs-lookup"><span data-stu-id="88fe7-108">Provides an overview of the factory design pattern and programming interface.</span></span>  
  
 [<span data-ttu-id="88fe7-109">Obtención de un objeto DbProviderFactory</span><span class="sxs-lookup"><span data-stu-id="88fe7-109">Obtaining a DbProviderFactory</span></span>](obtaining-a-dbproviderfactory.md)  
 <span data-ttu-id="88fe7-110">Muestra cómo enumerar los proveedores de datos instalados y cómo crear una clase <xref:System.Data.Common.DbConnection> a partir de `DbProviderFactory`.</span><span class="sxs-lookup"><span data-stu-id="88fe7-110">Demonstrates how to list the installed data providers and create a <xref:System.Data.Common.DbConnection> from a `DbProviderFactory`.</span></span>  
  
 [<span data-ttu-id="88fe7-111">DbConnection, DbCommand y DbException</span><span class="sxs-lookup"><span data-stu-id="88fe7-111">DbConnection, DbCommand and DbException</span></span>](dbconnection-dbcommand-and-dbexception.md)  
 <span data-ttu-id="88fe7-112">Muestra cómo crear objetos <xref:System.Data.Common.DbCommand> y <xref:System.Data.Common.DbDataReader>, y cómo controlar los errores de datos con <xref:System.Data.Common.DbException>.</span><span class="sxs-lookup"><span data-stu-id="88fe7-112">Demonstrates how to create a <xref:System.Data.Common.DbCommand> and <xref:System.Data.Common.DbDataReader>, and how to handle data errors using <xref:System.Data.Common.DbException>.</span></span>  
  
 [<span data-ttu-id="88fe7-113">Modificación de datos con un objeto DbDataAdapter</span><span class="sxs-lookup"><span data-stu-id="88fe7-113">Modifying Data with a DbDataAdapter</span></span>](modifying-data-with-a-dbdataadapter.md)  
 <span data-ttu-id="88fe7-114">Muestra cómo usar un objeto <xref:System.Data.Common.DbCommandBuilder> con <xref:System.Data.Common.DbDataAdapter> para recuperar y modificar datos.</span><span class="sxs-lookup"><span data-stu-id="88fe7-114">Demonstrates how to use a <xref:System.Data.Common.DbCommandBuilder> with a <xref:System.Data.Common.DbDataAdapter> to retrieve and modify data.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="88fe7-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="88fe7-115">See also</span></span>

- [<span data-ttu-id="88fe7-116">Recuperar y modificar datos en ADO.NET</span><span class="sxs-lookup"><span data-stu-id="88fe7-116">Retrieving and Modifying Data in ADO.NET</span></span>](retrieving-and-modifying-data.md)
- [<span data-ttu-id="88fe7-117">Información general sobre ADO.NET</span><span class="sxs-lookup"><span data-stu-id="88fe7-117">ADO.NET Overview</span></span>](ado-net-overview.md)
