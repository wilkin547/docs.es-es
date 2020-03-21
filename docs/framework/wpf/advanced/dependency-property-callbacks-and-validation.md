---
title: Devoluciones de llamada y validación de las propiedades de dependencia
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- dependency properties [WPF], validation
- coerce value callbacks [WPF]
- callbacks [WPF], validation
- dependency properties [WPF], callbacks
- validation of dependency properties [WPF]
ms.assetid: 48db5fb2-da7f-49a6-8e81-3540e7b25825
ms.openlocfilehash: c5f7439753037aeb5c2ff558da63e063ad65a5e1
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79186437"
---
# <a name="dependency-property-callbacks-and-validation"></a>Devoluciones de llamada y validación de las propiedades de dependencia
En este tema se describe cómo crear propiedades de dependencia mediante implementaciones personalizadas alternativas de características relacionadas con las propiedades, como la determinación de la validación, las devoluciones de llamada que se invocan cuando cambia el valor efectivo de la propiedad y la invalidación de posibles influencias externas en la determinación del valor. En este tema también se describen los escenarios donde es apropiado expandir los comportamientos predeterminados del sistema de propiedades mediante estas técnicas.  

<a name="prerequisites"></a>
## <a name="prerequisites"></a>Requisitos previos  
 En este tema se supone que entiende los escenarios básicos de la implementación de una propiedad de dependencia y cómo se aplican los metadatos a una propiedad de dependencia personalizada. Consulte [Propiedades de dependencia personalizadas](custom-dependency-properties.md) y [Metadatos de las propiedades de dependencia](dependency-property-metadata.md) para obtener contexto.  
  
