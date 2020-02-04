---
title: Enumerar instancias de SQL Server
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: ddf1c83c-9d40-45e6-b04d-9828c6cbbfdc
ms.openlocfilehash: c59db5869ed848071611cdbf985b45dc59790d69
ms.sourcegitcommit: 19014f9c081ca2ff19652ca12503828db8239d48
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "76979994"
---
# <a name="enumerating-instances-of-sql-server-adonet"></a><span data-ttu-id="9bd44-102">Enumerar instancias de SQL Server (ADO.NET)</span><span class="sxs-lookup"><span data-stu-id="9bd44-102">Enumerating Instances of SQL Server (ADO.NET)</span></span>
<span data-ttu-id="9bd44-103">SQL Server permite a las aplicaciones encontrar SQL Server instancias dentro de la red actual.</span><span class="sxs-lookup"><span data-stu-id="9bd44-103">SQL Server permits applications to find SQL Server instances within the current network.</span></span> <span data-ttu-id="9bd44-104">La clase <xref:System.Data.Sql.SqlDataSourceEnumerator> expone esta información para el programador de la aplicación, suministrando una <xref:System.Data.DataTable> que contiene información acerca de todos los servidores visibles.</span><span class="sxs-lookup"><span data-stu-id="9bd44-104">The <xref:System.Data.Sql.SqlDataSourceEnumerator> class exposes this information to the application developer, providing a <xref:System.Data.DataTable> containing information about all the visible servers.</span></span> <span data-ttu-id="9bd44-105">Esta tabla devuelta contiene una lista de instancias de servidor disponibles en la red que coincide con la lista proporcionada cuando un usuario intenta crear una nueva conexión y expande la lista desplegable que contiene todos los servidores disponibles en el cuadro de diálogo Propiedades de la **conexión** .</span><span class="sxs-lookup"><span data-stu-id="9bd44-105">This returned table contains a list of server instances available on the network that matches the list provided when a user attempts to create a new connection, and expands the drop-down list containing all the available servers on the **Connection Properties** dialog box.</span></span> <span data-ttu-id="9bd44-106">Los resultados mostrados no siempre están completos.</span><span class="sxs-lookup"><span data-stu-id="9bd44-106">The results displayed are not always complete.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="9bd44-107">Como sucede con la mayoría de servicios de Windows, es mejor ejecutar el servicio de explorador de SQL con los menos privilegios posibles.</span><span class="sxs-lookup"><span data-stu-id="9bd44-107">As with most Windows services, it is best to run the SQL Browser service with the least possible privileges.</span></span> <span data-ttu-id="9bd44-108">Para obtener más información acerca de este servicio y cómo administrar su comportamiento, vea los Libros en pantalla de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="9bd44-108">See SQL Server Books Online for more information on the SQL Browser service, and how to manage its behavior.</span></span>  
  
## <a name="retrieving-an-enumerator-instance"></a><span data-ttu-id="9bd44-109">Recuperación de una instancia de enumeración</span><span class="sxs-lookup"><span data-stu-id="9bd44-109">Retrieving an Enumerator Instance</span></span>  
 <span data-ttu-id="9bd44-110">Para recuperar la tabla que contiene información acerca de las instancias de SQL Server disponibles, primero debe recuperar un enumerador mediante la propiedad <xref:System.Data.Sql.SqlDataSourceEnumerator.Instance%2A> compartida o estática:</span><span class="sxs-lookup"><span data-stu-id="9bd44-110">In order to retrieve the table containing information about the available SQL Server instances, you must first retrieve an enumerator, using the shared/static <xref:System.Data.Sql.SqlDataSourceEnumerator.Instance%2A> property:</span></span>  
  
```vb  
Dim instance As System.Data.Sql.SqlDataSourceEnumerator = _  
   System.Data.Sql.SqlDataSourceEnumerator.Instance  
```  
  
```csharp  
System.Data.Sql.SqlDataSourceEnumerator instance =   
   System.Data.Sql.SqlDataSourceEnumerator.Instance  
```  
  
 <span data-ttu-id="9bd44-111">Una vez que haya recuperado la instancia estática, puede llamar al método <xref:System.Data.Sql.SqlDataSourceEnumerator.GetDataSources%2A>, que devuelve una <xref:System.Data.DataTable> que contiene información acerca de los servidores disponibles:</span><span class="sxs-lookup"><span data-stu-id="9bd44-111">Once you have retrieved the static instance, you can call the <xref:System.Data.Sql.SqlDataSourceEnumerator.GetDataSources%2A> method, which returns a <xref:System.Data.DataTable> containing information about the available servers:</span></span>  
  
