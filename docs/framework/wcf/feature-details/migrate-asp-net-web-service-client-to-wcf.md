---
title: 'Cómo: Migrar el código de cliente de servicio web ASP.NET a Windows Communication Foundation'
ms.date: 03/30/2017
ms.assetid: 2e0a22a7-e1d5-4718-8997-4319a7cd9027
ms.openlocfilehash: cb60f9cb2e8f35ee703b049eae9e3d99c1ec7d49
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33491135"
---
# <a name="how-to-migrate-aspnet-web-service-client-code-to-the-windows-communication-foundation"></a>Cómo: Migrar el código de cliente de servicio web ASP.NET a Windows Communication Foundation
El procedimiento siguiente describe los amplios pasos que deben seguirse para migrar el código de cliente de servicio Web ASP.NET a WCF.  
  
## <a name="procedure"></a>Procedimiento  
  
#### <a name="to-migrate-aspnet-web-service-client-code-to-wcf"></a>Para migrar un código de cliente de servicio web de ASP.NET a WCF  
  
1.  Asegúrese de que existe un conjunto completo de pruebas para el cliente.  
  
2.  Utilice Visual Studio 2005 para actualizar la aplicación cliente a .NET 2.0. Ejecute el conjunto de pruebas.  
  
3.  Elimine el código de cliente de ASP.NET del proyecto de cliente. Ese código está en módulos generados mediante la herramienta WSDL.exe.  
  
4.  Generar código de cliente WCF mediante el [la herramienta de utilidad de metadatos de ServiceModel (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md). Agregue ese código al proyecto de cliente y fusione mediante combinación el resultado de configuración con el archivo de configuración existente del cliente.  
  
5.  Compile la aplicación. Reparar los errores de compilación reemplazando las referencias a los tipos de cliente ASP.NET anteriores con referencias a los nuevos tipos de cliente WCF.  
  
6.  Ejecute el conjunto de pruebas.  
  
## <a name="see-also"></a>Vea también  
 [Migración del código del servicio web ASP.NET a Windows Communication Foundation](../../../../docs/framework/wcf/feature-details/migrate-asp-net-web-service-to-wcf.md)
