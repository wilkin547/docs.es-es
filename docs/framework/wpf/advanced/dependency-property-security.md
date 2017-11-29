---
title: Seguridad de las propiedades de dependencia
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- wrappers [WPF], access
- wrappers [WPF], security
- dependency properties [WPF], security
- security [WPF], wrappers
- validation [WPF], dependency properties
- dependency properties [WPF], access
- security [WPF], dependency properties
ms.assetid: d10150ec-90c5-4571-8d35-84bafa2429a4
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: c8c1dc0ea45efe32e36b649d92111fff3d5f61a7
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/22/2017
---
# <a name="dependency-property-security"></a>Seguridad de las propiedades de dependencia
Por lo general, las propiedades de dependencia deben considerarse propiedades públicas. La naturaleza del sistema de propiedades de [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] impide realizar garantías de seguridad sobre un valor de propiedad de dependencia.  
  
  
<a name="AccessSecurity"></a>   
## <a name="access-and-security-of-wrappers-and-dependency-properties"></a>Procedimiento para acceder a los contenedores y las propiedades de dependencia y protegerlos  
 Normalmente, las propiedades de dependencia se implementan junto con las propiedades [!INCLUDE[TLA#tla_clr](../../../../includes/tlasharptla-clr-md.md)] del "contenedor", que permiten obtener o establecer fácilmente la propiedad de una instancia. Pero los contenedores son prácticos solo los métodos que implementan subyacente <xref:System.Windows.DependencyObject.GetValue%2A> y <xref:System.Windows.DependencyObject.SetValue%2A> llamadas estáticas que se utilizan al interactuar con las propiedades de dependencia. Visto de otro modo, las propiedades se exponen como propiedades [!INCLUDE[TLA#tla_clr](../../../../includes/tlasharptla-clr-md.md)] que están respaldadas por una propiedad de dependencia en lugar de un campo privado. Los mecanismos de seguridad que se aplican a los contenedores no imitan el comportamiento del sistema de propiedades ni el acceso a la propiedad de dependencia subyacente. Colocar una petición de seguridad en el contenedor únicamente impedirá el uso del método útil pero no impedirá que las llamadas a <xref:System.Windows.DependencyObject.GetValue%2A> o <xref:System.Windows.DependencyObject.SetValue%2A>. De forma similar, aplicar un nivel de acceso protegido o privado en los contenedores no proporciona ninguna seguridad efectiva.  
  
 Si va a escribir sus propias propiedades de dependencia, debe declarar los contenedores y los <xref:System.Windows.DependencyProperty> identificador de campo como miembros públicos, para que los llamadores no obtengan información engañosa sobre el verdadero nivel de acceso de esa propiedad (debido a su almacén que se va a se implementa como una propiedad de dependencia).  
  
 Para una propiedad de dependencia personalizada, puede registrar la propiedad como una propiedad de dependencia de solo lectura y se proporcionan un medio eficaz de evitar una propiedad que se va a establecer cualquiera que no contiene una referencia a la <xref:System.Windows.DependencyPropertyKey> para esa propiedad. Para obtener más información, consulte [Propiedades de dependencia de solo lectura](../../../../docs/framework/wpf/advanced/read-only-dependency-properties.md).  
  
> [!NOTE]
>  Declarar un <xref:System.Windows.DependencyProperty> identificador campo privado no está prohibido y es posible que se puede utilizar para ayudar a reducir el espacio de nombres expuesto inmediatamente de una clase personalizada, pero dicha propiedad no debería considerarse "privada" en el mismo sentido como el [!INCLUDE[TLA#tla_clr](../../../../includes/tlasharptla-clr-md.md)] definiciones de lenguaje definen ese nivel de acceso, por razones descritas en la sección siguiente.  
  
<a name="PropertySystemExposure"></a>   
## <a name="property-system-exposure-of-dependency-properties"></a>Exposición del sistema de propiedades de las propiedades de dependencia  
 No se suelen ser útil, y es potencialmente puede inducir a error, declare un <xref:System.Windows.DependencyProperty> como cualquier tipo de acceso de nivel no sea público. Ese valor de nivel de acceso solo impide que alguien pueda obtener una referencia a la instancia de la clase de declaración. Pero hay varios aspectos del sistema de propiedades que va a devolver un <xref:System.Windows.DependencyProperty> como medio para identificar una propiedad determinada, tal y como existe en una instancia de una clase o una instancia de la clase derivada, y este identificador es todavía puede usar en un <xref:System.Windows.DependencyObject.SetValue%2A> llamar incluso Si el identificador estático original se declara como no público. Además, <xref:System.Windows.DependencyObject.OnPropertyChanged%2A> métodos virtuales reciban información de cualquier propiedad de dependencia existente cuyo valor haya cambiado. Además, la <xref:System.Windows.DependencyObject.GetLocalValueEnumerator%2A> método devuelve los identificadores de cualquier propiedad en instancias con establecida localmente un valor.  
  
### <a name="validation-and-security"></a>Validación y seguridad  
 Aplicar una petición para un <xref:System.Windows.DependencyProperty.ValidateValueCallback%2A> y espera el error de validación en un error de petición para impedir que se está estableciendo una propiedad no es un mecanismo de seguridad adecuada. Invalidación del valor establecido que se aplica a través de <xref:System.Windows.DependencyProperty.ValidateValueCallback%2A> también se puede suprimir los llamadores malintencionados, si los llamadores funcionan dentro del dominio de aplicación.  
  
## <a name="see-also"></a>Vea también  
 [Propiedades de dependencia personalizadas](../../../../docs/framework/wpf/advanced/custom-dependency-properties.md)
