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
# <a name="xreference-markup-extension"></a><span data-ttu-id="fff0f-102">x:Reference (extensión de marcado)</span><span class="sxs-lookup"><span data-stu-id="fff0f-102">x:Reference Markup Extension</span></span>

<span data-ttu-id="fff0f-103">Hace referencia a una instancia que se declara en otro lugar del marcado XAML.</span><span class="sxs-lookup"><span data-stu-id="fff0f-103">References an instance that is declared elsewhere in XAML markup.</span></span> <span data-ttu-id="fff0f-104">La referencia hace referencia `x:Name`a un elemento .</span><span class="sxs-lookup"><span data-stu-id="fff0f-104">The reference refers to an element's `x:Name`.</span></span>

## <a name="xaml-attribute-usage"></a><span data-ttu-id="fff0f-105">Uso de atributos XAML</span><span class="sxs-lookup"><span data-stu-id="fff0f-105">XAML Attribute Usage</span></span>

```xaml
<object property="{x:Reference instancexName}" .../>
```

## <a name="xaml-object-element-usage"></a><span data-ttu-id="fff0f-106">Uso de elementos de objeto XAML</span><span class="sxs-lookup"><span data-stu-id="fff0f-106">XAML Object Element Usage</span></span>

```xaml
<object>
  <object.property>
    <x:Reference Name="instancexName"/>
  </object.property>
</object>
```

## <a name="xaml-values"></a><span data-ttu-id="fff0f-107">Valores XAML</span><span class="sxs-lookup"><span data-stu-id="fff0f-107">XAML Values</span></span>

|||
|-|-|
|`instancexName`|<span data-ttu-id="fff0f-108">El `x:Name` valor (o <xref:System.Windows.Markup.RuntimeNamePropertyAttribute>valor de la propiedad -identified) de la instancia a la que se hace referencia.</span><span class="sxs-lookup"><span data-stu-id="fff0f-108">The `x:Name` value (or value of the <xref:System.Windows.Markup.RuntimeNamePropertyAttribute>-identified property) of the referenced instance.</span></span>|

## <a name="remarks"></a><span data-ttu-id="fff0f-109">Observaciones</span><span class="sxs-lookup"><span data-stu-id="fff0f-109">Remarks</span></span>

<span data-ttu-id="fff0f-110">`x:Reference`proporciona compatibilidad de nivel de lenguaje XAML para un concepto de referencia de elemento que, de lo contrario, se implementó en marcos específicos como WPFWPF.</span><span class="sxs-lookup"><span data-stu-id="fff0f-110">`x:Reference` provides XAML language-level support for an element reference concept that was otherwise implemented in specific frameworks such as WPF.</span></span>

## <a name="xreference-and-wpf"></a><span data-ttu-id="fff0f-111">x:Referencia y WPF</span><span class="sxs-lookup"><span data-stu-id="fff0f-111">x:Reference and WPF</span></span>

<span data-ttu-id="fff0f-112">En WPFWPF y XAML 2006, las referencias de <xref:System.Windows.Data.Binding.ElementName%2A> elemento se abordan mediante la característica de nivel de marco de trabajo de enlace.</span><span class="sxs-lookup"><span data-stu-id="fff0f-112">In WPF and XAML 2006, element references are addressed by the framework-level feature of <xref:System.Windows.Data.Binding.ElementName%2A> binding.</span></span> <span data-ttu-id="fff0f-113">Para la mayoría de <xref:System.Windows.Data.Binding.ElementName%2A> las aplicaciones y escenarios de WPFWPF, el enlace todavía debe usarse.</span><span class="sxs-lookup"><span data-stu-id="fff0f-113">For most WPF applications and scenarios, <xref:System.Windows.Data.Binding.ElementName%2A> binding should still be used.</span></span> <span data-ttu-id="fff0f-114">Las excepciones a esta guía general pueden incluir casos en los que hay contexto de datos u otras consideraciones de ámbito que hacen que el enlace de datos no sea práctico y donde no se implica la compilación de marcado.</span><span class="sxs-lookup"><span data-stu-id="fff0f-114">Exceptions to this general guidance might include cases where there are data context or other scoping considerations that make data binding impractical and where markup compilation is not involved.</span></span>

<span data-ttu-id="fff0f-115">`x:Reference`es una construcción definida en XAML 2009.</span><span class="sxs-lookup"><span data-stu-id="fff0f-115">`x:Reference` is a construct defined in XAML 2009.</span></span> <span data-ttu-id="fff0f-116">En WPF, puede usar características de XAML 2009 pero solo para XAML que esté compilado por marcado para WPF.</span><span class="sxs-lookup"><span data-stu-id="fff0f-116">In WPF, you can use XAML 2009 features, but only for XAML that is not WPF markup-compiled.</span></span> <span data-ttu-id="fff0f-117">El XAML compilado por marcado para WPF y el formulario BAML de XAML no admiten de momento palabras clave ni características del lenguaje XAML 2009.</span><span class="sxs-lookup"><span data-stu-id="fff0f-117">Markup-compiled XAML and the BAML form of XAML do not currently support the XAML 2009 language keywords and features.</span></span>