<a name="Validation_Callbacks"></a>
## <a name="validation-callbacks"></a>Devoluciones de llamada de validación  
 Las devoluciones de llamada de validación pueden asignarse a una propiedad de dependencia cuando se registra por primera vez. La devolución de llamada de validación no forma parte de los metadatos de propiedad; es una entrada directa <xref:System.Windows.DependencyProperty.Register%2A> del método. Por lo tanto, una vez creada una devolución de llamada de validación para una propiedad de dependencia, una nueva implementación no puede invalidarla.  
  
 [!code-csharp[DPCallbackOverride#CurrentDefinitionWithWrapper](~/samples/snippets/csharp/VS_Snippets_Wpf/DPCallbackOverride/CSharp/SDKSampleLibrary/class1.cs#currentdefinitionwithwrapper)]
 [!code-vb[DPCallbackOverride#CurrentDefinitionWithWrapper](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DPCallbackOverride/visualbasic/sdksamplelibrary/class1.vb#currentdefinitionwithwrapper)]  
  
 Las devoluciones de llamada se implementan de forma que obtienen un valor de objeto. Devuelven `true` si el valor proporcionado es válido para la propiedad; en caso contrario, devuelven `false`. Se supone que la propiedad es del tipo correcto por el tipo registrado con el sistema de propiedades, por lo que la comprobación de tipo en las devoluciones de llamada no se suele llevar a cabo. El sistema de propiedades usa las devoluciones de llamada en distintas operaciones. Esto incluye la inicialización del tipo inicial por <xref:System.Windows.DependencyObject.SetValue%2A>valor predeterminado, el cambio mediante programación invocando y o los intentos de invalidar metadatos con el nuevo valor predeterminado proporcionado. Si cualquiera de estas operaciones invoca la devolución de llamada de validación y devuelve `false`, se generará una excepción. Los escritores de aplicaciones deben estar preparados para controlar estas excepciones. Un uso común de las devoluciones de llamada de validación es validar los valores de enumeración o restringir los valores de números enteros o dobles cuando la propiedad establece medidas que deben ser cero o un valor superior.  
  
 Las devoluciones de llamada de validación están diseñadas específicamente como validadores de clase, no como validadores de instancia. Los parámetros de la devolución <xref:System.Windows.DependencyObject> de llamada no comunican un específico en el que se establecen las propiedades que se van a validar. Por lo tanto, las devoluciones de llamada de validación no resultan útiles para aplicar las posibles "dependencias" que podrían influir en un valor de propiedad, donde el valor específico de la instancia de una propiedad depende de factores, tales como los valores específicos de la instancia de otras propiedades o el estado de tiempo de ejecución.  
  
 A continuación se muestra código de ejemplo para un escenario de devolución <xref:System.Double> de llamada <xref:System.Double.PositiveInfinity> <xref:System.Double.NegativeInfinity>de validación muy simple: validar que una propiedad que se escribe como primitiva no es o .  
  
 [!code-csharp[DPCallbackOverride#ValidateValueCallback](~/samples/snippets/csharp/VS_Snippets_Wpf/DPCallbackOverride/CSharp/SDKSampleLibrary/class1.cs#validatevaluecallback)]
 [!code-vb[DPCallbackOverride#ValidateValueCallback](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DPCallbackOverride/visualbasic/sdksamplelibrary/class1.vb#validatevaluecallback)]  
  
<a name="Coerce_Value_Callbacks_and_Property_Changed_Events"></a>
## <a name="coerce-value-callbacks-and-property-changed-events"></a>Devoluciones de llamada de valor de coerción y eventos de propiedad cambiada  
 Las devoluciones de llamada de <xref:System.Windows.DependencyObject> valor coerce <xref:System.Windows.PropertyChangedCallback> pasan la instancia específica de las propiedades, al igual que las implementaciones que invoca el sistema de propiedades cada vez que cambia el valor de una propiedad de dependencia. Con estas dos devoluciones de llamada combinadas, puede crear una serie de propiedades en aquellos elementos donde los cambios en una propiedad forzarán una coerción o reevaluación de otra propiedad.  
  
 Un escenario típico para usar la vinculación de propiedades de dependencia es cuando tiene una propiedad controlada por la interfaz de usuario donde el elemento contiene una propiedad para el valor mínimo y otra para el máximo, además de una tercera propiedad para el valor real o actual. Aquí, si el máximo está ajustado de manera que el valor actual supera el nuevo máximo, querrá forzar el valor actual para que no supere el nuevo máximo, además de una relación similar entre los valores mínimo y actual.  
  
 El siguiente es un código de ejemplo muy breve para una sola de las tres propiedades de dependencia que ilustran esta relación. En el ejemplo se muestra cómo está registrada la propiedad `CurrentReading` de un conjunto Min/Max/Current de propiedades *Reading relacionadas. Usa la validación como se muestra en la sección anterior.  
  
 [!code-csharp[DPCallbackOverride#CurrentDefinitionWithWrapper](~/samples/snippets/csharp/VS_Snippets_Wpf/DPCallbackOverride/CSharp/SDKSampleLibrary/class1.cs#currentdefinitionwithwrapper)]
 [!code-vb[DPCallbackOverride#CurrentDefinitionWithWrapper](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DPCallbackOverride/visualbasic/sdksamplelibrary/class1.vb#currentdefinitionwithwrapper)]  
  
 La devolución de llamada de la propiedad cambiada Current se usa para reenviar el cambio a otras propiedades dependientes, mediante la invocación explícita de las devoluciones de llamada del valor de coerción registradas para esas otras propiedades:  
  
 [!code-csharp[DPCallbackOverride#OnPCCurrent](~/samples/snippets/csharp/VS_Snippets_Wpf/DPCallbackOverride/CSharp/SDKSampleLibrary/class1.cs#onpccurrent)]
 [!code-vb[DPCallbackOverride#OnPCCurrent](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DPCallbackOverride/visualbasic/sdksamplelibrary/class1.vb#onpccurrent)]  
  
 La devolución de llamada de valor de coerción comprueba los valores de propiedades de las que depende potencialmente la propiedad actual y fuerza el valor actual si es necesario:  
  
 [!code-csharp[DPCallbackOverride#CoerceCurrent](~/samples/snippets/csharp/VS_Snippets_Wpf/DPCallbackOverride/CSharp/SDKSampleLibrary/class1.cs#coercecurrent)]
 [!code-vb[DPCallbackOverride#CoerceCurrent](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DPCallbackOverride/visualbasic/sdksamplelibrary/class1.vb#coercecurrent)]  
  
> [!NOTE]
> Los valores predeterminados de las propiedades no se fuerzan. Un valor de propiedad igual al valor predeterminado puede producirse si un valor <xref:System.Windows.DependencyObject.ClearValue%2A>de propiedad todavía tiene su valor predeterminado inicial, o mediante la compensación de otros valores con .  
  
 Las devoluciones de llamada de valor de coerción y propiedad cambiada forman parte de los metadatos de las propiedades. Por lo tanto, puede cambiar las devoluciones de llamada de una propiedad de dependencia determinada, tal como existe en un tipo que se deriva del tipo que posee la propiedad de dependencia, mediante la invalidación de los metadatos de esa propiedad en el tipo.  
  
<a name="Advanced"></a>
## <a name="advanced-coercion-and-callback-scenarios"></a>Escenarios de coerción y llamada de devolución avanzados  
  
### <a name="constraints-and-desired-values"></a>Restricciones y valores deseados  
 El <xref:System.Windows.PropertyMetadata.CoerceValueCallback%2A> sistema de propiedades utilizará las devoluciones de llamada para coaccionar un valor de acuerdo con la lógica que declare, pero un valor coaccionado de una propiedad establecida localmente conservará un "valor deseado" internamente. Si las restricciones se basan en otros valores de propiedad que pueden cambiar dinámicamente durante el ciclo de vida de la aplicación, las restricciones de coerción también cambian de forma dinámica y la propiedad restringida puede cambiar su valor para que se aproxime al valor deseado lo máximo posible según las nuevas restricciones. El valor se convertirá en el valor deseado si se levantan todas las restricciones. Se pueden introducir algunos escenarios de dependencia complejos en el caso de tener varias propiedades que sean dependientes entre sí de manera circular. Por ejemplo, en el escenario Min/Max/Current, puede elegir que las propiedades Minimum y Maximum las pueda establecer el usuario. En este caso, es posible que deba forzar que Maximum sea siempre mayor que Minimum y viceversa. No obstante, si esa coerción está activa y la propiedad Maximum fuerza la propiedad Minimum, Current no se puede establecer, ya que depende de ambas y está restringida al intervalo entre los valores, que es cero. A continuación, si se ajustan las propiedades Maximum o Minimum, parecerá que Current "sigue" a uno de los valores, ya que el valor deseado de Current sigue estando almacenado e intenta alcanzar el valor deseado a medida que se suavizan las restricciones.  
  
 Técnicamente, no hay nada incorrecto en las dependencias complejas, pero pueden suponer un ligero deterioro del rendimiento si requieren grandes cantidades de reevaluaciones y también pueden ser confusas para los usuarios si afectan a la interfaz de usuario directamente. Tenga cuidado con las devoluciones de llamada de propiedad cambiada y valor de coerción, y asegúrese de que la coerción que se está intentando pueda tratarse de la manera más ambigua posible y no sea "sobrerrestrictiva".  
  
### <a name="using-coercevalue-to-cancel-value-changes"></a>Uso de CoerceValue para cancelar cambios de valor  
 El sistema de <xref:System.Windows.CoerceValueCallback> propiedades tratará <xref:System.Windows.DependencyProperty.UnsetValue> cualquiera que devuelva el valor como un caso especial. Este caso especial significa que el cambio <xref:System.Windows.CoerceValueCallback> de propiedad que dio lugar a la llamada debe ser rechazado por el sistema de propiedades y que el sistema de propiedades debe informar en su lugar cualquier valor anterior que tenía la propiedad. Este mecanismo puede ser útil para comprobar que los cambios en una propiedad iniciados de manera asincrónica siguen siendo válidos para el estado actual del objeto y suprimirlos si no lo son. Otro escenario posible es la posibilidad de suprimir de manera selectiva un valor según el componente de determinación del valor propiedad que sea responsable del valor comunicado. Para ello, puede usar <xref:System.Windows.DependencyProperty> el pasado en la devolución <xref:System.Windows.DependencyPropertyHelper.GetValueSource%2A>de llamada y <xref:System.Windows.ValueSource>el identificador de propiedad como entrada para , y, a continuación, procesar el archivo .  
  
## <a name="see-also"></a>Consulte también

- [Descripción general de las propiedades de dependencia](dependency-properties-overview.md)
- [Metadatos de las propiedades de dependencia](dependency-property-metadata.md)
- [Propiedades de dependencia personalizadas](custom-dependency-properties.md)
