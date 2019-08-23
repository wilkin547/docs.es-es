---
title: <add> de <serviceActivations>
ms.date: 03/30/2017
ms.assetid: e5b01fc8-ee84-48b7-95fd-95ab54fa871f
ms.openlocfilehash: 929773fcb6b6a3ee5c75aa970147277d9dbe7b45
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "69920022"
---
# <a name="add-of-serviceactivations"></a>\<Agregar > de \<serviceActivations >

Un elemento de configuración que le permite definir la configuración de activación de servicio virtual que se asigna a los tipos de servicio Windows Communication Foundation (WCF). Esto hace posible activar servicios hospedados en WAS/IIS sin un archivo .svc.

\<system.ServiceModel>\
\<serviceHostingEnvironment>

## <a name="syntax"></a>Sintaxis

```xml
<serviceHostingEnvironment>
    <serviceActivations>
      <add factory="String"
           service="String" />
  </serviceActivations>
</serviceHostingEnvironment>
```

## <a name="attributes-and-elements"></a>Atributos y elementos

En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.

### <a name="attributes"></a>Atributos

|Atributo|DESCRIPCIÓN|
|---------------|-----------------|
|factory|Cadena que especifica el nombre de tipo de CLR del generador que genera un elemento de activación de servicio.|
|service|ServiceType que implementa el servicio (Typename calificado completo o Typename corto (cuando se coloca en la carpeta App_Code).|
|relativeAddress|La dirección relativa dentro de la aplicación de IIS actual (por ejemplo “Service.svc”. En WCF 4.0 esta dirección relativa debe contener una de las extensiones de archivo conocidas (.svc, .xamlx, …). No tiene que existir ningún archivo físico para relativeUrl|

### <a name="child-elements"></a>Elementos secundarios

Ninguno.

### <a name="parent-elements"></a>Elementos primarios

|Elemento|DESCRIPCIÓN|
|-------------|-----------------|
|[\<serviceHostingEnvironment>](servicehostingenvironment.md)|Sección de configuración que describe la configuración de activación.|

## <a name="remarks"></a>Comentarios

En el siguiente ejemplo se muestra cómo configurar los valores de activación dentro del archivo web.config.

```xml
<configuration>
  <system.serviceModel>
    <serviceHostingEnvironment>
      <serviceActivations>
        <add service="GreetingService" />
      </serviceActivations>
    </serviceHostingEnvironment>
  </system.serviceModel>
</configuration>
```

Con esta configuración, puede activar GreetingService sin usar un archivo .svc.

Observe que `<serviceHostingEnvironment>` es una configuración de nivel de aplicación. Tiene que colocar el archivo `web.config` que contiene la configuración en la raíz de la aplicación virtual. Además, `serviceHostingEnvironment` es una sección machineToApplication heredable. Si registra un solo servicio en la raíz del equipo, cada servicio de la aplicación heredará este servicio.

La activación basada en la configuración admite la activación a través de protocolos http y distintos de http. Requiere extensiones en relativeAddress, es decir,. SVC,. xoml o. xamlx. Puede asignar sus propias extensiones al buildProviders conocido, que le permitirá activar el servicio a través de cualquier extensión. Si existe conflicto, la sección `<serviceActivations>` invalida los registros de .svc.

## <a name="see-also"></a>Vea también

- <xref:System.ServiceModel.Configuration.ServiceActivationElement>
- <xref:System.ServiceModel.Configuration.ServiceHostingEnvironmentSection>
- <xref:System.ServiceModel.ServiceHostingEnvironment>
