---
title: "Propiedades de dependencia de tipo de colecci&#243;n | Microsoft Docs"
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
  - "propiedades de tipo de colección"
  - "propiedades de dependencia"
  - "propiedades, tipo de colección"
  - "propiedades, dependency"
ms.assetid: 99f96a42-3ab7-4f64-a16b-2e10d654e97c
caps.latest.revision: 10
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 7
---
# Propiedades de dependencia de tipo de colecci&#243;n
En este se proporciona orientación y sugerencias de modelos de implementación de una [propiedad de dependencia](GTMT) cuyo tipo sea de colección.  
  
   
  
<a name="implementing"></a>   
## Implementar una propiedad de dependencia de tipo de colección  
 Para las propiedades de dependencia en general, el modelo de implementación que se sigue consiste en definir un contenedor de propiedad [!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)], donde esa propiedad está respaldada por un identificador de <xref:System.Windows.DependencyProperty>, en lugar de por un campo u otra construcción.  Este mismo modelo se sigue al implementar una propiedad de tipo de colección.  Sin embargo, una propiedad de tipo de colección presenta cierta complejidad en el modelo cada vez el tipo contenido en la colección es, a su vez, una clase derivada de <xref:System.Windows.DependencyObject> o <xref:System.Windows.Freezable>.  
  
