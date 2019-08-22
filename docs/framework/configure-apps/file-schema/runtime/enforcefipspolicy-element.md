---
title: <enforceFIPSPolicy> (Elemento)
ms.date: 03/30/2017
helpviewer_keywords:
- enforceFIPSPolicy element
- FIPS
- <enforceFIPSPolicy> element
- Federal Information Processing Standards (FIPS)
ms.assetid: c35509c4-35cf-43c0-bb47-75e4208aa24e
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: eb28eddf7e9f13bceaf47de28633073f59f3920d
ms.sourcegitcommit: cdf67135a98a5a51913dacddb58e004a3c867802
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/21/2019
ms.locfileid: "69663750"
---
# <a name="enforcefipspolicy-element"></a>\<enforceFIPSPolicy >, elemento
Especifica si se debe exigir un requisito de configuración del equipo que indique que los algoritmos criptográficos deben cumplir con los Estándares federales de procesamiento de la información (FIPS).  
  
 \<Elemento Configuration >  
\<Elemento > en tiempo de ejecución  
\<enforceFIPSPolicy >, elemento  
  
## <a name="syntax"></a>Sintaxis  
  
```xml  
<enforceFIPSPolicy enabled="true|false" />  
```  
  
## <a name="attributes-and-elements"></a>Atributos y elementos  
 En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.  
  
### <a name="attributes"></a>Atributos  
  
|Atributo|DESCRIPCIÓN|  
|---------------|-----------------|  
|enabled|Atributo necesario.<br /><br /> Especifica si se debe habilitar la aplicación de un requisito de configuración de equipo de que los algoritmos criptográficos deben ser compatibles con FIPS.|  
  
## <a name="enabled-attribute"></a>Atributo enabled  
  
|Value|DESCRIPCIÓN|  
|-----------|-----------------|  
|`true`|Si el equipo está configurado para requerir que los algoritmos criptográficos sean conformes a FIPS, se aplicará ese requisito. Si una clase implementa un algoritmo que no es compatible con FIPS, los constructores o `Create` métodos de esa clase inician excepciones cuando se ejecutan en ese equipo. Este es el valor predeterminado.|  
|`false`|No es necesario que los algoritmos criptográficos que usa la aplicación sean compatibles con FIPS, independientemente de la configuración del equipo.|  
  
### <a name="child-elements"></a>Elementos secundarios  
 Ninguno.  
  
### <a name="parent-elements"></a>Elementos primarios  
  
|Elemento|DESCRIPCIÓN|  
|-------------|-----------------|  
|`configuration`|Elemento raíz de cada archivo de configuración usado por las aplicaciones de Common Language Runtime y .NET Framework.|  
|`runtime`|Contiene información del enlace del ensamblado y de la recolección de elementos no utilizados.|  
  
## <a name="remarks"></a>Comentarios  
 A partir del .NET Framework 2,0, la creación de clases que implementan algoritmos criptográficos se controla mediante la configuración del equipo. Si el equipo está configurado para requerir que los algoritmos sean compatibles con FIPS, y una clase implementa un algoritmo que no es compatible con FIPS, cualquier intento de crear una instancia de esa clase produce una excepción. Los constructores producen <xref:System.InvalidOperationException> una excepción y `Create` los métodos producen <xref:System.Reflection.TargetInvocationException> una excepción con una <xref:System.InvalidOperationException> excepción interna.  
  
 Si la aplicación se ejecuta en equipos cuyas configuraciones requieren el cumplimiento de FIPS, y la aplicación usa un algoritmo que no es compatible con FIPS, puede usar este elemento en el archivo de configuración para evitar que el Common Language Runtime (CLR) de aplicando la compatibilidad con FIPS. Este elemento se presentó en el .NET Framework 2,0 Service Pack 1.  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se muestra cómo evitar que CLR aplique la compatibilidad con FIPS.  
  
```xml  
<configuration>  
    <runtime>  
        <enforceFIPSPolicy enabled="false"/>  
    </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a>Vea también

- [Esquema de la configuración de Common Language Runtime](index.md)
- [Esquema de los archivos de configuración](../index.md)
- [Modelo de criptografía](../../../../../docs/standard/security/cryptography-model.md)
