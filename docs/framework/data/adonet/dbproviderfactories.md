---
title: Objetos DbProviderFactory
ms.date: 03/30/2017
ms.assetid: 2a8e2640-3a49-42a1-a3a9-b43026907ae1
ms.openlocfilehash: 2376cf39228cb5e8208112333ba06bb80070de84
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59208821"
---
# <a name="dbproviderfactories"></a><span data-ttu-id="f9aab-102">Objetos DbProviderFactory</span><span class="sxs-lookup"><span data-stu-id="f9aab-102">DbProviderFactories</span></span>
<span data-ttu-id="f9aab-103">El espacio de nombres <xref:System.Data.Common> proporciona clases para la creación de instancias <xref:System.Data.Common.DbProviderFactory> que permiten trabajar con orígenes de datos específicos.</span><span class="sxs-lookup"><span data-stu-id="f9aab-103">The <xref:System.Data.Common> namespace provides classes for creating <xref:System.Data.Common.DbProviderFactory> instances to work with specific data sources.</span></span> <span data-ttu-id="f9aab-104">Cuando crea una instancia <xref:System.Data.Common.DbProviderFactory> y le pasa información acerca del proveedor de datos, la instancia `DbProviderFactory` puede determinar el objeto fuertemente tipado correcto que debe devolver en función de la información que se ha proporcionado.</span><span class="sxs-lookup"><span data-stu-id="f9aab-104">When you create a <xref:System.Data.Common.DbProviderFactory> instance and pass it information about the data provider, the `DbProviderFactory` can determine the correct, strongly typed connection object to return based on the information it has been provided.</span></span>  
  
 <span data-ttu-id="f9aab-105">Comenzando con la versión 4 de .NET Framework , los proveedores de datos como <xref:System.Data.Odbc>, <xref:System.Data.OleDb>, <xref:System.Data.SqlClient> y <xref:System.Data.OracleClient> ya no aparecen en el archivo machine.config; sin embargo, sí aparecerán los proveedores personalizados.</span><span class="sxs-lookup"><span data-stu-id="f9aab-105">Beginning in the .NET Framework version 4, data providers such as <xref:System.Data.Odbc>, <xref:System.Data.OleDb>, <xref:System.Data.SqlClient>, and <xref:System.Data.OracleClient> are no longer listed in machine.config file, but custom providers will continue to be listed there.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="f9aab-106">En esta sección</span><span class="sxs-lookup"><span data-stu-id="f9aab-106">In This Section</span></span>  
 [<span data-ttu-id="f9aab-107">Información general sobre el modelo de fábrica</span><span class="sxs-lookup"><span data-stu-id="f9aab-107">Factory Model Overview</span></span>](../../../../docs/framework/data/adonet/factory-model-overview.md)  
 <span data-ttu-id="f9aab-108">Proporciona una introducción al patrón de diseño de generadores y a la interfaz de programación.</span><span class="sxs-lookup"><span data-stu-id="f9aab-108">Provides an overview of the factory design pattern and programming interface.</span></span>  
  
 [<span data-ttu-id="f9aab-109">Obtención de un objeto DbProviderFactory</span><span class="sxs-lookup"><span data-stu-id="f9aab-109">Obtaining a DbProviderFactory</span></span>](../../../../docs/framework/data/adonet/obtaining-a-dbproviderfactory.md)  
 <span data-ttu-id="f9aab-110">Muestra cómo enumerar los proveedores de datos instalados y cómo crear una clase <xref:System.Data.Common.DbConnection> a partir de `DbProviderFactory`.</span><span class="sxs-lookup"><span data-stu-id="f9aab-110">Demonstrates how to list the installed data providers and create a <xref:System.Data.Common.DbConnection> from a `DbProviderFactory`.</span></span>  
  
 [<span data-ttu-id="f9aab-111">DbConnection, DbCommand y DbException</span><span class="sxs-lookup"><span data-stu-id="f9aab-111">DbConnection, DbCommand and DbException</span></span>](../../../../docs/framework/data/adonet/dbconnection-dbcommand-and-dbexception.md)  
 <span data-ttu-id="f9aab-112">Muestra cómo crear objetos <xref:System.Data.Common.DbCommand> y <xref:System.Data.Common.DbDataReader>, y cómo controlar los errores de datos con <xref:System.Data.Common.DbException>.</span><span class="sxs-lookup"><span data-stu-id="f9aab-112">Demonstrates how to create a <xref:System.Data.Common.DbCommand> and <xref:System.Data.Common.DbDataReader>, and how to handle data errors using <xref:System.Data.Common.DbException>.</span></span>  
  
 [<span data-ttu-id="f9aab-113">Modificación de datos con un objeto DbDataAdapter</span><span class="sxs-lookup"><span data-stu-id="f9aab-113">Modifying Data with a DbDataAdapter</span></span>](../../../../docs/framework/data/adonet/modifying-data-with-a-dbdataadapter.md)  
 <span data-ttu-id="f9aab-114">Muestra cómo usar un objeto <xref:System.Data.Common.DbCommandBuilder> con <xref:System.Data.Common.DbDataAdapter> para recuperar y modificar datos.</span><span class="sxs-lookup"><span data-stu-id="f9aab-114">Demonstrates how to use a <xref:System.Data.Common.DbCommandBuilder> with a <xref:System.Data.Common.DbDataAdapter> to retrieve and modify data.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f9aab-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="f9aab-115">See also</span></span>

- [<span data-ttu-id="f9aab-116">Recuperar y modificar datos en ADO.NET</span><span class="sxs-lookup"><span data-stu-id="f9aab-116">Retrieving and Modifying Data in ADO.NET</span></span>](../../../../docs/framework/data/adonet/retrieving-and-modifying-data.md)
- [<span data-ttu-id="f9aab-117">Proveedores administrados de ADO.NET y Centro para desarrolladores de DataSet</span><span class="sxs-lookup"><span data-stu-id="f9aab-117">ADO.NET Managed Providers and DataSet Developer Center</span></span>](https://go.microsoft.com/fwlink/?LinkId=217917)
