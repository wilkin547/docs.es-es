---
description: Más información acerca de cómo enumerar instancias de SQL Server (ADO.NET)
title: Enumerar instancias de SQL Server
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: ddf1c83c-9d40-45e6-b04d-9828c6cbbfdc
ms.openlocfilehash: dd52142a06d5c7203eb8a2a14d0e6fc48f1e2a27
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99672314"
---
# <a name="enumerating-instances-of-sql-server-adonet"></a><span data-ttu-id="ea872-103">Enumerar instancias de SQL Server (ADO.NET)</span><span class="sxs-lookup"><span data-stu-id="ea872-103">Enumerating Instances of SQL Server (ADO.NET)</span></span>

<span data-ttu-id="ea872-104">SQL Server permite que las aplicaciones busquen instancias de SQL Server en la red actual.</span><span class="sxs-lookup"><span data-stu-id="ea872-104">SQL Server permits applications to find SQL Server instances within the current network.</span></span> <span data-ttu-id="ea872-105">La clase <xref:System.Data.Sql.SqlDataSourceEnumerator> expone esta información al desarrollador de la aplicación y proporciona un <xref:System.Data.DataTable> que contiene información sobre todos los servidores visibles.</span><span class="sxs-lookup"><span data-stu-id="ea872-105">The <xref:System.Data.Sql.SqlDataSourceEnumerator> class exposes this information to the application developer, providing a <xref:System.Data.DataTable> containing information about all the visible servers.</span></span> <span data-ttu-id="ea872-106">Esta tabla devuelta contiene una lista de las instancias de servidor disponibles en la red que coincide con la lista proporcionada cuando un usuario intenta crear una nueva conexión y amplía la lista desplegable que contiene todos los servidores disponibles en el cuadro de diálogo **Propiedades de conexión**.</span><span class="sxs-lookup"><span data-stu-id="ea872-106">This returned table contains a list of server instances available on the network that matches the list provided when a user attempts to create a new connection, and expands the drop-down list containing all the available servers on the **Connection Properties** dialog box.</span></span> <span data-ttu-id="ea872-107">Los resultados mostrados no siempre están completos.</span><span class="sxs-lookup"><span data-stu-id="ea872-107">The results displayed are not always complete.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="ea872-108">Al igual que con la mayoría de los servicios de Windows, es mejor ejecutar el servicio SQL Browser con la cantidad mínima de privilegios posible.</span><span class="sxs-lookup"><span data-stu-id="ea872-108">As with most Windows services, it is best to run the SQL Browser service with the least possible privileges.</span></span> <span data-ttu-id="ea872-109">Para obtener más información sobre el servicio SQL Browser y cómo administrar su comportamiento, vea los Libros en pantalla de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="ea872-109">See SQL Server Books Online for more information on the SQL Browser service, and how to manage its behavior.</span></span>  
  
## <a name="retrieving-an-enumerator-instance"></a><span data-ttu-id="ea872-110">Recuperación de una instancia de enumeración</span><span class="sxs-lookup"><span data-stu-id="ea872-110">Retrieving an Enumerator Instance</span></span>  

 <span data-ttu-id="ea872-111">Para recuperar la tabla que contiene información sobre las instancias de SQL Server disponibles, primero debe recuperar un enumerador mediante la propiedad <xref:System.Data.Sql.SqlDataSourceEnumerator.Instance%2A> compartida o estática:</span><span class="sxs-lookup"><span data-stu-id="ea872-111">In order to retrieve the table containing information about the available SQL Server instances, you must first retrieve an enumerator, using the shared/static <xref:System.Data.Sql.SqlDataSourceEnumerator.Instance%2A> property:</span></span>  
  
```vb  
Dim instance As System.Data.Sql.SqlDataSourceEnumerator = _  
   System.Data.Sql.SqlDataSourceEnumerator.Instance  
```  
  
```csharp  
System.Data.Sql.SqlDataSourceEnumerator instance =
   System.Data.Sql.SqlDataSourceEnumerator.Instance  
```  
  
 <span data-ttu-id="ea872-112">Una vez que haya recuperado la instancia estática, puede llamar al método <xref:System.Data.Sql.SqlDataSourceEnumerator.GetDataSources%2A>, que devuelve un valor <xref:System.Data.DataTable> que contiene información sobre los servidores disponibles:</span><span class="sxs-lookup"><span data-stu-id="ea872-112">Once you have retrieved the static instance, you can call the <xref:System.Data.Sql.SqlDataSourceEnumerator.GetDataSources%2A> method, which returns a <xref:System.Data.DataTable> containing information about the available servers:</span></span>  
  
```vb  
Dim dataTable As System.Data.DataTable = instance.GetDataSources()  
```  
  
