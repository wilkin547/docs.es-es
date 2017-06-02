---
title: "Enumerar instancias de SQL Server (ADO.NET) | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: ddf1c83c-9d40-45e6-b04d-9828c6cbbfdc
caps.latest.revision: 8
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 7
---
# Enumerar instancias de SQL Server (ADO.NET)
[!INCLUDE[ssNoVersion](../../../../../includes/ssnoversion-md.md)] permite que las aplicaciones busquen instancias de [!INCLUDE[ssNoVersion](../../../../../includes/ssnoversion-md.md)] en la red actual.  La clase <xref:System.Data.Sql.SqlDataSourceEnumerator> expone esta información para el programador de la aplicación, suministrando una <xref:System.Data.DataTable> que contiene información acerca de todos los servidores visibles.  Esta tabla devuelta contiene una lista con las instancias de servidor disponibles en la red que coincide con la lista proporcionada cuando un usuario intenta crear una nueva conexión, y expande la lista desplegable que contiene todos los servidores disponibles en el cuadro de diálogo **Propiedades de conexión**.  Los resultados mostrados no siempre están completos.  
  
> [!NOTE]
>  Como sucede con la mayoría de servicios de Windows, es mejor ejecutar el servicio de explorador de SQL con los menos privilegios posibles.  Para obtener más información acerca del servicio SQL Browser y acerca de cómo administrar su comportamiento, vea los Libros en pantalla de [!INCLUDE[ssNoVersion](../../../../../includes/ssnoversion-md.md)].  
  
## Recuperación de una instancia de enumeración  
 Para recuperar la tabla que contiene información acerca de las instancias de [!INCLUDE[ssNoVersion](../../../../../includes/ssnoversion-md.md)] disponibles, primero debe recuperar un enumerador mediante la propiedad <xref:System.Data.Sql.SqlDataSourceEnumerator.Instance%2A> compartida o estática:  
  
```vb  
Dim instance As System.Data.Sql.SqlDataSourceEnumerator = _  
   System.Data.Sql.SqlDataSourceEnumerator.Instance  
```  
  
```csharp  
System.Data.Sql.SqlDataSourceEnumerator instance =   
   System.Data.Sql.SqlDataSourceEnumerator.Instance  
```  
  
 Una vez que haya recuperado la instancia estática, puede llamar al método <xref:System.Data.Sql.SqlDataSourceEnumerator.GetDataSources%2A>, que devuelve una <xref:System.Data.DataTable> que contiene información acerca de los servidores disponibles:  
  
```vb  
Dim dataTable As System.Data.DataTable = instance.GetDataSources()  
```  
  
```csharp  
System.Data.DataTable dataTable = instance.GetDataSources();  
```  
  
 La tabla que devuelve la llamada al método contiene las siguientes columnas, cada una de las cuales incluye valores `string`:  
  
|Columna|Descripción|  
|-------------|-----------------|  
|**ServerName**|Nombre del servidor.|  
|**InstanceName**|Nombre de la instancia del servidor.  Si el servidor se ejecuta como instancia predeterminada, esta columna se muestra en blanco.|  
|**IsClustered**|Indica si el servidor forma parte de un clúster.|  
|**Versión**|Versión del servidor.  Por ejemplo:<br /><br /> -   9,00.x \([!INCLUDE[ssVersion2005](../../../../../includes/ssversion2005-md.md)]\)<br />-   10.0.xx \([!INCLUDE[ssKatmai](../../../../../includes/sskatmai-md.md)]\)<br />-   10.50.x \([!INCLUDE[ssKilimanjaro](../../../../../includes/sskilimanjaro-md.md)]\)<br />-   11.0.xx \([!INCLUDE[ssNoVersion](../../../../../includes/ssnoversion-md.md)] 2012\)|  
  
## Limitaciones de la enumeración  
 Es posible que en la lista no aparezcan todos los servidores disponibles.  La lista puede variar dependiendo de algunos factores, como los tiempos de espera o el tráfico de la red.  Como consecuencia, la lista puede ser diferente en dos llamadas consecutivas.  Solo aparecerán en la lista los servidores de la misma red.  Normalmente, los paquetes de difusión no recorren los enrutadores; este es el motivo de que a lo mejor no pueda ver uno de los servidores que aparecen en la lista, aunque se mantenga estable entre llamadas.  
  
 Los servidores de la lista pueden tener o no información adicional como `IsClustered` y la versión.  Todo depende de cómo se haya obtenido la lista.  Los servidores que aparecen en la lista a través del servicio de explorador de [!INCLUDE[ssNoVersion](../../../../../includes/ssnoversion-md.md)] tendrán más detalles que los que se encuentran a través de la infraestructura de Windows, que solo muestra el nombre.  
  
> [!NOTE]
>  La enumeración de servidores solo se encuentra disponible cuando se ejecuta con plena confianza.  Los ensamblados que se ejecutan en un entorno de confianza parcial no podrán utilizarla, aunque dispongan del permiso de seguridad de acceso del código \(CAS\) <xref:System.Data.SqlClient.SqlClientPermission>.  
  
 [!INCLUDE[ssNoVersion](../../../../../includes/ssnoversion-md.md)] proporciona información para <xref:System.Data.Sql.SqlDataSourceEnumerator> mediante el uso de un servicio externo de Windows llamado SQL Browser.  Este servicio está habilitado de forma predeterminada, pero los administradores pueden desactivarlo o deshabilitarlo, para que la instancia del servidor sea invisible para esta clase.  
  
## Ejemplo  
 La siguiente aplicación de consola recupera información acerca de todas las instancias de [!INCLUDE[ssNoVersion](../../../../../includes/ssnoversion-md.md)] visibles y muestra esta información en la ventana de la consola.  
  
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
  
## Vea también  
 [SQL Server y ADO.NET](../../../../../docs/framework/data/adonet/sql/index.md)   
 [Proveedores administrados de ADO.NET y centro de desarrolladores de conjuntos de datos](http://go.microsoft.com/fwlink/?LinkId=217917)