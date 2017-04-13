---
title: "Programar con dominios de aplicaci&#243;n y ensamblados | Microsoft Docs"
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
  - "dominios de la aplicación, programar"
  - "ensamblados [.NET Framework], programar"
  - "programar dominios de aplicación"
  - "programar ensamblados"
ms.assetid: 96d3b8e3-bef8-4da0-9a81-9841e23a94e9
caps.latest.revision: 11
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 11
---
# Programar con dominios de aplicaci&#243;n y ensamblados
Los hosts como Microsoft Internet Explorer, ASP.NET y shell de Windows cargan Common Language Runtime en un proceso, crean un [dominio de aplicación](../../../docs/framework/app-domains/application-domains.md) en ese proceso y, a continuación, cargan y ejecutan el código de usuario en ese dominio de aplicación al ejecutar una aplicación .NET Framework.  En la mayoría de los casos, no es necesario crear dominios de aplicación y cargar ensamblados en ellos porque el host de motor en tiempo de ejecución realiza esas tareas.  
  
 Sin embargo, al crear una aplicación que hospedará al Common Language Runtime, la creación de herramientas o código que se desean descargar mediante programación o de componentes conectables que se pueden descargar y volver a cargar sobre la marcha, significa que se están creando dominios de aplicación propios.  Aunque no vaya a crear un host de motor en tiempo de ejecución, en esta sección se ofrece información importante sobre el trabajo con dominios de aplicación y ensamblados cargados en dichos dominios.  
  
## En esta sección  
 [Temas "Cómo..." sobre dominios de aplicación y ensamblados](../../../docs/framework/app-domains/application-domains-and-assemblies-how-to-topics.md)  
 Proporciona vínculos a todos los temas "Cómo..." de la documentación conceptual sobre la programación con dominios de aplicación y ensamblados.  
  
 [Utilizar dominios de aplicación](../../../docs/framework/app-domains/use.md)  
 Proporciona ejemplos de creación, configuración y utilización de dominios de aplicación.  
  
 [Programar con ensamblados](../../../docs/framework/app-domains/programming-with-assemblies.md)  
 Describe cómo crear, firmar y establecer atributos en los ensamblados.  
  
## Secciones relacionadas  
 [Emitir métodos y ensamblados dinámicos](../../../docs/framework/reflection-and-codedom/emitting-dynamic-methods-and-assemblies.md)  
 Describe la creación de ensamblados dinámicos.  
  
 [Ensamblados en Common Language Runtime](../../../docs/framework/app-domains/assemblies-in-the-common-language-runtime.md)  
 Proporciona una introducción general a los conceptos de los ensamblados.  
  
 [Dominios de aplicación](../../../docs/framework/app-domains/application-domains.md)  
 Proporciona una introducción general a los conceptos de los dominios de aplicación.  
  
 [Información general sobre la reflexión](../../../docs/framework/reflection-and-codedom/reflection.md)  
 Describe cómo se usa la clase **Reflection** para obtener información sobre un ensamblado.