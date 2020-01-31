---
title: Soportar múltiples enlaces de sitios de IIS
ms.date: 03/30/2017
ms.assetid: 40440495-254d-45c8-a8c6-b29f364892ba
ms.openlocfilehash: e364be55687323d3059c4a7e084818e3f7d54d5f
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/24/2020
ms.locfileid: "76743442"
---
# <a name="supporting-multiple-iis-site-bindings"></a>Soportar múltiples enlaces de sitios de IIS
Al hospedar un servicio de Windows Communication Foundation (WCF) en Internet Information Services (IIS) 7,0, puede que desee proporcionar varias direcciones base que usen el mismo protocolo en el mismo sitio. Esto permite que el mismo servicio responda a varios URI diferentes. Esto resulta útil si desea hospedar un servicio que escucha en `http://www.contoso.com` y `http://contoso.com`. También es útil crear un servicio que tenga una dirección base para los usuarios internos y una dirección base independiente para los usuarios externos. Por ejemplo: `http://internal.contoso.com` y `http://www.contoso.com`.  
  
> [!NOTE]
> Esta funcionalidad solo está disponible mediante el protocolo HTTP.  
  
## <a name="multiple-base-addresses"></a>Múltiples direcciones base  
 Esta característica solo está disponible para los servicios WCF que se hospedan en IIS. Esta característica no está habilitada de manera predeterminada. Para habilitarla, debe agregar el atributo `multipleSiteBindingsEnabled` al elemento <`serviceHostingEnvironment`> del archivo Web. config y establecerlo en `true`, como se muestra en el ejemplo siguiente.  
  
```xml  
<serviceHostingEnvironment multipleSiteBindingsEnabled="true"/>  
```  
  
 Al hospedar un servicio WCF en IIS, IIS crea una dirección base basada en el URI para el directorio virtual que contiene la aplicación. Puede agregar direcciones base adicionales que usen el mismo protocolo mediante el Administrador de Internet Information Services para agregar uno o más enlaces al sitio web. Para cada enlace especifique un protocolo (HTTP o HTTPS), una dirección IP, un puerto y un nombre de host. Para obtener más información acerca del uso del administrador de Internet Information Services, vea [Administrador de IIS (IIS 7)](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc753842(v=ws.10)). Para obtener más información sobre cómo agregar enlaces a un sitio, vea [crear un sitio web (IIS 7)](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc772350(v=ws.10)) .  
  
 Especificar varias direcciones base para el mismo sitio afecta al contenido de la página de ayuda de WCF, al importar el esquema y a la información de WSDL/MEX generada por el servicio. La página de ayuda de WCF muestra la línea de comandos que se va a usar para generar un cliente de WCF que pueda comunicarse con el servicio. Esta línea de comandos contiene solo la primera dirección especificada en el enlace de IIS del sitio web. De igual forma, al importar el esquema, se usa solo la primera dirección base especificada en el enlace de IIS. Los datos de WSDL y MEX contienen todas las direcciones base especificadas en los enlaces de IIS.  
  
> [!WARNING]
> Esto significa que, si un servicio tiene dos direcciones base, una para los usuarios internos y una para los usuarios externos, ambas se especifican en la información de WSDL/MEX generada por el servicio.
