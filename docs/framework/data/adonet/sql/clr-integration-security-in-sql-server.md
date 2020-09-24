---
title: Seguridad de integración de CLR en SQL Server
ms.date: 03/30/2017
ms.assetid: 489fe096-fd1d-42de-8438-bf7aed46aea2
ms.openlocfilehash: e5d15b4e5ac36f7ecddf45179c65a60995a1a578
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/24/2020
ms.locfileid: "91147780"
---
# <a name="clr-integration-security-in-sql-server"></a>Seguridad de integración de CLR en SQL Server

Microsoft SQL Server proporciona la integración del componente Common Language Runtime (CLR) de .NET Framework. La integración de CLR permite escribir procedimientos almacenados, desencadenadores, tipos definidos por el usuario, funciones definidas por el usuario, agregados definidos por el usuario y funciones con valores de tabla de secuencias, mediante el uso de cualquier lenguaje de .NET Framework, como Microsoft Visual Basic .NET o Microsoft Visual C#.  
  
 El CLR admite un modelo de seguridad llamado seguridad de acceso del código (CAS) para el código administrado. En este modelo, se conceden permisos a los ensamblados en función de la evidencia que proporciona el código en los metadatos. SQL Server integra el modelo de seguridad basado en usuario de SQL Server con el modelo de seguridad basado en el acceso del código de CLR.  
  
## <a name="external-resources"></a>Recursos externos  

 Para obtener más información sobre la integración de CLR con SQL Server, vea los siguientes recursos.  
  
|Recurso|Descripción|  
|--------------|-----------------|  
|[Seguridad de acceso del código](../../../misc/code-access-security.md)|Contiene temas que describen CAS en .NET Framework.|  
|[Seguridad de la integración CLR](/sql/relational-databases/clr-integration/security/clr-integration-security)|Describe el modelo de seguridad para el código administrado que se ejecuta en SQL Server.|  
  
## <a name="see-also"></a>Vea también

- [Proteger aplicaciones de ADO.NET](../securing-ado-net-applications.md)
- [Escenarios de seguridad de aplicaciones en SQL Server](application-security-scenarios-in-sql-server.md)
- [Integración con Common Language Runtime de SQL Server](sql-server-common-language-runtime-integration.md)
- [Información general de ADO.NET](../ado-net-overview.md)
