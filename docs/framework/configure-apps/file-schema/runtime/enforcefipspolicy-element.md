---
title: '&lt;enforceFIPSPolicy&gt; elemento'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- enforceFIPSPolicy element
- FIPS
- <enforceFIPSPolicy> element
- Federal Information Processing Standards (FIPS)
ms.assetid: c35509c4-35cf-43c0-bb47-75e4208aa24e
caps.latest.revision: "7"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: fb8cb1ea4d011eb25aee14ddd53d3dc882f75d8e
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="ltenforcefipspolicygt-element"></a>&lt;enforceFIPSPolicy&gt; elemento
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
|enabled|Atributo necesario.<br /><br /> Especifica si se habilita el cumplimiento de un requisito de configuración de equipo que los algoritmos criptográficos deben ser compatibles con FIPS.|  
  
## <a name="enabled-attribute"></a>Atributo enabled  
  
|Valor|Descripción|  
|-----------|-----------------|  
|`true`|Si el equipo se configura para requerir algoritmos criptográficos que se va a ser compatible con FIPS, ese requisito se aplica. Si una clase que implementa un algoritmo que no es compatible con FIPS, los constructores o `Create` métodos de esa clase lanzan excepciones cuando se ejecutan en ese equipo. Este es el valor predeterminado.|  
|`false`|Algoritmos criptográficos utilizados por la aplicación no se tiene que ser compatible con FIPS, independientemente de la configuración del equipo.|  
  
### <a name="child-elements"></a>Elementos secundarios  
 Ninguno.  
  
### <a name="parent-elements"></a>Elementos primarios  
  
|Elemento|Descripción|  
|-------------|-----------------|  
|`configuration`|Elemento raíz de cada archivo de configuración usado por las aplicaciones de Common Language Runtime y .NET Framework.|  
|`runtime`|Contiene información del enlace del ensamblado y de la recolección de elementos no utilizados.|  
  
## <a name="remarks"></a>Comentarios  
 A partir de .NET Framework 2.0, la creación de clases que implementan algoritmos criptográficos se controla mediante la configuración del equipo. Si el equipo está configurado para requerir algoritmos para ser compatible con FIPS, y una clase que implementa un algoritmo que no es compatible con FIPS, cualquier intento de crear una instancia de esa clase produce una excepción. Constructores de producen una <xref:System.InvalidOperationException> excepción, y `Create` métodos lanzan una <xref:System.Reflection.TargetInvocationException> excepción con interior <xref:System.InvalidOperationException> excepción.  
  
 Si la aplicación se ejecuta en equipos cuyas configuraciones exigir el cumplimiento de FIPS, y la aplicación utiliza un algoritmo que no es compatible con FIPS, puede usar este elemento en el archivo de configuración para evitar que common language runtime (CLR) de exigir el cumplimiento de FIPS. Este elemento se introdujo en la [!INCLUDE[net_v20SP1_long](../../../../../includes/net-v20sp1-long-md.md)].  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se muestra cómo impedir que el CLR de exigir el cumplimiento de FIPS.  
  
```xml  
<configuration>  
    <runtime>  
        <enforceFIPSPolicy enabled="false"/>  
    </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a>Vea también  
 [Esquema de la configuración de Common Language Runtime](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)  
 [Esquema de los archivos de configuración](../../../../../docs/framework/configure-apps/file-schema/index.md)  
 [Modelo de criptografía](../../../../../docs/standard/security/cryptography-model.md)
