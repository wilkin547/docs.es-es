---
title: Integración de AJAX y compatibilidad de JSON
ms.date: 03/30/2017
helpviewer_keywords:
- AJAX integration and JSON support [WCF]
ms.assetid: 3851a8fc-d861-4ac1-873c-96af0343d3a7
ms.openlocfilehash: f1748372af520955c139dffb2e6e80ae066c9397
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/15/2020
ms.locfileid: "90536072"
---
# <a name="ajax-integration-and-json-support"></a>Integración de AJAX y compatibilidad de JSON
La compatibilidad de Windows Communication Foundation (WCF) para JavaScript asincrónico y XML (AJAX) de ASP.NET y el formato de datos de notación de objetos JavaScript (JSON) permiten que los servicios WCF expongan las operaciones a los clientes AJAX. Los clientes AJAX son páginas web que ejecutan código JavaScript y obtienen acceso a estos servicios WCF mediante solicitudes HTTP. Los temas de esta sección proporcionan información sobre esta compatibilidad y sobre cómo implementarla.  
  
 Para obtener más información acerca de ASP.NET AJAX y su integración con ASP.NET 2,0, consulte [información general sobre la ASP.NET AJAX](/previous-versions/aspnet/bb398874(v=vs.100)).  
  
## <a name="in-this-section"></a>En esta sección  
 [Creación de servicios WCF para AJAX de ASP.NET](creating-wcf-services-for-aspnet-ajax.md)  
 Describe cómo se puede exponer un servicio WCF a los clientes AJAX agregando el punto de conexión de AJAX adecuado bien mediante configuración o mediante un generador de host de servicio personalizado para generar un host de servicio que configure el extremo de AJAX automáticamente.  
  
 [Creación de servicios AJAX WCF sin ASP.NET](creating-wcf-ajax-services-without-aspnet.md)  
 Describe cómo crear un servicio WCF sin usar ASP.NET.  
  
 [Compatibilidad con JSON y otros formatos de transferencia de datos](support-for-json-and-other-data-transfer-formats.md)  
 Describe la compatibilidad del formato de JSON utilizada normalmente (en lugar de XML) para la mensajería con servicios de AJAX de ASP.NET.  
  
 [Procedimiento para migrar servicios web de ASP.NET con AJAX habilitado a WCF](how-to-migrate-ajax-enabled-aspnet-web-services-to-wcf.md)  
 Describe cómo migrar un servicio Web ASP.NET con AJAX habilitado a un servicio Web WCF.  
  
## <a name="see-also"></a>Vea también

- <xref:System.ServiceModel.Activation.WebScriptServiceHostFactory>
- [Modelo de programación de web HTTP de WCF](wcf-web-http-programming-model.md)
