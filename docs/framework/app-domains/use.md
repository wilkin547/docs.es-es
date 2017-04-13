---
title: "Utilizar dominios de aplicaci&#243;n | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-bcl"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "dominios de aplicación, acerca de"
  - "Common Language Runtime, dominios de aplicación"
  - "tiempo de ejecución, dominios de aplicación"
ms.assetid: c6d99815-e022-4d2c-9420-1d7ab5b9d504
caps.latest.revision: 15
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 15
---
# Utilizar dominios de aplicaci&#243;n
Los dominios de aplicación proporcionan una unidad de aislamiento para Common Language Runtime.  Se crean y ejecutan dentro de un proceso.  Por lo general, los dominios de aplicación los crea un host de motor en tiempo de ejecución, que es una aplicación encargada de cargar el motor en tiempo de ejecución en un proceso y ejecutar el código de usuario dentro de un dominio de aplicación.  El host de motor en tiempo de ejecución crea un proceso y un dominio de aplicación predeterminado y ejecuta el código administrado en su interior.  Entre los hosts de motor en tiempo de ejecución están ASP.NET, Microsoft Internet Explorer y el shell de Windows.  
  
 Para la mayoría de las aplicaciones, no es necesario crear un dominio de aplicación propio, ya que el host de motor en tiempo de ejecución crea los que sean necesarios.  Sin embargo, puede crear y configurar dominios de aplicación adicionales si su aplicación necesita aislar el código o utilizar y descargar archivos DLL.  
  
## En esta sección  
 [Cómo: Crear un dominio de aplicación](../../../docs/framework/app-domains/how-to-create-an-application-domain.md)  
 Explica cómo se crean dominios de aplicación mediante programación.  
  
 [Cómo: Descargar un dominio de aplicación](../../../docs/framework/app-domains/how-to-unload-an-application-domain.md)  
 Explica cómo se descargan dominios de aplicación mediante programación.  
  
 [Cómo: Configurar un dominio de aplicación](../../../docs/framework/app-domains/how-to-configure-an-application-domain.md)  
 Proporciona una introducción a la configuración de dominios de aplicación.  
  
 [Recuperar información de instalación de un dominio de aplicación](../../../docs/framework/app-domains/retrieve-setup-information.md)  
 Explica cómo se recupera información de instalación de dominios de aplicación.  
  
 [Cómo: Cargar ensamblados en un dominio de aplicación](../../../docs/framework/app-domains/how-to-load-assemblies-into-an-application-domain.md)  
 Explica cómo se carga ensamblados en un dominio de aplicación.  
  
 [Cómo: Obtener información sobre tipos y miembros desde un ensamblado](../../../docs/framework/app-domains/how-to-obtain-type-and-member-information-from-an-assembly.md)  
 Describe cómo se recupera información de ensamblados.  
  
 [Copias sombra de ensamblados](../../../docs/framework/app-domains/shadow-copy-assemblies.md)  
 Describe cómo las copias sombra permiten las actualizaciones de los ensamblados mientras están en uso, y cómo configurar las copias sombra.  
  
 [Cómo: Recibir notificaciones de excepciones de primera oportunidad](../../../docs/framework/app-domains/how-to-receive-first-chance-exception-notifications.md)  
 Explica cómo recibir una notificación sobre una excepción que se produce antes de que Common Language Runtime comience a buscar controladores de excepciones.  
  
 [Resolver cargas de ensamblado](../../../docs/framework/app-domains/resolve-assembly-loads.md)  
 Proporciona orientación sobre cómo utilizar el evento <xref:System.AppDomain.AssemblyResolve?displayProperty=fullName> para resolver los errores de carga de ensamblados.  
  
## Referencia  
 <xref:System.AppDomain>  
 Representa un dominio de aplicación.  Proporciona métodos para crear y controlar dominios de aplicación.  
  
## Secciones relacionadas  
 [Ensamblados en Common Language Runtime](../../../docs/framework/app-domains/assemblies-in-the-common-language-runtime.md)  
 Proporciona información general sobre las funciones que desempeñan los ensamblados.  
  
 [Programar con ensamblados](../../../docs/framework/app-domains/programming-with-assemblies.md)  
 Describe cómo crear, firmar y establecer atributos en los ensamblados.  
  
 [Emitting Dynamic Methods and Assemblies](../../../docs/framework/reflection-and-codedom/emitting-dynamic-methods-and-assemblies.md)  
 Describe la creación de ensamblados dinámicos.  
  
 [Dominios de aplicación](../../../docs/framework/app-domains/application-domains.md)  
 Proporciona una introducción general a los conceptos de los dominios de aplicación.  
  
 [Información general sobre la reflexión](../../../docs/framework/reflection-and-codedom/reflection.md)  
 Describe cómo se usa la clase **Reflection** para obtener información sobre un ensamblado.