```vb  
Dim dataTable As System.Data.DataTable = instance.GetDataSources()  
```  
  
```csharp  
System.Data.DataTable dataTable = instance.GetDataSources();  
```  
  
 <span data-ttu-id="9bd44-112">La tabla que devuelve la llamada al método contiene las siguientes columnas, cada una de las cuales incluye valores `string`:</span><span class="sxs-lookup"><span data-stu-id="9bd44-112">The table returned from the method call contains the following columns, all of which contain `string` values:</span></span>  
  
|<span data-ttu-id="9bd44-113">Columna</span><span class="sxs-lookup"><span data-stu-id="9bd44-113">Column</span></span>|<span data-ttu-id="9bd44-114">Descripción</span><span class="sxs-lookup"><span data-stu-id="9bd44-114">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="9bd44-115">**ServerName**</span><span class="sxs-lookup"><span data-stu-id="9bd44-115">**ServerName**</span></span>|<span data-ttu-id="9bd44-116">Nombre del servidor.</span><span class="sxs-lookup"><span data-stu-id="9bd44-116">Name of the server.</span></span>|  
|<span data-ttu-id="9bd44-117">**NombreDeInstancia**</span><span class="sxs-lookup"><span data-stu-id="9bd44-117">**InstanceName**</span></span>|<span data-ttu-id="9bd44-118">Nombre de la instancia del servidor.</span><span class="sxs-lookup"><span data-stu-id="9bd44-118">Name of the server instance.</span></span> <span data-ttu-id="9bd44-119">Si el servidor se ejecuta como instancia predeterminada, esta columna se muestra en blanco.</span><span class="sxs-lookup"><span data-stu-id="9bd44-119">Blank if the server is running as the default instance.</span></span>|  
|<span data-ttu-id="9bd44-120">**IsClustered**</span><span class="sxs-lookup"><span data-stu-id="9bd44-120">**IsClustered**</span></span>|<span data-ttu-id="9bd44-121">Indica si el servidor forma parte de un clúster.</span><span class="sxs-lookup"><span data-stu-id="9bd44-121">Indicates whether the server is part of a cluster.</span></span>|  
|<span data-ttu-id="9bd44-122">**Version**</span><span class="sxs-lookup"><span data-stu-id="9bd44-122">**Version**</span></span>|<span data-ttu-id="9bd44-123">Versión del servidor.</span><span class="sxs-lookup"><span data-stu-id="9bd44-123">Version of the server.</span></span> <span data-ttu-id="9bd44-124">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="9bd44-124">For example:</span></span><br /><br /> <span data-ttu-id="9bd44-125">-9,00. x (SQL Server 2005)</span><span class="sxs-lookup"><span data-stu-id="9bd44-125">-   9.00.x (SQL Server 2005)</span></span><br /><span data-ttu-id="9bd44-126">-10.0. XX (SQL Server 2008)</span><span class="sxs-lookup"><span data-stu-id="9bd44-126">-   10.0.xx (SQL Server 2008)</span></span><br /><span data-ttu-id="9bd44-127">-10,50. x (SQL Server 2008 R2)</span><span class="sxs-lookup"><span data-stu-id="9bd44-127">-   10.50.x (SQL Server 2008 R2)</span></span><br /><span data-ttu-id="9bd44-128">-11.0. XX (SQL Server 2012)</span><span class="sxs-lookup"><span data-stu-id="9bd44-128">-   11.0.xx (SQL Server 2012)</span></span>|  
  
