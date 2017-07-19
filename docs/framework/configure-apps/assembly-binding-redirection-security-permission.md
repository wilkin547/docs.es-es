---
title: "Permiso de seguridad para la redirecci&#243;n de enlaces de ensamblados | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
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
  - "ensamblados [.NET Framework], redirección de enlaces"
  - "ejecución en paralelo, redirección de enlaces de ensamblados"
ms.assetid: 24a5cdff-7ed9-4195-93f3-edf6899019fc
caps.latest.revision: 9
author: "mcleblanc"
ms.author: "markl"
manager: "markl"
caps.handback.revision: 8
---
# Permiso de seguridad para la redirecci&#243;n de enlaces de ensamblados
Para realizar una redirección de enlaces de ensamblado de forma explícita en un archivo de configuración, se precisa permiso de seguridad.  Esto se aplica a la redirección de los ensamblados de .NET Framework y de los ensamblados de otros proveedores.  El permiso se otorga estableciendo la marca de [BindingRedirects](frlrfSystemSecurityPermissionsSecurityPermissionFlagClassTopic) en la [clase SecurityPermission](frlrfSystemSecurityPermissionsSecurityPermissionClassTopic).  De forma predeterminada, los ensamblados administrados no tienen ningún permiso.  
  
 El permiso de seguridad se concede para las aplicaciones que se ejecutan en la zona de confianza \(equipo local\) y en la zona de la intranet.  La redirección de enlace de ensamblados está totalmente prohibida en las aplicaciones que se ejecutan en la zona de Internet.  
  
 Cuando la redirección de un ensamblado se realiza en un archivo de directivas del editor que controla el editor de componentes, o en un archivo de configuración del equipo que controla el administrador, no se requiere ningún permiso.  Sin embargo, el permiso se requiere para que una aplicación explícitamente omita la directiva de editor mediante el elemento de [\<publisherPolicy apply\="no"\/\>](../../../docs/framework/configure-apps/file-schema/runtime/publisherpolicy-element.md) en el archivo de configuración de la aplicación.  
  
 La tabla siguiente muestra los valores de seguridad predeterminados para el marcador **BindingRedirects**.  
  
|Zona|Valor del marcador BindingRedirects|  
|----------|-----------------------------------------|  
|Zona de confianza \(equipo local\)|**ON**|  
|Zona de la intranet|**ON**|  
|Zona de Internet|**OFF**|  
|Zonas que no son de confianza|**OFF**|  
  
 Un administrador puede cambiar estos valores de seguridad para admitir o rechazar escenarios específicos en un equipo determinado.  No hay ninguna herramienta que permita cambiar el valor predeterminado del marcador **BindingRedirects**; el administrador debe editarlo manualmente en el archivo Security.config del equipo del usuario.  
  
## Vea también  
 [Publisher Policy Files and Side\-by\-Side Execution](http://msdn.microsoft.com/es-es/97a042be-4d72-40c3-91c0-76fd36bdf133)   
 [Cómo: Habilitar y deshabilitar redireccionamiento de enlaces automático](../../../docs/framework/configure-apps/how-to-enable-and-disable-automatic-binding-redirection.md)   
 [Ejecución simultánea](../../../docs/framework/deployment/side-by-side-execution.md)