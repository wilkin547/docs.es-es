---
title: Arquitectura de ADO.NET
ms.date: 03/30/2017
ms.assetid: fcd45b99-ae8f-45ab-8b97-d887beda734e
ms.openlocfilehash: 384f2397e0e2794c4326d635db9f81fe1078f374
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/03/2018
---
# <a name="adonet-architecture"></a>Arquitectura de ADO.NET
Tradicionalmente, el procesamiento de datos ha dependido principalmente de un modelo de dos niveles basado en una conexión. A medida que aumenta el uso que hace el procesamiento de datos de arquitecturas de varios niveles, los programadores están pasando a un enfoque sin conexión con el fin de proporcionar una mejor escalabilidad a sus aplicaciones.  
  
## <a name="adonet-components"></a>Componentes de ADO.NET  
 Los dos componentes principales de [!INCLUDE[ado_orcas_long](../../../../includes/ado-orcas-long-md.md)] para el acceso a los datos y su manipulación son los proveedores de datos [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] y <xref:System.Data.DataSet>.  
  
### <a name="net-framework-data-providers"></a>Proveedores de datos .NET Framework  
 Los proveedores de datos .NET Framework son componentes diseñados explícitamente para la manipulación de datos y el acceso rápido a datos de solo lectura y solo avance. El objeto `Connection` proporciona conectividad a un origen de datos. El objeto `Command` permite tener acceso a comandos de base de datos para devolver datos, modificar datos, ejecutar procedimientos almacenados y enviar o recuperar información sobre parámetros. `DataReader` proporciona un flujo de datos de alto rendimiento desde el origen de datos. Por último, el objeto `DataAdapter` proporciona el puente entre el objeto `DataSet` y el origen de datos. `DataAdapter` utiliza objetos `Command` para ejecutar comandos SQL en el origen de datos tanto para cargar `DataSet` con datos y reconciliar en el origen de datos los cambios aplicados a los datos incluidos en el `DataSet`. Para obtener más información, consulte [proveedores de datos de .NET Framework](../../../../docs/framework/data/adonet/data-providers.md) y [recuperar y modificar datos en ADO.NET](../../../../docs/framework/data/adonet/retrieving-and-modifying-data.md).  
  
### <a name="the-dataset"></a>DataSet  
 `DataSet` de ADO.NET está expresamente diseñado para el acceso a datos independientemente del origen de datos. Como resultado, se puede utilizar con múltiples y distintos orígenes de datos, con datos XML o para administrar datos locales de la aplicación. `DataSet` contiene una colección de uno o más objetos <xref:System.Data.DataTable> formados por filas y columnas de datos, así como información sobre claves principales, claves externas, restricciones y de relación relacionada con los datos incluidos en los objetos `DataTable`. Para obtener más información, consulte [conjuntos de datos, DataTable y DataView](../../../../docs/framework/data/adonet/dataset-datatable-dataview/index.md).  
  
 En el diagrama siguiente se ilustra la relación entre un proveedor de datos [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] y un `DataSet`.  
  
 ![Gráfico de ADO.Net](../../../../docs/framework/data/adonet/media/ado-1-bpuedev11.png "ado_1_bpuedev11")  
Arquitectura de ADO.NET  
  
### <a name="choosing-a-datareader-or-a-dataset"></a>Elegir un DataReader o un DataSet  
 Cuando decida si su aplicación debe utilizar un `DataReader` (consulte [recuperar datos mediante DataReader](../../../../docs/framework/data/adonet/retrieving-data-using-a-datareader.md)) o un `DataSet` (consulte [conjuntos de datos, DataTable y DataView](../../../../docs/framework/data/adonet/dataset-datatable-dataview/index.md)), tenga en cuenta el tipo de funcionalidad que requiera la aplicación. Use un `DataSet` para hacer lo siguiente:  
  
-   Almacene datos en la memoria caché de la aplicación para poder manipularlos. Si solamente necesita leer los resultados de una consulta, el `DataReader` es la mejor elección.  
  
-   Utilizar datos de forma remota entre un nivel y otro o desde un servicio Web XML.  
  
-   Interactuar con datos dinámicamente, por ejemplo para enlazar con un control de Windows Forms o para combinar y relacionar datos procedentes de varios orígenes.  
  
