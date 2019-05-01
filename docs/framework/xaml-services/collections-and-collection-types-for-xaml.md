---
title: Colecciones y tipos de colecciones para XAML
ms.date: 03/30/2017
ms.assetid: 58f8e7c6-9a41-4f25-8551-c042f1315baa
ms.openlocfilehash: 4123b64545f7c47a96c4cae496046a89b7e576b0
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61954185"
---
# <a name="collections-and-collection-types-for-xaml"></a>Colecciones y tipos de colecciones para XAML

Este tema describe cómo definir las propiedades de tipos que están diseñados para admitir una colección y para admitir la sintaxis XAML para crear instancias de elementos de la colección como elemento secundario de un elemento del objeto primario o un elemento de propiedad.

## <a name="xaml-collection-concepts"></a>Conceptos de la colección de XAML

Conceptualmente, cualquier relación de XAML donde hay varios elementos secundarios dentro del ámbito de un elemento de objeto XAML o elemento de propiedad XAML debe implementarse como una colección. Esa colección debe asociarse a una propiedad XAML concreto del tipo XAML que es el elemento primario en dicha relación. La propiedad debe ser una colección porque un procesador XAML espera asignar cada elemento de marcado para ser un elemento recién agregado de la propiedad de colección de respaldo.

En el nivel de lenguaje XAML, los requisitos exactos de compatibilidad colección no se definen por completo. El concepto que una colección puede ser una lista o un diccionario (pero no ambos) se define en el nivel de lenguaje XAML, pero qué tipos de respaldo representan cualquier listas o diccionarios no está definido por el lenguaje XAML.

En los servicios XAML de .NET Framework, el concepto de soporte técnico de colección XAML se define con mayor claridad en cuanto a seguridad de tipos de .NET Framework. En concreto, la compatibilidad XAML para las colecciones se basa en varios conceptos de .NET Framework y las API que se usan para listas y diccionarios en programación general de .NET Framework.

1. El <xref:System.Collections.IList> interfaz indica una colección de lista.

2. El <xref:System.Collections.IDictionary> interfaz indica una colección de diccionarios.

3. <xref:System.Array> Representa una matriz y una matriz es compatible con <xref:System.Collections.IList> métodos.

En cada uno de estos conceptos de la colección, se espera un procesador XAML de los servicios XAML de .NET Framework llamar a la `Add` método en una instancia específica del tipo de propiedad de colección. O bien, en un escenario de serialización, un procesador XAML genera instancias de tipo XAML discretas para cada elemento que se encuentra en la lista, diccionario o matriz basándose en el concepto de "Elementos" de la colección. Estos son: <xref:System.Collections.IList.Item%2A>; <xref:System.Collections.IDictionary.Item%2A>; la configuración explícita <xref:System.Array.System%23Collections%23IList%23Item%2A> para <xref:System.Array>.

## <a name="generic-collections"></a>Colecciones genéricas

Las colecciones genéricas pueden ser útiles para la programación de .NET Framework generales y también se pueden usar para las propiedades de colección XAML. Sin embargo, las interfaces de la interfaz genérica <xref:System.Collections.Generic.IList%601> y <xref:System.Collections.Generic.IDictionary%602> no se identifican los procesadores de XAML de los servicios XAML de .NET Framework como equivalente a la no genérica <xref:System.Collections.IList> o <xref:System.Collections.IDictionary>. En lugar de implementar las interfaces, un enfoque recomendado para los tipos de propiedad de colección genérica es derivar de las clases <xref:System.Collections.Generic.List%601> o <xref:System.Collections.Generic.Dictionary%602>. Estas clases implementan las interfaces no genéricas y, por tanto, incluyen la compatibilidad esperada para las colecciones de XAML en la implementación base.

## <a name="read-only-collections-and-initialization-logic"></a>Colecciones de solo lectura y lógica de inicialización

En la programación de .NET Framework, es un patrón de diseño común para realizar cualquier propiedad que contiene un valor de una colección como una colección de solo lectura. Este patrón permite que la instancia que posee la propiedad de colección para controlar mejor lo que sucede a la colección... En concreto, el patrón impide sustitución accidental de toda la colección ya existente estableciendo la propiedad. En este patrón, debe realizarse en su lugar cualquier acceso a la colección por llamadores con llamadas a métodos o propiedades compatibles con el tipo de colección o las interfaces de colección correspondiente como <xref:System.Collections.IList>.

Con este patrón implica que cualquier clase que expone una propiedad de colección de solo lectura en primer lugar debe inicializar esa propiedad para almacenar una colección vacía. Normalmente, la inicialización se realiza como parte del comportamiento de construcción de la clase. Para ser útil para XAML, es importante que siempre hace referencia esa lógica al constructor predeterminado, porque XAML generalmente llama al constructor predeterminado antes de procesar las propiedades (propiedades de colección o de otro modo).

## <a name="xaml-type-system-support-and-collections"></a>Colecciones y compatibilidad de sistema de tipos XAML

Más allá de los mecanismos básicos de análisis de XAML y rellenar o serializar propiedades de la colección, el sistema de tipos XAML, tal como está implementado en los servicios XAML de .NET Framework incluye varias características de diseño que pertenecen a las colecciones de XAML.

1. <xref:System.Xaml.XamlType.IsCollection%2A> Devuelve true si el tipo XAML está respaldado por un tipo que proporciona compatibilidad de la colección de XAML.

2. <xref:System.Xaml.XamlType.IsDictionary%2A> y <xref:System.Xaml.XamlType.IsArray%2A> , puede determinar qué modo de recopilación que admite el tipo XAML. Para XAML personalizado procesadores que se basan en los servicios XAML de .NET Framework y el XAML, sistema de tipos pero no según existente <xref:System.Xaml.XamlWriter> implementaciones, saber qué modo de recopilación se utiliza podría ser necesario para saber qué método de invocación para procesamiento de la colección.

3. Cada uno de los valores de propiedad anteriores se pueden ver afectadas por las invalidaciones de <xref:System.Xaml.XamlType.LookupCollectionKind%2A> en un tipo XAML.
