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
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: 5069c518998ca1d93f6e1ce94d76c8d0c7da07bd
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/19/2018
---
# <a name="linq-to-sql-n-tier-with-aspnet"></a>N niveles de LINQ to SQL con ASP.NET
En aplicaciones de [!INCLUDE[vstecasp](../../../../../../includes/vstecasp-md.md)] que usan [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)], se utiliza el control de servidor web <xref:System.Web.UI.WebControls.LinqDataSource> . El control administra la mayor parte de la lógica necesaria para consultar contra [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)], pasar los datos al explorador, recuperarlos y enviarlos a [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <xref:System.Data.Linq.DataContext> , que, a continuación, actualiza la base de datos. El control, que se configura simplemente en el marcado, administra toda la transferencia de datos entre [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] y el explorador. Puesto que el control administra las interacciones con el nivel de presentación, y [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] administra la comunicación con la capa de datos, el trabajo principal en aplicaciones multinivel de [!INCLUDE[vstecasp](../../../../../../includes/vstecasp-md.md)] se centra en escribir la lógica empresarial personalizada.  
  
 Para obtener más información acerca de `LINQDataSource`, consulte [NIB: información general sobre el Control de servidor Web LinqDataSource](http://msdn.microsoft.com/library/104cfc3f-7385-47d3-8a51-830dfa791136).  
  
## <a name="see-also"></a>Vea también  
 [Aplicaciones de n niveles y remotas con LINQ to SQL](../../../../../../docs/framework/data/adonet/sql/linq/n-tier-and-remote-applications-with-linq-to-sql.md)
