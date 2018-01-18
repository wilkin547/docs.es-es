---
title: "Información general sobre el modelo de fábrica"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: b5dc81c4-7554-44b9-b513-769bd61e2e7b
caps.latest.revision: "4"
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: 0194cd6789ae6ddebeeee65abf1a4fca4a2bc0d6
ms.sourcegitcommit: ed26cfef4e18f6d93ab822d8c29f902cff3519d1
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/17/2018
---
# <a name="factory-model-overview"></a><span data-ttu-id="f5613-102">Información general sobre el modelo de fábrica</span><span class="sxs-lookup"><span data-stu-id="f5613-102">Factory Model Overview</span></span>
<span data-ttu-id="f5613-103">ADO.NET 2.0 incorporó nuevas clases base en el espacio de nombres <xref:System.Data.Common>.</span><span class="sxs-lookup"><span data-stu-id="f5613-103">ADO.NET 2.0 introduced new base classes in the <xref:System.Data.Common> namespace.</span></span> <span data-ttu-id="f5613-104">No se pueden crear instancias directamente de las clases base debido a que son abstractas.</span><span class="sxs-lookup"><span data-stu-id="f5613-104">The base classes are abstract, which means that they can't be directly instantiated.</span></span> <span data-ttu-id="f5613-105">Entre ellas se incluyen <xref:System.Data.Common.DbConnection>, <xref:System.Data.Common.DbCommand> y <xref:System.Data.Common.DbDataAdapter>, y las utilizan los proveedores de datos .NET Framework como <xref:System.Data.SqlClient> y <xref:System.Data.OleDb>.</span><span class="sxs-lookup"><span data-stu-id="f5613-105">They include <xref:System.Data.Common.DbConnection>, <xref:System.Data.Common.DbCommand>, and <xref:System.Data.Common.DbDataAdapter> and are shared by the .NET Framework data providers, such as <xref:System.Data.SqlClient> and <xref:System.Data.OleDb>.</span></span> <span data-ttu-id="f5613-106">El aumento de clases base simplifica la agregación de funcionalidades a los proveedores de datos .NET Framework sin necesidad de crear nuevas interfaces.</span><span class="sxs-lookup"><span data-stu-id="f5613-106">The addition of base classes simplifies adding functionality to the .NET Framework data providers without having to create new interfaces.</span></span>  
  
 <span data-ttu-id="f5613-107">ADO.NET 2.0 incorporó también clases base abstractas, con permiten al desarrollador escribir código de acceso a datos genérico que no dependa de un proveedor de datos concreto.</span><span class="sxs-lookup"><span data-stu-id="f5613-107">ADO.NET 2.0 also introduced abstract base classes, which enable a developer to write generic data access code that does not depend on a specific data provider.</span></span>  
  
## <a name="the-factory-design-pattern"></a><span data-ttu-id="f5613-108">Patrón de diseño de generador</span><span class="sxs-lookup"><span data-stu-id="f5613-108">The Factory Design Pattern</span></span>  
 <span data-ttu-id="f5613-109">El modelo de programación para la escritura de código independiente del proveedor se basa en el uso del patrón de diseño de generador utiliza una única API para tener acceso a las bases de datos de varios proveedores.</span><span class="sxs-lookup"><span data-stu-id="f5613-109">The programming model for writing provider-independent code is based on the use of the "factory" design pattern, which uses a single API to access databases across multiple providers.</span></span> <span data-ttu-id="f5613-110">Este patrón tiene un nombre muy apropiado, dado que exige el uso de un objeto especializado solamente para crear otros objetos, de forma muy parecida a una fábrica del mundo real.</span><span class="sxs-lookup"><span data-stu-id="f5613-110">This pattern is aptly named, as it calls for the use of a specialized object solely to create other objects, much like a real-world factory.</span></span> <span data-ttu-id="f5613-111">Para obtener una descripción más detallada del patrón de diseño de generador, vea "[escribir código genérico de acceso de datos en ASP.NET 2.0 y ADO.NET 2.0](http://go.microsoft.com/fwlink/?LinkId=55915)" y "Genérico de codificación con el ADO.NET 2.0 Base Classes and Factories" [http:// MSDN.Microsoft.com/library/default.asp?URL=/library/dnvs05/html/vsgenerics.asp](http://msdn.microsoft.com/library/default.asp?url=/library/dnvs05/html/vsgenerics.asp) en MSDN.</span><span class="sxs-lookup"><span data-stu-id="f5613-111">For a more detailed description of the factory design pattern, see "[Writing Generic Data Access Code in ASP.NET 2.0 and ADO.NET 2.0](http://go.microsoft.com/fwlink/?LinkId=55915)" and "Generic Coding with the ADO.NET 2.0 Base Classes and Factories" [http://msdn.microsoft.com/library/default.asp?url=/library/dnvs05/html/vsgenerics.asp](http://msdn.microsoft.com/library/default.asp?url=/library/dnvs05/html/vsgenerics.asp) on MSDN.</span></span>  
  
 <span data-ttu-id="f5613-112">A partir de ADO.NET 2.0, la clase <xref:System.Data.Common.DbProviderFactories> proporciona métodos `static` (o `Shared` en Visual Basic) para crear una instancia de <xref:System.Data.Common.DbProviderFactory>.</span><span class="sxs-lookup"><span data-stu-id="f5613-112">Starting with ADO.NET 2.0, the <xref:System.Data.Common.DbProviderFactories> class provides `static` (or `Shared` in Visual Basic) methods for creating a <xref:System.Data.Common.DbProviderFactory> instance.</span></span> <span data-ttu-id="f5613-113">La instancia devuelve luego un objeto fuertemente tipado basado en la información sobre el proveedor y la cadena de conexión suministrada en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="f5613-113">The instance then returns a correct strongly typed object based on provider information and the connection string supplied at run time.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f5613-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="f5613-114">See Also</span></span>  
 [<span data-ttu-id="f5613-115">Obtención de un objeto DbProviderFactory</span><span class="sxs-lookup"><span data-stu-id="f5613-115">Obtaining a DbProviderFactory</span></span>](../../../../docs/framework/data/adonet/obtaining-a-dbproviderfactory.md)  
 [<span data-ttu-id="f5613-116">DbConnection, DbCommand y DbException</span><span class="sxs-lookup"><span data-stu-id="f5613-116">DbConnection, DbCommand and DbException</span></span>](../../../../docs/framework/data/adonet/dbconnection-dbcommand-and-dbexception.md)  
 [<span data-ttu-id="f5613-117">Modificación de datos con un objeto DbDataAdapter</span><span class="sxs-lookup"><span data-stu-id="f5613-117">Modifying Data with a DbDataAdapter</span></span>](../../../../docs/framework/data/adonet/modifying-data-with-a-dbdataadapter.md)  
 [<span data-ttu-id="f5613-118">Proveedores administrados de ADO.NET y Centro para desarrolladores de DataSet</span><span class="sxs-lookup"><span data-stu-id="f5613-118">ADO.NET Managed Providers and DataSet Developer Center</span></span>](http://go.microsoft.com/fwlink/?LinkId=217917)