<a name="initializing"></a>   
## Inicializar la colección más allá del valor predeterminado  
 Al crear una propiedad de dependencia, no se especifica el valor predeterminado de la misma como el valor inicial del campo.  En su lugar, se especifica el valor predeterminado a través de los metadatos de la propiedad de dependencia.  Si la propiedad es un tipo de referencia, el valor predeterminado especificado en sus metadatos no es un valor predeterminado de una instancia individual, sino un valor predeterminado que se aplica a todas las instancias del tipo.  Por consiguiente, debe extremar las precauciones para no utilizar la colección estática singular definida por los metadatos de la propiedad de colección como el valor predeterminado activo de las instancias recién creadas de su tipo.  En vez de eso, debe asegurarse de establecer de manera deliberada el valor de colección en una colección única \(instancia\) como parte de la lógica del constructor de clase.  De lo contrario, habrá creado involuntariamente una clase singleton.  
  
 Considere el ejemplo siguiente.  En la sección siguiente del ejemplo se muestra la definición de una clase `Aquarium`.  La clase define la propiedad de dependencia de tipo de colección `AquariumObjects`, que utiliza el tipo <xref:System.Collections.Generic.List%601> genérico con una restricción de tipo <xref:System.Windows.FrameworkElement>.  En la llamada a <xref:System.Windows.DependencyProperty.Register%28System.String%2CSystem.Type%2CSystem.Type%2CSystem.Windows.PropertyMetadata%29> para la propiedad de dependencia, los metadatos establecen el valor predeterminado en un nuevo objeto <xref:System.Collections.Generic.List%601> genérico.  
  
 <!-- TODO: review snippet reference [!code-csharp[PropertiesOvwSupport#CollectionProblemDefinition](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PropertiesOvwSupport/CSharp/page4.xaml.cs#collectionproblemdefinition)]  -->
 [!code-vb[PropertiesOvwSupport#CollectionProblemDefinition](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/PropertiesOvwSupport/visualbasic/page4.xaml.vb#collectionproblemdefinition)]  
[!code-csharp[PropertiesOvwSupport#CollectionProblemEndB](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PropertiesOvwSupport/CSharp/page4.xaml.cs#collectionproblemendb)]
[!code-vb[PropertiesOvwSupport#CollectionProblemEndB](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/PropertiesOvwSupport/visualbasic/page4.xaml.vb#collectionproblemendb)]  
  
 Sin embargo, si se limita a dejar el código tal y como se muestra, ese valor predeterminado único de la lista se compartirá para todas las instancias de `Aquarium`.  Si ejecutara el código de pruebas siguiente, diseñado para mostrar cómo crear dos instancias independientes de `Aquarium` y agregar un tipo `Fish` único diferente a cada una de ellas, vería un resultado sorprendente:  
  
 [!code-csharp[PropertiesOvwSupport#CollectionProblemTestCode](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PropertiesOvwSupport/CSharp/page4.xaml.cs#collectionproblemtestcode)]
 [!code-vb[PropertiesOvwSupport#CollectionProblemTestCode](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/PropertiesOvwSupport/visualbasic/page4.xaml.vb#collectionproblemtestcode)]  
  
 ¡En lugar de que el recuento de cada colección sea de uno, el recuento de cada colección es de dos\!  Esto se debe a que cada `Aquarium` agregó `Fish` a la colección de valores predeterminados, resultante de una llamada de constructor única en los metadatos, con lo que se comparte entre todas las instancias.  Esta situación casi nunca es deseable.  
  
 Para corregir este problema, debe restablecer el valor de propiedad de dependencia de colección en una instancia única, como parte de la llamada al constructor de clase.  Dado que la propiedad es de dependencia y de sólo lectura, se utiliza el método <xref:System.Windows.DependencyObject.SetValue%28System.Windows.DependencyPropertyKey%2CSystem.Object%29> para establecerla, utilizando una clave <xref:System.Windows.DependencyPropertyKey> que sólo está accesible dentro de la clase.  
  
 [!code-csharp[PropertiesOvwSupport#CollectionProblemCtor](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PropertiesOvwSupport/CSharp/page4.xaml.cs#collectionproblemctor)]
 [!code-vb[PropertiesOvwSupport#CollectionProblemCtor](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/PropertiesOvwSupport/visualbasic/page4.xaml.vb#collectionproblemctor)]  
  
 Ahora, si ejecuta de nuevo el mismo código de pruebas de antes, los resultados serían más previsibles, ya que `Aquarium` tiene su propia colección única.  
  
 Habría una ligera variación en el modelo si optase por hacer la propiedad de colección de lectura y escritura.  En ese caso, podría llamar al descriptor de acceso set público desde el constructor para llevar a cabo la inicialización, en la que igualmente se llamaría a la firma sin clave de <xref:System.Windows.DependencyObject.SetValue%28System.Windows.DependencyProperty%2CSystem.Object%29> dentro del contenedor set, utilizando un identificador de <xref:System.Windows.DependencyProperty> público.  
  
## Comunicar los cambios de valores de enlace de propiedades de colección  
 Una propiedad de colección que también es de dependencia no comunica automáticamente los cambios a sus subpropiedades.  Si crea enlaces en una colección, esto puede evitar que el enlace comunique los cambios, lo que invalida algunos escenarios de enlace de datos.  Sin embargo, si utiliza el tipo de colección <xref:System.Windows.FreezableCollection%601>, entonces sí se comunican correctamente los cambios de las subpropiedades a los elementos contenidos en la colección y el enlace funciona como está previsto.  
  
 Para habilitar el enlace de subpropiedades en una colección de objetos de dependencia, cree la propiedad de colección como el tipo <xref:System.Windows.FreezableCollection%601>, con una restricción de tipo para esa colección a cualquier clase derivada de <xref:System.Windows.DependencyObject>.  
  
## Vea también  
 <xref:System.Windows.FreezableCollection%601>   
 [Clases XAML y personalizadas para WPF](../../../../docs/framework/wpf/advanced/xaml-and-custom-classes-for-wpf.md)   
 [Información general sobre el enlace de datos](../../../../docs/framework/wpf/data/data-binding-overview.md)   
 [Información general sobre las propiedades de dependencia](../../../../docs/framework/wpf/advanced/dependency-properties-overview.md)   
 [Propiedades de dependencia personalizadas](../../../../docs/framework/wpf/advanced/custom-dependency-properties.md)   
 [Metadatos de las propiedades de dependencia](../../../../docs/framework/wpf/advanced/dependency-property-metadata.md)