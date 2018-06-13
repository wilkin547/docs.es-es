---
title: Configuración de Internet Information Services 7.0 para Windows Communication Foundation
ms.date: 03/30/2017
ms.assetid: 1050d395-092e-44d3-b4ba-66be3b039ffb
ms.openlocfilehash: 3e34f46fbf3ccf12c6a89a7cac96143965d958d9
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33491721"
---
# <a name="configuring-internet-information-services-70-for-windows-communication-foundation"></a>Configuración de Internet Information Services 7.0 para Windows Communication Foundation
Internet Information Services (IIS) 7.0 tiene un diseño modular que le permite instalar de forma selectiva los componentes necesarios. Este diseño está basado en la nueva tecnología de componentización por manifiesto introducida en [!INCLUDE[wv](../../../../includes/wv-md.md)]. Hay más de 40 componentes de características independientes de [!INCLUDE[iisver](../../../../includes/iisver-md.md)] que se pueden instalar independientemente. Esto permite a los profesionales de TI personalizar la instalación con facilidad según sea necesario. En este tema se explica cómo configurar [!INCLUDE[iisver](../../../../includes/iisver-md.md)] para usar con Windows Communication Foundation (WCF) y determinar qué componentes son necesarios.  
  
## <a name="minimal-installation-installing-was"></a>Instalación mínima: instalación de WAS  
 La instalación mínima del paquete [!INCLUDE[iisver](../../../../includes/iisver-md.md)] completo es instalar el Servicio de activación de proceso de Windows (WAS). WAS es una característica independiente y es la única de [!INCLUDE[iisver](../../../../includes/iisver-md.md)] que está disponible para todos los sistemas operativos [!INCLUDE[wv](../../../../includes/wv-md.md)] (Home Basic, Home Premium, Business y Ultimate y Enterprise).  
  
 En el Panel de Control, haga clic en **programas** y, a continuación, haga clic en **o desactivar las características de Windows Active** que aparece en **programas y características**, el componente WAS se muestra en el lista como aparece en la siguiente ilustración.  
  
 ![Características de activar o desactivar diálogo](../../../../docs/framework/wcf/feature-details/media/wcfc-turnfeaturesonoroffs.gif "wcfc_TurnFeaturesOnOrOffs")  
  
 Esta característica tiene los siguientes componentes secundarios:  
  
-   Entorno de .NET  
  
-   API de configuración  
  
-   Modelo de proceso  
  
 Si se selecciona el nodo raíz de WAS, solo el **modelo de proceso** subnodo está activada de forma predeterminada. Tenga en cuenta que con esta instalación solo está instalando WAS, porque no se ofrece ninguna compatibilidad para un servidor web.  
  
 Para hacer que WCF o cualquier [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] aplicación para que funcione, compruebe el **entorno .NET** casilla de verificación. Esto significa que todos los componentes de WAS son necesarios para hacer que WCF y [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] funcionen bien. Estos se comprueban automáticamente cuando instala cualquiera de esos componentes.  
  
## <a name="iis-70-default-installation"></a>IIS 7.0: instalación predeterminada  
 Comprobando el **Internet Information Services** característica, algunos de los nodos secundarios se marcan automáticamente como se muestra en la siguiente ilustración.  
  
 ![Los valores predeterminados para las características de IIS 7.0](../../../../docs/framework/wcf/feature-details/media/wcfc-turningfeaturesonoroff2.gif "wcfc_TurningFeaturesOnOrOff2")  
  
 Ésta es la instalación predeterminada de [!INCLUDE[iisver](../../../../includes/iisver-md.md)]. Con esta instalación, puede utilizar [!INCLUDE[iisver](../../../../includes/iisver-md.md)] para prestar servicio al contenido estático (como páginas HTML y otro contenido). Sin embargo, no puede ejecutar [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] ni aplicaciones CGI ni hospedar los servicios WCF.  
  
## <a name="iis-70-installation-with-aspnet-support"></a>IIS 7.0: instalación con compatibilidad para ASP.NET  
 Debe instalar [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] para realizar el trabajo [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] en IIS 7.0. Después de comprobar **ASP.NET**, la pantalla debe ser similar a la siguiente ilustración.  
  
 ![Configuración obligatoria de Asp.NET](../../../../docs/framework/wcf/feature-details/media/wcfc-trunfeaturesonoroff3s.gif "wcfc_TrunFeaturesOnOrOFf3s")  
  
 Este es el entorno mínimo para ambos WCF y [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] aplicaciones para que funcionen [!INCLUDE[iisver](../../../../includes/iisver-md.md)].  
  
## <a name="iis-70-installation-with-iis-60-compatibility-components"></a>IIS 7.0: instalación con componentes de compatibilidad de IIS 6.0  
 Al instalar [!INCLUDE[iisver](../../../../includes/iisver-md.md)] en un sistema con Visual Studio 2005 o algún otro scripts de automatización o herramientas (como Adsutil.vbs) que configuran las aplicaciones virtuales que usan [!INCLUDE[iis601](../../../../includes/iis601-md.md)] Metabase API, asegúrese de que ha activado el [!INCLUDE[iis601](../../../../includes/iis601-md.md)]  **Herramientas de scripting**. Esto comprueba automáticamente los otros subnodos de [!INCLUDE[iis601](../../../../includes/iis601-md.md)] **compatibilidad con la administración**. La ilustración siguiente muestra la pantalla después de realizar esta acción.  
  
 ![Configuración de compatibilidad IIS 6.0 administración](../../../../docs/framework/wcf/feature-details/media/scfc-turnfeaturesonoroff5s.gif "scfc_TurnFeaturesOnOrOff5s")  
  
 Con esta instalación, tiene todo lo necesario para usar [!INCLUDE[iisver](../../../../includes/iisver-md.md)], [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] y las características WCF y ejemplos disponibles en la Web.  
  
## <a name="request-limits"></a>Límites de la solicitud  
 En [!INCLUDE[wv](../../../../includes/wv-md.md)] con IIS 7, se ha cambiado el valor predeterminado de los parámetros `maxUri` y `maxQueryStringSize`. De manera predeterminada, la solicitud de filtrado en IIS 7.0 admite una longitud de dirección URL de 4096 caracteres y una longitud de cadena de consulta de 2048 caracteres. Para cambiar estos valores predeterminados, agregue el siguiente XML al archivo App.config:  
  
 `<system.webServer>`  
  
 `<security>`  
  
 `<requestFiltering>`  
  
 `<requestLimits maxUrl="8192" maxQueryString="8192" />`  
  
 `</requestFiltering>`  
  
 `</security>`  
  
 `</system.webServer>`  
  
## <a name="see-also"></a>Vea también  
 [Arquitectura de activación de WAS](../../../../docs/framework/wcf/feature-details/was-activation-architecture.md)  
 [Configuración de WAS para su uso con WCF](../../../../docs/framework/wcf/feature-details/configuring-the-wpa--service-for-use-with-wcf.md)  
 [Instalación y configuración de los componentes de activación de WFC](../../../../docs/framework/wcf/feature-details/how-to-install-and-configure-wcf-activation-components.md)  
 [Características de hospedaje de Windows Server App Fabric](http://go.microsoft.com/fwlink/?LinkId=201276)
