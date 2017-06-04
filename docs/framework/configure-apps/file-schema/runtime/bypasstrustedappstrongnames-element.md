---
title: "Elemento &lt;bypassTrustedAppStrongNames&gt; | Microsoft Docs"
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
  - "<bypassTrustedAppStrongNames> (elemento)"
  - "bypassTrustedAppStrongNames (elemento)"
  - "característica de omisión de nombres seguros"
  - "ensamblados con nombre seguro, cargar en dominios de aplicación de confianza"
ms.assetid: 71b2ebf6-3843-41e2-ad52-ffa5cd083a40
caps.latest.revision: 18
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 18
---
# Elemento &lt;bypassTrustedAppStrongNames&gt;
Especifica si se va a omitir la validación de nombres seguros en ensamblados de plena confianza que se cargan en un objeto <xref:System.AppDomain> de plena confianza.  
  
## Sintaxis  
  
```  
<bypassTrustedAppStrongNames    
   enabled="true|false"/>  
```  
  
## Atributos y elementos  
 En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.  
  
### Atributos  
  
|Atributo|Descripción|  
|--------------|-----------------|  
|`enabled`|Atributo necesario.<br /><br /> Especifica si la característica de omisión que impide que se validen los nombres seguros de los ensamblados de plena confianza está habilitada.  Cuando esta característica está habilitada, no se valida la corrección de los nombres seguros cuando se carga el ensamblado.  El valor predeterminado es `true`.|  
  
## Atributo enabled  
  
|Valor|Descripción|  
|-----------|-----------------|  
|`true`|Las firmas con nombre seguro de ensamblados de plena confianza no se validan cuando los ensamblados se cargan en un objeto <xref:System.AppDomain> de plena confianza.  Éste es el valor predeterminado.|  
|`false`|Las firmas con nombre seguro de ensamblados de plena confianza se validan cuando los ensamblados se cargan en un objeto <xref:System.AppDomain> de plena confianza.  La firma con nombre seguro se comprueba únicamente para validar la exactitud de la firma; no se compara con otros nombres seguros en busca de coincidencias.|  
  
### Elementos secundarios  
 Ninguno.  
  
### Elementos primarios  
  
|Elemento|Descripción|  
|--------------|-----------------|  
|`configuration`|Elemento raíz de cada archivo de configuración usado por las aplicaciones de Common Language Runtime y .NET Framework.|  
|`runtime`|Contiene información del enlace del ensamblado y de la recolección de elementos no utilizados.|  
  
## Comentarios  
 La característica de omisión de nombres seguros evita la sobrecarga que supone la comprobación de firmas con nombre seguro de ensamblados de plena confianza.  
  
 La característica de omisión se aplica a cualquier ensamblado que esté firmado con un nombre seguro y que tenga las siguientes características:  
  
-   Sea de plena confianza y no tenga la evidencia <xref:System.Security.Policy.StrongName> \(que tenga, por ejemplo, la evidencia de zona `MyComputer`\).  
  
-   Esté cargado en un objeto <xref:System.AppDomain> de plena confianza.  
  
-   Se haya cargado desde una ubicación situada bajo la propiedad <xref:System.AppDomainSetup.ApplicationBase%2A> de ese objeto <xref:System.AppDomain>.  
  
-   No se haya firmado con retraso.  
  
> [!NOTE]
>  Si la característica de omisión se desactivó en todas las aplicaciones del equipo mediante una clave del Registro, este valor del archivo de configuración no tiene ningún efecto.  Para obtener más información, vea [Cómo: Deshabilitar la característica de omisión de nombres seguros](../../../../../docs/framework/app-domains/how-to-disable-the-strong-name-bypass-feature.md).  
  
## Ejemplo  
 En el ejemplo siguiente se muestra cómo se especifica el comportamiento que valida la firma con nombre seguro de ensamblados de plena confianza.  
  
```  
<configuration>  
   <runtime>  
      <bypassTrustedAppStrongNames enabled="false"/>  
   </runtime>  
</configuration>  
```  
  
## Vea también  
 [Esquema de la configuración de Common Language Runtime](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)   
 [Esquema de los archivos de configuración](../../../../../docs/framework/configure-apps/file-schema/index.md)   
 [Cómo: Deshabilitar la característica de omisión de nombres seguros](../../../../../docs/framework/app-domains/how-to-disable-the-strong-name-bypass-feature.md)