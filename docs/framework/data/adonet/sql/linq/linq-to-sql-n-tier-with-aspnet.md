---
description: 'Más información acerca de: LINQ to SQL N niveles con ASP.NET'
title: N niveles de LINQ to SQL con ASP.NET
ms.date: 03/30/2017
ms.assetid: f6cc863a-d6a6-4281-ba8b-197c01cf6c6f
ms.openlocfilehash: a455525f8f0bbef38487b058d89fd2c9b4dda377
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99803807"
---
# <a name="linq-to-sql-n-tier-with-aspnet"></a>N niveles de LINQ to SQL con ASP.NET

En las aplicaciones de ASP.NET que usan [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] , se utiliza el <xref:System.Web.UI.WebControls.LinqDataSource> control de servidor Web. El control administra la mayor parte de la lógica que debe tener para realizar consultas [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] , pasar los datos al explorador, recuperarlos y enviarlos a la [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <xref:System.Data.Linq.DataContext> , que actualiza la base de datos. El control, que se configura simplemente en el marcado, administra toda la transferencia de datos entre [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] y el explorador. Dado que el control administra las interacciones con el nivel de presentación y [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] controla la comunicación con la capa de datos, el enfoque principal en las aplicaciones de varios niveles de ASP.net es escribir la lógica de negocios personalizada.  
  
 Para obtener más información sobre `LINQDataSource` , vea [información general sobre el control de servidor Web LinqDataSource](/previous-versions/aspnet/bb547113(v=vs.100)).  
  
## <a name="see-also"></a>Vea también

- [Aplicaciones de N niveles y remotas con LINQ to SQL](n-tier-and-remote-applications-with-linq-to-sql.md)
