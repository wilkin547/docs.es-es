---
title: "&lt;generatePublisherEvidence&gt; (Elemento) | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - "<generatePublisherEvidence> (elemento)"
  - "generatePublisherEvidence (elemento)"
ms.assetid: 7d208f50-e8d5-4a42-bc1a-1cf3590706a8
caps.latest.revision: 21
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 21
---
# &lt;generatePublisherEvidence&gt; (Elemento)
Especifica si el runtime crea evidencia de <xref:System.Security.Policy.Publisher> para la seguridad de acceso del código \(CAS\).  
  
## Sintaxis  
  
```  
<generatePublisherEvidence    
   enabled="true|false"/>  
```  
  
## Atributos y elementos  
 En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.  
  
### Atributos  
  
|Atributo|Descripción|  
|--------------|-----------------|  
|`enabled`|Atributo necesario.<br /><br /> Especifica si el runtime crea evidencia de <xref:System.Security.Policy.Publisher> .|  
  
## Atributo enabled  
  
|Valor|Descripción|  
|-----------|-----------------|  
|`false`|No crea la evidencia <xref:System.Security.Policy.Publisher> .|  
|`true`|Crea la evidencia <xref:System.Security.Policy.Publisher> .  Éste es el valor predeterminado.|  
  
### Elementos secundarios  
 Ninguno.  
  
### Elementos primarios  
  
|Elemento|Descripción|  
|--------------|-----------------|  
|`configuration`|Elemento raíz de cada archivo de configuración usado por las aplicaciones de Common Language Runtime y .NET Framework.|  
|`runtime`|Contiene información sobre las opciones de inicialización del motor en tiempo de ejecución.|  
  
## Comentarios  
  
> [!NOTE]
>  En [!INCLUDE[net_v40_long](../../../../../includes/net-v40-long-md.md)] y posteriores, este elemento no tiene efecto en los tiempos de carga del ensamblado.  Para obtener más información, consulte la sección "Simplificación de la directiva de seguridad" en [Cambios de seguridad](../../../../../docs/framework/security/security-changes.md).  
  
 Common Language Runtime \(CLR\) intenta comprobar la firma Authenticode en el momento de la carga para crear la evidencia <xref:System.Security.Policy.Publisher> del ensamblado.  Sin embargo, de forma predeterminada, la mayoría de las aplicaciones no necesitan la evidencia <xref:System.Security.Policy.Publisher>.  La directiva CAS estándar no confía en <xref:System.Security.Policy.PublisherMembershipCondition>.  Debe evitar el costo innecesario que supone comprobar la firma del editor a menos que su aplicación se ejecute en un equipo con directivas CAS personalizadas o desee satisfacer las peticiones de <xref:System.Security.Permissions.PublisherIdentityPermission> en un entorno de confianza parcial. \(Las peticiones de permisos de identidad siempre son correctas un entorno de plena confianza.\)  
  
> [!NOTE]
>  Es recomendable que los servicios utilicen el elemento `<generatePublisherEvidence>` para mejorar el rendimiento de inicio.  Utilizar este elemento también puede ayudar a evitar retrasos que podrían provocar agotamiento del tiempo de espera y la cancelación del inicio del servicio.  
  
## Archivo de configuración  
 Este elemento sólo puede utilizarse en el archivo de configuración de la aplicación.  
  
## Ejemplo  
 El ejemplo siguiente muestra cómo utilizar el elemento `<generatePublisherEvidence>` para deshabilitar la comprobación de la directiva de editor CAS para una aplicación.  
  
```  
<configuration>  
    <runtime>  
        <generatePublisherEvidence enabled="false"/>  
    </runtime>  
</configuration>  
```  
  
## Vea también  
 [Esquema de la configuración de Common Language Runtime](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)   
 [Esquema de los archivos de configuración](../../../../../docs/framework/configure-apps/file-schema/index.md)