---
description: 'Más información sobre: integración con las aplicaciones COM información general'
title: Integración con la información general de las aplicaciones COM
ms.date: 03/30/2017
helpviewer_keywords:
- COM [WCF], integration overview
ms.assetid: 02c5697f-6e2e-47d6-b715-f3a28aebfbd5
ms.openlocfilehash: a179fd73c8065fff1e16d3f86202d717df155b81
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99802819"
---
# <a name="integrating-with-com-applications-overview"></a>Integración con la información general de las aplicaciones COM

Windows Communication Foundation (WCF) proporciona al desarrollador de código administrado un entorno completo para crear aplicaciones conectadas. Sin embargo, si tiene una inversión sustancial en código basado en COM no administrado y no desea migrar, todavía puede integrar los servicios Web de WCF directamente en el código existente mediante el moniker de servicio de WCF. El moniker de servicio se puede utilizar a partir de una gama amplia de entornos de desarrollo basados en COM, como Office VBA, Visual Basic 6.0 o Visual C++ 6.0.

> [!NOTE]
> El moniker de servicio utiliza un canal de comunicación WCF para todas las comunicaciones. Los mecanismos de identidad y seguridad para ese canal difieren de aquéllos utilizados en los proxies COM y DCOM estándar. Además, dado que el moniker de servicio utiliza un canal de comunicación WCF, el período de tiempo de espera predeterminado es un minuto para todas las llamadas.

El moniker de servicio se usa con la `GetObject` función para proporcionar al desarrollador no administrado un enfoque con establecimiento inflexible de tipos y específico de com para llamar a los servicios Web de WCF. Esto requiere una definición local y visible para COM del contrato de servicio Web de WCF y el enlace que se va a utilizar. Al igual que otros clientes de WCF, el moniker de servicio debe construir un canal con tipo al servicio, aunque esta construcción de canal se produce de forma transparente en el programador COM en la primera llamada al método.

En común con otros clientes de WCF, cuando se usa el moniker, las aplicaciones especifican la dirección, el enlace y el contrato para comunicarse con un servicio. El contrato se puede especificar de una de las maneras siguientes:

- Contrato con tipo: el contrato se registra como un tipo visible COM en el equipo cliente.

- Contrato de WSDL: el contrato se proporciona con la forma de un documento WSDL.

- Contrato de MEX: el contrato se recupera en el tiempo de ejecución a partir de un extremo de intercambio de metadatos (MEX).

## <a name="parameters-supported-by-the-service-moniker"></a>Parámetros admitidos por el moniker de servicio

En la tabla siguiente se muestran los parámetros admitidos por el moniker de servicio.

|Parámetro|Descripción|
|---------------|-----------------|
|`address`|Ubicación de URL del servicio.|
|`binding`|Nombre de sección de enlace desde la configuración de la aplicación.|
|`bindingConfiguration`|Instancia del enlace con nombre desde la sección de enlace con nombre.|
|`contract`|Identificador de interfaz (IID) que representa el contrato de servicio o el nombre del contrato (de MEX).|
|`wsdl`|Documento WSDL que proporciona un formulario alternativo de definición de contrato.|
|`spnIdentity`|Identidad del nombre de entidad de seguridad de servidor (SPN) que se va a utilizar para comunicarse con el servicio.|
|`upnIdentity`|Identidad del nombre principal del usuario (UPN) que se va a utilizar para comunicarse con el servicio.|
|`dnsIdentity`|Identidad de DNS que se va a utilizar para comunicarse con el servicio.|
|`mexAddress`|Ubicación de la dirección URL del punto de conexión de intercambio de metadatos (MEX) del servicio.|
|`mexBinding`|El nombre de la sección de enlace a partir de la configuración de la aplicación para conectarse con el extremo MEX.|
|`mexBindingConfiguration`|Instancia de enlace con nombre desde la que la sección de enlace con nombre se conecta con el punto de conexión MEX.|
|`bindingNamespace`|El espacio de nombres del nombre de la sección de enlace desde el MEX recuperado.|
|`contractNamespace`|El espacio de nombres del contrato desde el MEX recuperado.|
|`mexSpnIdentity`|Identidad del nombre de entidad de seguridad de servidor (SPN) que se va a utilizar para comunicarse con el extremo MEX.|
|`mexUpnIdentity`|Identidad del nombre principal del usuario (UPN) que se va a utilizar para comunicarse con el punto de conexión MEX.|
|`mexDnsIdentity`|Identidad de DNS que se va a utilizar para comunicarse con el punto de conexión MEX.|
|`serializer`|Especifique el uso de "xml" o serializador de "datacontract."|

> [!NOTE]
> Incluso cuando se usa con clientes basados en COM completamente, el moniker de servicio requiere WCF y el .NET Framework de compatibilidad de 2,0 para instalarse en el equipo cliente. También es fundamental que las aplicaciones cliente que utilizan el moniker de servicio carguen la versión adecuada del tiempo de ejecución de .NET Framework. Al utilizar el moniker en aplicaciones de Office, es posible que sea necesario un archivo de configuración para asegurarse de que se carga la versión de marco correcta. Por ejemplo, con Excel, el texto siguiente debería colocarse en un archivo denominado Excel.exe.config en el mismo directorio que el archivo Excel.exe:
>
> `<?xml version="1.0" encoding="utf-8"?>`
>
> `<configuration xmlns=` `http://schemas.microsoft.com/.NetConfiguration/v2.0` `>`
>
> `<startup>`
>
> `<requiredRuntime version="v2.0.50727" />`
>
> `</startup>`
>
> `</configuration>`

## <a name="see-also"></a>Vea también

- [Procedimiento para registrar y configurar un moniker de servicio](how-to-register-and-configure-a-service-moniker.md)
