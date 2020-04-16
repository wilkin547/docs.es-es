---
title: Colecciones y tipos de colecciones para XAML
ms.date: 03/30/2017
ms.assetid: 58f8e7c6-9a41-4f25-8551-c042f1315baa
ms.openlocfilehash: 2ec58026c605df31489c8aab4c4cc714dab11474
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/24/2020
ms.locfileid: "81432585"
---
# <a name="collections-and-collection-types-for-xaml"></a>Colecciones y tipos de colección para XAML

En este artículo se describe cómo definir propiedades de tipos que están diseñados para admitir una colección y para admitir la sintaxis XAML para crear instancias de elementos de colección como elementos secundarios de un elemento de objeto primario o elemento de propiedad.

## <a name="xaml-collection-concepts"></a>Conceptos de colección XAML

Conceptualmente, cualquier relación en XAML donde hay varios elementos secundarios dentro del ámbito de un elemento de objeto XAML o un elemento de propiedad XAML debe implementarse como una colección. Esa colección debe estar asociada a una propiedad XAML determinada del tipo XAML que es el elemento primario de esa relación. La propiedad debe ser una colección porque un procesador XAML espera asignar cada elemento en el marcado para que sea un elemento recién agregado de la propiedad de colección de respaldo.

En el nivel de lenguaje XAML, los requisitos exactos de la compatibilidad con la colección no están completamente definidos. El concepto de que una colección puede ser una lista o un diccionario (pero no ambos) se define en el nivel de lenguaje XAML, pero qué tipos de respaldo representan listas o diccionarios no está definido por el lenguaje XAML.

En los servicios XAML de .NET, el concepto de compatibilidad con la colección XAML se define más claramente en términos de tipos de respaldo de .NET. En concreto, la compatibilidad de XAML para colecciones se basa en varios conceptos y API de .NET que se usan para listas y diccionarios en la programación general de .NET.

1. La <xref:System.Collections.IList> interfaz indica una colección de listas.

2. La <xref:System.Collections.IDictionary> interfaz indica una colección de diccionarios.

3. <xref:System.Array>representa una matriz y una <xref:System.Collections.IList> matriz admite métodos.

En cada uno de estos conceptos de colección, `Add` un procesador XAML de Servicios XAML de .NET espera llamar al método en una instancia específica del tipo de la propiedad de colección. O bien, en un escenario de serialización, un procesador XAML genera instancias de tipo XAML discretas para cada elemento que se encuentra en la lista, diccionario o matriz en función del concepto específico de cada colección de "Items". Estos elementos <xref:System.Collections.IList.Item%2A?displayProperty=nameWithType>son: ; <xref:System.Collections.IDictionary.Item%2A?displayProperty=nameWithType>; el <xref:System.Array.System%23Collections%23IList%23Item%2A?displayProperty=nameWithType> explícito <xref:System.Array>para .

## <a name="generic-collections"></a>Colecciones genéricas

Las colecciones genéricas pueden ser útiles para la programación general de .NET y también se pueden usar para las propiedades de la colección XAML. Sin embargo, <xref:System.Collections.Generic.IList%601> las <xref:System.Collections.Generic.IDictionary%602> interfaces genéricas y no se identifican por los <xref:System.Collections.IList> <xref:System.Collections.IDictionary>procesadores XAML de servicios XAML de .NET como equivalentes a los no genéricos o . En lugar de implementar las interfaces, un enfoque recomendado para <xref:System.Collections.Generic.List%601> <xref:System.Collections.Generic.Dictionary%602>los tipos de propiedad de colección genérica es derivar de las clases o . Estas clases implementan las interfaces no genéricas y, por lo tanto, incluyen la compatibilidad esperada para las colecciones XAML en la implementación base.

## <a name="read-only-collections-and-initialization-logic"></a>Colecciones de solo lectura y lógica de inicialización

En la programación de .NET, es un patrón de diseño común para hacer cualquier propiedad que contiene un valor de una colección como una colección de solo lectura. Este patrón permite que la instancia propietaria de la propiedad collection controle mejor lo que sucede con la colección. En concreto, el patrón evita la sustitución accidental de toda la colección preexistente estableciendo la propiedad. En este patrón, cualquier acceso a la colección por los llamadores debe realizarse en su lugar <xref:System.Collections.IList>llamando a métodos o propiedades según lo admitido por el tipo de colección o las interfaces de colección relevantes como .

El uso de este patrón implica que cualquier clase que expone una propiedad de colección de solo lectura debe inicializar primero esa propiedad para contener una colección vacía. Normalmente, la inicialización se realiza como parte del comportamiento de construcción de la clase. Para ser útil para XAML, es importante que el constructor sin parámetros siempre haga referencia a esta lógica, porque XAML suele llamar al constructor sin parámetros antes de procesar las propiedades (propiedades de colección o de otro modo).

## <a name="xaml-type-system-support-and-collections"></a>Compatibilidad y cobros del sistema de tipos XAML

Más allá de la mecánica básica de análisis de XAML y rellenar o serializar propiedades de colección, el sistema de tipos XAML tal como se implementa en Servicios XAML de .NET incluye varias características de diseño que pertenecen a colecciones en XAML.

1. <xref:System.Xaml.XamlType.IsCollection%2A>devuelve true si el tipo XAML está respaldado por un tipo que proporciona compatibilidad con la colección XAML.

2. <xref:System.Xaml.XamlType.IsDictionary%2A>y <xref:System.Xaml.XamlType.IsArray%2A> puede identificar aún más qué modo de colección admite el tipo XAML. Para los procesadores XAML personalizados que se basan en los <xref:System.Xaml.XamlWriter> servicios XAML de .NET y el sistema de tipos XAML, pero no en las implementaciones existentes, es posible que sea necesario saber qué modo de colección se usa para saber qué método invocar para el procesamiento de la colección.

3. Cada uno de los valores de propiedad <xref:System.Xaml.XamlType.LookupCollectionKind%2A> anteriores está potencialmente influenciado por invalidaciones de un tipo XAML.
