---
title: "Traza de la red en .NET Framework | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - "capturar el tráfico de red"
  - "depurar [.NET Framework], traza de la red"
  - "implementar aplicaciones [.NET Framework], tráfico de red"
  - "Internet, traza de la red"
  - "invocaciones de método"
  - "métodos, traza de la red"
  - "Recursos de red"
  - "traza de la red"
  - "traza de la red, acerca de la traza de la red"
  - "red, traza de la red"
  - "Redes"
  - "resultado, traza de la red"
  - "seguimiento de depuración habilitado"
  - "seguimiento [.NET Framework], red"
  - "seguimiento de tráfico"
ms.assetid: e993b7c3-087f-45d8-9c02-9dded936d804
caps.latest.revision: 9
author: "mcleblanc"
ms.author: "markl"
manager: "markl"
caps.handback.revision: 9
---
# Traza de la red en .NET Framework
El seguimiento de red de .NET Framework proporciona acceso a información sobre las invocaciones de métodos y el tráfico de red generado por una aplicación administrada.  Esta característica es útil para depurar las aplicaciones en desarrollo y para analizar las aplicaciones implementadas.  El resultado proporcionado por la traza de la red se puede personalizar para admitir diferentes escenarios de uso en tiempo de desarrollo y en un entorno de producción.  
  
 Para habilitar el seguimiento de red en .NET Framework, debe seleccionar un destino para el resultado del seguimiento y agregar opciones de configuración de seguimiento de la red al archivo de configuración de la aplicación o del equipo.  Para obtener descripciones de los archivos de configuración y de cómo se utilizan, vea [Archivos de configuración](../../../docs/framework/configure-apps/index.md).  Para obtener información sobre cómo habilitar el seguimiento de red, vea [Habilitar el seguimiento de red](../../../docs/framework/network-programming/enabling-network-tracing.md).  Para obtener información sobre los valores que se deben agregar al archivo de configuración, vea [Cómo: Configurar el seguimiento de red](../../../docs/framework/network-programming/how-to-configure-network-tracing.md).  
  
 Cuando se habilita el seguimiento, puede capturar la información de seguimiento generada por las clases de **System.Net**.  Los miembros de la clase de red que generan información de seguimiento incluyen la siguiente nota en la sección Comentarios de la documentación de la biblioteca de clases de .NET Framework:  
  
> [!NOTE]
>  Este miembro genera información de seguimiento cuando se habilita el seguimiento de red en la aplicación.  Para obtener más información, vea Seguimiento de red.  
  
## Vea también  
 [Habilitación del seguimiento de red](../../../docs/framework/network-programming/enabling-network-tracing.md)   
 [Cómo: Configurar la traza de la red](../../../docs/framework/network-programming/how-to-configure-network-tracing.md)   
 [Interpretar el seguimiento de red](../../../docs/framework/network-programming/interpreting-network-tracing.md)   
 [Introduction to Instrumentation and Tracing](http://msdn.microsoft.com/es-es/e924e57c-33cf-4b0e-9e7f-a45d13e38f2c)