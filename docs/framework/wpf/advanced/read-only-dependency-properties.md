---
title: Propiedades de dependencia de sólo lectura
ms.date: 03/30/2017
helpviewer_keywords:
- dependency properties [WPF], read-only
- read-only dependency properties [WPF]
ms.assetid: f23d6ec9-3780-4c09-a2ff-b2f0a2deddf1
ms.openlocfilehash: aa6893b100311ead74f610dd20f327d130dff74a
ms.sourcegitcommit: 24a4a8eb6d8cfe7b8549fb6d823076d7c697e0c6
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/23/2019
ms.locfileid: "68401654"
---
# <a name="read-only-dependency-properties"></a>Propiedades de dependencia de sólo lectura
En este tema se describen las propiedades de dependencia de solo lectura, incluidas las propiedades de dependencia de solo lectura existentes y los escenarios y las técnicas para crear una propiedad de dependencia de solo lectura personalizada.  

<a name="prerequisites"></a>   
## <a name="prerequisites"></a>Requisitos previos  
 En este tema se supone que entiende los escenarios básicos de la implementación de una propiedad de dependencia y cómo se aplican los metadatos a una propiedad de dependencia personalizada. Consulte [Propiedades de dependencia personalizadas](custom-dependency-properties.md) y [Metadatos de las propiedades de dependencia](dependency-property-metadata.md) para obtener contexto.  
  
<a name="existing"></a>   
## <a name="existing-read-only-dependency-properties"></a>Propiedades de dependencia de solo lectura existentes  
 Algunas de las propiedades de dependencia definidas en el marco de [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] son de solo lectura. La razón típica para especificar una propiedad de dependencia de solo lectura es que son propiedades que se deben usar para determinar el estado, si ese estado depende de muchos factores, pero, simplemente, establecer la propiedad en ese estado no es deseable desde una perspectiva de diseño de la interfaz de usuario. Por ejemplo, la propiedad <xref:System.Windows.UIElement.IsMouseOver%2A> es realmente simplemente un estado de exposición, tal y como se determina a partir de la entrada del mouse. Cualquier intento de establecer este valor mediante programación y sortear la entrada de ratón real sería imprevisible y daría lugar a incoherencias.  
  
 Al no poder establecerse, las propiedades de dependencia de solo lectura no son adecuadas para muchos de los escenarios para los que las propiedades de dependencia suelen ofrecen una solución, es decir: enlace de datos, aplicar directamente estilos a un valor, validación, animación, herencia). A pesar de que no se pueden establecer, las propiedades de solo lectura todavía tienen algunas funciones adicionales que admiten las propiedades de dependencia en el sistema de propiedades. La funcionalidad restante más importante es que la propiedad de dependencia de solo lectura aún puede usarse como desencadenador de propiedad en un estilo. Los desencadenadores no se pueden habilitar con una propiedad de Common Language Runtime normal (CLR). debe ser una propiedad de dependencia. La propiedad <xref:System.Windows.UIElement.IsMouseOver%2A> mencionada es un ejemplo perfecto de un escenario en el que podría ser bastante útil definir un estilo para un control, donde alguna propiedad visible, como fondo, primer plano, o propiedades similares de los elementos compuestos dentro de la el control cambiará cuando el usuario coloque un mouse sobre alguna región definida del control. Los procesos de invalidación inherentes del sistema de propiedades también pueden detectar y notificar los cambios en una propiedad de dependencia de solo lectura y, de hecho, esto admite la función de desencadenador de propiedad internamente.  
  
<a name="new"></a>   
## <a name="creating-custom-read-only-dependency-properties"></a>Crear propiedades de dependencia de solo lectura  
 Asegúrese de leer la sección anterior sobre por qué no funcionan las propiedades de dependencia de solo lectura para muchos escenarios típicos de propiedades de dependencia. Pero si tiene un escenario adecuado, es posible que quiera crear su propia propiedad de dependencia de solo lectura.  
  
 Gran parte del proceso de creación de una propiedad de dependencia de solo lectura es el mismo que se describe en los temas [Propiedades de dependencia personalizadas](custom-dependency-properties.md) e [Implementar una propiedad de dependencia](how-to-implement-a-dependency-property.md). Hay tres diferencias importantes:  
  
- Al registrar la propiedad, llame al <xref:System.Windows.DependencyProperty.RegisterReadOnly%2A> método en lugar de al método normal <xref:System.Windows.DependencyProperty.Register%2A> para el registro de propiedades.  
  
- Al implementar la propiedad de "contenedor" de CLR, asegúrese de que el contenedor no tenga una implementación de conjunto, de modo que no haya ninguna incoherencia en el estado de solo lectura para el contenedor público que exponga.  
  
- El objeto devuelto por el registro de solo lectura <xref:System.Windows.DependencyPropertyKey> es en <xref:System.Windows.DependencyProperty>lugar de. Todavía debe almacenar este campo como miembro, pero, normalmente, no lo convertiría en un miembro público del tipo.  
  
 Por supuesto, cualquier valor o campo privado que respalde la propiedad de dependencia de solo lectura se puede escribir completamente con cualquier lógica que decida. Sin embargo, la manera más sencilla de establecer la propiedad inicialmente o como parte de la lógica en tiempo de ejecución es usar las API del sistema de propiedades, en lugar de eludir el sistema de propiedades y establecer el campo de respaldo privado directamente. En concreto, hay una firma de <xref:System.Windows.DependencyObject.SetValue%2A> que acepta un parámetro de tipo. <xref:System.Windows.DependencyPropertyKey> Cómo y dónde se establece este valor mediante programación dentro de la lógica de la aplicación afectará a la forma en que se <xref:System.Windows.DependencyPropertyKey> desea establecer el acceso en el creado cuando se registró por primera vez en la propiedad de dependencia. Si controla toda esta lógica dentro de la clase, puede hacerla privada o, si necesita establecerla desde otras partes del ensamblado, puede establecerla como interna. Un enfoque consiste en llamar <xref:System.Windows.DependencyObject.SetValue%2A> a dentro de un controlador de eventos de clase de un evento pertinente que informa a una instancia de clase de que el valor de la propiedad almacenada debe cambiarse. Otro enfoque consiste en asociar las propiedades de dependencia mediante el <xref:System.Windows.PropertyChangedCallback> uso <xref:System.Windows.CoerceValueCallback> de las devoluciones de llamada y emparejadas como parte de los metadatos de las propiedades durante el registro.  
  
 Dado que <xref:System.Windows.DependencyPropertyKey> es privado y no se propaga por el sistema de propiedades fuera del código, una propiedad de dependencia de solo lectura tiene una mejor seguridad de establecimiento que una propiedad de dependencia de lectura y escritura. Para una propiedad de dependencia de solo lectura, el campo de identificación es explícitamente o implícitamente público y, por lo tanto, se puede establecer la propiedad. Para obtener más información específica, consulte [Seguridad de las propiedades de dependencia](dependency-property-security.md).  
  
## <a name="see-also"></a>Vea también

- [Información general sobre las propiedades de dependencia](dependency-properties-overview.md)
- [Propiedades de dependencia personalizadas](custom-dependency-properties.md)
- [Aplicar estilos y plantillas](../controls/styling-and-templating.md)
