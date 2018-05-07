---
title: Soportar múltiples enlaces de sitios de IIS
ms.date: 03/30/2017
ms.assetid: 40440495-254d-45c8-a8c6-b29f364892ba
ms.openlocfilehash: 9b92243bb7aaea5c8ecf708ce863e6979bc9f17c
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
---
# <a name="supporting-multiple-iis-site-bindings"></a>Soportar múltiples enlaces de sitios de IIS
Al hospedar un servicio de Windows Communication Foundation (WCF) en servicios de Internet Information Server (IIS) 7.0, puede que desee proporcionar varias direcciones base que usen el mismo protocolo en el mismo sitio. Esto permite que el mismo servicio responda a varios URI diferentes. Esto es útil cuando desea hospedar un servicio que escucha en http://www.contoso.com y http://contoso.com. También es útil crear un servicio que tenga una dirección base para los usuarios internos y una dirección base independiente para los usuarios externos. Por ejemplo: http://internal.contoso.com y http://www.contoso.com.  
  
> [!NOTE]
>  Esta funcionalidad solo está disponible mediante el protocolo HTTP.  
  
## <a name="multiple-base-addresses"></a>Múltiples direcciones base  
 Esta característica solo está disponible para los servicios WCF que se hospedan en IIS. Esta característica no está habilitada de manera predeterminada. Para habilitarlo debe agregar el `multipleSiteBindingsEnabled` atribuir a la <`serviceHostingEnvironment`> elemento en el archivo Web.config de archivos y establézcalo en `true`, como se muestra en el ejemplo siguiente.  
  
```xml  
<serviceHostingEnvironment multipleSiteBindingsEnabled="true"/>  
```  
  
 Al hospedar un servicio WCF en IIS, IIS crea una dirección base en función de la URI para el directorio virtual que contiene la aplicación. Puede agregar direcciones base adicionales que usen el mismo protocolo mediante el Administrador de Internet Information Services para agregar uno o más enlaces al sitio web. Para cada enlace especifique un protocolo (HTTP o HTTPS), una dirección IP, un puerto y un nombre de host. Para obtener más información acerca de cómo utilizar el Administrador de Internet Information Services, vea [el Administrador de IIS (IIS 7)](http://go.microsoft.com/fwlink/?LinkId=164057). Para obtener más información acerca de cómo agregar enlaces a un sitio, consulte [crear un sitio Web (IIS 7)](http://go.microsoft.com/fwlink/?LinkId=164060)  
  
 Especificar varias direcciones base para el mismo sitio afecta al contenido de la página de Ayuda de WCF, importación de esquema y la información de WSDL/MEX generada por el servicio. La página de Ayuda de WCF muestra la línea de comandos utilizada para generar a un cliente WCF que puede comunicarse con el servicio. Esta línea de comandos contiene solo la primera dirección especificada en el enlace de IIS del sitio web. De igual forma, al importar el esquema, se usa solo la primera dirección base especificada en el enlace de IIS. Los datos de WSDL y MEX contienen todas las direcciones base especificadas en los enlaces de IIS.  
  
> [!WARNING]
>  Esto significa que, si un servicio tiene dos direcciones base, una para los usuarios internos y una para los usuarios externos, ambas se especifican en la información de WSDL/MEX generada por el servicio.
