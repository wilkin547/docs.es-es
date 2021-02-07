---
description: 'Más información acerca de: <bypassTrustedAppStrongNames> elemento'
title: <bypassTrustedAppStrongNames> (Elemento)
ms.date: 03/30/2017
helpviewer_keywords:
- strong-name bypass feature
- bypassTrustedAppStrongNames element
- strong-named assemblies, loading into trusted application domains
- <bypassTrustedAppStrongNames> element
ms.assetid: 71b2ebf6-3843-41e2-ad52-ffa5cd083a40
ms.openlocfilehash: d23b9efa19481027480f2a1c7dab22bc97a05e13
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99719167"
---
# <a name="bypasstrustedappstrongnames-element"></a>\<bypassTrustedAppStrongNames> (Elemento)

Especifica si se omitirá la validación de nombres seguros en ensamblados de plena confianza que se cargan en una plena confianza <xref:System.AppDomain> .

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<runtime>**](runtime-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<bypassTrustedAppStrongNames>**

## <a name="syntax"></a>Sintaxis

```xml
<bypassTrustedAppStrongNames
   enabled="true|false"/>
```

## <a name="attributes-and-elements"></a>Atributos y elementos

En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.

### <a name="attributes"></a>Atributos

|Atributo|Descripción|
|---------------|-----------------|
|`enabled`|Atributo necesario.<br /><br /> Especifica si está habilitada la característica de omisión que evita la validación de nombres seguros para los ensamblados de plena confianza. Cuando esta característica está habilitada, los nombres seguros no se validan para comprobar su exactitud cuando se carga el ensamblado. De manera predeterminada, es `true`.|

## <a name="enabled-attribute"></a>Atributo enabled

|Value|Descripción|
|-----------|-----------------|
|`true`|Las firmas de nombre seguro de los ensamblados de plena confianza no se validan cuando los ensamblados se cargan en una plena confianza <xref:System.AppDomain> . Este es el valor predeterminado.|
|`false`|Las firmas de nombre seguro de los ensamblados de plena confianza se validan cuando los ensamblados se cargan en una plena confianza <xref:System.AppDomain> . La firma de nombre seguro se comprueba únicamente para comprobar la exactitud de la firma; no se compara con otro nombre seguro para buscar coincidencias.|

### <a name="child-elements"></a>Elementos secundarios

Ninguno.

### <a name="parent-elements"></a>Elementos primarios

|Elemento|Descripción|
|-------------|-----------------|
|`configuration`|Elemento raíz de cada archivo de configuración usado por las aplicaciones de Common Language Runtime y .NET Framework.|
|`runtime`|Contiene información del enlace del ensamblado y de la recolección de elementos no utilizados.|

## <a name="remarks"></a>Observaciones

La característica de omisión de nombres seguros evita la sobrecarga de la comprobación de la firma de nombre seguro de los ensamblados de plena confianza.

La característica de omisión se aplica a cualquier ensamblado que esté firmado con un nombre seguro y que:

- De plena confianza sin la <xref:System.Security.Policy.StrongName> evidencia (por ejemplo, tiene `MyComputer` evidencia de zona).

- se cargue en un <xref:System.AppDomain> de plena confianza;

- se cargue desde una ubicación en la propiedad <xref:System.AppDomainSetup.ApplicationBase%2A> de ese <xref:System.AppDomain>;

- no tenga firma retrasada.

> [!NOTE]
> Si la característica de omisión se ha desactivado para todas las aplicaciones del equipo mediante una clave del registro, este valor del archivo de configuración no tiene ningún efecto. Para obtener más información, consulte [Cómo: deshabilitar la característica de omisión de Strong-Name](../../../../standard/assembly/disable-strong-name-bypass-feature.md).

## <a name="example"></a>Ejemplo

En el ejemplo siguiente se muestra cómo especificar el comportamiento que valida la firma de nombre seguro en los ensamblados de plena confianza.

```xml
<configuration>
   <runtime>
      <bypassTrustedAppStrongNames enabled="false"/>
   </runtime>
</configuration>
```

## <a name="see-also"></a>Vea también

- [Esquema de la configuración de Common Language Runtime](index.md)
- [Esquema de los archivos de configuración](../index.md)
- [Cómo: Deshabilitar la característica de omisión de nombres seguros](../../../../standard/assembly/disable-strong-name-bypass-feature.md)