-   Realizar procesamientos exhaustivos de datos sin necesidad de tener una conexión abierta con el origen de datos, lo que libera la conexión para que la utilicen otros clientes.  
  
 Si no necesita la funcionalidad proporcionada por el `DataSet`, puede mejorar el rendimiento de su aplicación si utiliza el `DataReader` para devolver sus datos de solo avance y de solo lectura. Aunque la `DataAdapter` utiliza la `DataReader` para rellenar el contenido de un `DataSet` (consulte [llenar un DataSet desde un DataAdapter](../../../../docs/framework/data/adonet/populating-a-dataset-from-a-dataadapter.md)), mediante el uso de la `DataReader`, puede mejorar el rendimiento porque usará la memoria que sea consumido por la `DataSet`y evitar el procesamiento necesario para crear y rellenar el contenido de la `DataSet`.  
  
## <a name="linq-to-dataset"></a>LINQ to DataSet  
 LINQ to DataSet proporciona capacidades de consulta y comprobación de tipo en tiempo de compilación de los datos almacenados en caché de un objeto DataSet. Permite escribir consultas en uno de los lenguajes de desarrollo de .NET Framework, como C# o Visual Basic. Para más información, vea [LINQ to DataSet](../../../../docs/framework/data/adonet/linq-to-dataset.md).  
  
## <a name="linq-to-sql"></a>LINQ to SQL  
 LINQ to SQL admite consultas en un modelo de objetos asignado a las estructuras de datos de una base de datos relacional sin utilizar un modelo conceptual intermedio. Cada tabla se representa mediante una clase distinta, acoplando de manera precisa el modelo de objetos al esquema de la base de datos relacional. LINQ to SQL convierte las consultas de Language-Integrated Query del modelo de objetos a Transact-SQL y las envía a la base de datos para su ejecución. Cuando la base de datos devuelve los resultados, LINQ to SQL los vuelve a traducir a objetos. Para más información, vea [LINQ to SQL](../../../../docs/framework/data/adonet/sql/linq/index.md).  
  
## <a name="adonet-entity-framework"></a>ADO.NET Entity Framework  
 ADO.NET Entity Framework está diseñado para permitir que los desarrolladores creen aplicaciones de acceso a los datos programando en un modelo de aplicación conceptual en lugar de programar directamente en un esquema de almacenamiento relacional. El objetivo es reducir la cantidad de código y mantenimiento que se necesita para las aplicaciones orientadas a datos. Para obtener más información, consulte [ADO.NET Entity Framework](../../../../docs/framework/data/adonet/ef/index.md).  
  
## <a name="wcf-data-services"></a>Servicios de datos de WCF  
 Describe cómo se usa [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] para implementar servicios de datos en web o en una intranet. Los datos se estructuran como entidades y relaciones de acuerdo a las especificaciones de Entity Data Model. Los datos implementados en este modelo se pueden direccionar mediante el protocolo HTTP estándar. Para obtener más información, consulte [4.5 de servicios de datos de WCF](../../../../docs/framework/data/wcf/index.md).  
  
## <a name="xml-and-adonet"></a>XML y ADO.NET  
 [!INCLUDE[vstecado](../../../../includes/vstecado-md.md)] aprovecha la eficacia de XML para proporcionar acceso a datos sin conexión. [!INCLUDE[vstecado](../../../../includes/vstecado-md.md)] fue diseñado teniendo en cuenta las clases de XML incluidas en [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)]; ambos son componentes de una única arquitectura.  
  
 [!INCLUDE[vstecado](../../../../includes/vstecado-md.md)] y las clases de XML incluidas en [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] convergen en el objeto `DataSet`. `DataSet` se puede rellenar con datos procedentes de un origen XML, ya sea éste un archivo o una secuencia XML. `DataSet` se puede escribir como XML conforme al consorcio World Wide Web (W3C), que incluye su esquema como esquema lenguaje de definición de esquemas XML, independientemente del origen de los datos incluidos en `DataSet`. Puesto que el formato nativo de serialización del `DataSet` es XML, es un medio excelente para mover datos de un nivel a otro, por lo que `DataSet` es idóneo para usar datos y contextos de esquemas de interacción remota desde y hacia un servicio Web XML. Para obtener más información, vea [XML Documents and Data](../../../../docs/standard/data/xml/index.md) (Documentos y datos XML).  
  
## <a name="see-also"></a>Vea también  
 [Información general sobre ADO.NET](../../../../docs/framework/data/adonet/ado-net-overview.md)  
 [Proveedores administrados de ADO.NET y Centro para desarrolladores de DataSet](http://go.microsoft.com/fwlink/?LinkId=217917)
