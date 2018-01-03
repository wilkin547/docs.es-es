---
title: "Seguridad de integración de CLR en SQL Server"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 489fe096-fd1d-42de-8438-bf7aed46aea2
caps.latest.revision: "5"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.workload: dotnet
ms.openlocfilehash: aa211005f13fca2c55ff693a12b3e37629e39ad3
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="clr-integration-security-in-sql-server"></a>Seguridad de integración de CLR en SQL Server
Microsoft SQL Server proporciona la integración del componente Common Language Runtime (CLR) de .NET Framework. La integración de CLR permite escribir procedimientos almacenados, desencadenadores, tipos definidos por el usuario, funciones definidas por el usuario, agregados definidos por el usuario y funciones con valores de tabla de secuencias, mediante el uso de cualquier lenguaje de .NET Framework, como Microsoft Visual Basic .NET o Microsoft Visual C#.  
  
 El CLR admite un modelo de seguridad llamado seguridad de acceso del código (CAS) para el código administrado. En este modelo, se conceden permisos a los ensamblados en función de la evidencia que proporciona el código en los metadatos. SQL Server integra el modelo de seguridad basado en usuario de SQL Server con el modelo de seguridad basado en el acceso del código de CLR.  
  
## <a name="external-resources"></a>Recursos externos  
 Para obtener más información sobre la integración de CLR con SQL Server, vea los siguientes recursos.  
  
|Recurso|Descripción|  
|--------------|-----------------|  
|[Seguridad de acceso del código](http://msdn.microsoft.com/en-us/23a20143-241d-4fe5-9d9f-3933fd594c03)|Contiene temas que describen CAS en .NET Framework.|  
|[Seguridad de la integración de CLR](http://go.microsoft.com/fwlink/?LinkId=59998)|Describe el modelo de seguridad para el código administrado que se ejecuta en SQL Server.|  
  
## <a name="see-also"></a>Vea también  
 [Proteger aplicaciones de ADO.NET](../../../../../docs/framework/data/adonet/securing-ado-net-applications.md)  
 [Escenarios de seguridad de aplicaciones en SQL Server](../../../../../docs/framework/data/adonet/sql/application-security-scenarios-in-sql-server.md)  
 [Integración con Common Language Runtime de SQL Server](../../../../../docs/framework/data/adonet/sql/sql-server-common-language-runtime-integration.md)  
 [Proveedores administrados de ADO.NET y Centro para desarrolladores de DataSet](http://go.microsoft.com/fwlink/?LinkId=217917)
