---
title: N niveles de LINQ to SQL con ASP.NET
ms.date: 03/30/2017
ms.assetid: f6cc863a-d6a6-4281-ba8b-197c01cf6c6f
ms.openlocfilehash: b85392408d2fa62c481381c5028e228f280a1dc8
ms.sourcegitcommit: d2ccb199ae6bc5787b4762e9ea6d3f6fe88677af
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/12/2019
ms.locfileid: "56093657"
---
# <a name="linq-to-sql-n-tier-with-aspnet"></a>N niveles de LINQ to SQL con ASP.NET
En aplicaciones de [!INCLUDE[vstecasp](../../../../../../includes/vstecasp-md.md)] que usan [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)], se utiliza el control de servidor web <xref:System.Web.UI.WebControls.LinqDataSource> . El control administra la mayor parte de la lógica necesaria para consultar contra [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)], pasar los datos al explorador, recuperarlos y enviarlos a [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <xref:System.Data.Linq.DataContext> , que, a continuación, actualiza la base de datos. El control, que se configura simplemente en el marcado, administra toda la transferencia de datos entre [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] y el explorador. Puesto que el control administra las interacciones con el nivel de presentación, y [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] administra la comunicación con la capa de datos, el trabajo principal en aplicaciones multinivel de [!INCLUDE[vstecasp](../../../../../../includes/vstecasp-md.md)] se centra en escribir la lógica empresarial personalizada.  
  
 Para obtener más información acerca de `LINQDataSource`, consulte [información general sobre el Control de servidor Web LinqDataSource](https://docs.microsoft.com/previous-versions/aspnet/bb547113(v=vs.100)).  
  
## <a name="see-also"></a>Vea también
- [Aplicaciones de n niveles y remotas con LINQ to SQL](../../../../../../docs/framework/data/adonet/sql/linq/n-tier-and-remote-applications-with-linq-to-sql.md)
