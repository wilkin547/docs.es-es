---
title: Seguridad de las propiedades de dependencia
ms.date: 03/30/2017
helpviewer_keywords:
- wrappers [WPF], access
- wrappers [WPF], security
- dependency properties [WPF], security
- security [WPF], wrappers
- validation [WPF], dependency properties
- dependency properties [WPF], access
- security [WPF], dependency properties
ms.assetid: d10150ec-90c5-4571-8d35-84bafa2429a4
ms.openlocfilehash: d9dd9306980b80f7845c10e8c0ccb59f29821245
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "69940840"
---
# <a name="dependency-property-security"></a>Seguridad de las propiedades de dependencia
Por lo general, las propiedades de dependencia deben considerarse propiedades públicas. La naturaleza del sistema de propiedades de [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] impide realizar garantías de seguridad sobre un valor de propiedad de dependencia.  

<a name="AccessSecurity"></a>   
## <a name="access-and-security-of-wrappers-and-dependency-properties"></a>Procedimiento para acceder a los contenedores y las propiedades de dependencia y protegerlos  
 Normalmente, las propiedades de dependencia se implementan junto con propiedades de "contenedor" Common Language Runtime (CLR) que simplifican la obtención o el establecimiento de la propiedad de una instancia. Sin embargo, los contenedores son simplemente métodos útiles que implementan las <xref:System.Windows.DependencyObject.GetValue%2A> llamadas <xref:System.Windows.DependencyObject.SetValue%2A> estáticas y subyacentes que se usan al interactuar con las propiedades de dependencia. Al pensar en él de otra forma, las propiedades se exponen como propiedades de Common Language Runtime (CLR) que se realizan respaldadas por una propiedad de dependencia en lugar de por un campo privado. Los mecanismos de seguridad que se aplican a los contenedores no imitan el comportamiento del sistema de propiedades ni el acceso a la propiedad de dependencia subyacente. La realización de una petición de seguridad en el contenedor solo impedirá el uso del método conveniente, pero no <xref:System.Windows.DependencyObject.GetValue%2A> impedirá llamadas a o. <xref:System.Windows.DependencyObject.SetValue%2A> De forma similar, aplicar un nivel de acceso protegido o privado en los contenedores no proporciona ninguna seguridad efectiva.  
  
 Si está escribiendo sus propias propiedades de dependencia, debe declarar los contenedores y el <xref:System.Windows.DependencyProperty> campo identificador como miembros públicos, de modo que los llamadores no obtengan información engañosa sobre el nivel de acceso real de esa propiedad (debido a que su almacén está se implementa como una propiedad de dependencia).  
  
 En el caso de una propiedad de dependencia personalizada, puede registrar la propiedad como una propiedad de dependencia de solo lectura, lo que proporciona un medio eficaz para impedir que una propiedad sea establecida por cualquier persona que no contenga una referencia a <xref:System.Windows.DependencyPropertyKey> para esa propiedad. Para obtener más información, consulte [Propiedades de dependencia de solo lectura](read-only-dependency-properties.md).  
  
> [!NOTE]
> Declarar un campo <xref:System.Windows.DependencyProperty> de identificador Private no está prohibido y se puede usar para ayudar a reducir el espacio de nombres expuesto inmediatamente de una clase personalizada, pero dicha propiedad no se debe considerar "Private" en el mismo sentido que Common Language las definiciones de lenguaje en tiempo de ejecución (CLR) definen ese nivel de acceso, por las razones descritas en la sección siguiente.  
  
<a name="PropertySystemExposure"></a>   
## <a name="property-system-exposure-of-dependency-properties"></a>Exposición del sistema de propiedades de las propiedades de dependencia  
 Por lo general, no es útil, y es potencialmente engañosa, declarar <xref:System.Windows.DependencyProperty> como cualquier nivel de acceso distinto de Public. Ese valor de nivel de acceso solo impide que alguien pueda obtener una referencia a la instancia de la clase de declaración. Pero hay varios aspectos del sistema de propiedades que devolverán un <xref:System.Windows.DependencyProperty> como medio para identificar una propiedad determinada tal como existe en una instancia de una clase o una instancia de clase derivada, y este identificador todavía se puede usar en una <xref:System.Windows.DependencyObject.SetValue%2A> llamada incluso Si el identificador estático original se declara como NonPublic. Además, <xref:System.Windows.DependencyObject.OnPropertyChanged%2A> los métodos virtuales reciben información de cualquier propiedad de dependencia existente que haya cambiado el valor. Además, el <xref:System.Windows.DependencyObject.GetLocalValueEnumerator%2A> método devuelve identificadores para cualquier propiedad en las instancias con un valor establecido localmente.  
  
### <a name="validation-and-security"></a>Validación y seguridad  
 Aplicar una solicitud a un <xref:System.Windows.DependencyProperty.ValidateValueCallback%2A> y esperar el error de validación en un error de demanda para evitar que se establezca una propiedad no es un mecanismo de seguridad adecuado. La invalidación de valor establecido que se aplica a <xref:System.Windows.DependencyProperty.ValidateValueCallback%2A> través de también se puede suprimir mediante llamadores malintencionados, si esos llamadores funcionan dentro del dominio de aplicación.  
  
## <a name="see-also"></a>Vea también

- [Propiedades de dependencia personalizadas](custom-dependency-properties.md)
