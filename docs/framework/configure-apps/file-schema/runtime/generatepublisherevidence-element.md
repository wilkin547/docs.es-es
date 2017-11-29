---
title: '&lt;generatePublisherEvidence&gt; elemento'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- generatePublisherEvidence element
- <generatePublisherEvidence> element
ms.assetid: 7d208f50-e8d5-4a42-bc1a-1cf3590706a8
caps.latest.revision: "21"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 78293c396687f9c0c99ffdfbe94cf1f3c548289d
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="ltgeneratepublisherevidencegt-element"></a>&lt;generatePublisherEvidence&gt; elemento
Especifica si el runtime crea <xref:System.Security.Policy.Publisher> evidencia de seguridad de acceso del código (CAS).  
  
 \<configuration>  
\<en tiempo de ejecución >  
\<generatePublisherEvidence >  
  
## <a name="syntax"></a>Sintaxis  
  
```xml  
<generatePublisherEvidence    
   enabled="true|false"/>  
```  
  
## <a name="attributes-and-elements"></a>Atributos y elementos  
 En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.  
  
### <a name="attributes"></a>Atributos  
  
|Atributo|Descripción|  
|---------------|-----------------|  
|`enabled`|Atributo necesario.<br /><br /> Especifica si el runtime crea <xref:System.Security.Policy.Publisher> evidencia.|  
  
## <a name="enabled-attribute"></a>Atributo enabled  
  
|Valor|Descripción|  
|-----------|-----------------|  
|`false`|No crea <xref:System.Security.Policy.Publisher> evidencia.|  
|`true`|Crea <xref:System.Security.Policy.Publisher> evidencia. Este es el valor predeterminado.|  
  
### <a name="child-elements"></a>Elementos secundarios  
 Ninguno.  
  
### <a name="parent-elements"></a>Elementos primarios  
  
|Elemento|Descripción|  
|-------------|-----------------|  
|`configuration`|Elemento raíz de cada archivo de configuración usado por las aplicaciones de Common Language Runtime y .NET Framework.|  
|`runtime`|Contiene información sobre las opciones de inicialización del motor en tiempo de ejecución.|  
  
## <a name="remarks"></a>Comentarios  
  
> [!NOTE]
>  En el [!INCLUDE[net_v40_long](../../../../../includes/net-v40-long-md.md)] y versiones posteriores, este elemento no tiene ningún efecto en los tiempos de carga de ensamblado. Para obtener más información, vea la sección "Simplificación de la directiva de seguridad" en [cambios de seguridad](../../../../../docs/framework/security/security-changes.md).  
  
 Common language runtime (CLR) intenta comprobar la firma Authenticode en tiempo de carga para crear <xref:System.Security.Policy.Publisher> evidencia del ensamblado. Sin embargo, de forma predeterminada, la mayoría de las aplicaciones no es necesario <xref:System.Security.Policy.Publisher> evidencia. La directiva CAS estándar no se basa en el <xref:System.Security.Policy.PublisherMembershipCondition>. Debe evitar el costo de inicio innecesarias asociado a comprobar la firma del editor a menos que la aplicación se ejecuta en un equipo con la directiva CAS personalizada o pretende satisfacer las demandas de <xref:System.Security.Permissions.PublisherIdentityPermission> en un entorno de confianza parcial. (Las peticiones de permisos de identidad siempre correctamente en un entorno de plena confianza).  
  
> [!NOTE]
>  Se recomienda que usan los servicios el `<generatePublisherEvidence>` elemento para mejorar el rendimiento de inicio.  Uso de este elemento también puede ayudar a evitar los retrasos que pueden provocar un tiempo de espera y la cancelación del inicio del servicio.  
  
## <a name="configuration-file"></a>Archivo de configuración  
 Este elemento se puede usar únicamente en el archivo de configuración de aplicación.  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se muestra cómo utilizar el `<generatePublisherEvidence>` elemento que se va a deshabilitar la comprobación de directiva de edición de entidades emisoras de certificados para una aplicación.  
  
```xml  
<configuration>  
    <runtime>  
        <generatePublisherEvidence enabled="false"/>  
    </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a>Vea también  
 [Esquema de la configuración de Common Language Runtime](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)  
 [Esquema de los archivos de configuración](../../../../../docs/framework/configure-apps/file-schema/index.md)
