---
title: "Elemento &lt;assemblyBinding&gt; para &lt;configuration&gt; | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/assemblyBinding"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - "<assemblyBinding> (elemento)"
  - "assemblyBinding (elemento)"
ms.assetid: 6cc55983-b894-449b-8e26-b258e53939cd
caps.latest.revision: 6
author: "mcleblanc"
ms.author: "markl"
manager: "markl"
caps.handback.revision: 6
---
# Elemento &lt;assemblyBinding&gt; para &lt;configuration&gt;
Especifica la directiva de enlace del ensamblado en el nivel de configuración.  
  
## Sintaxis  
  
```  
<assemblyBinding    
   xmlns="urn:schemas-microsoft-com:asm.v1">  
</assemblyBinding>  
```  
  
## Atributos y elementos  
 En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.  
  
### Atributos  
  
|Atributo|Descripción|  
|--------------|-----------------|  
|`xmlns`|Atributo necesario.<br /><br /> Especifica el espacio de nombres XML que requiere el enlace del ensamblado.  Utilice la cadena "urn:schemas\-microsoft\-com:asm.v1" como el valor de este atributo.|  
  
### Elementos secundarios  
  
|Elemento|Descripción|  
|--------------|-----------------|  
|[\<linkedConfiguration\> \(elemento\)](../../../../docs/framework/configure-apps/file-schema/linkedconfiguration-element.md)|Especifica un archivo de configuración para incluirlo.|  
  
### Elementos primarios  
  
|Elemento|Descripción|  
|--------------|-----------------|  
|[Elemento \<configuration\>](../../../../docs/framework/configure-apps/file-schema/configuration-element.md)|Elemento raíz de cada archivo de configuración usado por las aplicaciones de Common Language Runtime y .NET Framework.|  
  
## Comentarios  
 [\<linkedConfiguration\> \(elemento\)](../../../../docs/framework/configure-apps/file-schema/linkedconfiguration-element.md) simplifica la administración de los ensamblados de componentes al permitir que los archivos de configuración de la aplicación incluyan archivos de configuración de ensamblado en ubicaciones conocidas, en lugar de duplicar los valores de configuración de ensamblado.  
  
> [!NOTE]
>  El elemento `<linkedConfiguration>` no se admite en las aplicaciones con manifiestos en paralelo de Windows.  
  
## Ejemplo  
 En el ejemplo de código siguiente se muestra cómo incluir un archivo de configuración en el disco duro local.  
  
```  
<configuration>  
   <assemblyBinding xmlns="urn:schemas-microsoft-com:asm.v1">  
      <linkedConfiguration href="file://c:\Program Files\Contoso\sharedConfig.xml"/>  
   </assemblyBinding>  
</configuration>  
```  
  
## Vea también  
 [Esquema de los archivos de configuración](../../../../docs/framework/configure-apps/file-schema/index.md)