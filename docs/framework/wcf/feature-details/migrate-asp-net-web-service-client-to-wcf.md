---
title: "Cómo: Migrar el código de cliente de servicio web ASP.NET a Windows Communication Foundation"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 2e0a22a7-e1d5-4718-8997-4319a7cd9027
caps.latest.revision: "6"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: b93460fd6d331b43b49f10cf78fc8863ca1d8d88
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/02/2017
---
# <a name="how-to-migrate-aspnet-web-service-client-code-to-the-windows-communication-foundation"></a>Cómo: Migrar el código de cliente de servicio web ASP.NET a Windows Communication Foundation
El procedimiento siguiente describe los amplios pasos que se han de seguir para migrar el código de cliente del servicio web de ASP.NET a [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].  
  
## <a name="procedure"></a>Procedimiento  
  
#### <a name="to-migrate-aspnet-web-service-client-code-to-wcf"></a>Para migrar un código de cliente de servicio web de ASP.NET a WCF  
  
1.  Asegúrese de que existe un conjunto completo de pruebas para el cliente.  
  
2.  Utilice Visual Studio 2005 para actualizar la aplicación cliente a .NET 2.0. Ejecute el conjunto de pruebas.  
  
3.  Elimine el código de cliente de ASP.NET del proyecto de cliente. Ese código está en módulos generados mediante la herramienta WSDL.exe.  
  
4.  Generar [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] código de cliente mediante la [la herramienta de utilidad de metadatos de ServiceModel (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md). Agregue ese código al proyecto de cliente y fusione mediante combinación el resultado de configuración con el archivo de configuración existente del cliente.  
  
5.  Compile la aplicación. Repare los errores de compilación reemplazando las referencias a los tipos de cliente de ASP.NET anteriores por referencias a los nuevos tipos de cliente de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].  
  
6.  Ejecute el conjunto de pruebas.  
  
## <a name="see-also"></a>Vea también  
 [Cómo: migrar código del servicio Web de ASP.NET a Windows Communication Foundation](../../../../docs/framework/wcf/feature-details/migrate-asp-net-web-service-to-wcf.md)
