---
title: "Elemento &lt;requiredRuntime&gt; | Microsoft Docs"
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
  - "http://schemas.microsoft.com/.NetConfiguration/v2.0#requiredRuntime"
  - "http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/startup/requiredRuntime"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - "&lt;requiredRuntime&gt; (elemento)"
  - "etiquetas contenedoras, &lt;requiredRuntime&gt; (elemento)"
  - "requiredRuntime (elemento)"
ms.assetid: 9fa1639e-beb8-43be-b7a4-12f7b229c34b
caps.latest.revision: 11
author: "mcleblanc"
ms.author: "markl"
manager: "markl"
caps.handback.revision: 11
---
# Elemento &lt;requiredRuntime&gt;
Especifica que la aplicación sólo es compatible con la versión 1.0 de Common Language Runtime.  
  
## Sintaxis  
  
```  
  
   <requiredRuntime    
version="runtime version"  
safemode="true|false"/>  
```  
  
## Atributos y elementos  
 En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.  
  
### Atributos  
  
|Atributo|Descripción|  
|--------------|-----------------|  
|`version`|Atributo opcional.<br /><br /> Un valor de cadena que especifica la versión de .NET Framework con la que es compatible la aplicación.  El valor de cadena debe coincidir con el nombre de directorio situado bajo la carpeta raíz de la instalación de .NET Framework.  No se analiza el contenido del valor de cadena.|  
|`safemode`|Atributo opcional.<br /><br /> Especifica si el código de inicio del motor de ejecución busca en el Registro para determinar la versión del motor de ejecución.|  
  
## Atributo safemode  
  
|Valor|Descripción|  
|-----------|-----------------|  
|`false`|El código de inicio del runtime busca en el Registro.  Este es el valor predeterminado.|  
|`true`|El código de inicio del runtime no busca en el Registro.|  
  
### Elementos secundarios  
 Ninguno.  
  
### Elementos primarios  
  
|Elemento|Descripción|  
|--------------|-----------------|  
|`configuration`|Elemento raíz de cada archivo de configuración usado por las aplicaciones de Common Language Runtime y .NET Framework.|  
|`startup`|Contiene el elemento `<requiredRuntime>`.|  
  
## Comentarios  
 Las aplicaciones compiladas para ser compatibles únicamente con la versión 1.0 del runtime deben usar el elemento `<requiredRuntime>`.  Las aplicaciones compiladas utilizando la versión 1.1 o posterior del runtime deben utilizar el elemento `<supportedRuntime>`.  
  
> [!NOTE]
>  Si utiliza la función [CorBindToRuntimeByCfg](../../../../../ocs/framework/unmanaged-api/hosting/corbindtoruntimebycfg-function.md) para especificar el archivo de configuración, debe utilizar el elemento `<requiredRuntime>` para todas las versiones del runtime.  Se omite el elemento `<supportedRuntime>` al usar [CorBindToRuntimeByCfg](../../../../../ocs/framework/unmanaged-api/hosting/corbindtoruntimebycfg-function.md).  
  
 La cadena del atributo `version` debe coincidir con el nombre de la carpeta de instalación de la versión especificada de .NET Framework.  Esta cadena no se interpreta.  Si el código de inicio del motor de ejecución no encuentra una carpeta coincidente, no carga el motor de ejecución, el código de inicio muestra un mensaje de error y cierra la aplicación.  
  
> [!NOTE]
>  El código de inicio de una aplicación que está hospedada en Microsoft Internet Explorer omite el elemento `<requiredRuntime>`.  
  
## Ejemplo  
 En el siguiente ejemplo se muestra cómo especificar la versión del motor de ejecución en un archivo de configuración.  
  
```  
<configuration>  
   <startup>  
      <requiredRuntime version="v1.0.3705" safemode="true"/>  
   </startup>  
</configuration>  
```  
  
## Vea también  
 [Esquema de la configuración de inicio](../../../../../docs/framework/configure-apps/file-schema/startup/index.md)   
 [Esquema de los archivos de configuración](../../../../../docs/framework/configure-apps/file-schema/index.md)   
 [\<PaveOver\> Specifying Which Runtime Version to Use](http://msdn.microsoft.com/es-es/c376208d-980d-42b4-865b-fbe0d9cc97c2)