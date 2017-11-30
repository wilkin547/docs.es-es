---
title: N niveles de LINQ to SQL con servicios Web
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 9cb10eb8-957f-4beb-a271-5f682016fed2
caps.latest.revision: "3"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: a8577c10dd4d3e2118a4b4dca8b22766a54fc854
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="linq-to-sql-n-tier-with-web-services"></a>N niveles de LINQ to SQL con servicios Web
[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]está diseñado especialmente para su uso en el nivel intermedio en una capa de acceso a datos de correspondencia imprecisa (DAL) como un servicio Web. Si el nivel de presentación es una página web ASP.NET, el control de servidor web <xref:System.Web.UI.WebControls.LinqDataSource> se utiliza para controlar la transferencia de datos entre la interfaz de usuario y [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] en el de nivel intermedio. Si el nivel de presentación no es una página ASP.NET, entonces el nivel intermedio y el nivel de presentación deben realizar un trabajo adicional para administrar la serialización y deserialización de datos.  
  
## <a name="setting-up-linq-to-sql-on-the-middle-tier"></a>Establecer LINQ to SQL en el nivel intermedio  
 En un servicio Web o aplicación de n niveles, el nivel intermedio contiene el contexto de los datos y las clases de entidad. Puede crear estas clases manualmente o mediante SQLMetal.exe o el [!INCLUDE[vs_ordesigner_long](../../../../../../includes/vs-ordesigner-long-md.md)], como se describe en otra parte de la documentación. En tiempo de diseño, tiene la opción de hacer las clases de entidad serializables. Para obtener más información, consulte [Cómo: hacer Serializable de entidades](../../../../../../docs/framework/data/adonet/sql/linq/how-to-make-entities-serializable.md). Otra opción consiste en crear un conjunto independiente de clases que encapsulan los datos que se van a serializar y, a continuación, proyectar en esos tipos serializables cuando se devuelvan datos en las consultas de [!INCLUDE[vbteclinq](../../../../../../includes/vbteclinq-md.md)].  
  
 A continuación, se define la interfaz con los métodos a los que los clientes llamarán para recuperar, insertar y actualizar datos. Los métodos de interfaz envuelven las consultas de [!INCLUDE[vbteclinq](../../../../../../includes/vbteclinq-md.md)]. Puede utilizar cualquier tipo de mecanismo de serialización para administrar las llamadas a métodos remotos y la serialización de datos. El único requisito es que, si tiene relaciones cíclicas o bidireccionales en su modelo de objetos, como las que existen entre Clientes y Pedidos en el modelo de objetos estándar de Northwind, deberá utilizar un serializador que admita esa situación. Windows Communication Foundation (WCF) <xref:System.Runtime.Serialization.DataContractSerializer> admite relaciones bidireccionales, pero no así el serializador XmlSerializer que se utiliza con servicios Web que no son de WCF. Si selecciona el serializador XmlSerializer, deberá asegurarse de que su modelo de objetos no contenga relaciones cíclicas.  
  
 Para obtener más información acerca de Windows Communication Foundation, consulte [servicios Windows Communication Foundation y servicios de datos de WCF en Visual Studio](/visualstudio/data-tools/windows-communication-foundation-services-and-wcf-data-services-in-visual-studio).  
  
 Implemente sus reglas de empresa u otra lógica específica del dominio utilizando las clases parciales y métodos de <xref:System.Data.Linq.DataContext> y las clases de entidad para conectar con eventos de tiempo de ejecución de  [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]. Para obtener más información, consulte [implementar lógica de negocios de N niveles](../../../../../../docs/framework/data/adonet/sql/linq/implementing-business-logic-linq-to-sql.md).  
  
## <a name="defining-the-serializable-types"></a>Definir los tipos serializables  
 El nivel de cliente o de presentación debe contar con las definiciones de tipo para las clases que recibirá desde el nivel intermedio. Esos tipos pueden ser clases de entidad propiamente dichas o clases especiales que envuelven sólo ciertos campos de las clases de entidad para la comunicación remota. En cualquier caso, [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] resulta completamente indiferente de cómo el nivel de presentación adquiere esas definiciones de tipo. Por ejemplo, el nivel de presentación podría utilizar WCF para generar los tipos automáticamente, o podría tener una copia de una DLL en la que se definen esos tipos, o simplemente podría definir sus propias versiones de los tipos.  
  
