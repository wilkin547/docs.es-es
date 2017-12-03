---
title: "Adoptación de Windows Communication Foundation"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 49ba71e2-9468-4082-84c5-cf8daf95e34a
caps.latest.revision: "12"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: e27ee5f2e1b2ad042fd8c0104e89b99eb5e4bc96
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/02/2017
---
# <a name="adopting-windows-communication-foundation"></a>Adoptación de Windows Communication Foundation
Puede decidir utilizar [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] para desarrollar nuevas aplicaciones, al mismo tiempo que sigue manteniendo las aplicaciones existentes desarrolladas mediante ASP.NET. Dado que [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] está diseñado para ser la opción más conveniente para facilitar la comunicación con aplicaciones creadas en .NET Framework en cualquier escenario, puede actuar como una herramienta estándar para resolver una gran variedad de problemas de comunicaciones de software en cualquier modo que ASP.NET no puede.  
  
 Las nuevas aplicaciones de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] se pueden implementar en los mismos equipos que los servicios web ASP.NET existentes. Si los servicios web ASP.NET existentes utilizan una versión de .NET Framework anterior a la versión 2.0, puede utilizar la herramienta de registro de ASP.NET IIS para implementar de manera selectiva aplicaciones .NET Framework 2.0 a las aplicaciones IIS en las que nuevas aplicaciones de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] se hospedarán. Dicha herramienta se documenta en [herramienta de registro de IIS de ASP.NET (Aspnet_regiis.exe)](http://go.microsoft.com/fwlink/?LinkId=94687), y ha creado una interfaz de usuario en la consola de administración de IIS 6.0.  
  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] se puede utilizar para agregar nuevas características a los servicios web ASP.NET existentes agregando los servicios de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] configurados para ejecutarse en modo de compatibilidad de ASP.NET para las aplicaciones de servicio web ASP.NET existentes en IIS. Debido al modo de compatibilidad de ASP.NET, el código para los nuevos servicios de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] puede obtener acceso y actualizar la misma información de estado de la aplicación que el código de ASP.NET preexistente, mediante la clase <xref:System.Web.HttpContext>. Las aplicaciones también pueden compartir las mismas bibliotecas de clases.  
  
 Los clientes de[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] pueden usar servicios web ASP.NET. Los clientes de servicio web ASP.NET pueden usar los servicios de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] configurados con <xref:System.ServiceModel.BasicHttpBinding>. Los servicios web ASP.NET pueden coexistir con aplicaciones de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] e [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] se puede utilizar incluso para agregar características a los servicios web ASP.NET existentes. Dadas todas estas maneras en las que se pueden utilizar los servicios de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] y los servicios web ASP.NET conjuntamente, puede querer migrar servicios web ASP.NET a [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] si requiere características que proporciona [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] y no los servicios web ASP.NET.  
  
 Incluso en los pocos casos donde es necesario, considere cuidadosamente que migrar código de una tecnología a otra pocas veces es el enfoque correcto. El motivo para adoptar la nueva tecnología es el de cumplir nuevos requisitos que no se pueden cumplir con la tecnología anterior y, en ese caso, lo correcto sería diseñar una nueva solución que cumpla el nuevo y ampliado conjunto de requisitos. El nuevo diseño se beneficia de su experiencia con el sistema existente y de la sabiduría adquirida desde que se diseñó el sistema. El nuevo diseño también puede utilizar las funciones completas de las nuevas tecnologías en lugar de reproducir el diseño anterior en la nueva plataforma. Después de crear prototipos de elementos clave del nuevo diseño, se hace más fácil reutilizar código del sistema existente dentro del nuevo.  
  
 Para los pocos casos en los que migrar desde los servicios web ASP.NET a [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] es la solución correcta, la siguiente sección proporciona alguna orientación sobre cómo realizarlo. Hay consejos sobre cómo migrar servicios y cómo migrar clientes.  
  
 Para obtener un análisis completo sobre cómo migrar los servicios Web ASP.NET existentes a WCF vea [servicios Web ASP.NET y Windows Communication Foundation](http://go.microsoft.com/fwlink/?LinkID=71761). En esta sección se describe cómo implementar un servicio WCF conforme a partir de los metadatos para su servicio web ASP.NET y cómo migrar servicio web ASP.NET y código de cliente a [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].  
  
## <a name="see-also"></a>Vea también  
 [Cómo: recuperar metadatos e implementar un servicio conforme](../../../../docs/framework/wcf/feature-details/how-to-retrieve-metadata-and-implement-a-compliant-service.md)  
 [Cómo: migrar código del servicio Web de ASP.NET a Windows Communication Foundation](../../../../docs/framework/wcf/feature-details/migrate-asp-net-web-service-to-wcf.md)  
 [Cómo: migrar código de cliente de servicio Web ASP.NET a Windows Communication Foundation](../../../../docs/framework/wcf/feature-details/migrate-asp-net-web-service-client-to-wcf.md)
