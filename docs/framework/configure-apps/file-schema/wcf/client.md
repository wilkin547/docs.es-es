---
title: <client>
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.ServiceModel/client
- http://schemas.microsoft.com/.NetConfiguration/v2.0#client
ms.assetid: bf0f7031-76c8-4e7e-a6c6-9ad9119134be
ms.openlocfilehash: 7aa3755be97a839cb576d53852b75cfe50e39276
ms.sourcegitcommit: 559259da2738a7b33a46c0130e51d336091c2097
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/22/2019
ms.locfileid: "72773948"
---
# <a name="client"></a>> de \<cliente
El elemento `client` define una lista de extremos a los que un cliente puede conectarse.

[ **\<configuration>** ](../configuration-element.md)\
&nbsp;&nbsp;[ **\<> System. serviceModel**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp; **\<cliente** >

## <a name="syntax"></a>Sintaxis

```xml
<system.serviceModel>
  <client>
    <endpoint>
    </endpoint>
    <metadata>
    </metadata>
  </client>
</system.serviceModel>
```

## <a name="attributes-and-elements"></a>Atributos y elementos
 En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.

### <a name="attributes"></a>Atributos
 Ninguno

### <a name="child-elements"></a>Elementos secundarios

|Elemento|Descripción|
|-------------|-----------------|
|[\<punto de conexión >](endpoint-of-client.md)|Contiene una colección de elementos de extremo que especifican los puntos de conexión a los que este cliente puede conectarse.|
|[metadatos de\<](metadata.md)|Contiene los valores para procesar los metadatos.|

### <a name="parent-elements"></a>Elementos primarios

|Elemento|Descripción|
|-------------|-----------------|
|[\<system.serviceModel>](system-servicemodel.md)|El elemento raíz de todos los elementos de configuración de la Windows Communication Foundation (WCF).|

## <a name="remarks"></a>Comentarios
 La sección `client` define una lista de puntos de conexión a los que un cliente puede conectarse. Cada extremo enumerado en la sección de cliente define su propio enlace, comportamiento y contrato. La combinación de los atributos `name` y `contract` identifica singularmente. El código de cliente especifica el `name` para conectar el servicio que el cliente implementa a un extremo. Si se omite el atributo de `name`, el extremo actúa como el extremo predeterminado para el contrato que implementa.

 Además, esta sección también especifica los valores para procesar los metadatos.

## <a name="example"></a>Ejemplo

```xml
<client>
  <endpoint address="/HelloWorld/"
            bindingConfiguration="usingDefaults"
            name="MyBinding"
            binding="customBinding"
            contract="HelloWorld">
    <addressProperties actingAs="http://www.microsoft.com/TestActor"
                       identityData="BasicReadWrite"
                       identityType="Spn"
                       isAddressPrivate="false">
  </endpoint>
</client>
```

## <a name="see-also"></a>Vea también

- <xref:System.ServiceModel.Configuration.ClientSection>
- <xref:System.ServiceModel.Configuration.MetadataElement>
- [Configuración del cliente de WCF](../../../wcf/feature-details/client-configuration.md)
- [Clientes](../../../wcf/feature-details/clients.md)
