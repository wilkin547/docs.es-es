---
title: Propiedades de dependencia de tipo de colección
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- properties [WPF], dependency
- properties [WPF], collection-type
- dependency properties [WPF]
- collection-type properties [WPF]
ms.assetid: 99f96a42-3ab7-4f64-a16b-2e10d654e97c
ms.openlocfilehash: 039ae0cb314eba2f1bb3e5b39f2127a5e694f334
ms.sourcegitcommit: f348c84443380a1959294cdf12babcb804cfa987
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/12/2019
ms.locfileid: "73974156"
---
# <a name="collection-type-dependency-properties"></a>Propiedades de dependencia de tipo de colección
En este tema se proporciona una guía y modelos recomendados para implementar una propiedad de dependencia donde el tipo de la propiedad es un tipo de colección.  

<a name="implementing"></a>   
## <a name="implementing-a-collection-type-dependency-property"></a>Implementar una propiedad de dependencia de tipo de colección  
 En el caso de una propiedad de dependencia en general, el modelo de implementación que se sigue es que se define un contenedor de propiedades CLR, donde esa propiedad está respaldada por un identificador de <xref:System.Windows.DependencyProperty> en lugar de un campo u otra construcción. Siga este mismo modelo al implementar una propiedad de tipo de colección. Sin embargo, una propiedad de tipo de colección introduce cierta complejidad en el patrón siempre que el tipo contenido en la colección sea un <xref:System.Windows.DependencyObject> o <xref:System.Windows.Freezable> clase derivada.  
  
<a name="initializing"></a>   
## <a name="initializing-the-collection-beyond-the-default-value"></a>Inicialización de la colección más allá del valor predeterminado  
 Cuando cree una propiedad de dependencia, no especifique el valor predeterminado de la propiedad como el valor inicial del campo. En su lugar, especifique el valor predeterminado a través de los metadatos de la propiedad de dependencia. Si la propiedad es un tipo de referencia, el valor predeterminado especificado en los metadatos de la propiedad de dependencia no es un valor predeterminado por instancia; en su lugar, es un valor predeterminado que se aplica a todas las instancias del tipo. Por lo tanto, debe tener cuidado de no usar la colección estática singular definida por los metadatos de la propiedad de colección como el valor predeterminado operativo para las instancias recién creadas del tipo. En su lugar, debe asegurarse de establecer deliberadamente el valor de la colección en una colección única (instancia) como parte de la lógica del constructor de clase. De lo contrario, habrá creado involuntariamente una clase singleton.  
  
 Considere el ejemplo siguiente. En la siguiente sección del ejemplo se muestra la definición de una clase `Aquarium`, que contiene un error con el valor predeterminado. La clase define la propiedad de dependencia de tipo de colección `AquariumObjects`, que usa el tipo de <xref:System.Collections.Generic.List%601> genérico con una restricción de tipo <xref:System.Windows.FrameworkElement>. En la llamada <xref:System.Windows.DependencyProperty.Register%28System.String%2CSystem.Type%2CSystem.Type%2CSystem.Windows.PropertyMetadata%29> para la propiedad de dependencia, los metadatos establecen el valor predeterminado para que sea un nuevo <xref:System.Collections.Generic.List%601>genérico.

