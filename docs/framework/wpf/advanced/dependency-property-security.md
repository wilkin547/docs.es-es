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
ms.openlocfilehash: 85806ee9fb01cd2ca07697230c46a8847fdf8c6a
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "62053553"
---
# <a name="dependency-property-security"></a>Seguridad de las propiedades de dependencia
Por lo general, las propiedades de dependencia deben considerarse propiedades públicas. La naturaleza del sistema de propiedades de [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] impide realizar garantías de seguridad sobre un valor de propiedad de dependencia.  

<a name="AccessSecurity"></a>   
## <a name="access-and-security-of-wrappers-and-dependency-properties"></a>Procedimiento para acceder a los contenedores y las propiedades de dependencia y protegerlos  
 Normalmente, las propiedades de dependencia se implementan junto con las propiedades [!INCLUDE[TLA#tla_clr](../../../../includes/tlasharptla-clr-md.md)] del "contenedor", que permiten obtener o establecer fácilmente la propiedad de una instancia. Pero los contenedores son métodos de conveniencia realidad, que implementan subyacente <xref:System.Windows.DependencyObject.GetValue%2A> y <xref:System.Windows.DependencyObject.SetValue%2A> las llamadas estáticas que se utilizan al interactuar con las propiedades de dependencia. Visto de otro modo, las propiedades se exponen como propiedades [!INCLUDE[TLA#tla_clr](../../../../includes/tlasharptla-clr-md.md)] que están respaldadas por una propiedad de dependencia en lugar de un campo privado. Los mecanismos de seguridad que se aplican a los contenedores no imitan el comportamiento del sistema de propiedades ni el acceso a la propiedad de dependencia subyacente. Al colocar una petición de seguridad en el contenedor solo impedirá el uso del método útil, pero no impedirá que las llamadas a <xref:System.Windows.DependencyObject.GetValue%2A> o <xref:System.Windows.DependencyObject.SetValue%2A>. De forma similar, aplicar un nivel de acceso protegido o privado en los contenedores no proporciona ninguna seguridad efectiva.  
  
 Si escribe sus propias propiedades de dependencia, debe declarar los contenedores y los <xref:System.Windows.DependencyProperty> identificador de campo como miembros públicos, para que los llamadores no obtengan información confusa sobre el verdadero nivel de acceso de esa propiedad (debido a su almacén que se va a implementado como una propiedad de dependencia).  
  
 Para una propiedad de dependencia personalizada, puede registrar la propiedad como una propiedad de dependencia de solo lectura y proporciona un medio eficaz de evitar una propiedad que se va a establecer cualquiera que no contiene una referencia a la <xref:System.Windows.DependencyPropertyKey> para esa propiedad. Para obtener más información, consulte [Propiedades de dependencia de solo lectura](read-only-dependency-properties.md).  
  
> [!NOTE]
>  Declarar un <xref:System.Windows.DependencyProperty> privado del campo de identificador no está prohibido y es posible que se puede usar para ayudar a reducir el espacio de nombres expuesto inmediatamente de una clase personalizada, pero dicha propiedad no debe considerarse "privada" en el mismo sentido que la [!INCLUDE[TLA#tla_clr](../../../../includes/tlasharptla-clr-md.md)] definiciones de lenguaje definen ese nivel de acceso, por razones descritas en la sección siguiente.  
  
<a name="PropertySystemExposure"></a>   
## <a name="property-system-exposure-of-dependency-properties"></a>Exposición del sistema de propiedades de las propiedades de dependencia  
 No resulta útil por lo general, y es potencialmente puede inducir a error, declare un <xref:System.Windows.DependencyProperty> como cualquier acceso de nivel aparte público. Ese valor de nivel de acceso solo impide que alguien pueda obtener una referencia a la instancia de la clase de declaración. Sin embargo, hay varios aspectos del sistema de propiedades que va a devolver un <xref:System.Windows.DependencyProperty> como medio para identificar una propiedad determinada tal como existe en una instancia de una clase o una instancia de la clase derivada, y este identificador es todavía se puede utilizar en un <xref:System.Windows.DependencyObject.SetValue%2A> incluso llamar Si el identificador estático original se declara como no público. Además, <xref:System.Windows.DependencyObject.OnPropertyChanged%2A> métodos virtuales reciben información de cualquier propiedad de dependencia existente cuyo valor haya cambiado. Además, el <xref:System.Windows.DependencyObject.GetLocalValueEnumerator%2A> método devuelve identificadores para cualquier propiedad en instancias con establecida localmente un valor.  
  
### <a name="validation-and-security"></a>Validación y seguridad  
 Aplicar una petición para un <xref:System.Windows.DependencyProperty.ValidateValueCallback%2A> y se espera el error de validación en un error de demanda para impedir que una propiedad que se va a establecer no es un mecanismo de seguridad adecuada. Invalidación del valor establecido que se aplica a través de <xref:System.Windows.DependencyProperty.ValidateValueCallback%2A> también la pueden suprimir llamadores malintencionados, si estos operan dentro del dominio de aplicación.  
  
## <a name="see-also"></a>Vea también

- [Propiedades de dependencia personalizadas](custom-dependency-properties.md)
