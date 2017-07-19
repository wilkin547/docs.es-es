---
title: "Collections and Collection Types for XAML | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-wpf"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 58f8e7c6-9a41-4f25-8551-c042f1315baa
caps.latest.revision: 2
author: "wadepickett"
ms.author: "wpickett"
manager: "wpickett"
caps.handback.revision: 2
---
# Collections and Collection Types for XAML
En este tema se describe cómo definir propiedades de los tipos que están diseñadas para admitir una colección, y para admitir la sintaxis XAML para crear instancias de elementos de colección como elementos secundarios del elemento de un elemento de objeto primario o el elemento de propiedad.  
  
## conceptos de la colección de XAML  
 Conceptualmente, cualquier relación de XAML donde hay varios elementos secundarios dentro del ámbito de un elemento de objeto XAML o propiedad de XAML se debe implementar como una colección.  Esa colección debe estar asociado a una propiedad concreta de XAML de XAML tipo que es el elemento primario de esa relación.  La propiedad debe ser una colección porque un procesador XAML espera que cada elemento de marcado para que sea elemento recién agregado de la propiedad de colección de respaldo.  
  
 En el nivel del lenguaje XAML, los requisitos exactos de soporte de la colección no son totalmente definidos.  El concepto que una colección puede ser o una lista o un diccionario \(pero no ambos\) se define en el nivel de lenguaje XAML, pero que los tipos de respaldo representan las listas o diccionarios no lo define el lenguaje XAML.  
  
 En los servicios XAML de.NET Framework, el concepto de compatibilidad de la colección de XAML es más bien definido en términos de tipos de respaldo de .NET Framework.  Específicamente, la compatibilidad de XAML para las colecciones se basa en varios conceptos de .NET Framework y API que se utilizan para la programación de .NET Framework de las listas y los diccionarios en general.  
  
1.  La interfaz de <xref:System.Collections.IList> indica una colección list.  
  
2.  la interfaz de <xref:System.Collections.IDictionary> indica una colección dicionary.  
  
3.  <xref:System.Array> representa una matriz, y una matriz admite los métodos de <xref:System.Collections.IList> .  
  
 En cada uno de estos conceptos de la colección, un procesador servicios XAML de.NET Framework espera llamar al método de `Add` en una instancia concreta del tipo de propiedad de la colección.  O, en un escenario de serialización, un procesador XAML genera instancias discretas de XAML\-tipo para cada elemento encontrado en la lista, el diccionario matriz o según el concepto específico de cada colección de “elementos”.  Estos son: <xref:System.Collections.IList.Item%2A>; <xref:System.Collections.IDictionary.Item%2A>; <xref:System.Array.System%23Collections%23IList%23Item%2A> explícito para <xref:System.Array>.  
  
## colecciones genéricas  
 Las colecciones genéricas pueden ser útiles para general la programación de.NET Framework, y también se pueden utilizar para las propiedades de la colección de XAML.  Sin embargo, las interfaces genéricas <xref:System.Collections.Generic.IList%601> y <xref:System.Collections.Generic.IDictionary%602> no se identifican los procesadores servicios XAML de.NET Framework es equivalente a <xref:System.Collections.IList> no genérico o a <xref:System.Collections.IDictionary>.  En lugar de implementar las interfaces, un enfoque recomendado para tipos de propiedad de colección genéricos es derivar de las clases <xref:System.Collections.Generic.List%601> o <xref:System.Collections.Generic.Dictionary%602>.  Estas clases implementan interfaces no genéricas e incluyen así compatibilidad esperado para las colecciones de XAML en la implementación base.  
  
## Colecciones de solo lectura y inicialización Lógica  
 En la programación de.NET Framework, es un modelo de diseño común para crear cualquier propiedad que celebre un valor de una colección como una colección de solo lectura.  Este modelo permite la instancia que posee la propiedad de colección para mejorar el control qué ocurre a la colección.  Específicamente, el modelo evita el reemplazo accidental de la colección predefinida completa estableciendo la propiedad.  En este modelo, cualquier acceso a la colección de los llamadores en lugar de ello debe crear llamando a los métodos o propiedades como se admitido por el tipo de colección o las interfaces de intercalación pertinentes como <xref:System.Collections.IList>.  
  
 Con este modelo implica que cualquier clase que exponga una propiedad de solo lectura de la colección debe inicializar esa propiedad para contener una colección vacía.  La inicialización se realiza normalmente como parte del comportamiento de la construcción de la clase.  Para ser útil para XAML, es importante que por lógica hace referencia siempre al constructor predeterminado, porque XAML llama normalmente al constructor predeterminado antes de procesar las propiedades \(propiedades de colección u otro\).  
  
## Compatibilidad y colecciones del sistema de tipos XAML  
 Aparte de los mecanismos básicos de analizar XAML y de rellenar o de serializar propiedades de colección, el sistema de tipos de XAML implementados en los servicios XAML de.NET Framework incluye varias características de diseño que pertenecen a las colecciones en XAML.  
  
1.  <xref:System.Xaml.XamlType.IsCollection%2A> devuelve true si un tipo admite el tipo XAML que proporciona compatibilidad con la colección de XAML.  
  
2.  <xref:System.Xaml.XamlType.IsDictionary%2A> y <xref:System.Xaml.XamlType.IsArray%2A> pueden identificar más que el modo de recolección el tipo XAML admite.  Para los procesadores XAML personalizados basados en los servicios XAML de.NET Framework y el sistema de tipos XAML pero no se basan en las implementaciones de existentes <xref:System.Xaml.XamlWriter> , saber utilizan a qué modo de recolección podría ser necesario para saber qué método para invocar para el procesamiento de la colección.  
  
3.  Cada uno de los valores de propiedad anteriores potencialmente se afectan por reemplazos de <xref:System.Xaml.XamlType.LookupCollectionKind%2A> en un tipo XAML.