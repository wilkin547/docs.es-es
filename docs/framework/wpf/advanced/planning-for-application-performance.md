---
title: Planear para mejorar el rendimiento de aplicaciones
ms.date: 03/30/2017
helpviewer_keywords:
- applications [WPF], optimizing
- WPF application [WPF], optimizing
ms.assetid: c91bd0c5-a193-46ff-9da1-eb7a3a76a3b3
ms.openlocfilehash: 3fadba2fe8036fc558e18f80bd7cb1ffc977b762
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54632119"
---
# <a name="planning-for-application-performance"></a>Planear para mejorar el rendimiento de aplicaciones
El éxito de alcanzar sus objetivos de rendimiento depende del grado de desarrollar la estrategia de rendimiento. El planeamiento es la primera fase de desarrollo de cualquier producto. En este tema se describe unas reglas muy sencillas para desarrollar una estrategia de buen rendimiento.  
  
## <a name="think-in-terms-of-scenarios"></a>Pensar en términos de escenarios  
 Escenarios le permite centrarse en los componentes fundamentales de la aplicación. Escenarios suelen derivarse de los clientes, así como productos de la competencia. Siempre estudiar a sus clientes y descubra lo que hace realmente les entusiasmados con su producto y sus competidores. Comentarios de sus clientes pueden ayudarle a determinar el escenario principal de la aplicación. Por ejemplo, si está diseñando un componente que se usará en el inicio, es probable que el componente se llamará solo una vez, cuando se inicia la aplicación. Tiempo de inicio se convierte en su escenario clave. Otros ejemplos de escenarios clave podrían ser la velocidad de fotograma deseada para las secuencias de animación, o el máximo permitido para la aplicación de espacio de trabajo.  
  
## <a name="define-goals"></a>Definir objetivos  
 Los objetivos le ayudan a determinar si se está ejecutando una aplicación con mayor rapidez o lentitud. Debe definir objetivos para todos los escenarios. Todos los objetivos de rendimiento que defina deben basarse en las expectativas de sus clientes. Puede ser difícil de rendimiento del conjunto de objetivos desde el principio en el desarrollo de aplicaciones de ciclos, cuando todavía hay muchos problemas sin resolver. Sin embargo, es mejor establecer un objetivo inicial y revisarlo posteriormente que no tener ningún objetivo en absoluto.  
  
## <a name="understand-your-platform"></a>Entender la plataforma  
 Mantener siempre el ciclo de medición, investigar, refinar y corregir durante su ciclo de desarrollo de aplicaciones. Desde el principio hasta el final del ciclo de desarrollo, debe medir el rendimiento de la aplicación en un entorno estable y confiable. Debe evitar la variabilidad causado por factores externos. Por ejemplo, al probar el rendimiento, debe deshabilitar el antivirus y las actualizaciones automáticas, como SMS, los resultados de pruebas para no afectar al rendimiento. Después de medir el rendimiento de la aplicación, deberá identificar los cambios que dará como resultado las mayores mejoras. Una vez que haya modificado la aplicación, inicie el ciclo de nuevo.  
  
## <a name="make-performance-tuning-an-iterative-process"></a>Realizar un proceso iterativo de ajuste del rendimiento  
 Debe conocer el costo relativo de cada característica que se va a usar. Por ejemplo, el uso de reflexión en Microsoft .NET Framework suele ser rendimiento intensivo en cuanto a los recursos informáticos, por lo que desea usarlo con prudencia. Esto no significa para evitar el uso de reflexión, sólo que debe ser cuidadoso al equilibrar los requisitos de rendimiento de la aplicación con las exigencias de rendimiento de las características que usa.  
  
## <a name="build-towards-graphical-richness"></a>Aumentar progresivamente la riqueza gráfica  
 Una técnica clave para la creación de un enfoque escalable para alcanzar [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] rendimiento de la aplicación consiste en aumentar progresivamente la riqueza gráfica y la complejidad. Inicie siempre con el uso de los recursos de rendimiento intensivo mínimos para lograr sus objetivos de escenario. Una vez que se lograr estos objetivos, aumentar progresivamente la riqueza de gráfico usando más características de uso intensivo de rendimiento, teniendo siempre presente los objetivos del escenario. Recuerde que [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] es una plataforma muy completa y proporciona características de gráficos sofisticadas. Utilizando las características de rendimiento intensivo sin pensar puede afectar negativamente el rendimiento general de la aplicación.  
  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] los controles son intrínsecamente extensibles por lo que permite la personalización generalizada de su aspecto, sin modificar su comportamiento de control. Aprovechando las ventajas de estilos, plantillas de datos y plantillas de control, puede crear y gradualmente una personalizables [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] que se adapta a sus requisitos de rendimiento.  
  
## <a name="see-also"></a>Vea también
- [Optimizar WPF: Rendimiento de aplicaciones](../../../../docs/framework/wpf/advanced/optimizing-wpf-application-performance.md)
- [Aprovechar el hardware](../../../../docs/framework/wpf/advanced/optimizing-performance-taking-advantage-of-hardware.md)
- [Presentación y diseño](../../../../docs/framework/wpf/advanced/optimizing-performance-layout-and-design.md)
- [Imágenes y gráficos 2D](../../../../docs/framework/wpf/advanced/optimizing-performance-2d-graphics-and-imaging.md)
- [Comportamiento de objetos](../../../../docs/framework/wpf/advanced/optimizing-performance-object-behavior.md)
- [Recursos de la aplicación](../../../../docs/framework/wpf/advanced/optimizing-performance-application-resources.md)
- [Texto](../../../../docs/framework/wpf/advanced/optimizing-performance-text.md)
- [Enlace de datos](../../../../docs/framework/wpf/advanced/optimizing-performance-data-binding.md)
- [Otras recomendaciones de rendimiento](../../../../docs/framework/wpf/advanced/optimizing-performance-other-recommendations.md)
