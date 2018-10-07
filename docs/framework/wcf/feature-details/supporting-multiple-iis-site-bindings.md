---
title: Soportar múltiples enlaces de sitios de IIS
ms.date: 03/30/2017
ms.assetid: 40440495-254d-45c8-a8c6-b29f364892ba
ms.openlocfilehash: 5a8b06d86b505452f9ded808f727343b1453e592
ms.sourcegitcommit: 586dbdcaef9767642436b1e4efbe88fb15473d6f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/06/2018
ms.locfileid: "48840873"
---
# <a name="supporting-multiple-iis-site-bindings"></a>Soportar múltiples enlaces de sitios de IIS
Al hospedar un servicio de Windows Communication Foundation (WCF) en Internet Information Services (IIS) 7.0, puede proporcionar varias direcciones base que usan el mismo protocolo en el mismo sitio. Esto permite que el mismo servicio responda a varios URI diferentes. Esto es útil cuando desee hospedar un servicio que escucha en `http://www.contoso.com` y `http://contoso.com`. También es útil crear un servicio que tenga una dirección base para los usuarios internos y una dirección base independiente para los usuarios externos. Por ejemplo: `http://internal.contoso.com` y `http://www.contoso.com`.  
  
> [!NOTE]
>  Esta funcionalidad solo está disponible mediante el protocolo HTTP.  
  
## <a name="multiple-base-addresses"></a>Múltiples direcciones base  
 Esta característica solo está disponible para los servicios WCF que se hospedan en IIS. Esta característica no está habilitada de manera predeterminada. Para habilitarla, debe agregar el `multipleSiteBindingsEnabled` atributo a la <`serviceHostingEnvironment`> elemento en el archivo Web.config de archivos y establézcalo en `true`, como se muestra en el ejemplo siguiente.  
  
```xml  
<serviceHostingEnvironment multipleSiteBindingsEnabled="true"/>  
```  
  
 Al hospedar un servicio WCF en IIS, IIS crea automáticamente una dirección base según el URI en el directorio virtual que contiene la aplicación. Puede agregar direcciones base adicionales que usen el mismo protocolo mediante el Administrador de Internet Information Services para agregar uno o más enlaces al sitio web. Para cada enlace especifique un protocolo (HTTP o HTTPS), una dirección IP, un puerto y un nombre de host. Para obtener más información sobre cómo usar el Administrador de Internet Information Services, consulte [el Administrador de IIS (IIS 7)](https://go.microsoft.com/fwlink/?LinkId=164057). Para obtener más información sobre cómo agregar enlaces a un sitio, consulte [crear un sitio Web (IIS 7)](https://go.microsoft.com/fwlink/?LinkId=164060)  
  
 Especificar varias direcciones base para el mismo sitio afecta al contenido de la página de Ayuda de WCF, importación de esquema y la información de WSDL/MEX generada por el servicio. La página de Ayuda de WCF muestra la línea de comandos utilizada para generar a un cliente WCF que puede comunicarse con el servicio. Esta línea de comandos contiene solo la primera dirección especificada en el enlace de IIS del sitio web. De igual forma, al importar el esquema, se usa solo la primera dirección base especificada en el enlace de IIS. Los datos de WSDL y MEX contienen todas las direcciones base especificadas en los enlaces de IIS.  
  
> [!WARNING]
>  Esto significa que, si un servicio tiene dos direcciones base, una para los usuarios internos y una para los usuarios externos, ambas se especifican en la información de WSDL/MEX generada por el servicio.
