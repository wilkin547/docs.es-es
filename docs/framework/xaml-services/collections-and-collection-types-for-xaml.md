---
title: Colecciones y tipos de colecciones para XAML
ms.date: 03/30/2017
ms.assetid: 58f8e7c6-9a41-4f25-8551-c042f1315baa
ms.openlocfilehash: 63f6346837f77dbdbdcb4a90ec5af725be69ee02
ms.sourcegitcommit: 30a83efb57c468da74e9e218de26cf88d3254597
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/20/2019
ms.locfileid: "68364339"
---
# <a name="collections-and-collection-types-for-xaml"></a>Colecciones y tipos de colecciones para XAML

En este tema se describe cómo definir las propiedades de los tipos diseñados para admitir una colección y para admitir la sintaxis XAML para crear instancias de los elementos de la colección como elementos secundarios de un elemento de objeto primario o elemento de propiedad.

## <a name="xaml-collection-concepts"></a>Conceptos de la colección XAML

Conceptualmente, cualquier relación en XAML donde haya varios elementos secundarios dentro del ámbito de un elemento de objeto XAML o un elemento de propiedad XAML debe implementarse como una colección. Esa colección debe estar asociada a una propiedad XAML determinada del tipo XAML que sea el elemento primario de esa relación. La propiedad debe ser una colección porque un procesador XAML espera asignar cada elemento de marcado para que sea un elemento recién agregado de la propiedad de la colección de respaldo.

En el nivel de lenguaje XAML, los requisitos exactos de la compatibilidad con colecciones no están totalmente definidos. El concepto de que una colección puede ser una lista o un diccionario (pero no ambos) se define en el nivel de lenguaje XAML, pero los tipos de respaldo que representan listas o diccionarios no están definidos por el lenguaje XAML.

En .NET Framework servicios XAML, el concepto de compatibilidad con colecciones XAML se define con mayor claridad en cuanto a .NET Framework tipos de respaldo. En concreto, la compatibilidad con XAML para las colecciones se basa en varios conceptos de .NET Framework y API que se usan para las listas y los diccionarios en la programación de .NET Framework general.

1. La <xref:System.Collections.IList> interfaz indica una colección de listas.

2. La <xref:System.Collections.IDictionary> interfaz indica una colección de diccionarios.

3. <xref:System.Array>representa una matriz y una matriz admite <xref:System.Collections.IList> métodos.

En cada uno de estos conceptos de colección, un .NET Framework procesador XAML de servicios XAML espera llamar `Add` al método en una instancia específica del tipo de la propiedad de la colección. O bien, en un escenario de serialización, un procesador XAML genera instancias discretas de tipo XAML para cada elemento que se encuentra en la lista, diccionario o matriz basándose en el concepto de "elementos" específico de cada colección. Estos son: <xref:System.Collections.IList.Item%2A>; ; explícitamente <xref:System.Array.System%23Collections%23IList%23Item%2A> para <xref:System.Array>. <xref:System.Collections.IDictionary.Item%2A>

## <a name="generic-collections"></a>Colecciones genéricas

Las colecciones genéricas pueden ser útiles para la programación de .NET Framework general y también se pueden usar para las propiedades de colección XAML. Sin embargo, las interfaces <xref:System.Collections.Generic.IList%601> genéricas y <xref:System.Collections.Generic.IDictionary%602> no se identifican mediante los procesadores XAML de los servicios XAML de .NET Framework como <xref:System.Collections.IList> equivalentes a los de o <xref:System.Collections.IDictionary>no genéricos. En lugar de implementar las interfaces, un enfoque recomendado para los tipos de propiedad de colección genérica es derivar <xref:System.Collections.Generic.Dictionary%602>de las clases <xref:System.Collections.Generic.List%601> o. Estas clases implementan las interfaces no genéricas y, por tanto, incluyen la compatibilidad esperada con las colecciones XAML en la implementación base.

## <a name="read-only-collections-and-initialization-logic"></a>Colecciones de solo lectura y lógica de inicialización

En la programación de .NET Framework, es un patrón de diseño común para convertir en una colección de solo lectura cualquier propiedad que contenga un valor de una colección. Este patrón permite que la instancia que posee la propiedad de colección controle mejor lo que sucede con la colección. En concreto, el patrón evita la sustitución accidental de toda la colección existente previamente mediante el establecimiento de la propiedad. En este patrón, el acceso a la colección mediante llamadores debe realizarse llamando a métodos o propiedades según sea compatible con el tipo de colección y/o las interfaces de colección relevantes como <xref:System.Collections.IList>.

El uso de este patrón implica que cualquier clase que exponga una propiedad de colección de solo lectura debe inicializar primero esa propiedad para contener una colección vacía. Normalmente, la inicialización se realiza como parte del comportamiento de construcción de la clase. Para que sea útil para XAML, es importante que el constructor sin parámetros siempre haga referencia a dicha lógica, ya que XAML normalmente llama al constructor sin parámetros antes de procesar las propiedades (propiedades de la colección o de otro modo).

## <a name="xaml-type-system-support-and-collections"></a>Compatibilidad y colecciones del sistema de tipos XAML

Además de los mecanismos básicos para analizar XAML y rellenar o serializar las propiedades de una colección, el sistema de tipos XAML tal como se implementa en .NET Framework servicios XAML incluye varias características de diseño que pertenecen a colecciones en XAML.

1. <xref:System.Xaml.XamlType.IsCollection%2A>Devuelve true si el tipo XAML está respaldado por un tipo que proporciona compatibilidad con la colección XAML.

2. <xref:System.Xaml.XamlType.IsDictionary%2A>y <xref:System.Xaml.XamlType.IsArray%2A> pueden identificar mejor el modo de recopilación que admite el tipo XAML. En el caso de los procesadores XAML personalizados que se basan en .NET Framework servicios XAML y el sistema de tipos XAML <xref:System.Xaml.XamlWriter> , pero no en las implementaciones existentes, es posible que sea necesario saber qué modo de recopilación se usa para saber qué método se debe invocar. procesamiento de recopilación.

3. Los valores de propiedad anteriores pueden verse afectados por invalidaciones de <xref:System.Xaml.XamlType.LookupCollectionKind%2A> en un tipo XAML.
