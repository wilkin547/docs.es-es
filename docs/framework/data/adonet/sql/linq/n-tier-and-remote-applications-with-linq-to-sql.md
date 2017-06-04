---
title: "Aplicaciones remotas y de n niveles con LINQ to SQL | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 854a1cdd-53cb-45f5-83ca-63962a9b3598
caps.latest.revision: 5
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 5
---
# Aplicaciones remotas y de n niveles con LINQ to SQL
Puede crear aplicaciones multinivel o de n niveles que utilicen [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)].  Normalmente, el contexto de datos de [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)], las clases de entidad y la lógica de construcción de consultas se encuentran en el nivel intermedio como la capa de acceso a datos \(DAL\).  La lógica empresarial y los datos no persistentes se pueden implementar completamente en clases parciales y métodos de entidades y en el contexto de los datos, o se pueden implementar en clases independientes.  
  
 La capa de presentación o de cliente llama a los métodos en la interfaz remota de nivel intermedio, y la capa de acceso a datos \(DAL\) en ese nivel ejecutará consultas o procedimientos almacenados asignados a métodos <xref:System.Data.Linq.DataContext>.  El nivel intermedio devuelve los datos a los clientes generalmente como representaciones XML de entidades u objetos proxy.  
  
 En el nivel intermedio, las entidades son creadas por el contexto de los datos, el cual realiza el seguimiento de su estado, y administra la carga aplazada desde, y el envío de los cambios a, la base de datos.  Estas entidades están "asociadas" al `DataContext`.  Sin embargo, una vez que las entidades se han enviado a otro nivel a través de la serialización, quedan desasociadas, lo cual significa que el `DataContext` ya no realiza el seguimiento de su estado.  Las entidades que el cliente devuelve para las actualizaciones se deben volver a asociar al contexto de los datos antes de que [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] pueda enviar los cambios a la base de datos.  El cliente es responsable de devolver valores originales y\/o marcas de tiempo al nivel intermedio si se requieren para las comprobaciones de simultaneidad optimista.  
  
 En aplicaciones ASP.NET, <xref:System.Web.UI.WebControls.LinqDataSource> administra la mayor parte de esta complejidad.  Para obtener más información, consulte [NIB: LinqDataSource Web Server Control Overview](http://msdn.microsoft.com/es-es/104cfc3f-7385-47d3-8a51-830dfa791136).  
  
## Recursos adicionales  
 Para obtener más información sobre cómo implementar aplicaciones de n niveles que utilizan [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)], consulte los temas siguientes:  
  
-   [N niveles de LINQ to SQL con ASP.NET](../../../../../../docs/framework/data/adonet/sql/linq/linq-to-sql-n-tier-with-aspnet.md)  
  
-   [Niveles de LINQ to SQL con servicios Web](../../../../../../docs/framework/data/adonet/sql/linq/linq-to-sql-n-tier-with-web-services.md)  
  
-   [LINQ to SQL con aplicaciones cliente\-servidor que se corresponden estrictamente](../../../../../../docs/framework/data/adonet/sql/linq/linq-to-sql-with-tightly-coupled-client-server-applications.md)  
  
-   [Implementar lógica empresarial de n niveles](../../../../../../docs/framework/data/adonet/sql/linq/implementing-business-logic-linq-to-sql.md)  
  
-   [Recuperación de datos y operaciones CUD en aplicaciones de niveles N \(LINQ to SQL\)](../../../../../../docs/framework/data/adonet/sql/linq/data-retrieval-and-cud-operations-in-n-tier-applications.md)  
  
 Para obtener más información sobre aplicaciones de n niveles que utilizan conjuntos de datos de ADO.NET, vea [Trabajar con conjuntos de datos en aplicaciones de n capas](../Topic/Work%20with%20datasets%20in%20n-tier%20applications.md).  
  
## Vea también  
 [Información general](../../../../../../docs/framework/data/adonet/sql/linq/background-information.md)