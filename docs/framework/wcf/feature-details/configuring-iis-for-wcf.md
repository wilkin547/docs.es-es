---
title: Configuración de Internet Information Services 7.0 para Windows Communication Foundation
ms.date: 03/30/2017
ms.assetid: 1050d395-092e-44d3-b4ba-66be3b039ffb
ms.openlocfilehash: 865e19d6626846481347274774d3ea59f2f7ecdd
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96284217"
---
# <a name="configuring-internet-information-services-70-for-windows-communication-foundation"></a>Configuración de Internet Information Services 7.0 para Windows Communication Foundation

Internet Information Services (IIS) 7.0 tiene un diseño modular que le permite instalar de forma selectiva los componentes necesarios. Este diseño se basa en la nueva tecnología de componentes controlado por manifiestos introducida en Windows Vista. Hay más de 40 componentes de características independientes de IIS 7,0 que se pueden instalar de forma independiente. Esto permite a los profesionales de TI personalizar la instalación con facilidad según sea necesario. En este tema se describe cómo configurar IIS 7,0 para su uso con Windows Communication Foundation (WCF) y determinar qué componentes son necesarios.

## <a name="minimal-installation-installing-was"></a>Instalación mínima: instalación de WAS

 La instalación mínima de todo el paquete de IIS 7,0 es instalar el servicio de activación de procesos de Windows (WAS). WAS es una característica independiente y es la única característica de IIS 7,0 que está disponible para todos los sistemas operativos Windows Vista (Home Basic, Home Premium, Business y Ultimate y Enterprise).

 En el panel de control, haga clic en **programas** y, a continuación, haga clic en **activar o desactivar las características de Windows** , que aparece en **programas y características**, el componente was se muestra en la lista como se muestra en la siguiente ilustración.

 ![Diálogo de activación o desactivación de las características](media/wcfc-turnfeaturesonoroffs.gif "wcfc_TurnFeaturesOnOrOffs")

 Esta característica tiene los siguientes componentes secundarios:

- Entorno .NET

- API de configuración

- Modelo de proceso

 Si selecciona el nodo raíz de WAS, solo se comprueba de forma predeterminada el subnodo del **modelo de proceso** . Tenga en cuenta que con esta instalación solo está instalando WAS, porque no se ofrece ninguna compatibilidad para un servidor web.

 Para que WCF o cualquier aplicación de ASP.NET funcione, active la casilla **.net Environment** . Esto significa que todos los componentes de WAS son necesarios para que WCF y ASP.NET funcionen correctamente. Estos se comprueban automáticamente cuando instala cualquiera de esos componentes.

## <a name="iis-70-default-installation"></a>IIS 7.0: instalación predeterminada

 Al comprobar la característica de **Internet Information Services** , algunos de los subnodos se comprueban automáticamente como se muestra en la siguiente ilustración.

 ![Valores predeterminados de las características de IIS 7.0](media/wcfc-turningfeaturesonoroff2.gif "wcfc_TurningFeaturesOnOrOff2")

 Esta es la instalación predeterminada de IIS 7,0. Con esta instalación, puede usar IIS 7,0 para atender contenido estático (como páginas HTML y otro contenido). Sin embargo, no se pueden ejecutar aplicaciones ASP.NET o CGI ni servicios WCF de host.

## <a name="iis-70-installation-with-aspnet-support"></a>IIS 7.0: instalación con compatibilidad para ASP.NET

 Debe instalar ASP.NET para que ASP.NET funcione en IIS 7,0. Después de comprobar **ASP.net**, la pantalla debe ser similar a la siguiente ilustración.

 ![Configuración requerida Asp.NET](media/wcfc-trunfeaturesonoroff3s.gif "wcfc_TrunFeaturesOnOrOFf3s")

 Este es el entorno mínimo para que las aplicaciones WCF y ASP.NET funcionen en IIS 7,0.

## <a name="iis-70-installation-with-iis-60-compatibility-components"></a>IIS 7.0: instalación con componentes de compatibilidad de IIS 6.0

 Al instalar IIS 7,0 en un sistema con Visual Studio 2005 o en otros scripts o herramientas de automatización (como Adsutil.vbs) que configuren aplicaciones virtuales que usen la API de metabase de IIS 6,0, asegúrese de comprobar las **herramientas de scripting** de IIS 6,0. Esto comprueba automáticamente los otros subnodos de compatibilidad con la **Administración** de IIS 6,0. En la ilustración siguiente se muestra la pantalla una vez hecho esto:

 ![Configuración de la compatibilidad con la administración de IIS 6.0](media/scfc-turnfeaturesonoroff5s.gif "scfc_TurnFeaturesOnOrOff5s")

 Con esta instalación, tiene todo lo necesario para usar las características de IIS 7,0, ASP.NET y WCF y ejemplos disponibles en la Web.

## <a name="request-limits"></a>Límites de la solicitud

 En Windows Vista con IIS 7, se ha cambiado el valor predeterminado de la `maxUri` configuración de y `maxQueryStringSize` . De manera predeterminada, la solicitud de filtrado en IIS 7.0 admite una longitud de dirección URL de 4096 caracteres y una longitud de cadena de consulta de 2048 caracteres. Para cambiar estos valores predeterminados, agregue el siguiente XML al archivo App.config:

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

- [Arquitectura de activación de WAS](was-activation-architecture.md)
- [Configuración de WAS para su uso con WCF](configuring-the-wpa--service-for-use-with-wcf.md)
- [Procedimiento para instalar y configurar los componentes de activación de WFC](how-to-install-and-configure-wcf-activation-components.md)
- [Características de hospedaje de Windows Server AppFabric](/previous-versions/appfabric/ee677189(v=azure.10))
