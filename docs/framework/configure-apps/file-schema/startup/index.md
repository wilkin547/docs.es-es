---
title: "Esquema de la configuraci&#243;n de inicio | Microsoft Docs"
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
  - "esquema de configuración [.NET Framework], configuración de inicio"
  - "configuración de inicio del esquema"
  - "esquema de la configuración de inicio"
ms.assetid: 03de6972-442a-4648-9f3e-efa654e3b949
caps.latest.revision: 10
author: "mcleblanc"
ms.author: "markl"
manager: "markl"
caps.handback.revision: 10
---
# Esquema de la configuraci&#243;n de inicio
En la configuración de inicio se especifica la versión de Common Language Runtime que debe ejecutar la aplicación.  
  
|Elemento|Descripción|  
|--------------|-----------------|  
|[\<requiredRuntime\>](../../../../../docs/framework/configure-apps/file-schema/startup/requiredruntime-element.md)|Especifica que la aplicación sólo es compatible con la versión 1.0 de Common Language Runtime.  Las aplicaciones compiladas con la versión 1.1 deben utilizar el elemento de **\<supportedRuntime\>** .|  
|[\<supportedRuntime\>](../../../../../docs/framework/configure-apps/file-schema/startup/supportedruntime-element.md)|Especifica qué versiones de Common Language Runtime admite la aplicación.|  
|[\<startup\>](../../../../../docs/framework/configure-apps/file-schema/startup/startup-element.md)|Contiene los elementos de **\<requiredRuntime\>** y de **\<supportedRuntime\>** .|  
  
## Vea también  
 [Esquema de los archivos de configuración](../../../../../docs/framework/configure-apps/file-schema/index.md)   
 [\<PaveOver\> Specifying Which Runtime Version to Use](http://msdn.microsoft.com/es-es/c376208d-980d-42b4-865b-fbe0d9cc97c2)