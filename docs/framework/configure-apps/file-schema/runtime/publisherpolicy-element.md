---
title: "Elemento &lt;publisherPolicy&gt; | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/runtime/assemblyBinding/publisherPolicy"
  - "http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/runtime/assemblyBinding/dependentAssembly/publisherPolicy"
  - "http://schemas.microsoft.com/.NetConfiguration/v2.0#publisherPolicy"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - "<publisherPolicy> (elemento)"
  - "etiquetas contenedoras, <publisherPolicy> (elemento)"
  - "publisherPolicy (elemento)"
ms.assetid: 4613407e-d0a8-4ef2-9f81-a6acb9fdc7d4
caps.latest.revision: 18
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 17
---
# Elemento &lt;publisherPolicy&gt;
Especifica si el motor de ejecución aplica la directiva de editor.  
  
## Sintaxis  
  
```  
  
<publisherPolicy apply="yes|no"/>  
```  
  
## Atributos y elementos  
 En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.  
  
### Atributos  
  
|Atributo|Descripción|  
|--------------|-----------------|  
|`apply`|Especifica si se aplica la directiva de editor.|  
  
## aplicar atributo  
  
|Valor|Descripción|  
|-----------|-----------------|  
|`yes`|Aplica la directiva de editor.  Ésta es la configuración predeterminada.|  
|`no`|No se aplica la directiva de editor.|  
  
### Elementos secundarios  
 Ninguno.  
  
### Elementos primarios  
  
|Elemento|Descripción|  
|--------------|-----------------|  
|`configuration`|Elemento raíz de cada archivo de configuración usado por las aplicaciones de Common Language Runtime y .NET Framework.|  
|`runtime`|Contiene información del enlace del ensamblado y de la recolección de elementos no utilizados.|  
  
## Comentarios  
 Cuando un proveedor lanza una nueva versión de un ensamblado, puede incluir una directiva de editor para que las aplicaciones que utilizan una versión anterior utilicen a partir de ese momento la nueva versión.  Para especificar si solicitar directiva de editor un ensamblado determinado, el elemento de **\<publisherPolicy\>** en el elemento de **\<dependentAssembly\>** .  
  
 El valor predeterminado del atributo **apply** es **yes**.  Si se establece el atributo **apply** en **no**, se invalida cualquier valor **yes** anterior de un ensamblado.  
  
 El permiso se requiere para que una aplicación explícitamente omita la directiva de editor mediante el elemento de [\<de publisherPolicy de apply\= " no”\/\>](../../../../../docs/framework/configure-apps/file-schema/runtime/publisherpolicy-element.md) en el archivo de configuración de la aplicación.  El permiso se otorga estableciendo la marca de [BindingRedirects](frlrfSystemSecurityPermissionsSecurityPermissionFlagClassTopic) en la [clase SecurityPermission](frlrfSystemSecurityPermissionsSecurityPermissionClassTopic).  Para obtener más información, vea [Permiso de seguridad para la redirección de enlace de ensamblados](../../../../../docs/framework/configure-apps/assembly-binding-redirection-security-permission.md).  
  
## Ejemplo  
 En el ejemplo siguiente se desactiva la directiva de editor para el ensamblado `myAssembly`.  
  
```  
<configuration>  
   <runtime>  
      <assemblyBinding xmlns="urn:schemas-microsoft-com:asm.v1">  
         <dependentAssembly>  
            <assemblyIdentity name="myAssembly"  
                                    publicKeyToken="32ab4ba45e0a69a1"  
                                    culture="neutral" />  
            <publisherPolicy apply="no"/>  
         </dependentAssembly>  
      </assemblyBinding>  
   </runtime>  
</configuration>  
```  
  
## Vea también  
 [Esquema de la configuración de Common Language Runtime](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)   
 [Esquema de los archivos de configuración](../../../../../docs/framework/configure-apps/file-schema/index.md)   
 [Cómo el motor en tiempo de ejecución ubica ensamblados](../../../../../docs/framework/deployment/how-the-runtime-locates-assemblies.md)   
 [Redirigir versiones de ensamblado](../../../../../docs/framework/configure-apps/redirect-assembly-versions.md)