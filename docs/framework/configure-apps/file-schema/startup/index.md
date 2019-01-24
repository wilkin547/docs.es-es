---
title: Esquema de configuración de inicio
ms.date: 03/30/2017
helpviewer_keywords:
  - startup settings schema
  - schema startup settings
  - 'configuration schema [.NET Framework], startup settings'
ms.assetid: 03de6972-442a-4648-9f3e-efa654e3b949
author: mcleblanc
ms.author: markl
---
# <a name="startup-settings-schema"></a>Esquema de configuración de inicio

La configuración de inicio especifica la versión de Common Language Runtime que debe ejecutar la aplicación.  
  
|Elemento|Descripción|  
|-------------|-----------------|  
|[\<requiredRuntime>](requiredruntime-element.md)|Especifica que la aplicación solo admite la versión 1.0 de Common Language Runtime. Las aplicaciones compiladas con la versión 1.1 en tiempo de ejecución deberían usar el elemento **\<supportedRuntime>**.|  
|[\<supportedRuntime>](supportedruntime-element.md)|Especifica qué versiones de Common Language Runtime admite la aplicación.|  
|[\<startup>](startup-element.md)|Contiene los elementos **\<requiredRuntime>** y **\<supportedRuntime>**.|  
  
## <a name="see-also"></a>Vea también

- [Esquema de los archivos de configuración](../index.md)
- [Cómo: Configuración de una aplicación para que admita .NET Framework 4 o versiones posteriores](../../../migration-guide/how-to-configure-an-app-to-support-net-framework-4-or-4-5.md)
