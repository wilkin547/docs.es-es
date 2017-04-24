---
title: "Devoluciones de llamada y validaci&#243;n de las propiedades de dependencia | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-wpf"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "devoluciones de llamada, validación"
  - "CoerceValue Callbacks"
  - "propiedades de dependencia, devoluciones de llamada"
  - "propiedades de dependencia, validación"
  - "validación de propiedades de dependencia"
ms.assetid: 48db5fb2-da7f-49a6-8e81-3540e7b25825
caps.latest.revision: 17
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 16
---
# Devoluciones de llamada y validaci&#243;n de las propiedades de dependencia
En este tema se describe cómo crear propiedades de dependencia utilizando implementaciones personalizadas alternativas para las características relacionadas con propiedades, tales como la determinación de validación, las devoluciones de llamada que se invocan cada vez que cambia el valor efectivo de la propiedad, y la invalidación de posibles influencias externas para la determinación del valor.  En este tema también se explican los escenarios donde es apropiado expandir los comportamientos del sistema de propiedades predeterminado mediante estas técnicas.  
  
   
  
<a name="prerequisites"></a>   
## Requisitos previos  
 En este tema se supone que entiende los escenarios básicos de la implementación de una propiedad de dependencia, así como la aplicación de una propiedad a una propiedad de dependencia personalizada.  Vea [Propiedades de dependencia personalizadas](../../../../docs/framework/wpf/advanced/custom-dependency-properties.md) y [Metadatos de las propiedades de dependencia](../../../../docs/framework/wpf/advanced/dependency-property-metadata.md) para obtener contexto.  
  
