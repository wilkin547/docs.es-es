---
title: Architecture
description: 'Obtenga información sobre la arquitectura de ADO.NET, incluidos los dos componentes principales para tener acceso a los datos y manipularlos: el .NET Framework proveedores de datos y el conjunto de datos.'
ms.date: 03/30/2017
ms.assetid: fcd45b99-ae8f-45ab-8b97-d887beda734e
ms.openlocfilehash: 91e5b1e33ed1bc6e2acf6068a03bb8185324470d
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/02/2020
ms.locfileid: "84287186"
---
# <a name="adonet-architecture"></a>Arquitectura de ADO.NET
Tradicionalmente, el procesamiento de datos ha dependido principalmente de un modelo de dos niveles basado en una conexión. A medida que aumenta el uso que hace el procesamiento de datos de arquitecturas de varios niveles, los programadores están pasando a un enfoque sin conexión con el fin de proporcionar una mejor escalabilidad a sus aplicaciones.  
  
## <a name="adonet-components"></a>Componentes de ADO.NET  
 Los dos componentes principales de ADO.NET para tener acceso a los datos y manipularlos son los .NET Framework proveedores de datos y <xref:System.Data.DataSet> .  
  
### <a name="net-framework-data-providers"></a>Proveedores de datos .NET Framework  
 Los proveedores de datos .NET Framework son componentes diseñados explícitamente para la manipulación de datos y el acceso rápido a datos de solo lectura y solo avance. El objeto `Connection` proporciona conectividad a un origen de datos. El objeto `Command` permite tener acceso a comandos de base de datos para devolver datos, modificar datos, ejecutar procedimientos almacenados y enviar o recuperar información sobre parámetros. `DataReader` proporciona un flujo de datos de alto rendimiento desde el origen de datos. Por último, el objeto `DataAdapter` proporciona el puente entre el objeto `DataSet` y el origen de datos. `DataAdapter` utiliza objetos `Command` para ejecutar comandos SQL en el origen de datos tanto para cargar `DataSet` con datos y reconciliar en el origen de datos los cambios aplicados a los datos incluidos en el `DataSet`. Para obtener más información, vea [.NET Framework proveedores de datos](data-providers.md) y [recuperar y modificar datos en ADO.net](retrieving-and-modifying-data.md).  
  
### <a name="the-dataset"></a>DataSet  
 `DataSet` de ADO.NET está expresamente diseñado para el acceso a datos independientemente del origen de datos. Como resultado, se puede utilizar con múltiples y distintos orígenes de datos, con datos XML o para administrar datos locales de la aplicación. `DataSet` contiene una colección de uno o más objetos <xref:System.Data.DataTable> formados por filas y columnas de datos, así como información sobre claves principales, claves externas, restricciones y de relación relacionada con los datos incluidos en los objetos `DataTable`. Para obtener más información, vea conjuntos de datos [, tablas de datos y vistas](./dataset-datatable-dataview/index.md)de datos.  
  
 En el diagrama siguiente se ilustra la relación entre un proveedor de datos de .NET Framework y un `DataSet` .  
  
 ![Gráfico de ADO.NET](./media/ado-1-bpuedev11.png "ado_1_bpuedev11")  
Arquitectura de ADO.NET  
  
### <a name="choosing-a-datareader-or-a-dataset"></a>Elegir un DataReader o un DataSet  
 Cuando decida si la aplicación debe usar un `DataReader` (vea [recuperar datos mediante un DataReader](retrieving-data-using-a-datareader.md)) o un `DataSet` (vea conjuntos de datos [, DataTables y vistas](./dataset-datatable-dataview/index.md)de datos), tenga en cuenta el tipo de funcionalidad que requiere la aplicación. Use un `DataSet` para hacer lo siguiente:  
  
- Almacene datos en la memoria caché de la aplicación para poder manipularlos. Si solamente necesita leer los resultados de una consulta, el `DataReader` es la mejor elección.  
  
- Utilizar datos de forma remota entre un nivel y otro o desde un servicio Web XML.  
  
- Interactuar con datos dinámicamente, por ejemplo para enlazar con un control de Windows Forms o para combinar y relacionar datos procedentes de varios orígenes.  
  
