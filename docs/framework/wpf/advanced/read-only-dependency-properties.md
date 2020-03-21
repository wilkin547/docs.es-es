---
title: Propiedades de dependencia de sólo lectura
ms.date: 03/30/2017
helpviewer_keywords:
- dependency properties [WPF], read-only
- read-only dependency properties [WPF]
ms.assetid: f23d6ec9-3780-4c09-a2ff-b2f0a2deddf1
ms.openlocfilehash: 8adc90182f0f42f52e6ace4e13c68acb3539516b
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79187180"
---
# <a name="read-only-dependency-properties"></a>Propiedades de dependencia de sólo lectura
En este tema se describen las propiedades de dependencia de solo lectura, incluidas las propiedades de dependencia de solo lectura existentes y los escenarios y las técnicas para crear una propiedad de dependencia de solo lectura personalizada.  

<a name="prerequisites"></a>
## <a name="prerequisites"></a>Requisitos previos  
 En este tema se supone que entiende los escenarios básicos de la implementación de una propiedad de dependencia y cómo se aplican los metadatos a una propiedad de dependencia personalizada. Consulte [Propiedades de dependencia personalizadas](custom-dependency-properties.md) y [Metadatos de las propiedades de dependencia](dependency-property-metadata.md) para obtener contexto.  
  
<a name="existing"></a>
## <a name="existing-read-only-dependency-properties"></a>Propiedades de dependencia de solo lectura existentes  
 Algunas de las propiedades de dependencia definidas en el marco de [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] son de solo lectura. La razón típica para especificar una propiedad de dependencia de solo lectura es que son propiedades que se deben usar para determinar el estado, si ese estado depende de muchos factores, pero, simplemente, establecer la propiedad en ese estado no es deseable desde una perspectiva de diseño de la interfaz de usuario. Por ejemplo, <xref:System.Windows.UIElement.IsMouseOver%2A> la propiedad es realmente el estado de superficie según lo determinado a partir de la entrada del mouse. Cualquier intento de establecer este valor mediante programación y sortear la entrada de ratón real sería imprevisible y daría lugar a incoherencias.  
  
 Al no poder establecerse, las propiedades de dependencia de solo lectura no son adecuadas para muchos de los escenarios para los que las propiedades de dependencia suelen ofrecen una solución, es decir: enlace de datos, aplicar directamente estilos a un valor, validación, animación, herencia). A pesar de que no se pueden establecer, las propiedades de solo lectura todavía tienen algunas funciones adicionales que admiten las propiedades de dependencia en el sistema de propiedades. La funcionalidad restante más importante es que la propiedad de dependencia de solo lectura aún puede usarse como desencadenador de propiedad en un estilo. No se pueden habilitar desencadenadores con una propiedad normal de Common Language Runtime (CLR); debe ser una propiedad de dependencia. La propiedad antes <xref:System.Windows.UIElement.IsMouseOver%2A> mencionada es un ejemplo perfecto de un escenario donde podría ser muy útil definir un estilo para un control, donde alguna propiedad visible como un fondo, primer plano o propiedades similares de elementos compuestos dentro del control cambiará cuando el usuario coloca un mouse sobre alguna región definida del control. Los procesos de invalidación inherentes del sistema de propiedades también pueden detectar y notificar los cambios en una propiedad de dependencia de solo lectura y, de hecho, esto admite la función de desencadenador de propiedad internamente.  
  
<a name="new"></a>
## <a name="creating-custom-read-only-dependency-properties"></a>Crear propiedades de dependencia de solo lectura  
 Asegúrese de leer la sección anterior sobre por qué no funcionan las propiedades de dependencia de solo lectura para muchos escenarios típicos de propiedades de dependencia. Pero si tiene un escenario adecuado, es posible que quiera crear su propia propiedad de dependencia de solo lectura.  
  
 Gran parte del proceso de creación de una propiedad de dependencia de solo lectura es el mismo que se describe en los temas [Propiedades de dependencia personalizadas](custom-dependency-properties.md) e [Implementar una propiedad de dependencia](how-to-implement-a-dependency-property.md). Hay tres diferencias importantes:  
  
- Al registrar la propiedad, <xref:System.Windows.DependencyProperty.RegisterReadOnly%2A> llame al <xref:System.Windows.DependencyProperty.Register%2A> método en lugar del método normal para el registro de propiedades.  
  
- Al implementar la propiedad "wrapper" de CLR, asegúrese de que el contenedor tampoco tiene una implementación establecida, por lo que no hay ninguna incoherencia en el estado de solo lectura para el contenedor público que expone.  
  
- El objeto devuelto por el <xref:System.Windows.DependencyPropertyKey> registro <xref:System.Windows.DependencyProperty>de solo lectura es en lugar de . Todavía debe almacenar este campo como miembro, pero, normalmente, no lo convertiría en un miembro público del tipo.  
  
 Por supuesto, cualquier valor o campo privado que respalde la propiedad de dependencia de solo lectura se puede escribir completamente con cualquier lógica que decida. Sin embargo, la forma más sencilla de establecer la propiedad inicialmente o como parte de la lógica de tiempo de ejecución es usar las API del sistema de propiedades, en lugar de eludir el sistema de propiedades y establecer el campo de respaldo privado directamente. En particular, hay una <xref:System.Windows.DependencyObject.SetValue%2A> firma de que <xref:System.Windows.DependencyPropertyKey>acepta un parámetro de tipo . Cómo y dónde establecer este valor mediante programación dentro de la <xref:System.Windows.DependencyPropertyKey> lógica de la aplicación afectará a cómo desea establecer el acceso en el creado cuando registró por primera vez la propiedad de dependencia. Si controla toda esta lógica dentro de la clase, puede hacerla privada o, si necesita establecerla desde otras partes del ensamblado, puede establecerla como interna. Un enfoque consiste <xref:System.Windows.DependencyObject.SetValue%2A> en llamar dentro de un controlador de eventos de clase de un evento relevante que informa a una instancia de clase que el valor de propiedad almacenado debe cambiarse. Otro enfoque consiste en unir las <xref:System.Windows.PropertyChangedCallback> propiedades <xref:System.Windows.CoerceValueCallback> de dependencia mediante el uso de pares y devoluciones de llamada como parte de los metadatos de esas propiedades durante el registro.  
  
 Dado <xref:System.Windows.DependencyPropertyKey> que es privado y no lo propaga el sistema de propiedades fuera del código, una propiedad de dependencia de solo lectura tiene una mejor seguridad de configuración que una propiedad de dependencia de lectura y escritura. Para una propiedad de dependencia de solo lectura, el campo de identificación es explícitamente o implícitamente público y, por lo tanto, se puede establecer la propiedad. Para obtener más información específica, consulte [Seguridad de las propiedades de dependencia](dependency-property-security.md).  
  
## <a name="see-also"></a>Consulte también

- [Descripción general de las propiedades de dependencia](dependency-properties-overview.md)
- [Propiedades de dependencia personalizadas](custom-dependency-properties.md)
- [Aplicar estilos y plantillas](../../../desktop-wpf/fundamentals/styles-templates-overview.md)
