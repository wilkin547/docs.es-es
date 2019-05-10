---
title: Configuración de Internet Information Services 7.0 para Windows Communication Foundation
ms.date: 03/30/2017
ms.assetid: 1050d395-092e-44d3-b4ba-66be3b039ffb
ms.openlocfilehash: 6962ed1dccca6db2e55554459742adab210585ef
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/28/2019
ms.locfileid: "64655002"
---
# <a name="configuring-internet-information-services-70-for-windows-communication-foundation"></a>Configuración de Internet Information Services 7.0 para Windows Communication Foundation

Internet Information Services (IIS) 7.0 tiene un diseño modular que le permite instalar de forma selectiva los componentes necesarios. Este diseño está basado en la nueva tecnología de componentización por manifiesto introducida en [!INCLUDE[wv](../../../../includes/wv-md.md)]. Hay más de 40 componentes de características independientes de IIS 7.0 que se pueden instalar independientemente. Esto permite a los profesionales de TI personalizar la instalación con facilidad según sea necesario. En este tema se describe cómo configurar IIS 7.0 para su uso con Windows Communication Foundation (WCF) y determinar qué componentes son necesarios.

## <a name="minimal-installation-installing-was"></a>Instalación mínima: Instalación de WAS
 La instalación mínima de todo el paquete de IIS 7.0 es instalar el servicio de activación de procesos de Windows (WAS). Se ha es una característica independiente y es la única característica de IIS 7.0 con la que está disponible para todos los [!INCLUDE[wv](../../../../includes/wv-md.md)] los sistemas operativos (Home Basic, Home Premium, Business y Ultimate y Enterprise).

 En el Panel de Control, haga clic en **programas** y, a continuación, haga clic en **o desactivar las características de Windows Active** que aparece en **programas y características**, el componente WAS se muestra en el lista como se muestra en la siguiente ilustración.

 ![Activar las características o fuera del cuadro de diálogo](../../../../docs/framework/wcf/feature-details/media/wcfc-turnfeaturesonoroffs.gif "wcfc_TurnFeaturesOnOrOffs")

 Esta característica tiene los siguientes componentes secundarios:

- Entorno de .NET

- API de configuración

- Modelo de proceso

 Si se selecciona el nodo raíz de WAS, solo el **modelo de proceso** subnodo está activada de forma predeterminada. Tenga en cuenta que con esta instalación solo está instalando WAS, porque no se ofrece ninguna compatibilidad para un servidor web.

 Para realizar cualquier trabajo de la aplicación ASP.NET o de WCF, compruebe el **entorno .NET** casilla de verificación. Esto significa que todos los componentes de WAS son necesarios para hacer que WCF y ASP.NET funcionan bien. Estos se comprueban automáticamente cuando instala cualquiera de esos componentes.

## <a name="iis-70-default-installation"></a>IIS 7.0: Instalación predeterminada
 Comprobando la **Internet Information Services** característica, algunos de los nodos secundarios se comprueban automáticamente tal como se muestra en la siguiente ilustración.

 ![Los valores predeterminados para las características de IIS 7.0](../../../../docs/framework/wcf/feature-details/media/wcfc-turningfeaturesonoroff2.gif "wcfc_TurningFeaturesOnOrOff2")

 Se trata de la instalación predeterminada de IIS 7.0. Con esta instalación, puede utilizar IIS 7.0 para contenido estático de servicio (por ejemplo, páginas HTML y otro contenido). Sin embargo, no se puede ejecutar las aplicaciones ASP.NET o CGI u hospedar servicios WCF.

## <a name="iis-70-installation-with-aspnet-support"></a>IIS 7.0: Instalación con compatibilidad de ASP.NET
 Debe instalar ASP.NET para que ASP.NET funcione en IIS 7.0. Después de comprobar **ASP.NET**, la pantalla debería parecerse a la siguiente ilustración.

 ![Los valores obligatorios Asp.NET](../../../../docs/framework/wcf/feature-details/media/wcfc-trunfeaturesonoroff3s.gif "wcfc_TrunFeaturesOnOrOFf3s")

 Este es el entorno mínimo para que las aplicaciones WCF y ASP.NET funcionan en IIS 7.0.

## <a name="iis-70-installation-with-iis-60-compatibility-components"></a>IIS 7.0: Instalación con componentes de compatibilidad 6.0 de IIS
 Cuando se instala IIS 7.0 en un sistema con Visual Studio 2005 o algunos otros scripts de automatización o las herramientas (como Adsutil.vbs) que configura aplicaciones virtuales que usan la API de Metabase de IIS 6.0, asegúrese de que comprueba el IIS 6.0 **herramientas de Scripting**. Esto comprueba automáticamente los demás nodos secundarios de IIS 6.0 **compatibilidad con la administración**. La siguiente ilustración muestra la pantalla después de ello:

 ![Configuración de compatibilidad IIS 6.0 administración](../../../../docs/framework/wcf/feature-details/media/scfc-turnfeaturesonoroff5s.gif "scfc_TurnFeaturesOnOrOff5s")

 Con esta instalación, tiene todo lo necesario para usar características de IIS 7.0, ASP.NET y WCF y ejemplos disponibles en la Web.

## <a name="request-limits"></a>Límites de la solicitud
 En [!INCLUDE[wv](../../../../includes/wv-md.md)] con IIS 7, se ha cambiado el valor predeterminado de los parámetros `maxUri` y `maxQueryStringSize`. De manera predeterminada, la solicitud de filtrado en IIS 7.0 admite una longitud de dirección URL de 4096 caracteres y una longitud de cadena de consulta de 2048 caracteres. Para cambiar estos valores predeterminados, agregue el siguiente XML al archivo App.config:

```xml
 <system.webServer>
    <security>
        <requestFiltering>
            <requestLimits maxUrl="8192" maxQueryString="8192" />
        </requestFiltering>
    </security>
 </system.webServer>
 ```

## <a name="see-also"></a>Vea también

- [Arquitectura de activación de WAS](../../../../docs/framework/wcf/feature-details/was-activation-architecture.md)
- [Configuración de WAS para su uso con WCF](../../../../docs/framework/wcf/feature-details/configuring-the-wpa--service-for-use-with-wcf.md)
- [Cómo: Instalar y configurar componentes de activación de WCF](../../../../docs/framework/wcf/feature-details/how-to-install-and-configure-wcf-activation-components.md)
- [Características de hospedaje de Windows Server AppFabric](https://go.microsoft.com/fwlink/?LinkId=201276)