## <a name="retrieving-and-inserting-data"></a>Recuperar e insertar datos  
 El nivel intermedio define una interfaz que especifica cómo el nivel de presentación obtiene acceso a los datos. Por ejemplo: `GetProductByID(int productID)` o `GetCustomers()`. En el nivel intermedio, el cuerpo del método crea generalmente una nueva instancia de <xref:System.Data.Linq.DataContext> y ejecuta una consulta contra una o más de su tabla. A continuación, el nivel intermedio devuelve el resultado como un <xref:System.Collections.Generic.IEnumerable%601>, donde `T` es una clase de entidad u otro tipo que se utiliza para la serialización. El nivel de presentación nunca envía o recibe directamente variables de consulta a o desde el nivel intermedio. Los dos niveles intercambian valores, objetos y colecciones de datos concretos. Después de haber recibido una colección, el nivel de presentación puede utilizar [!INCLUDE[vbteclinq](../../../../../../includes/vbteclinq-md.md)] to Objects para consultarla si es necesario.  
  
 Al insertar datos, el nivel de presentación puede construir un nuevo objeto y enviarlo al nivel intermedio, o puede hacer que el nivel intermedio construya el objeto en función de los valores que proporciona. En general, la recuperación e inserción de datos en aplicaciones de n niveles no difiere mucho del proceso para aplicaciones de 2 niveles. Para obtener más información, consulte [consultar la base de datos](../../../../../../docs/framework/data/adonet/sql/linq/querying-the-database.md) y [decisiones y enviar los cambios de datos](../../../../../../docs/framework/data/adonet/sql/linq/making-and-submitting-data-changes.md).  
  
## <a name="tracking-changes-for-updates-and-deletes"></a>Seguimiento de cambios para actualizaciones y eliminaciones  
 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] admite simultaneidad optimista basada en marcas de tiempo (también denominadas RowVersions) y en valores originales. Si las tablas de base de datos tienen marcas de tiempo, entonces las actualizaciones y eliminaciones requieren poco trabajo adicional en el nivel intermedio o en el nivel de presentación. Sin embargo, si debe utilizar valores originales para las comprobaciones de simultaneidad optimista, entonces el nivel de presentación es el responsable de realizar el seguimiento de esos valores y devolverlos cuando realiza las actualizaciones. Esto es debido a que en el nivel intermedio no se hace un seguimiento de los cambios que se realizan en entidades en el nivel de presentación. De hecho, la recuperación original de una entidad y su posible actualización se realizan generalmente mediante dos instancias completamente independientes de <xref:System.Data.Linq.DataContext>.  
  
 Cuanto mayor es el número de cambios que realiza el nivel de presentación, más complejo se hace realizar el seguimiento de esos cambios y empaquetarlos de vuelta hacia el nivel intermedio. La implementación de un mecanismo para comunicar los cambios depende completamente de la aplicación. El único requisito es que se deben dar a [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] aquellos valores originales que se requieren para las comprobaciones de la simultaneidad optimista.  
  
 Para obtener más información, consulte [recuperación de datos y operaciones CUD en aplicaciones de N niveles (LINQ to SQL)](../../../../../../docs/framework/data/adonet/sql/linq/data-retrieval-and-cud-operations-in-n-tier-applications.md).  
  
## <a name="see-also"></a>Vea también  
 [N niveles y las aplicaciones remotas con LINQ to SQL](../../../../../../docs/framework/data/adonet/sql/linq/n-tier-and-remote-applications-with-linq-to-sql.md)  
 [NIB: Información general sobre el Control de servidor Web LinqDataSource](http://msdn.microsoft.com/en-us/104cfc3f-7385-47d3-8a51-830dfa791136)