```csharp  
System.Data.DataTable dataTable = instance.GetDataSources();  
```  
  
 <span data-ttu-id="ea872-113">La tabla devuelta por la llamada al método contiene las columnas siguientes, todas las cuales contienen valores `string`:</span><span class="sxs-lookup"><span data-stu-id="ea872-113">The table returned from the method call contains the following columns, all of which contain `string` values:</span></span>  
  
|<span data-ttu-id="ea872-114">Columna</span><span class="sxs-lookup"><span data-stu-id="ea872-114">Column</span></span>|<span data-ttu-id="ea872-115">Descripción</span><span class="sxs-lookup"><span data-stu-id="ea872-115">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="ea872-116">**ServerName**</span><span class="sxs-lookup"><span data-stu-id="ea872-116">**ServerName**</span></span>|<span data-ttu-id="ea872-117">Nombre del servidor.</span><span class="sxs-lookup"><span data-stu-id="ea872-117">Name of the server.</span></span>|  
|<span data-ttu-id="ea872-118">**InstanceName**</span><span class="sxs-lookup"><span data-stu-id="ea872-118">**InstanceName**</span></span>|<span data-ttu-id="ea872-119">Nombre de instancia del servidor.</span><span class="sxs-lookup"><span data-stu-id="ea872-119">Name of the server instance.</span></span> <span data-ttu-id="ea872-120">En blanco si el servidor se ejecuta como la instancia predeterminada.</span><span class="sxs-lookup"><span data-stu-id="ea872-120">Blank if the server is running as the default instance.</span></span>|  
|<span data-ttu-id="ea872-121">**IsClustered**</span><span class="sxs-lookup"><span data-stu-id="ea872-121">**IsClustered**</span></span>|<span data-ttu-id="ea872-122">Indica si el servidor forma o no parte de un clúster.</span><span class="sxs-lookup"><span data-stu-id="ea872-122">Indicates whether the server is part of a cluster.</span></span>|  
|<span data-ttu-id="ea872-123">**Versión**</span><span class="sxs-lookup"><span data-stu-id="ea872-123">**Version**</span></span>|<span data-ttu-id="ea872-124">Versión del servidor.</span><span class="sxs-lookup"><span data-stu-id="ea872-124">Version of the server.</span></span> <span data-ttu-id="ea872-125">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="ea872-125">For example:</span></span><br /><br /> <span data-ttu-id="ea872-126">- 9.00.x (SQL Server 2005)</span><span class="sxs-lookup"><span data-stu-id="ea872-126">-   9.00.x (SQL Server 2005)</span></span><br /><span data-ttu-id="ea872-127">-   10.0.xx (SQL Server 2008)</span><span class="sxs-lookup"><span data-stu-id="ea872-127">-   10.0.xx (SQL Server 2008)</span></span><br /><span data-ttu-id="ea872-128">- 10.50.x (SQL Server 2008 R2)</span><span class="sxs-lookup"><span data-stu-id="ea872-128">-   10.50.x (SQL Server 2008 R2)</span></span><br /><span data-ttu-id="ea872-129">-   11.0.xx (SQL Server 2012)</span><span class="sxs-lookup"><span data-stu-id="ea872-129">-   11.0.xx (SQL Server 2012)</span></span>|  
  
