---
title: "Elemento &lt;bindingRedirect&gt; | Microsoft Docs"
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
  - "http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/runtime/assemblyBinding/dependentAssembly/bindingRedirect"
  - "http://schemas.microsoft.com/.NetConfiguration/v2.0#bindingRedirect"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - "<bindingRedirect> (elemento)"
  - "bindingRedirect (elemento)"
  - "etiquetas contenedoras, <bindingRedirect> (elemento)"
ms.assetid: 67784ecd-9663-434e-bd6a-26975e447ac0
caps.latest.revision: 12
author: "mcleblanc"
ms.author: "markl"
manager: "markl"
caps.handback.revision: 11
---
# Elemento &lt;bindingRedirect&gt;
Redirige una versión de ensamblado a otra versión.  
  
## Sintaxis  
  
```  
  
   <bindingRedirect    
oldVersion="existing assembly version"  
newVersion="new assembly version"/>  
```  
  
## Atributos y elementos  
 En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.  
  
### Atributos  
  
|Atributo|Descripción|  
|--------------|-----------------|  
|`oldVersion`|Atributo necesario.<br /><br /> Especifica la versión del ensamblado solicitada originalmente.  El formato de número de versión del ensamblado es *major.minor.build.revision*.  Los valores válidos para cada una de las partes de este número de versión van del 0 al 65535.<br /><br /> También se puede especificar un intervalo de versiones con el siguiente formato:<br /><br /> *n.n.n.n \- n.n.n.n*|  
|`newVersion`|Atributo necesario.<br /><br /> Especifica la versión del ensamblado que se va a usar, en lugar de la versión solicitada originalmente, con el formato: *n.n.n.n*<br /><br /> Este valor puede especificar una versión anterior a `oldVersion`.|  
  
### Elementos secundarios  
  
|Elemento|Descripción|  
|--------------|-----------------|  
|Ninguno||  
  
### Elementos primarios  
  
|Elemento|Descripción|  
|--------------|-----------------|  
|`assemblyBinding`|Contiene información sobre la redirección de versiones de ensamblado y las ubicaciones de ensamblados.|  
|`configuration`|Elemento raíz de cada archivo de configuración usado por las aplicaciones de Common Language Runtime y .NET Framework.|  
|`dependentAssembly`|Encapsula la directiva de enlace y la ubicación de cada ensamblado.  Use un elemento dependentAssembly para cada ensamblado.|  
|`runtime`|Contiene información del enlace del ensamblado y de la recolección de elementos no utilizados.|  
  
## Comentarios  
 Al compilar una aplicación .NET Framework en un ensamblado con nombre seguro, la aplicación usa esa versión del ensamblado en tiempo de ejecución de forma predeterminada, aunque haya disponible otra versión posterior.  No obstante, la aplicación puede configurarse para ejecutarla en una versión más reciente del ensamblado.  Para obtener información detallada sobre cómo el runtime usa estos archivos para determinar la versión del ensamblado que se va a emplear, vea el tema sobre [cómo el runtime busca ensamblados](../../../../../docs/framework/deployment/how-the-runtime-locates-assemblies.md).  
  
 Se puede redirigir más de una versión de ensamblado con la inclusión de varios elementos `bindingRedirect` en un elemento `dependentAssembly`.  También puede redirigirse de una versión más reciente a una versión anterior del ensamblado.  
  
 Para realizar una redirección de enlaces de ensamblado de forma explícita en un archivo de configuración, se precisa permiso de seguridad.  Esto se aplica a la redirección de los ensamblados de .NET Framework y de los ensamblados de otros proveedores.  El permiso se otorga estableciendo la marca de [BindingRedirects](frlrfSystemSecurityPermissionsSecurityPermissionFlagClassTopic) en la [clase SecurityPermission](frlrfSystemSecurityPermissionsSecurityPermissionClassTopic).  Para obtener más información, vea [Permiso de seguridad para la redirección de enlace de ensamblados](../../../../../docs/framework/configure-apps/assembly-binding-redirection-security-permission.md).  
  
## Ejemplo  
 En el ejemplo siguiente se muestra cómo redirigir una versión de ensamblado a otra versión.  
  
```  
<configuration>  
   <runtime>  
      <assemblyBinding xmlns="urn:schemas-microsoft-com:asm.v1">  
         <dependentAssembly>  
            <assemblyIdentity name="myAssembly"  
                              publicKeyToken="32ab4ba45e0a69a1"  
                              culture="neutral" />  
            <bindingRedirect oldVersion="1.0.0.0"  
                             newVersion="2.0.0.0"/>  
         </dependentAssembly>  
      </assemblyBinding>  
   </runtime>  
</configuration>  
```  
  
## Vea también  
 [Esquema de la configuración de Common Language Runtime](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)   
 [Esquema de los archivos de configuración](../../../../../docs/framework/configure-apps/file-schema/index.md)   
 [Redirigir versiones de ensamblado](../../../../../docs/framework/configure-apps/redirect-assembly-versions.md)