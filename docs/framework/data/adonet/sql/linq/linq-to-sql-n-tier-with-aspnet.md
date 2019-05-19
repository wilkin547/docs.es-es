---
title: N niveles de LINQ to SQL con ASP.NET
ms.date: 03/30/2017
ms.assetid: f6cc863a-d6a6-4281-ba8b-197c01cf6c6f
ms.openlocfilehash: 85ead36d1d927084c11dca1bd73a192b16e4ab7b
ms.sourcegitcommit: c4e9d05644c9cb89de5ce6002723de107ea2e2c4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/19/2019
ms.locfileid: "65880753"
---
# <a name="linq-to-sql-n-tier-with-aspnet"></a>N niveles de LINQ to SQL con ASP.NET
En las aplicaciones de ASP.NET que usan [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)], usa el <xref:System.Web.UI.WebControls.LinqDataSource> control de servidor Web. El control administra la mayor parte de la lógica necesaria para consultar contra [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)], pasar los datos al explorador, recuperarlos y enviarlos a [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <xref:System.Data.Linq.DataContext> , que, a continuación, actualiza la base de datos. El control, que se configura simplemente en el marcado, administra toda la transferencia de datos entre [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] y el explorador. Dado que el control administra las interacciones con el nivel de presentación y [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] controla la comunicación con la capa de datos, debe centrarse principalmente en aplicaciones de varios niveles de ASP.NET es sobre cómo escribir su lógica empresarial personalizada.  
  
 Para obtener más información acerca de `LINQDataSource`, consulte [información general sobre el Control de servidor Web LinqDataSource](https://docs.microsoft.com/previous-versions/aspnet/bb547113(v=vs.100)).  
  
## <a name="see-also"></a>Vea también

- [Aplicaciones de n niveles y remotas con LINQ to SQL](../../../../../../docs/framework/data/adonet/sql/linq/n-tier-and-remote-applications-with-linq-to-sql.md)
