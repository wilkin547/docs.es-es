---
title: "&lt;enforceFIPSPolicy&gt; (elemento) | Microsoft Docs"
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
  - "<enforceFIPSPolicy> (elemento)"
  - "enforceFIPSPolicy (elemento)"
  - "Estándares federales de procesamiento de la información (FIPS)"
  - "FIPS"
ms.assetid: c35509c4-35cf-43c0-bb47-75e4208aa24e
caps.latest.revision: 7
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 7
---
# &lt;enforceFIPSPolicy&gt; (elemento)
Especifica si se va a exigir el cumplimiento del requisito de configuración de equipo por el que los algoritmos criptográficos deben ser compatibles con los estándares federales de procesamiento de información \(FIPS\).  
  
## Sintaxis  
  
```  
<enforceFIPSPolicy enabled="true|false" />  
```  
  
## Atributos y elementos  
 En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.  
  
### Atributos  
  
|Atributo|Descripción|  
|--------------|-----------------|  
|enabled|Atributo necesario.<br /><br /> Especifica si se va a exigir el cumplimiento del requisito de configuración de equipo por el que los algoritmos criptográficos deben ser conformes a FIPS.|  
  
## Atributo enabled  
  
|Valor|Descripción|  
|-----------|-----------------|  
|`true`|Si el equipo está configurado para requerir que los algoritmos criptográficos sean conformes a FIPS, se aplica dicho requisito.  Si una clase implementa un algoritmo no conforme a FIPS, los constructores o métodos `Create` para esa clase producen excepciones cuando se ejecutan en ese equipo.  Éste es el valor predeterminado.|  
|`false`|No es necesario que los algoritmos criptográficos utilizados por la aplicación cumplan el estándar FIPS, independientemente de la configuración del equipo.|  
  
### Elementos secundarios  
 Ninguno.  
  
### Elementos primarios  
  
|Elemento|Descripción|  
|--------------|-----------------|  
|`configuration`|Elemento raíz de cada archivo de configuración usado por las aplicaciones de Common Language Runtime y .NET Framework.|  
|`runtime`|Contiene información del enlace del ensamblado y de la recolección de elementos no utilizados.|  
  
## Comentarios  
 A partir de .NET Framework 2.0, la creación de clases que implementan algoritmos criptográficos está controlada por la configuración del equipo.  Si el equipo está configurado para exigir los algoritmos conformes a FIPS y una clase implementa un algoritmo que no es conforme a FIPS, cualquier intento de crear una instancia de esa clase produce una excepción.  Los constructores producen una excepción <xref:System.InvalidOperationException> y los métodos `Create` producen una excepción <xref:System.Reflection.TargetInvocationException> con una excepción <xref:System.InvalidOperationException> interna.  
  
 Si la aplicación se ejecuta en equipos cuya configuración requiere el cumplimiento de FIPS y dicha aplicación usa un algoritmo no compatible con este estándar, puede usar este elemento en el archivo de configuración para evitar que Common Language Runtime \(CLR\) aplique el cumplimiento de FIPS.  Este elemento se incorporó en [!INCLUDE[net_v20SP1_long](../../../../../includes/net-v20sp1-long-md.md)].  
  
## Ejemplo  
 En el ejemplo siguiente se muestra cómo evitar que CLR aplique el cumplimiento de FIPS.  
  
```  
<configuration>  
    <runtime>  
        <enforceFIPSPolicy enabled="false"/>  
    </runtime>  
</configuration>  
```  
  
## Vea también  
 [Esquema de la configuración de Common Language Runtime](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)   
 [Esquema de los archivos de configuración](../../../../../docs/framework/configure-apps/file-schema/index.md)   
 [Cryptography Model](../../../../../docs/standard/security/cryptography-model.md)