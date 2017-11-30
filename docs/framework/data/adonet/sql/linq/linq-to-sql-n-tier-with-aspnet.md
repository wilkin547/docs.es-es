---
title: N niveles de LINQ to SQL con ASP.NET
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: f6cc863a-d6a6-4281-ba8b-197c01cf6c6f
caps.latest.revision: "3"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: 643f38c495a57dd98c3524eaf82cdbdfe42220c2
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="linq-to-sql-n-tier-with-aspnet"></a>N niveles de LINQ to SQL con ASP.NET
En aplicaciones de [!INCLUDE[vstecasp](../../../../../../includes/vstecasp-md.md)] que usan [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)], se utiliza el control de servidor web <xref:System.Web.UI.WebControls.LinqDataSource> . El control administra la mayor parte de la lógica necesaria para consultar contra [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)], pasar los datos al explorador, recuperarlos y enviarlos a [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <xref:System.Data.Linq.DataContext> , que, a continuación, actualiza la base de datos. El control, que se configura simplemente en el marcado, administra toda la transferencia de datos entre [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] y el explorador. Puesto que el control administra las interacciones con el nivel de presentación, y [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] administra la comunicación con la capa de datos, el trabajo principal en aplicaciones multinivel de [!INCLUDE[vstecasp](../../../../../../includes/vstecasp-md.md)] se centra en escribir la lógica empresarial personalizada.  
  
 Para obtener más información sobre `LINQDataSource`, consulte [Información general sobre el control de servidor web LinqDataSource](http://msdn.microsoft.com/en-us/104cfc3f-7385-47d3-8a51-830dfa791136).  
  
## <a name="see-also"></a>Vea también  
 [N niveles y las aplicaciones remotas con LINQ to SQL](../../../../../../docs/framework/data/adonet/sql/linq/n-tier-and-remote-applications-with-linq-to-sql.md)
