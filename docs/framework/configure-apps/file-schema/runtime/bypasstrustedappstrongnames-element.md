---
title: <bypassTrustedAppStrongNames> (Elemento)
ms.date: 03/30/2017
helpviewer_keywords:
- strong-name bypass feature
- bypassTrustedAppStrongNames element
- strong-named assemblies, loading into trusted application domains
- <bypassTrustedAppStrongNames> element
ms.assetid: 71b2ebf6-3843-41e2-ad52-ffa5cd083a40
ms.openlocfilehash: 50e67e97d74b896a680cc18270d32aa7a8eb8035
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73118172"
---
# <a name="bypasstrustedappstrongnames-element"></a>Elemento \<bypassTrustedAppStrongNames>

Especifica si se omitirá la validación de nombres seguros en ensamblados de plena confianza que se cargan en un <xref:System.AppDomain>de plena confianza.

[ **\<configuration>** ](../configuration-element.md)\
&nbsp;&nbsp;[ **\<en tiempo de ejecución >** ](runtime-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp; **\<bypassTrustedAppStrongNames >**

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

|Valor|Descripción|
|-----------|-----------------|
|`true`|Las firmas de nombre seguro de los ensamblados de plena confianza no se validan cuando los ensamblados se cargan en un <xref:System.AppDomain>de plena confianza. Este es el valor predeterminado.|
|`false`|Las firmas de nombre seguro de los ensamblados de plena confianza se validan cuando los ensamblados se cargan en un <xref:System.AppDomain>de plena confianza. La firma de nombre seguro se comprueba únicamente para comprobar la exactitud de la firma; no se compara con otro nombre seguro para buscar coincidencias.|

### <a name="child-elements"></a>Elementos secundarios

Ninguno.

### <a name="parent-elements"></a>Elementos primarios

|Elemento|Descripción|
|-------------|-----------------|
|`configuration`|Elemento raíz de cada archivo de configuración usado por las aplicaciones de Common Language Runtime y .NET Framework.|
|`runtime`|Contiene información del enlace del ensamblado y de la recolección de elementos no utilizados.|

## <a name="remarks"></a>Comentarios

La característica de omisión de nombres seguros evita la sobrecarga de la comprobación de la firma de nombre seguro de los ensamblados de plena confianza.

La característica de omisión se aplica a cualquier ensamblado que esté firmado con un nombre seguro y que:

- De plena confianza sin la <xref:System.Security.Policy.StrongName> evidencia (por ejemplo, tiene `MyComputer` evidencia de zona).

- se cargue en un <xref:System.AppDomain> de plena confianza;

- se cargue desde una ubicación en la propiedad <xref:System.AppDomainSetup.ApplicationBase%2A> de ese <xref:System.AppDomain>;

- no tenga firma retrasada.

> [!NOTE]
> Si la característica de omisión se ha desactivado para todas las aplicaciones del equipo mediante una clave del registro, este valor del archivo de configuración no tiene ningún efecto. Para obtener más información, consulte [Cómo: deshabilitar la característica de omisión de nombres seguros](../../../app-domains/how-to-disable-the-strong-name-bypass-feature.md).

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
- [Cómo: deshabilitar la característica de omisión de nombres seguros](../../../../standard/assembly/disable-strong-name-bypass-feature.md)