> [!WARNING]
> El código siguiente no se comporta correctamente.

 [!code-csharp[PropertiesOvwSupport2#CollectionProblemDefinition](~/samples/snippets/csharp/VS_Snippets_Wpf/PropertiesOvwSupport2/CSharp/page.xaml.cs#collectionproblemdefinition)]
 [!code-vb[PropertiesOvwSupport2#CollectionProblemDefinition](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PropertiesOvwSupport2/visualbasic/page.xaml.vb#collectionproblemdefinition)]  
  
 Sin embargo, si se limita a dejar el código tal como se muestra, ese valor predeterminado de lista único se comparte en todas las instancias de `Aquarium`. Si ejecutara el siguiente código de prueba, destinado a mostrar cómo se crea una instancia de dos instancias `Aquarium` independientes y se agrega un único valor `Fish` diferente a cada una de ellas, vería un resultado sorprendente:  
  
 [!code-csharp[PropertiesOvwSupport#CollectionProblemTestCode](~/samples/snippets/csharp/VS_Snippets_Wpf/PropertiesOvwSupport/CSharp/page4.xaml.cs#collectionproblemtestcode)]
 [!code-vb[PropertiesOvwSupport#CollectionProblemTestCode](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PropertiesOvwSupport/visualbasic/page4.xaml.vb#collectionproblemtestcode)]  
  
 En lugar de tener un recuento de uno, cada colección tiene un recuento de dos. Esto se debe a que cada `Aquarium` agregó su `Fish` a la colección de valores predeterminados, que resultó de una única llamada de constructor en los metadatos y, por tanto, se compartió en todas las instancias. Esta situación casi nunca es la deseada.  
  
 Para corregir este problema, debe restablecer el valor de la propiedad de dependencia de la colección en una instancia única, como parte de la llamada al constructor de clase. Dado que la propiedad es una propiedad de dependencia de solo lectura, use el método <xref:System.Windows.DependencyObject.SetValue%28System.Windows.DependencyPropertyKey%2CSystem.Object%29> para establecerla, utilizando el <xref:System.Windows.DependencyPropertyKey> que solo es accesible dentro de la clase.  
  
 [!code-csharp[PropertiesOvwSupport#CollectionProblemCtor](~/samples/snippets/csharp/VS_Snippets_Wpf/PropertiesOvwSupport/CSharp/page4.xaml.cs#collectionproblemctor)]
 [!code-vb[PropertiesOvwSupport#CollectionProblemCtor](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PropertiesOvwSupport/visualbasic/page4.xaml.vb#collectionproblemctor)]  
  
 Ahora, si ejecutara el mismo código de prueba de nuevo, podría obtener resultados más previsibles, donde cada `Aquarium` admite su propia colección única.  
  
 Se produciría una ligera variación en este modelo si decidiera definir la propiedad de colección como de lectura y escritura. En ese caso, puede llamar al descriptor de acceso set público desde el constructor para realizar la inicialización, lo que seguiría llamando a la firma sin clave de <xref:System.Windows.DependencyObject.SetValue%28System.Windows.DependencyProperty%2CSystem.Object%29> dentro del contenedor del conjunto, mediante un identificador de <xref:System.Windows.DependencyProperty> público.  
  
## <a name="reporting-binding-value-changes-from-collection-properties"></a>Notificación de cambios en los valores de enlace de las propiedades de colección  
 Una propiedad de colección que es una propiedad de dependencia no notifica automáticamente los cambios en sus subpropiedades. Si está creando enlaces en una colección, esto puede impedir que el enlace comunique los cambios, lo que invalidaría algunos escenarios de enlace de datos. Sin embargo, si usa el tipo de colección <xref:System.Windows.FreezableCollection%601> como tipo de colección, los cambios de subpropiedades en los elementos contenidos en la colección se indican correctamente y el enlace funciona según lo esperado.  
  
 Para habilitar el enlace de subpropiedades en una colección de objetos de dependencia, cree la propiedad de colección como de tipo <xref:System.Windows.FreezableCollection%601>, con una restricción de tipo para esa colección en cualquier clase derivada <xref:System.Windows.DependencyObject>.  
  
## <a name="see-also"></a>Vea también

- <xref:System.Windows.FreezableCollection%601>
- [Clases XAML y personalizadas para WPF](xaml-and-custom-classes-for-wpf.md)
- [Información general sobre el enlace de datos](../../../desktop-wpf/data/data-binding-overview.md)
- [Información general sobre las propiedades de dependencia](dependency-properties-overview.md)
- [Propiedades de dependencia personalizadas](custom-dependency-properties.md)
- [Metadatos de las propiedades de dependencia](dependency-property-metadata.md)