## <a name="enumeration-limitations"></a><span data-ttu-id="9bd44-129">Limitaciones de la enumeración</span><span class="sxs-lookup"><span data-stu-id="9bd44-129">Enumeration Limitations</span></span>  
 <span data-ttu-id="9bd44-130">Es posible que en la lista no aparezcan todos los servidores disponibles.</span><span class="sxs-lookup"><span data-stu-id="9bd44-130">All of the available servers may or may not be listed.</span></span> <span data-ttu-id="9bd44-131">La lista puede variar dependiendo de algunos factores, como los tiempos de espera o el tráfico de la red.</span><span class="sxs-lookup"><span data-stu-id="9bd44-131">The list can vary depending on factors such as timeouts and network traffic.</span></span> <span data-ttu-id="9bd44-132">Como consecuencia, la lista puede ser diferente en dos llamadas consecutivas.</span><span class="sxs-lookup"><span data-stu-id="9bd44-132">This can cause the list to be different on two consecutive calls.</span></span> <span data-ttu-id="9bd44-133">Solo aparecerán en la lista los servidores de la misma red.</span><span class="sxs-lookup"><span data-stu-id="9bd44-133">Only servers on the same network will be listed.</span></span> <span data-ttu-id="9bd44-134">Normalmente, los paquetes de difusión no recorren los enrutadores; este es el motivo de que a lo mejor no pueda ver uno de los servidores que aparecen en la lista, aunque se mantenga estable entre llamadas.</span><span class="sxs-lookup"><span data-stu-id="9bd44-134">Broadcast packets typically won't traverse routers, which is why you may not see a server listed, but it will be stable across calls.</span></span>  
  
 <span data-ttu-id="9bd44-135">Los servidores de la lista pueden tener o no información adicional como `IsClustered` y la versión.</span><span class="sxs-lookup"><span data-stu-id="9bd44-135">Listed servers may or may not have additional information such as `IsClustered` and version.</span></span> <span data-ttu-id="9bd44-136">Todo depende de cómo se haya obtenido la lista.</span><span class="sxs-lookup"><span data-stu-id="9bd44-136">This is dependent on how the list was obtained.</span></span> <span data-ttu-id="9bd44-137">Los servidores que aparecen en la lista a través del servicio de explorador de SQL Server tendrán más detalles que los que se encuentran a través de la infraestructura de Windows, que solo muestra el nombre.</span><span class="sxs-lookup"><span data-stu-id="9bd44-137">Servers listed through the SQL Server browser service will have more details than those found through the Windows infrastructure, which will list only the name.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="9bd44-138">La enumeración de servidores solo se encuentra disponible cuando se ejecuta con plena confianza.</span><span class="sxs-lookup"><span data-stu-id="9bd44-138">Server enumeration is only available when running in full-trust.</span></span> <span data-ttu-id="9bd44-139">Los ensamblados que se ejecutan en un entorno de confianza parcial no podrán utilizarla, aunque dispongan del permiso de seguridad de acceso del código (CAS) <xref:System.Data.SqlClient.SqlClientPermission>.</span><span class="sxs-lookup"><span data-stu-id="9bd44-139">Assemblies running in a partially-trusted environment will not be able to use it, even if they have the <xref:System.Data.SqlClient.SqlClientPermission> Code Access Security (CAS) permission.</span></span>  
  
 <span data-ttu-id="9bd44-140">SQL Server proporciona información para la <xref:System.Data.Sql.SqlDataSourceEnumerator> mediante el uso de un servicio de Windows externo denominado SQL Browser.</span><span class="sxs-lookup"><span data-stu-id="9bd44-140">SQL Server provides information for the <xref:System.Data.Sql.SqlDataSourceEnumerator> through the use of an external Windows service named SQL Browser.</span></span> <span data-ttu-id="9bd44-141">Este servicio está habilitado de forma predeterminada, pero los administradores pueden desactivarlo o deshabilitarlo, para que la instancia del servidor sea invisible para esta clase.</span><span class="sxs-lookup"><span data-stu-id="9bd44-141">This service is enabled by default, but administrators may turn it off or disable it, making the server instance invisible to this class.</span></span>  
  
## <a name="example"></a><span data-ttu-id="9bd44-142">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="9bd44-142">Example</span></span>  
 <span data-ttu-id="9bd44-143">La siguiente aplicación de consola recupera información acerca de todas las instancias de SQL Server visibles y muestra esta información en la ventana de la consola.</span><span class="sxs-lookup"><span data-stu-id="9bd44-143">The following console application retrieves information about all of the visible SQL Server instances and displays the information in the console window.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="9bd44-144">Vea también</span><span class="sxs-lookup"><span data-stu-id="9bd44-144">See also</span></span>

- [<span data-ttu-id="9bd44-145">SQL Server y ADO.NET</span><span class="sxs-lookup"><span data-stu-id="9bd44-145">SQL Server and ADO.NET</span></span>](index.md)
- [<span data-ttu-id="9bd44-146">Información general sobre ADO.NET</span><span class="sxs-lookup"><span data-stu-id="9bd44-146">ADO.NET Overview</span></span>](../ado-net-overview.md)
