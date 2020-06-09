---
title: Activación basada en la configuración en IIS y WAS
ms.date: 03/30/2017
ms.assetid: 6a927e1f-b905-4ee5-ad0f-78265da38238
ms.openlocfilehash: 5e1672f4dd67950178c95d3e043e16072fcd0ef4
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/09/2020
ms.locfileid: "84593586"
---
# <a name="configuration-based-activation-in-iis-and-was"></a>Activación basada en la configuración en IIS y WAS

Normalmente, al hospedar un servicio de Windows Communication Foundation (WCF) en Internet Information Services (IIS) o en el servicio de activación de procesos de Windows (WAS), debe proporcionar un archivo. SVC. El archivo .svc contiene el nombre del servicio y un generador de host de servicio personalizado opcional. Este archivo adicional agrega una sobrecarga de administración. La característica de activación basada en la configuración elimina el requisito de tener un archivo .svc y, por lo tanto, la sobrecarga asociada.

## <a name="configuration-based-activation"></a>Activación basada en la configuración

La activación basada en la configuración toma los metadatos que se solían encontrar en el archivo .svc y los coloca en el archivo Web.config. En el `serviceHostingEnvironment` elemento<> hay un `serviceActivations` elemento> <. Dentro del <`serviceActivations` elemento> son uno o varios `add` elementos de> de <, uno para cada servicio hospedado. El `add` elemento> de <contiene atributos que le permiten establecer la dirección relativa para el servicio y el tipo de servicio o un generador de host de servicio. El siguiente ejemplo de configuración muestra cómo se utiliza esta sección.

> [!NOTE]
> Cada <`add` elemento> debe especificar un servicio o un atributo de generador. Se puede especificar tanto el servicio como los atributos de generador.

```xml
<serviceHostingEnvironment>
  <serviceActivations>
    <add relativeAddress="MyServiceAddress" service="Service" factory="MyServiceHostFactory"/>
  </serviceActivations>
</serviceHostingEnvironment>
```

 Con esto en el archivo Web.config, puede colocar el código fuente del servicio en el directorio App_Code de la aplicación o un ensamblado compatible en el directorio Bin de la aplicación.

> [!NOTE]
>
> - Cuando se usa la activación basada en la configuración, no se admite código insertado en los archivos .svc.
> - El `relativeAddress` atributo debe establecerse en una dirección relativa como " \<sub-directory> /Service.SVC" o "~/ \< Sub-Directory/Service. SVC".
> - Se produce una excepción de configuración si registra una dirección relativa que no tiene una extensión conocida asociada a WCF.
> - La dirección relativa especificada es relativa a la raíz de la aplicación virtual.
> - Debido al modelo jerárquico de la configuración, las direcciones relativas registradas en el equipo y en el sitio son heredadas por aplicaciones virtuales.
> - Los registros de un archivo de configuración tienen prioridad sobre la configuración de .svc, .xamlx, .xoml u otro archivo.
> - Cualquier '\' (barras diagonales inversas) en un URI enviada a IIS/WAS se convierte automáticamente en '/' (barra diagonal). Si se agrega una dirección relativa que contiene una '\' y le envía a IIS un URI que usa la dirección relativa, la barra diagonal inversa se convierte en una barra diagonal e IIS no puede hacerla coincidir con la dirección relativa. IIS envía información de traza que indica que no se ha detectado ninguna coincidencia.

## <a name="see-also"></a>Vea también

- <xref:System.ServiceModel.Configuration.ServiceHostingEnvironmentSection.ServiceActivations%2A>
- [Servicios de hospedaje](../hosting-services.md)
- [Hospedar información general de servicios de flujo de trabajo](hosting-workflow-services-overview.md)
- [\<serviceHostingEnvironment>](../../configure-apps/file-schema/wcf/servicehostingenvironment.md)
- [Características de hospedaje de Windows Server AppFabric](https://docs.microsoft.com/previous-versions/appfabric/ee677189(v=azure.10))
