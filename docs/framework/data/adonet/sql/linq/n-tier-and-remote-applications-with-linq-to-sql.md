---
title: Aplicaciones de n niveles y remotas con LINQ to SQL
ms.date: 03/30/2017
ms.assetid: 854a1cdd-53cb-45f5-83ca-63962a9b3598
ms.openlocfilehash: 6fd31fd565d09b53cba74cd307f211d5bc0d68b7
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
---
# <a name="n-tier-and-remote-applications-with-linq-to-sql"></a>Aplicaciones de n niveles y remotas con LINQ to SQL
Puede crear aplicaciones multinivel o de n niveles que utilicen [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]. Normalmente, el [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] lógica de construcción de consulta, contexto de datos y las clases de entidad que se encuentran en el nivel intermedio como la capa de acceso a datos (DAL). La lógica empresarial y los datos no persistentes se pueden implementar completamente en clases parciales y métodos de entidades y en el contexto de los datos, o se pueden implementar en clases independientes.  
  
 La capa de presentación o de cliente llama a los métodos en la interfaz remota de nivel intermedio, y la capa de acceso a datos (DAL) en ese nivel ejecutará consultas o procedimientos almacenados asignados a métodos <xref:System.Data.Linq.DataContext>. El nivel intermedio devuelve los datos a los clientes generalmente como representaciones XML de entidades u objetos proxy.  
  
 En el nivel intermedio, las entidades son creadas por el contexto de los datos, el cual realiza el seguimiento de su estado, y administra la carga aplazada desde, y el envío de los cambios a, la base de datos. Estas entidades están "asociadas" al `DataContext`. Sin embargo, una vez que las entidades se han enviado a otro nivel a través de la serialización, quedan desasociadas, lo cual significa que el `DataContext` ya no realiza el seguimiento de su estado. Las entidades que el cliente devuelve para las actualizaciones se deben volver a asociar al contexto de los datos antes de que [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] pueda enviar los cambios a la base de datos. El cliente es responsable de devolver valores originales y/o marcas de tiempo al nivel intermedio si se requieren para las comprobaciones de simultaneidad optimista.  
  
 En aplicaciones ASP.NET, <xref:System.Web.UI.WebControls.LinqDataSource> administra la mayor parte de esta complejidad. Para obtener más información, consulte [NIB: información general sobre el Control de servidor Web LinqDataSource](http://msdn.microsoft.com/library/104cfc3f-7385-47d3-8a51-830dfa791136).  
  
## <a name="additional-resources"></a>Recursos adicionales  
 Para obtener más información sobre cómo implementar aplicaciones de n niveles que utilizan [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)], consulte los temas siguientes:  
  
-   [N niveles de LINQ to SQL con ASP.NET](../../../../../../docs/framework/data/adonet/sql/linq/linq-to-sql-n-tier-with-aspnet.md)  
  
-   [N niveles de LINQ to SQL con servicios web](../../../../../../docs/framework/data/adonet/sql/linq/linq-to-sql-n-tier-with-web-services.md)  
  
-   [LINQ to SQL con aplicaciones cliente/servidor estrechamente asociadas](../../../../../../docs/framework/data/adonet/sql/linq/linq-to-sql-with-tightly-coupled-client-server-applications.md)  
  
-   [Implementación de una lógica de negocios de n niveles](../../../../../../docs/framework/data/adonet/sql/linq/implementing-business-logic-linq-to-sql.md)  
  
-   [Recuperación de datos y operaciones CUD en aplicaciones de n niveles (LINQ to SQL)](../../../../../../docs/framework/data/adonet/sql/linq/data-retrieval-and-cud-operations-in-n-tier-applications.md)  
  
 Para obtener más información acerca de las aplicaciones de n niveles que utilizan conjuntos de datos ADO.NET, vea [trabajar con conjuntos de datos en aplicaciones de n niveles](http://msdn.microsoft.com/library/f6ae2ee0-ea5f-4a79-8f4b-e21c115afb20).  
  
## <a name="see-also"></a>Vea también  
 [Información general](../../../../../../docs/framework/data/adonet/sql/linq/background-information.md)
