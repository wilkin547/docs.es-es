---
title: "Planear para mejorar el rendimiento de aplicaciones | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-wpf"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "aplicaciones, optimizar"
  - "aplicación WPF, optimizar"
ms.assetid: c91bd0c5-a193-46ff-9da1-eb7a3a76a3b3
caps.latest.revision: 6
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 6
---
# Planear para mejorar el rendimiento de aplicaciones
La consecución de los objetivos de rendimiento depende de lo bien que desarrolle su estrategia de rendimiento.  La planeación es la primera fase del desarrollo de cualquier producto.  En este tema se describen algunas reglas muy simples para desarrollar una estrategia de rendimiento acertada.  
  
## Pensar en términos de escenarios  
 Los escenarios pueden ayudarle a centrarse en los componentes críticos de la aplicación.  Los escenarios suelen derivarse de los clientes, así como de los productos de la competencia.  Estudie siempre a sus clientes y averigüe qué es lo que les interesa de su producto y de los productos de la competencia.  Los comentarios de sus clientes pueden ayudarle a determinar el escenario principal de la aplicación.  Por ejemplo, si va a diseñar un componente que se usará en el inicio, es probable que solamente se llame a este componente una vez, cuando se inicia la aplicación.  En este caso, el escenario clave es el momento del inicio.  Otros ejemplos de escenarios clave podrían ser la velocidad de los fotogramas en las secuencias de animación o el espacio de trabajo máximo permitido para la aplicación.  
  
## Definir los objetivos  
 Los objetivos le ayudan a determinar si el rendimiento de una aplicación es superior o inferior.  Debe definir objetivos para todos los escenarios.  Todos los objetivos de rendimiento que defina deberán basarse en las expectativas de sus clientes.  Puede ser difícil establecer los objetivos de rendimiento desde el principio del ciclo de programación, cuando todavía quedan muchos problemas sin resolver.  Sin embargo, es mejor fijar un objetivo inicial y revisarlo posteriormente que no tener ningún objetivo en absoluto.  
  
## Entender la plataforma  
 Mantenga en todo momento el ciclo de medir, investigar, refinar y corregir durante el ciclo de programación de la aplicación.  Desde el principio hasta el final del ciclo de programación, es preciso medir el rendimiento de la aplicación en un entorno confiable y estable.  Debe evitar las variaciones producidas por factores externos.  Por ejemplo, al realizar pruebas de rendimiento, debe deshabilitar los antivirus y las actualizaciones automáticas, como SMS, para que no afecten a los resultados de dichas pruebas.  Después de medir el rendimiento de la aplicación, deberá identificar los cambios que darán lugar a las mayores mejoras.  Cuando haya modificado la aplicación, inicie de nuevo el ciclo.  
  
## Convertir el ajuste del rendimiento en un proceso reiterativo  
 Debe conocer el costo relativo de cada característica que va a utilizar.  Por ejemplo, el uso de la reflexión en [!INCLUDE[TLA#tla_avalonwinfx](../../../../includes/tlasharptla-avalonwinfx-md.md)] suele afectar intensamente al rendimiento por lo que se refiere a los recursos informáticos, de modo que es importante utilizarla juiciosamente.  Esto no significa que haya que evitar el uso de la reflexión, únicamente que debe asegurarse de equilibrar los requisitos de rendimiento de la aplicación con las exigencias de rendimiento de las características que utilice.  
  
## Aumentar progresivamente la riqueza gráfica  
 Una técnica clave para crear un enfoque escalable que permita lograr un rendimiento adecuado de las aplicaciones de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] es aumentar progresivamente la riqueza gráfica y la complejidad.  Empiece siempre utilizando los recursos que menos afectan al rendimiento para lograr los objetivos del escenario.  Cuando haya logrado estos objetivos, aumente progresivamente la riqueza gráfica mediante características que afectan con mayor intensidad al rendimiento, teniendo siempre presentes los objetivos del escenario.  Recuerde que [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] es una plataforma extremadamente completa que proporciona características gráficas muy ricas.  El uso irreflexivo de características que afectan intensamente al rendimiento puede impactar negativamente en el rendimiento de la aplicación en su conjunto.  
  
 La extensibilidad es inherente a los controles de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], lo que permite una personalización generalizada de su aspecto sin modificar su comportamiento de control.  Aprovechando los estilos, las plantillas de datos y las plantillas de control puede crear y modificar gradualmente una [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] personalizable adaptada a los requisitos de rendimiento.  
  
## Vea también  
 [Optimizar WPF: Rendimiento de aplicaciones](../../../../docs/framework/wpf/advanced/optimizing-wpf-application-performance.md)   
 [Aprovechar el hardware](../../../../docs/framework/wpf/advanced/optimizing-performance-taking-advantage-of-hardware.md)   
 [Presentación y diseño](../../../../docs/framework/wpf/advanced/optimizing-performance-layout-and-design.md)   
 [Imágenes y gráficos GDI\+](../../../../docs/framework/wpf/advanced/optimizing-performance-2d-graphics-and-imaging.md)   
 [Comportamiento de objetos](../../../../docs/framework/wpf/advanced/optimizing-performance-object-behavior.md)   
 [Recursos de aplicación](../../../../docs/framework/wpf/advanced/optimizing-performance-application-resources.md)   
 [Text](../../../../docs/framework/wpf/advanced/optimizing-performance-text.md)   
 [Enlace de datos](../../../../docs/framework/wpf/advanced/optimizing-performance-data-binding.md)   
 [Otras recomendaciones de rendimiento](../../../../docs/framework/wpf/advanced/optimizing-performance-other-recommendations.md)