- Realizar procesamientos exhaustivos de datos sin necesidad de tener una conexión abierta con el origen de datos, lo que libera la conexión para que la utilicen otros clientes.  
  
 Si no necesita la funcionalidad proporcionada por el `DataSet`, puede mejorar el rendimiento de su aplicación si utiliza el `DataReader` para devolver sus datos de solo avance y de solo lectura. Aunque `DataAdapter` usa `DataReader` para rellenar el contenido de un `DataSet` (vea [rellenar un conjunto de un DataSet desde un DataAdapter](populating-a-dataset-from-a-dataadapter.md)), mediante el uso de `DataReader` , puede mejorar el rendimiento porque ahorrará memoria que consumirá el `DataSet` , y evitará el procesamiento necesario para crear y rellenar el contenido de `DataSet` .  
  
## <a name="linq-to-dataset"></a>LINQ to DataSet  
 LINQ to DataSet proporciona capacidades de consulta y comprobación de tipo en tiempo de compilación de los datos almacenados en caché de un objeto DataSet. Permite escribir consultas en uno de los lenguajes de desarrollo de .NET Framework, como C# o Visual Basic. Para más información, vea [LINQ to DataSet](linq-to-dataset.md).  
  
## <a name="linq-to-sql"></a>LINQ a SQL  
 LINQ to SQL admite consultas en un modelo de objetos asignado a las estructuras de datos de una base de datos relacional sin utilizar un modelo conceptual intermedio. Cada tabla se representa mediante una clase distinta, acoplando de manera precisa el modelo de objetos al esquema de la base de datos relacional. LINQ to SQL convierte las consultas de Language-Integrated Query del modelo de objetos a Transact-SQL y las envía a la base de datos para su ejecución. Cuando la base de datos devuelve los resultados, LINQ to SQL los vuelve a traducir a objetos. Para más información, vea [LINQ to SQL](./sql/linq/index.md).  
  
## <a name="adonet-entity-framework"></a>ADO.NET Entity Framework  
 ADO.NET Entity Framework está diseñado para permitir que los desarrolladores creen aplicaciones de acceso a los datos programando en un modelo de aplicación conceptual en lugar de programar directamente en un esquema de almacenamiento relacional. El objetivo es reducir la cantidad de código y mantenimiento que se necesita para las aplicaciones orientadas a datos. Para obtener más información, consulte [ADO.NET Entity Framework](./ef/index.md).  
  
## <a name="wcf-data-services"></a>Servicios de datos de WCF  
 WCF Data Services se utiliza para implementar servicios de datos en Internet o en una intranet. Los datos se estructuran como entidades y relaciones de acuerdo a las especificaciones de Entity Data Model. Los datos implementados en este modelo se pueden direccionar mediante el protocolo HTTP estándar. Para obtener más información, vea [WCF Data Services 4.5](../wcf/index.md).  
  
## <a name="xml-and-adonet"></a>XML y ADO.NET  
 ADO.NET aprovecha la eficacia de XML para proporcionar acceso sin conexión a los datos. ADO.NET se diseñó a mano con las clases XML del .NET Framework; ambos son componentes de una única arquitectura.  
  
 ADO.NET y las clases XML del .NET Framework convergen en el `DataSet` objeto. `DataSet` se puede rellenar con datos procedentes de un origen XML, ya sea éste un archivo o una secuencia XML. `DataSet` se puede escribir como XML conforme al consorcio World Wide Web (W3C), que incluye su esquema como esquema lenguaje de definición de esquemas XML, independientemente del origen de los datos incluidos en `DataSet`. Puesto que el formato nativo de serialización del `DataSet` es XML, es un medio excelente para mover datos de un nivel a otro, por lo que `DataSet` es idóneo para usar datos y contextos de esquemas de interacción remota desde y hacia un servicio Web XML. Para obtener más información, vea [XML Documents and Data](../../../standard/data/xml/index.md) (Documentos y datos XML).  
  
## <a name="see-also"></a>Consulte también

- [Información general de ADO.NET](ado-net-overview.md)