<a name="Validation_Callbacks"></a>   
## Devoluciones de llamada de validación  
 Las devoluciones de llamada de validación se pueden asignar a una propiedad de dependencia cuando se registra por primera vez.  La devolución de llamada de validación no forma parte de los metadatos de la propiedad; es una entrada directa del método <xref:System.Windows.DependencyProperty.Register%2A>.  Por consiguiente, una vez creada una devolución de llamada de validación para una propiedad de dependencia, no puede invalidarse mediante una nueva implementación.  
  
 [!code-csharp[DPCallbackOverride#CurrentDefinitionWithWrapper](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DPCallbackOverride/CSharp/SDKSampleLibrary/class1.cs#currentdefinitionwithwrapper)]
 [!code-vb[DPCallbackOverride#CurrentDefinitionWithWrapper](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DPCallbackOverride/visualbasic/sdksamplelibrary/class1.vb#currentdefinitionwithwrapper)]  
  
 Las devoluciones de llamada se implementan de modo que se les proporcione un valor de objeto.  Devuelven `true` si el valor proporcionado es válido para la propiedad; de lo contrario, devuelven `false`.  Se supone que la propiedad es del tipo correcto con respecto al tipo registrado en el sistema de propiedades, por lo que normalmente no se comprueba su tipo dentro de las devoluciones de llamada.  El sistema de propiedades utiliza las devoluciones de llamada en varias operaciones diferentes.  Entre ellas, se incluyen la inicialización de tipos por valores predeterminados, el cambio mediante programación invocando el método <xref:System.Windows.DependencyObject.SetValue%2A>, o los intentos de invalidación de metadatos con el nuevo valor predeterminado proporcionado.  Si cualquiera de estas operaciones invoca la devolución de llamada de validación, y devuelve `false`, entonces se inicia una excepción.  El autor de la aplicación debe estar preparado para administrar estas excepciones.  Un uso común de las devoluciones de llamada de validación es la validación de valores de enumeración, o la restricción de valores de tipo Integer o Double cuando la propiedad establece medidas que deben ser mayores o iguales que cero.  
  
 Las devoluciones de llamada de validación están diseñadas específicamente como validadores de clase, no de instancias.  Los parámetros de la devolución de llamada no comunican un objeto <xref:System.Windows.DependencyObject> concreto para el que se establecen las propiedades que se van a validar.  Por consiguiente, las devoluciones de llamada de validación no resultan útiles para aplicar las posibles "dependencias" que podrían influir en el valor de una propiedad, donde el valor específico de la instancia de una propiedad depende de factores tales como los valores específicos de la instancia de otras propiedades, o el estado en tiempo de ejecución.  
  
 A continuación, se muestra un ejemplo de código para un escenario de devolución de llamada de validación muy simple: se valida que el valor de una propiedad cuyo tipo primitivo es <xref:System.Double> no es <xref:System.Double.PositiveInfinity> ni <xref:System.Double.NegativeInfinity>.  
  
 [!code-csharp[DPCallbackOverride#ValidateValueCallback](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DPCallbackOverride/CSharp/SDKSampleLibrary/class1.cs#validatevaluecallback)]
 [!code-vb[DPCallbackOverride#ValidateValueCallback](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DPCallbackOverride/visualbasic/sdksamplelibrary/class1.vb#validatevaluecallback)]  
  
<a name="Coerce_Value_Callbacks_and_Property_Changed_Events"></a>   
## Devoluciones de llamada de forzado de valores y eventos de cambio de propiedad  
 Las devoluciones de llamada de forzado de valores pasan la instancia de <xref:System.Windows.DependencyObject> específica para las propiedades, al igual que las implementaciones de <xref:System.Windows.PropertyChangedCallback> que invoca el sistema de propiedades cada vez que cambia el valor de una propiedad de dependencia.  Mediante el uso combinado de estas dos devoluciones de llamada, puede crear una serie de propiedades de elementos de tal forma que los cambios de una propiedad fuercen una conversión o reevaluación de otra propiedad.  
  
 Un escenario típico en que se suele usar la vinculación de propiedades de dependencia es aquél en que existe una propiedad controlada por la interfaz de usuario donde el elemento contiene una propiedad para cada valor mínimo y máximo, y una tercera propiedad para el valor real o actual.  Aquí, si el máximo se ajustara de tal modo que el valor actual superase el nuevo máximo, sería deseable forzar el valor actual de manera que no fuese mayor que el nuevo máximo, con una relación similar entre los valores mínimo y actual.  
  
 A continuación, se muestra un ejemplo de código muy breve con una sola de las tres propiedades de dependencia que ilustran esta relación.  En el ejemplo se muestra cómo se registra la propiedad `CurrentReading` de un conjunto Min\/Max\/Current de propiedades \*Reading.  Se utiliza la validación como se indica en la sección anterior.  
  
 [!code-csharp[DPCallbackOverride#CurrentDefinitionWithWrapper](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DPCallbackOverride/CSharp/SDKSampleLibrary/class1.cs#currentdefinitionwithwrapper)]
 [!code-vb[DPCallbackOverride#CurrentDefinitionWithWrapper](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DPCallbackOverride/visualbasic/sdksamplelibrary/class1.vb#currentdefinitionwithwrapper)]  
  
 La devolución de llamada de cambio de propiedad para el valor Current se utiliza para reenviar el cambio a otras propiedades dependientes, invocando explícitamente las devoluciones de llamada de forzado de valores registradas para esas otras propiedades:  
  
 [!code-csharp[DPCallbackOverride#OnPCCurrent](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DPCallbackOverride/CSharp/SDKSampleLibrary/class1.cs#onpccurrent)]
 [!code-vb[DPCallbackOverride#OnPCCurrent](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DPCallbackOverride/visualbasic/sdksamplelibrary/class1.vb#onpccurrent)]  
  
 La devolución de llamada de forzado de valores comprueba los valores de las propiedades de las que depende potencialmente la propiedad actual y fuerza el valor actual si es necesario:  
  
 [!code-csharp[DPCallbackOverride#CoerceCurrent](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DPCallbackOverride/CSharp/SDKSampleLibrary/class1.cs#coercecurrent)]
 [!code-vb[DPCallbackOverride#CoerceCurrent](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DPCallbackOverride/visualbasic/sdksamplelibrary/class1.vb#coercecurrent)]  
  
> [!NOTE]
>  Los valores predeterminados de las propiedades no se fuerzan.  Puede ocurrir que se produzca un valor de propiedad igual al predeterminado si un valor de propiedad sigue teniendo su valor predeterminado inicial, o si se borran otros valores con el método <xref:System.Windows.DependencyObject.ClearValue%2A>.  
  
 Las devoluciones de llamada de forzado de valores y de cambio de propiedad forman parte de los metadatos de una propiedad.  Por consiguiente, puede cambiar las devoluciones de llamada para una propiedad de dependencia determinada cuando existe en un tipo que se deriva del tipo que posee la propiedad de dependencia, invalidando los metadatos para esa propiedad en el tipo.  
  
<a name="Advanced"></a>   
## Escenarios avanzados de forzado y devolución de llamada  
  
### Restricciones y valores deseados  
 El sistema de propiedades utiliza las devoluciones de llamada de <xref:System.Windows.PropertyMetadata.CoerceValueCallback%2A> para forzar un valor de conformidad con la lógica que se declara, pero un valor forzado de una propiedad establecida localmente conservará internamente un "valor deseado".  Si las restricciones se basan en otros valores de propiedad que pueden cambiar dinámicamente en el transcurso de la duración de la aplicación, también se cambian dinámicamente las restricciones de forzado, con lo que puede suceder que cambie el valor de la propiedad restringida a fin de acercarse lo más posible al valor deseado en virtud de esas nuevas restricciones.  El valor se convertirá en el valor deseado si se retiran todas las restricciones.  Potencialmente, es posible incluir algunos escenarios de dependencia bastante complicados si tiene varias propiedades dependientes entre sí de manera circular.  Por ejemplo, en el escenario Min\/Max\/Current \(con tres valores: mínimo, máximo y actual\), podría permitir al usuario establecer el mínimo y el máximo.  En este caso, podría ser necesario forzar el valor máximo para que siempre sea mayor que el mínimo, y viceversa.  Pero si ese forzado está activo, y el máximo se fuerza al mínimo, dejará el valor actual en un estado que no permite establecerlo, porque depende de ambos valores y está restringido al intervalo comprendido entre ellos, que es cero.  A continuación, si se ajustan el máximo y el mínimo, el valor actual parecerá "seguir" a uno de los valores, porque el valor deseado del valor actual sigue estando almacenado e intenta alcanzar el valor deseado cuando se retiran las restricciones.  
  
 Técnicamente, no hay nada de malo en establecer dependencias complejas, pero pueden provocar un ligero deterioro del rendimiento si requieren grandes cantidades de reevaluaciones, además de resultar confusas para los usuarios si afectan directamente a la interfaz de usuario.  Extreme las precauciones con las devoluciones de llamada de cambio de propiedad y de forzado de valores: asegúrese de que el forzado previsto se pueda tratar del modo menos ambiguo posible y no cree un exceso de restricción.  
  
### Utilizar valores de forzado para cancelar cambios de valor  
 El sistema de propiedades tratará cualquier <xref:System.Windows.CoerceValueCallback> que devuelva el valor <xref:System.Windows.DependencyProperty.UnsetValue> como un caso especial.  Este caso especial significa que el sistema de propiedades debe rechazar el cambio de propiedad que ha dado lugar a la llamada a <xref:System.Windows.CoerceValueCallback>, y que el sistema de propiedades debe comunicar, en su lugar, el valor anterior que tenía la propiedad.  Este mecanismo puede ser útil para comprobar si los cambios de una propiedad iniciados de manera asincrónica siguen siendo válidos para el estado actual del objeto y suprimirlos en caso negativo.  Otro escenario posible es la supresión selectiva de un valor dependiendo de qué componente de la determinación del valor de propiedad sea responsable del valor comunicado.  Para ello, puede utilizar el objeto <xref:System.Windows.DependencyProperty> pasado en la devolución de llamada y el identificador de propiedad como entrada para el método <xref:System.Windows.DependencyPropertyHelper.GetValueSource%2A> y, a continuación, procesar <xref:System.Windows.ValueSource>.  
  
## Vea también  
 [Información general sobre las propiedades de dependencia](../../../../docs/framework/wpf/advanced/dependency-properties-overview.md)   
 [Metadatos de las propiedades de dependencia](../../../../docs/framework/wpf/advanced/dependency-property-metadata.md)   
 [Propiedades de dependencia personalizadas](../../../../docs/framework/wpf/advanced/custom-dependency-properties.md)