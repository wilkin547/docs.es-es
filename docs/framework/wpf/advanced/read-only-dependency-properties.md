---
title: Propiedades de dependencia de sólo lectura
ms.date: 03/30/2017
helpviewer_keywords:
- dependency properties [WPF], read-only
- read-only dependency properties [WPF]
ms.assetid: f23d6ec9-3780-4c09-a2ff-b2f0a2deddf1
ms.openlocfilehash: 45385e3e3eb8e756008a0d9ef560e061f9a31964
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59162428"
---
# <a name="read-only-dependency-properties"></a>Propiedades de dependencia de sólo lectura
En este tema se describen las propiedades de dependencia de solo lectura, incluidas las propiedades de dependencia de solo lectura existentes y los escenarios y las técnicas para crear una propiedad de dependencia de solo lectura personalizada.  

<a name="prerequisites"></a>   
## <a name="prerequisites"></a>Requisitos previos  
 En este tema se supone que entiende los escenarios básicos de la implementación de una propiedad de dependencia y cómo se aplican los metadatos a una propiedad de dependencia personalizada. Consulte [Propiedades de dependencia personalizadas](custom-dependency-properties.md) y [Metadatos de las propiedades de dependencia](dependency-property-metadata.md) para obtener contexto.  
  
<a name="existing"></a>   
## <a name="existing-read-only-dependency-properties"></a>Propiedades de dependencia de solo lectura existentes  
 Algunas de las propiedades de dependencia definidas en el marco de [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] son de solo lectura. La razón típica para especificar una propiedad de dependencia de solo lectura es que son propiedades que se deben usar para determinar el estado, si ese estado depende de muchos factores, pero, simplemente, establecer la propiedad en ese estado no es deseable desde una perspectiva de diseño de la interfaz de usuario. Por ejemplo, la propiedad <xref:System.Windows.UIElement.IsMouseOver%2A> en realidad, se muestra el estado según la entrada de ratón. Cualquier intento de establecer este valor mediante programación y sortear la entrada de ratón real sería imprevisible y daría lugar a incoherencias.  
  
 Al no poder establecerse, las propiedades de dependencia de solo lectura no son adecuadas para muchos de los escenarios para los que las propiedades de dependencia suelen ofrecen una solución, es decir: enlace de datos, aplicar directamente estilos a un valor, validación, animación, herencia). A pesar de que no se pueden establecer, las propiedades de solo lectura todavía tienen algunas funciones adicionales que admiten las propiedades de dependencia en el sistema de propiedades. La funcionalidad restante más importante es que la propiedad de dependencia de solo lectura aún puede usarse como desencadenador de propiedad en un estilo. No puede habilitar desencadenadores con una propiedad [!INCLUDE[TLA#tla_clr](../../../../includes/tlasharptla-clr-md.md)] normal: debe ser una propiedad de dependencia. La mencionada anteriormente <xref:System.Windows.UIElement.IsMouseOver%2A> propiedad es un ejemplo perfecto de un escenario donde podría ser bastante útil definir un estilo para un control, donde algunos propiedad visible como un fondo, primer plano o propiedades similares de elementos compuestos dentro de la control cambiará cuando el usuario coloca el mouse sobre alguna región definida del control. Los procesos de invalidación inherentes del sistema de propiedades también pueden detectar y notificar los cambios en una propiedad de dependencia de solo lectura y, de hecho, esto admite la función de desencadenador de propiedad internamente.  
  
<a name="new"></a>   
## <a name="creating-custom-read-only-dependency-properties"></a>Crear propiedades de dependencia de solo lectura  
 Asegúrese de leer la sección anterior sobre por qué no funcionan las propiedades de dependencia de solo lectura para muchos escenarios típicos de propiedades de dependencia. Pero si tiene un escenario adecuado, es posible que quiera crear su propia propiedad de dependencia de solo lectura.  
  
 Gran parte del proceso de creación de una propiedad de dependencia de solo lectura es el mismo que se describe en los temas [Propiedades de dependencia personalizadas](custom-dependency-properties.md) e [Implementar una propiedad de dependencia](how-to-implement-a-dependency-property.md). Hay tres diferencias importantes:  
  
-   Al registrar la propiedad, llame a la <xref:System.Windows.DependencyProperty.RegisterReadOnly%2A> método en lugar de la normal <xref:System.Windows.DependencyProperty.Register%2A> método para el registro de la propiedad.  
  
-   Al implementar la propiedad "wrapper" [!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)], asegúrese de que el contenedor no tenga tampoco ninguna implementación establecida, para que no haya ninguna incoherencia en el estado de solo lectura para el contenedor público que exponga.  
  
-   El objeto devuelto por el registro de solo lectura es <xref:System.Windows.DependencyPropertyKey> lugar <xref:System.Windows.DependencyProperty>. Todavía debe almacenar este campo como miembro, pero, normalmente, no lo convertiría en un miembro público del tipo.  
  
 Por supuesto, cualquier valor o campo privado que respalde la propiedad de dependencia de solo lectura se puede escribir completamente con cualquier lógica que decida. Sin embargo, la manera más sencilla de establecer la propiedad inicialmente o como parte de la lógica en tiempo de ejecución es usar [!INCLUDE[TLA2#tla_api#plural](../../../../includes/tla2sharptla-apisharpplural-md.md)] del sistema de propiedades, en lugar de burlar el sistema de propiedades y establecer el campo de respaldo privado directamente. En concreto, hay una firma de <xref:System.Windows.DependencyObject.SetValue%2A> que acepta un parámetro de tipo <xref:System.Windows.DependencyPropertyKey>. Cómo y dónde establezca este valor mediante programación dentro de la lógica de aplicación afectará a cómo se desea configurar el acceso en el <xref:System.Windows.DependencyPropertyKey> creado al registrar primero la propiedad de dependencia. Si controla toda esta lógica dentro de la clase, puede hacerla privada o, si necesita establecerla desde otras partes del ensamblado, puede establecerla como interna. Un enfoque consiste en llamar a <xref:System.Windows.DependencyObject.SetValue%2A> dentro de un controlador de eventos de clase de un evento pertinente que informa a una instancia de clase que debe cambiarse el valor de propiedad almacenado. Otro enfoque consiste en vincular las propiedades de dependencia mediante el uso de emparejado <xref:System.Windows.PropertyChangedCallback> y <xref:System.Windows.CoerceValueCallback> las devoluciones de llamada como parte de los metadatos de esas propiedades durante el registro.  
  
 Dado que el <xref:System.Windows.DependencyPropertyKey> es privado y no se propaga por el sistema de propiedad fuera de su código, una propiedad de dependencia de solo lectura tiene mejor seguridad de establecimiento de una propiedad de dependencia de lectura y escritura. Para una propiedad de dependencia de solo lectura, el campo de identificación es explícitamente o implícitamente público y, por lo tanto, se puede establecer la propiedad. Para obtener más información específica, consulte [Seguridad de las propiedades de dependencia](dependency-property-security.md).  
  
## <a name="see-also"></a>Vea también

- [Información general sobre las propiedades de dependencia](dependency-properties-overview.md)
- [Propiedades de dependencia personalizadas](custom-dependency-properties.md)
- [Aplicar estilos y plantillas](../controls/styling-and-templating.md)
