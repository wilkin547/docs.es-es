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
ms.openlocfilehash: 1a4e5ba5ac1a5a3c08c351531efc84291925ba4b
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/30/2019
ms.locfileid: "55267474"
---
# <a name="enforcefipspolicy-element"></a>\<enforceFIPSPolicy > elemento
Especifica si se debe exigir un requisito de configuración del equipo que indique que los algoritmos criptográficos deben cumplir con los Estándares federales de procesamiento de la información (FIPS).  
  
 \<Configuración > elemento  
\<en tiempo de ejecución > elemento  
\<enforceFIPSPolicy > elemento  
  
## <a name="syntax"></a>Sintaxis  
  
```xml  
<enforceFIPSPolicy enabled="true|false" />  
```  
  
## <a name="attributes-and-elements"></a>Atributos y elementos  
 En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.  
  
### <a name="attributes"></a>Atributos  
  
|Atributo|Descripción|  
|---------------|-----------------|  
|enabled|Atributo necesario.<br /><br /> Especifica si se habilita el cumplimiento de un requisito de configuración del equipo que los algoritmos criptográficos deben ser compatibles con FIPS.|  
  
## <a name="enabled-attribute"></a>Atributo enabled  
  
|Valor|Descripción|  
|-----------|-----------------|  
|`true`|Si el equipo está configurado para requerir que los algoritmos criptográficos sea compatible con FIPS, se aplicará este requisito. Si una clase implementa un algoritmo que no es compatible con FIPS, los constructores o `Create` métodos de esa clase producen excepciones cuando se ejecutan en ese equipo. Este es el valor predeterminado.|  
|`false`|Los algoritmos criptográficos utilizados por la aplicación no tienen que ser compatible con FIPS, independientemente de la configuración del equipo.|  
  
### <a name="child-elements"></a>Elementos secundarios  
 Ninguno.  
  
### <a name="parent-elements"></a>Elementos primarios  
  
|Elemento|Descripción|  
|-------------|-----------------|  
|`configuration`|Elemento raíz de cada archivo de configuración usado por las aplicaciones de Common Language Runtime y .NET Framework.|  
|`runtime`|Contiene información del enlace del ensamblado y de la recolección de elementos no utilizados.|  
  
## <a name="remarks"></a>Comentarios  
 A partir de .NET Framework 2.0, la creación de clases que implementan algoritmos criptográficos se controla mediante la configuración del equipo. Si el equipo está configurado para requerir algoritmos para ser compatible con FIPS, y una clase implementa un algoritmo que no es compatible con FIPS, cualquier intento de crear una instancia de esa clase produce una excepción. Constructores de producen una <xref:System.InvalidOperationException> excepción, y `Create` métodos inician una <xref:System.Reflection.TargetInvocationException> excepción con un interior <xref:System.InvalidOperationException> excepción.  
  
 Si la aplicación se ejecuta en equipos cuya configuración exigir el cumplimiento de FIPS y la aplicación utiliza un algoritmo que no es compatible con FIPS, puede usar este elemento en el archivo de configuración para evitar que common language runtime (CLR) de exigir el cumplimiento de FIPS. Este elemento se introdujo en la [!INCLUDE[net_v20SP1_long](../../../../../includes/net-v20sp1-long-md.md)].  
  
## <a name="example"></a>Ejemplo  
 El ejemplo siguiente muestra cómo evitar que el CLR exigir el cumplimiento de FIPS.  
  
```xml  
<configuration>  
    <runtime>  
        <enforceFIPSPolicy enabled="false"/>  
    </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a>Vea también
- [Esquema de la configuración de Common Language Runtime](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)
- [Esquema de los archivos de configuración](../../../../../docs/framework/configure-apps/file-schema/index.md)
- [Modelo de criptografía](../../../../../docs/standard/security/cryptography-model.md)
