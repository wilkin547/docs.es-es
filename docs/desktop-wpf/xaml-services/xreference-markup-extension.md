---
title: x:Reference (extensión de marcado)
ms.date: 03/30/2017
helpviewer_keywords:
- x:Reference markup extension [XAML Services]
- XAML [XAML Services], x:Reference Markup Extension
- Reference markup extension [XAML Services]
ms.assetid: 2982e68b-d26b-4aa3-826a-34c57a9c5199
ms.openlocfilehash: f06e259893111a436e5afe2df754c3edee326d54
ms.sourcegitcommit: c2d9718996402993cf31541f11e95531bc68bad0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/27/2020
ms.locfileid: "81432657"
---
# <a name="xreference-markup-extension"></a>x:Reference (extensión de marcado)

Hace referencia a una instancia que se declara en otro lugar del marcado XAML. La referencia hace referencia `x:Name`a un elemento .

## <a name="xaml-attribute-usage"></a>Uso de atributos XAML

```xaml
<object property="{x:Reference instancexName}" .../>
```

## <a name="xaml-object-element-usage"></a>Uso de elementos de objeto XAML

```xaml
<object>
  <object.property>
    <x:Reference Name="instancexName"/>
  </object.property>
</object>
```

## <a name="xaml-values"></a>Valores XAML

|||
|-|-|
|`instancexName`|El `x:Name` valor (o <xref:System.Windows.Markup.RuntimeNamePropertyAttribute>valor de la propiedad -identified) de la instancia a la que se hace referencia.|

## <a name="remarks"></a>Observaciones

`x:Reference`proporciona compatibilidad de nivel de lenguaje XAML para un concepto de referencia de elemento que, de lo contrario, se implementó en marcos específicos como WPFWPF.

## <a name="xreference-and-wpf"></a>x:Referencia y WPF

En WPFWPF y XAML 2006, las referencias de <xref:System.Windows.Data.Binding.ElementName%2A> elemento se abordan mediante la característica de nivel de marco de trabajo de enlace. Para la mayoría de <xref:System.Windows.Data.Binding.ElementName%2A> las aplicaciones y escenarios de WPFWPF, el enlace todavía debe usarse. Las excepciones a esta guía general pueden incluir casos en los que hay contexto de datos u otras consideraciones de ámbito que hacen que el enlace de datos no sea práctico y donde no se implica la compilación de marcado.

`x:Reference`es una construcción definida en XAML 2009. En WPF, puede usar características de XAML 2009 pero solo para XAML que esté compilado por marcado para WPF. El XAML compilado por marcado para WPF y el formulario BAML de XAML no admiten de momento palabras clave ni características del lenguaje XAML 2009.