## <a name="enumeration-limitations"></a><span data-ttu-id="ea872-130">Limitaciones de la enumeración</span><span class="sxs-lookup"><span data-stu-id="ea872-130">Enumeration Limitations</span></span>  

 <span data-ttu-id="ea872-131">Todos los servidores disponibles pueden o no aparecer en una lista.</span><span class="sxs-lookup"><span data-stu-id="ea872-131">All of the available servers may or may not be listed.</span></span> <span data-ttu-id="ea872-132">La lista puede variar en función de factores como los tiempos de espera y el tráfico de red.</span><span class="sxs-lookup"><span data-stu-id="ea872-132">The list can vary depending on factors such as timeouts and network traffic.</span></span> <span data-ttu-id="ea872-133">Esto puede hacer que la lista sea diferente en dos llamadas consecutivas.</span><span class="sxs-lookup"><span data-stu-id="ea872-133">This can cause the list to be different on two consecutive calls.</span></span> <span data-ttu-id="ea872-134">Solo se mostrarán los servidores de la misma red.</span><span class="sxs-lookup"><span data-stu-id="ea872-134">Only servers on the same network will be listed.</span></span> <span data-ttu-id="ea872-135">Los paquetes de difusión no suelen atravesar los enrutadores, por lo que es posible que no vea un servidor en la lista, aunque estará estable en todas las llamadas.</span><span class="sxs-lookup"><span data-stu-id="ea872-135">Broadcast packets typically won't traverse routers, which is why you may not see a server listed, but it will be stable across calls.</span></span>  
  
 <span data-ttu-id="ea872-136">Los servidores listados pueden tener o no información adicional, como `IsClustered` y versión.</span><span class="sxs-lookup"><span data-stu-id="ea872-136">Listed servers may or may not have additional information such as `IsClustered` and version.</span></span> <span data-ttu-id="ea872-137">Esto depende de la forma en que se obtuvo la lista.</span><span class="sxs-lookup"><span data-stu-id="ea872-137">This is dependent on how the list was obtained.</span></span> <span data-ttu-id="ea872-138">Los servidores que aparecen en la lista del servicio de explorador de SQL Server tienen más detalles que los que se encuentran a través de la infraestructura de Windows, que solo muestran el nombre.</span><span class="sxs-lookup"><span data-stu-id="ea872-138">Servers listed through the SQL Server browser service will have more details than those found through the Windows infrastructure, which will list only the name.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="ea872-139">La enumeración de servidores solo está disponible cuando se ejecuta en plena confianza.</span><span class="sxs-lookup"><span data-stu-id="ea872-139">Server enumeration is only available when running in full-trust.</span></span> <span data-ttu-id="ea872-140">Los ensamblados que se ejecutan en un entorno de confianza parcial no podrán usarla, aunque tengan el permiso de seguridad de acceso del código (CAS) de <xref:System.Data.SqlClient.SqlClientPermission>.</span><span class="sxs-lookup"><span data-stu-id="ea872-140">Assemblies running in a partially-trusted environment will not be able to use it, even if they have the <xref:System.Data.SqlClient.SqlClientPermission> Code Access Security (CAS) permission.</span></span>  
  
 <span data-ttu-id="ea872-141">SQL Server proporciona información para <xref:System.Data.Sql.SqlDataSourceEnumerator> mediante el uso de un servicio externo de Windows denominado SQL Browser.</span><span class="sxs-lookup"><span data-stu-id="ea872-141">SQL Server provides information for the <xref:System.Data.Sql.SqlDataSourceEnumerator> through the use of an external Windows service named SQL Browser.</span></span> <span data-ttu-id="ea872-142">Este servicio está habilitado de forma predeterminada, pero los administradores pueden desactivarlo o deshabilitarlo, lo que hace que la instancia del servidor sea invisible para esta clase.</span><span class="sxs-lookup"><span data-stu-id="ea872-142">This service is enabled by default, but administrators may turn it off or disable it, making the server instance invisible to this class.</span></span>  
  
## <a name="example"></a><span data-ttu-id="ea872-143">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="ea872-143">Example</span></span>  

 <span data-ttu-id="ea872-144">La siguiente aplicación de consola recupera información sobre todas las instancias visibles de SQL Server y muestra esa información en la ventana Consola.</span><span class="sxs-lookup"><span data-stu-id="ea872-144">The following console application retrieves information about all of the visible SQL Server instances and displays the information in the console window.</span></span>  
  
```vb  
Imports System.Data.Sql  
  
Module Module1  
  Sub Main()  
    ' Retrieve the enumerator instance and then the data.  
    Dim instance As SqlDataSourceEnumerator = _  
     SqlDataSourceEnumerator.Instance  
    Dim table As System.Data.DataTable = instance.GetDataSources()  
  
    ' Display the contents of the table.  
    DisplayData(table)  
  
    Console.WriteLine("Press any key to continue.")  
    Console.ReadKey()  
  End Sub  
  
  Private Sub DisplayData(ByVal table As DataTable)  
    For Each row As DataRow In table.Rows  
      For Each col As DataColumn In table.Columns  
        Console.WriteLine("{0} = {1}", col.ColumnName, row(col))  
      Next  
      Console.WriteLine("============================")  
    Next  
  End Sub  
End Module  
```  
  
```csharp  
using System.Data.Sql;  
  
class Program  
{  
  static void Main()  
  {  
    // Retrieve the enumerator instance and then the data.  
    SqlDataSourceEnumerator instance =  
      SqlDataSourceEnumerator.Instance;  
    System.Data.DataTable table = instance.GetDataSources();  
  
    // Display the contents of the table.  
    DisplayData(table);  
  
    Console.WriteLine("Press any key to continue.");  
    Console.ReadKey();  
  }  
  
  private static void DisplayData(System.Data.DataTable table)  
  {  
    foreach (System.Data.DataRow row in table.Rows)  
    {  
      foreach (System.Data.DataColumn col in table.Columns)  
      {  
        Console.WriteLine("{0} = {1}", col.ColumnName, row[col]);  
      }  
      Console.WriteLine("============================");  
    }  
  }  
}  
```  
  
## <a name="see-also"></a><span data-ttu-id="ea872-145">Vea también</span><span class="sxs-lookup"><span data-stu-id="ea872-145">See also</span></span>

- [<span data-ttu-id="ea872-146">SQL Server y ADO.NET</span><span class="sxs-lookup"><span data-stu-id="ea872-146">SQL Server and ADO.NET</span></span>](index.md)
- [<span data-ttu-id="ea872-147">Información general de ADO.NET</span><span class="sxs-lookup"><span data-stu-id="ea872-147">ADO.NET Overview</span></span>](../ado-net-overview.md)
