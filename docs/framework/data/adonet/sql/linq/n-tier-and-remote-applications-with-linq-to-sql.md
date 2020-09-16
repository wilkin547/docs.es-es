---
title: Aplicaciones de n niveles y remotas con LINQ to SQL
ms.date: 03/30/2017
ms.assetid: 854a1cdd-53cb-45f5-83ca-63962a9b3598
ms.openlocfilehash: 295be0157c260c05a2e4a7dbbfcd7e5cecbc85de
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/15/2020
ms.locfileid: "90548005"
---
# <a name="n-tier-and-remote-applications-with-linq-to-sql"></a>Aplicaciones de n niveles y remotas con LINQ to SQL
Puede crear aplicaciones multinivel o de n niveles que utilicen [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]. Normalmente, el [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] contexto de datos, las clases de entidad y la lógica de construcción de consultas se encuentran en el nivel intermedio como capa de acceso a datos (dal). La lógica empresarial y los datos no persistentes se pueden implementar completamente en clases parciales y métodos de entidades y en el contexto de los datos, o se pueden implementar en clases independientes.

 La capa de presentación o de cliente llama a los métodos en la interfaz remota de nivel intermedio, y la capa de acceso a datos (DAL) en ese nivel ejecutará consultas o procedimientos almacenados asignados a métodos <xref:System.Data.Linq.DataContext>. El nivel intermedio devuelve los datos a los clientes generalmente como representaciones XML de entidades u objetos proxy.

 En el nivel intermedio, las entidades son creadas por el contexto de los datos, el cual realiza el seguimiento de su estado, y administra la carga aplazada desde, y el envío de los cambios a, la base de datos. Estas entidades están "asociadas" al `DataContext`. Sin embargo, una vez que las entidades se han enviado a otro nivel a través de la serialización, quedan desasociadas, lo cual significa que el `DataContext` ya no realiza el seguimiento de su estado. Las entidades que el cliente devuelve para las actualizaciones se deben volver a asociar al contexto de los datos antes de que [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] pueda enviar los cambios a la base de datos. El cliente es responsable de devolver valores originales y/o marcas de tiempo al nivel intermedio si se requieren para las comprobaciones de simultaneidad optimista.

 En aplicaciones ASP.NET, <xref:System.Web.UI.WebControls.LinqDataSource> administra la mayor parte de esta complejidad. Para obtener más información, vea [información general sobre el control de servidor Web LinqDataSource](/previous-versions/aspnet/bb547113(v=vs.100)).

## <a name="additional-resources"></a>Recursos adicionales
 Para obtener más información sobre cómo implementar aplicaciones de n niveles que utilizan [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)], consulte los temas siguientes:

- [N niveles de LINQ to SQL con ASP.NET](linq-to-sql-n-tier-with-aspnet.md)

- [N niveles de LINQ to SQL con servicios Web](linq-to-sql-n-tier-with-web-services.md)

- [Implementación de una lógica de negocios de n niveles](implementing-business-logic-linq-to-sql.md)

- [Recuperación de datos y operaciones CUD en aplicaciones de n niveles (LINQ to SQL)](data-retrieval-and-cud-operations-in-n-tier-applications.md)

 Para obtener más información sobre las aplicaciones de n niveles que utilizan conjuntos de datos de ADO.NET, vea [trabajar con conjuntos de datos en aplicaciones de n niveles](/visualstudio/data-tools/work-with-datasets-in-n-tier-applications).

## <a name="see-also"></a>Vea también

- [Información general](background-information.md)
