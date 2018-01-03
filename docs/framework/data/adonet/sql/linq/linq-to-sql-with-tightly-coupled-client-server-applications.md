---
title: LINQ to SQL con aplicaciones cliente/servidor estrechamente asociadas
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: e083d805-dcf6-459d-b9af-9ef0563f2dd7
caps.latest.revision: "2"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.workload: dotnet
ms.openlocfilehash: a2fa902cfbea3c6eb15e1832231bb3ed83de5497
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="linq-to-sql-with-tightly-coupled-client-server-applications"></a>LINQ to SQL con aplicaciones cliente/servidor estrechamente asociadas
[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]puede utilizarse en el nivel intermedio con clientes inteligentes estrechamente acoplados en la capa de presentación. En escenarios que implican acceso a datos de solo lectura, sin comprobaciones de simultaneidad optimista, o simultaneidad optimista con marcas de tiempo, no existe mucha más complejidad que con escenarios no remotos. Sin embargo, cuando una base de datos requiere comprobaciones de simultaneidad optimista con valores originales, [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] no proporciona el nivel de compatibilidad para los viajes de ida y vuelta de los datos que sí se encuentra en los conjuntos de datos (DataSets). No obstante, un nivel intermedio de [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] puede intercambiar datos con clientes en cualquier plataforma.  
  
 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]en [!INCLUDE[vs_orcas_long](../../../../../../includes/vs-orcas-long-md.md)] no proporciona una infraestructura para el seguimiento de estado de la entidad después de que se han serializado a un cliente. [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]habilita arquitecturas orientadas a servicios donde las interacciones entre las capas de datos y la presentación son pequeñas y relativamente detalladas, pero no realiza ninguna ida y vuelta de los valores originales. Por consiguiente, si desea utilizar un cliente inteligente estrechamente acoplado con [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)], y una base de datos utiliza simultaneidad optimista con valores originales, tendrá que implementar su propio mecanismo para comunicar los cambios entre el nivel de presentación y el nivel intermedio. Depende del diseñador del sistema decidir si tiene sentido hacer este pequeño trabajo adicional para obtener las ventajas que proporciona [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] en el nivel intermedio. Por otro lado, si la base de datos tiene marcas de tiempo, no es necesario utilizar lógica personalizada para el seguimiento de los cambios.  
  
## <a name="see-also"></a>Vea también  
 [Aplicaciones de n niveles y remotas con LINQ to SQL](../../../../../../docs/framework/data/adonet/sql/linq/n-tier-and-remote-applications-with-linq-to-sql.md)  
 [N niveles de LINQ to SQL con servicios web](../../../../../../docs/framework/data/adonet/sql/linq/linq-to-sql-n-tier-with-web-services.md)  
 [Trabajar con conjuntos de datos en aplicaciones de n capas](http://msdn.microsoft.com/library/f6ae2ee0-ea5f-4a79-8f4b-e21c115afb20)
