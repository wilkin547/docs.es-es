---
title: Colecciones y tipos de colecciones para XAML
ms.date: 03/30/2017
ms.assetid: 58f8e7c6-9a41-4f25-8551-c042f1315baa
ms.openlocfilehash: 5605c97b13503e18e2f698f2a19f715663052b08
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
---
# <a name="collections-and-collection-types-for-xaml"></a>Colecciones y tipos de colecciones para XAML
En este tema se describe cómo definir propiedades de los tipos que se han diseñado para admitir una colección y para admitir la sintaxis XAML para crear instancias de elementos de la colección como elemento secundario de un elemento de objeto primario o un elemento de propiedad.  
  
## <a name="xaml-collection-concepts"></a>Conceptos de la colección de XAML  
 Conceptualmente, una relación en XAML donde hay varios elementos secundarios dentro del ámbito de un elemento de objeto XAML o elemento de propiedad XAML debe implementarse como una colección. Esa colección debe asociarse con una determinada propiedad XAML del tipo XAML que es el elemento primario en dicha relación. La propiedad debe ser una colección porque un procesador XAML espera asignar cada elemento de marcado para ser un elemento recién agregado de la propiedad de colección de copias de seguridad.  
  
 En el nivel de lenguaje XAML, los requisitos concretos de soporte de colección no se definen totalmente. El concepto que puede ser una colección de una lista o un diccionario (pero no ambos) se define en el nivel de lenguaje XAML, pero los tipos de copias de seguridad de representan cualquier listas o diccionarios no está definido por el lenguaje XAML.  
  
 En los servicios XAML de .NET Framework, el concepto de soporte de colección de XAML es más nítido en cuanto a los tipos de respaldo de .NET Framework. En concreto, la compatibilidad de XAML para las colecciones se basa en varios conceptos de .NET Framework y las API que se utilizan para listas y diccionarios en programación general en .NET Framework.  
  
1.  El <xref:System.Collections.IList> interfaz indica una colección de lista.  
  
2.  El <xref:System.Collections.IDictionary> interfaz indica una colección dicionary.  
  
3.  <xref:System.Array> Representa una matriz y una matriz es compatible con <xref:System.Collections.IList> métodos.  
  
 En cada uno de estos conceptos de la colección, se espera un procesador de servicios XAML de .NET Framework llamar a la `Add` método en una instancia concreta del tipo de propiedad de la colección. O bien, en un escenario de serialización, un procesador XAML produce instancias de tipo XAML discretos para cada elemento que se encuentra en la lista, el diccionario o la matriz basada en concepto específico de cada colección de "Elementos". Estos son: <xref:System.Collections.IList.Item%2A>; <xref:System.Collections.IDictionary.Item%2A>; el explícita <xref:System.Array.System%23Collections%23IList%23Item%2A> para <xref:System.Array>.  
  
## <a name="generic-collections"></a>Colecciones genéricas  
 Las colecciones genéricas pueden ser útiles para la programación general de .NET Framework y también pueden utilizarse para propiedades de colección de XAML. Sin embargo, la clase genérica interfaces <xref:System.Collections.Generic.IList%601> y <xref:System.Collections.Generic.IDictionary%602> no se identifican con procesadores de servicios XAML de .NET Framework como equivalente a no genérica <xref:System.Collections.IList> o <xref:System.Collections.IDictionary>. En lugar de implementar las interfaces, una solución recomendada para los tipos de propiedad de colección genérica es derivar de las clases <xref:System.Collections.Generic.List%601> o <xref:System.Collections.Generic.Dictionary%602>. Estas clases implementan las interfaces no genéricas y, por tanto, incluyen la compatibilidad de esperado para colecciones de XAML en la implementación base.  
  
## <a name="read-only-collections-and-initialization-logic"></a>Colecciones de solo lectura y la lógica de inicialización  
 En la programación de .NET Framework, es un modelo de diseño común para realizar cualquier propiedad que contiene un valor de una colección como una colección de solo lectura. Este patrón permite que la instancia que posee la propiedad de colección para controlar mejor lo que ocurre a la colección... En concreto, el patrón impide sustitución accidental de toda la colección existente estableciendo la propiedad. En este modelo, cualquier acceso a la colección por los llamadores en su lugar, debe realizarse mediante una llamada a métodos o propiedades como admitidos por el tipo de colección o las interfaces de colección relevante como <xref:System.Collections.IList>.  
  
 El uso de este patrón implica que cualquier clase que expone una propiedad de colección de solo lectura en primer lugar debe inicializar esa propiedad para almacenar una colección vacía. Normalmente, la inicialización se realiza como parte del comportamiento de construcción de la clase. Para ser útil para XAML, es importante que tales lógica siempre hace referencia al constructor predeterminado, dado que XAML generalmente llama al constructor predeterminado antes de procesar las propiedades (propiedades de colección o de otro modo).  
  
## <a name="xaml-type-system-support-and-collections"></a>Colecciones y compatibilidad de sistema de tipos XAML  
 Más allá de los mecanismos básicos de análisis de XAML y rellenar o serializar las propiedades de la colección, el sistema de tipos XAML, tal como se implementa en los servicios XAML de .NET Framework incluye varias características de diseño que pertenecen a las colecciones de XAML.  
  
1.  <xref:System.Xaml.XamlType.IsCollection%2A> Devuelve true si el tipo XAML está respaldado por un tipo que proporciona soporte de colección de XAML.  
  
2.  <xref:System.Xaml.XamlType.IsDictionary%2A> y <xref:System.Xaml.XamlType.IsArray%2A> , puede determinar qué modo de recopilación que admite el tipo XAML. Para XAML personalizado procesadores que se basan en los servicios XAML de .NET Framework y el XAML de sistema de tipos pero no se basa en existente <xref:System.Xaml.XamlWriter> implementaciones, saber qué modo de recopilación se utiliza puede ser necesario para saber qué método que se invocará para procesamiento de la colección.  
  
3.  Cada uno de los valores de propiedad anteriores se pueden ver afectadas por las invalidaciones de <xref:System.Xaml.XamlType.LookupCollectionKind%2A> en un tipo XAML.
