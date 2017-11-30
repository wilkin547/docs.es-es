---
title: Planear para mejorar el rendimiento de aplicaciones
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- applications [WPF], optimizing
- WPF application [WPF], optimizing
ms.assetid: c91bd0c5-a193-46ff-9da1-eb7a3a76a3b3
caps.latest.revision: "6"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: f47f56e28064c852e5d8f721bdb3a0f73172c12a
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="planning-for-application-performance"></a>Planear para mejorar el rendimiento de aplicaciones
El éxito de alcanzar los objetivos de rendimiento depende del grado de desarrollo de la estrategia de rendimiento. Planificación es la primera fase de desarrollo de cualquier producto. Este tema describen algunas reglas muy simples para desarrollar una estrategia de un buen rendimiento.  
  
## <a name="think-in-terms-of-scenarios"></a>Pensar en términos de escenarios  
 Escenarios le permitirá centrarse en los componentes fundamentales de la aplicación. Los escenarios suelen derivarse de los clientes, así como los productos de la competencia. Siempre estudiar a los clientes y a averiguar lo que realmente hace que sean ansiosos por sobre el producto y sus competidores. Comentarios de los clientes pueden ayudarle a determinar el escenario principal de la aplicación. Por ejemplo, si está diseñando un componente que se usará en el inicio, es probable que el componente se llamará solo una vez, cuando se inicia la aplicación. Tiempo de inicio se convierte en el escenario clave. Otros ejemplos de escenarios clave podrían ser la velocidad de fotogramas deseado para las secuencias de animación, o el máximo permitido para la aplicación del espacio de trabajo.  
  
## <a name="define-goals"></a>Definir los objetivos  
 Objetivos de ayudan a determinar si se está ejecutando una aplicación con mayor rapidez o lentitud. Debe definir objetivos para todos los escenarios. Todos los objetivos de rendimiento que defina deben basarse en las expectativas de los clientes. Puede ser difícil de rendimiento del conjunto de objetivos desde el principio para el desarrollo de aplicaciones de ciclos, cuando todavía hay muchos problemas sin resolver. Sin embargo, es mejor establecer un objetivo inicial y revisarlo posteriormente que no tener ningún objetivo en absoluto.  
  
## <a name="understand-your-platform"></a>Entender la plataforma  
 Mantenga siempre el ciclo de medir, investigar, refinar y corregir durante el ciclo de desarrollo de aplicaciones. Desde el principio hasta el final del ciclo de desarrollo, debe medir el rendimiento de la aplicación en un entorno estable y confiable. Debe evitar las variaciones producidas por factores externos. Por ejemplo, al probar el rendimiento, debe deshabilitar los programas antivirus o las actualizaciones automáticas como SMS, para no afectan al rendimiento de resultados de pruebas. Una vez que se mide el rendimiento de su aplicación, debe identificar los cambios que dará como resultado de las mejoras más importantes. Una vez que haya modificado la aplicación, inicie el ciclo de nuevo.  
  
## <a name="make-performance-tuning-an-iterative-process"></a>Realizar un proceso iterativo de optimización del rendimiento  
 Debe saber el costo relativo de cada característica que se va a usar. Por ejemplo, el uso de reflexión en [!INCLUDE[TLA#tla_avalonwinfx](../../../../includes/tlasharptla-avalonwinfx-md.md)] suele ser rendimiento intensivo en cuanto a recursos de proceso, por lo que desea usarlo con prudencia. Esto no significa para evitar el uso de reflexión, sólo que debe tener cuidado equilibrar los requisitos de rendimiento de la aplicación con las exigencias de rendimiento de las características que usa.  
  
## <a name="build-towards-graphical-richness"></a>Aumentar progresivamente la riqueza gráfica  
 Una técnica clave para crear un enfoque escalable para lograr [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] rendimiento de la aplicación consiste en aumentar progresivamente la riqueza gráfica y la complejidad. Inicie siempre con el uso de los recursos de rendimiento intensivo mínimos para lograr los objetivos del escenario. Una vez lograr estos objetivos, aumentar progresivamente la riqueza gráfica mediante el uso de más características de uso intensivo de rendimiento, teniendo siempre presente los objetivos del escenario. Recuerde que [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] es una plataforma muy amplio y proporciona características gráficas muy ricas. Usar las características de uso intensivo de rendimiento sin pensar puede afectar negativamente el rendimiento general de la aplicación.  
  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]los controles son intrínsecamente extensibles por lo que permite la personalización generalizada de su aspecto, sin modificar su comportamiento de control. Aprovechando las ventajas de estilos, plantillas de datos y plantillas de control, puede crear y gradualmente un [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] que se adapta a sus requisitos de rendimiento.  
  
## <a name="see-also"></a>Vea también  
 [Optimizar WPF: Rendimiento de aplicaciones](../../../../docs/framework/wpf/advanced/optimizing-wpf-application-performance.md)  
 [Aprovechar el hardware](../../../../docs/framework/wpf/advanced/optimizing-performance-taking-advantage-of-hardware.md)  
 [Presentación y diseño](../../../../docs/framework/wpf/advanced/optimizing-performance-layout-and-design.md)  
 [Imágenes y gráficos 2D](../../../../docs/framework/wpf/advanced/optimizing-performance-2d-graphics-and-imaging.md)  
 [Comportamiento de objetos](../../../../docs/framework/wpf/advanced/optimizing-performance-object-behavior.md)  
 [Recursos de la aplicación](../../../../docs/framework/wpf/advanced/optimizing-performance-application-resources.md)  
 [Text](../../../../docs/framework/wpf/advanced/optimizing-performance-text.md)  
 [Enlace de datos](../../../../docs/framework/wpf/advanced/optimizing-performance-data-binding.md)  
 [Otras recomendaciones de rendimiento](../../../../docs/framework/wpf/advanced/optimizing-performance-other-recommendations.md)
