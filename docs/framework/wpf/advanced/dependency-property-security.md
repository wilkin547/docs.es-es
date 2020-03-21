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
ms.openlocfilehash: f5640b348ccd68819052f58756489489371862d0
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79186390"
---
# <a name="dependency-property-security"></a>Seguridad de las propiedades de dependencia
Por lo general, las propiedades de dependencia deben considerarse propiedades públicas. La naturaleza del sistema de propiedades de [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] impide realizar garantías de seguridad sobre un valor de propiedad de dependencia.  

<a name="AccessSecurity"></a>
## <a name="access-and-security-of-wrappers-and-dependency-properties"></a>Procedimiento para acceder a los contenedores y las propiedades de dependencia y protegerlos  
 Normalmente, las propiedades de dependencia se implementan junto con las propiedades de Common Language Runtime (CLR) "envoltorio" que simplifican la obtención o configuración de la propiedad desde una instancia. Pero los contenedores son realmente solo métodos de conveniencia que implementan las llamadas subyacentes <xref:System.Windows.DependencyObject.GetValue%2A> y <xref:System.Windows.DependencyObject.SetValue%2A> estáticas que se usan al interactuar con propiedades de dependencia. Pensando en ello de otra manera, las propiedades se exponen como propiedades de Common Language Runtime (CLR) que están respaldadas por una propiedad de dependencia en lugar de por un campo privado. Los mecanismos de seguridad que se aplican a los contenedores no imitan el comportamiento del sistema de propiedades ni el acceso a la propiedad de dependencia subyacente. Colocar una demanda de seguridad en el contenedor sólo impedirá el <xref:System.Windows.DependencyObject.GetValue%2A> uso <xref:System.Windows.DependencyObject.SetValue%2A>del método de conveniencia, pero no impedirá las llamadas a o . De forma similar, aplicar un nivel de acceso protegido o privado en los contenedores no proporciona ninguna seguridad efectiva.  
  
 Si está escribiendo sus propias propiedades de dependencia, debe declarar los contenedores y el <xref:System.Windows.DependencyProperty> campo de identificador como miembros públicos, para que los llamadores no obtengan información engañosa sobre el nivel de acceso verdadero de esa propiedad (debido a que su almacén se implementa como una propiedad de dependencia).  
  
 Para una propiedad de dependencia personalizada, puede registrar su propiedad como una propiedad de dependencia de solo lectura y esto proporciona <xref:System.Windows.DependencyPropertyKey> un medio eficaz de impedir que cualquier persona que no tenga una referencia a esa propiedad establezca una propiedad. Para obtener más información, consulte [Propiedades de dependencia de solo lectura](read-only-dependency-properties.md).  
  
> [!NOTE]
> Declarar un <xref:System.Windows.DependencyProperty> campo de identificador privado no está prohibido y se puede usar para ayudar a reducir el espacio de nombres expuesto inmediatamente de una clase personalizada, pero dicha propiedad no debe considerarse "privada" en el mismo sentido que las definiciones de lenguaje de Common Language Runtime (CLR) definen ese nivel de acceso, por razones descritas en la sección siguiente.  
  
<a name="PropertySystemExposure"></a>
## <a name="property-system-exposure-of-dependency-properties"></a>Exposición del sistema de propiedades de las propiedades de dependencia  
 Por lo general, no es útil, y es <xref:System.Windows.DependencyProperty> potencialmente engañoso, declarar un nivel de acceso distinto del público. Ese valor de nivel de acceso solo impide que alguien pueda obtener una referencia a la instancia de la clase de declaración. Pero hay varios aspectos del sistema de <xref:System.Windows.DependencyProperty> propiedades que devolverán a como medio de identificar una propiedad determinada tal como existe en una <xref:System.Windows.DependencyObject.SetValue%2A> instancia de una clase o una instancia de clase derivada, y este identificador todavía se puede usar en una llamada incluso si el identificador estático original se declara como no público. Además, <xref:System.Windows.DependencyObject.OnPropertyChanged%2A> los métodos virtuales reciben información de cualquier propiedad de dependencia existente que haya cambiado el valor. Además, <xref:System.Windows.DependencyObject.GetLocalValueEnumerator%2A> el método devuelve identificadores para cualquier propiedad en instancias con un valor establecido localmente.  
  
### <a name="validation-and-security"></a>Validación y seguridad  
 Aplicar una demanda <xref:System.Windows.DependencyProperty.ValidateValueCallback%2A> a a y esperar el error de validación en un error de demanda para evitar que se establezca una propiedad no es un mecanismo de seguridad adecuado. Los llamadores malintencionados <xref:System.Windows.DependencyProperty.ValidateValueCallback%2A> también podrían suprimir la invalidación de valor establecido que se aplica ría también si los llamadores malintencionados, si esos llamadores operan dentro del dominio de aplicación.  
  
## <a name="see-also"></a>Consulte también

- [Propiedades de dependencia personalizadas](custom-dependency-properties.md)
