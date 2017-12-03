---
title: "Soportar múltiples enlaces de sitios de IIS"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 40440495-254d-45c8-a8c6-b29f364892ba
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: bf2dbccd81b9c2e7b4ec78863d3de0227baedf92
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/02/2017
---
# <a name="supporting-multiple-iis-site-bindings"></a>Soportar múltiples enlaces de sitios de IIS
Al hospedar un servicio de [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] en Internet Information Services (IIS) 7.0, puede que desee proporcionar varias direcciones base que usen el mismo protocolo en el mismo sitio. Esto permite que el mismo servicio responda a varios URI diferentes. Esto es útil si desea hospedar un servicio que realiza escuchas en http://www.contoso.com y http://contoso.com. También es útil crear un servicio que tenga una dirección base para los usuarios internos y una dirección base independiente para los usuarios externos. Por ejemplo: http://internal.contoso.com y http://www.contoso.com.  
  
> [!NOTE]
>  Esta funcionalidad solo está disponible mediante el protocolo HTTP.  
  
## <a name="multiple-base-addresses"></a>Múltiples direcciones base  
 Esta característica solo está disponible para los servicios de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] que se hospedan en IIS. Esta característica no está habilitada de manera predeterminada. Para habilitarlo debe agregar el `multipleSiteBindingsEnabled` atribuir a la <`serviceHostingEnvironment`> elemento en el archivo Web.config de archivos y establézcalo en `true`, como se muestra en el ejemplo siguiente.  
  
```xml  
<serviceHostingEnvironment multipleSiteBindingsEnabled="true"/>  
```  
  
 Al hospedar un servicio de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] en IIS, IIS crea una dirección base para usted según el URI para el directorio virtual que contiene la aplicación. Puede agregar direcciones base adicionales que usen el mismo protocolo mediante el Administrador de Internet Information Services para agregar uno o más enlaces al sitio web. Para cada enlace especifique un protocolo (HTTP o HTTPS), una dirección IP, un puerto y un nombre de host. [!INCLUDE[crabout](../../../../includes/crabout-md.md)]con el Administrador de Internet Information Services, consulte [el Administrador de IIS (IIS 7)](http://go.microsoft.com/fwlink/?LinkId=164057). [!INCLUDE[crabout](../../../../includes/crabout-md.md)]Agregar enlaces a un sitio, consulte [crear un sitio Web (IIS 7)](http://go.microsoft.com/fwlink/?LinkId=164060)  
  
 La especificación de múltiples direcciones base para el mismo sitio afecta al contenido de la página de Ayuda de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)], al esquema y a la información de WSDL/MEX generada por el servicio. La página de Ayuda de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] muestra la línea de comandos que se debe usar para generar un cliente de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] que pueda comunicarse con el servicio. Esta línea de comandos contiene solo la primera dirección especificada en el enlace de IIS del sitio web. De igual forma, al importar el esquema, se usa solo la primera dirección base especificada en el enlace de IIS. Los datos de WSDL y MEX contienen todas las direcciones base especificadas en los enlaces de IIS.  
  
> [!WARNING]
>  Esto significa que, si un servicio tiene dos direcciones base, una para los usuarios internos y una para los usuarios externos, ambas se especifican en la información de WSDL/MEX generada por el servicio.
