---
title: "Esquema de los archivos de configuraci&#243;n de .NET Framework | Microsoft Docs"
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
  - "configuración de las aplicaciones de .NET Framework, esquema de configuración"
  - "app.config (archivos), esquema"
  - "archivos de configuración de la aplicación, esquema"
  - "desarrollo de aplicaciones [.NET Framework], esquema"
  - "esquema de configuración [.NET Framework]"
  - "valores de configuración [.NET Framework], aplicaciones"
  - "etiquetas contenedoras"
  - "archivos de configuración enterprisesec"
  - "enterprisesec.config (archivos)"
  - "archivos de configuración del equipo"
  - "machine.config (archivos)"
  - "valores de configuración del esquema"
  - "esquemas, valores de configuración"
  - "seguridad [.NET Framework], archivos de configuración"
  - "security.config (archivos)"
  - "XML correcto"
  - "etiquetas XML"
ms.assetid: 69003d39-dc8a-460c-a6be-e6d93e690b38
caps.latest.revision: 20
author: "mcleblanc"
ms.author: "markl"
manager: "markl"
caps.handback.revision: 18
---
# Esquema de los archivos de configuraci&#243;n de .NET Framework
Los archivos de configuración son archivos XML estándar que se pueden utilizar para cambiar configuraciones y establecer directivas para las aplicaciones.  El esquema de configuración de .NET Framework se compone de elementos que se pueden usar en los archivos de configuración para controlar el comportamiento de las aplicaciones.  La tabla de contenido de esta sección refleja la jerarquía de esquema para el inicio, el tiempo de ejecución, la red y otros tipos de valores de configuración.  
  
 Para obtener información sobre los tipos, formato y ubicación de los archivos de configuración, vea el artículo [Configurar aplicaciones](../../../../docs/framework/configure-apps/index.md).  Para editar los archivos de configuración directamente, es conveniente estar familiarizado con XML.  
  
> [!IMPORTANT]
>  En los atributos y etiquetas XML de los archivos de configuración se distingue entre mayúsculas y minúsculas.  
  
## En esta sección  
 [Elemento \<configuration\>](../../../../docs/framework/configure-apps/file-schema/configuration-element.md)  
 Describe el elemento `<configuration>`, que es el elemento de nivel superior de todos los archivos de configuración.  
  
 [\<assemblyBinding\> \(elemento\)](../../../../docs/framework/configure-apps/file-schema/assemblybinding-element-for-configuration.md)  
 Especifica la directiva de enlace del ensamblado en el nivel de configuración.  
  
 [\<linkedConfiguration\> \(elemento\)](../../../../docs/framework/configure-apps/file-schema/linkedconfiguration-element.md)  
 Especifica un archivo de configuración para incluirlo.  
  
 [Esquema de la configuración de inicio](../../../../docs/framework/configure-apps/file-schema/startup/index.md)  
 Describe los elementos que especifican la versión utilizada de Common Language Runtime.  
  
 [Esquema de la configuración de Common Language Runtime](../../../../docs/framework/configure-apps/file-schema/runtime/index.md)  
 Describe los elementos que configura el enlace del ensamblado y el comportamiento del motor de ejecución.  
  
 [Esquema de la configuración de red](../../../../docs/framework/configure-apps/file-schema/network/index.md)  
 Describe los elementos que especifican cómo se conecta .NET Framework a Internet.  
  
 [Esquema de la configuración de criptografía](../../../../docs/framework/configure-apps/file-schema/cryptography/index.md)  
 Describe los elementos que asignan nombres de algoritmo descriptivos a las clases que implementan algoritmos criptográficos.  
  
 [Esquema de secciones de configuración](../../../../docs/framework/configure-apps/file-schema/configuration-sections-schema.md)  
 Describe los elementos necesarios para crear y utilizar las secciones de configuración de valores personalizados.  
  
 [Esquema de la configuración de seguimiento y depuración](../../../../docs/framework/configure-apps/file-schema/trace-debug/index.md)  
 Describe los elementos que especifican los modificadores y agentes de escucha de seguimiento.  
  
 [Esquema de configuración de compilador y proveedor de lenguaje](../../../../docs/framework/configure-apps/file-schema/compiler/index.md)  
 Describe los elementos que especifican la configuración del compilador para los proveedores de lenguaje disponibles.  
  
 [Esquema de la configuración de la aplicación](../../../../docs/framework/configure-apps/file-schema/application-settings-schema.md)  
 Describe los elementos que habilitan una aplicación de formularios Windows Forms o ASP.NET para almacenar y recuperar los valores del ámbito de usuario y del ámbito de aplicación.  
  
 [Esquema de configuración web](../../../../docs/framework/configure-apps/file-schema/web/index.md)  
 Describe todos los elementos del esquema de configuración web, que incluye elementos para configurar cómo funciona ASP.NET con una aplicación host como IIS.  Se usa en los archivos aspnet.config.  
  
## Secciones relacionadas  
 [Remoting Settings Schema](http://msdn.microsoft.com/es-es/dc2d1e62-9af7-4ca1-99fd-98b93bb4db9e)  
 Describe los elementos que configuran las aplicaciones cliente y servidor que implementa la comunicación remota.  
  
 [Esquema de configuración de ASP.NET](http://msdn.microsoft.com/library/b5ysx397\(v=vs.100\).aspx)  
 Describe los elementos que controlan el comportamiento de las aplicaciones web ASP.NET.  
  
 [Web Services Settings Schema](http://msdn.microsoft.com/es-es/f84d6d55-1add-4eb7-ae46-33df5833ea2e)  
 Describe los elementos que controlan el comportamiento de servicios Web de ASP.NET y sus clientes.  
  
 [Configuring .NET Framework Apps](http://msdn.microsoft.com/es-es/d789b592-fcb5-4e3d-8ac9-e0299adaaa42)  
 Describe cómo configurar la seguridad, el enlace del ensamblado y la comunicación remota de .NET Framework.