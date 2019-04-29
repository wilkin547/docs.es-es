---
title: x:Reference (extensión de marcado)
ms.date: 03/30/2017
helpviewer_keywords:
- x:Reference markup extension [XAML Services]
- XAML [XAML Services], x:Reference Markup Extension
- Reference markup extension [XAML Services]
ms.assetid: 2982e68b-d26b-4aa3-826a-34c57a9c5199
ms.openlocfilehash: 960f5c0e4192df72090c1a571dfc2fc5e3fd8ba3
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61938884"
---
# <a name="xreference-markup-extension"></a><span data-ttu-id="cb8a5-102">x:Reference (extensión de marcado)</span><span class="sxs-lookup"><span data-stu-id="cb8a5-102">x:Reference Markup Extension</span></span>
<span data-ttu-id="cb8a5-103">Hace referencia a una instancia que se declara en otra parte en el marcado XAML.</span><span class="sxs-lookup"><span data-stu-id="cb8a5-103">References an instance that is declared elsewhere in XAML markup.</span></span> <span data-ttu-id="cb8a5-104">La referencia se refiere a un elemento `x:Name`.</span><span class="sxs-lookup"><span data-stu-id="cb8a5-104">The reference refers to an element's `x:Name`.</span></span>  
  
## <a name="xaml-attribute-usage"></a><span data-ttu-id="cb8a5-105">Uso de atributos XAML</span><span class="sxs-lookup"><span data-stu-id="cb8a5-105">XAML Attribute Usage</span></span>  
  
```xaml  
<object property="{x:Reference instancexName}" .../>  
```  
  
## <a name="xaml-object-element-usage"></a><span data-ttu-id="cb8a5-106">Uso de elementos de objeto XAML</span><span class="sxs-lookup"><span data-stu-id="cb8a5-106">XAML Object Element Usage</span></span>  
  
```xaml  
<object>  
  <object.property>  
    <x:Reference Name="instancexName"/>  
  </object.property>  
</object>  
```  
  
## <a name="xaml-values"></a><span data-ttu-id="cb8a5-107">Valores XAML</span><span class="sxs-lookup"><span data-stu-id="cb8a5-107">XAML Values</span></span>  
  
|||  
|-|-|  
|`instancexName`|<span data-ttu-id="cb8a5-108">El `x:Name` valor (o el valor de la <xref:System.Windows.Markup.RuntimeNamePropertyAttribute>-identificado la propiedad) de la instancia que se hace referencia.</span><span class="sxs-lookup"><span data-stu-id="cb8a5-108">The `x:Name` value (or value of the <xref:System.Windows.Markup.RuntimeNamePropertyAttribute>-identified property) of the referenced instance.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="cb8a5-109">Comentarios</span><span class="sxs-lookup"><span data-stu-id="cb8a5-109">Remarks</span></span>  
 <span data-ttu-id="cb8a5-110">`x:Reference` proporciona soporte técnico de nivel de lenguaje XAML para un concepto de referencia de elemento si no se ha implementado en marcos de trabajo específicos, como WPF.</span><span class="sxs-lookup"><span data-stu-id="cb8a5-110">`x:Reference` provides XAML language-level support for an element reference concept that was otherwise implemented in specific frameworks such as WPF.</span></span>  
  
## <a name="xreference-and-wpf"></a><span data-ttu-id="cb8a5-111">x: Reference y WPF</span><span class="sxs-lookup"><span data-stu-id="cb8a5-111">x:Reference and WPF</span></span>  
 <span data-ttu-id="cb8a5-112">En WPF y XAML 2006, se abordan las referencias de elemento mediante la característica de nivel de marco de <xref:System.Windows.Data.Binding.ElementName%2A> enlace.</span><span class="sxs-lookup"><span data-stu-id="cb8a5-112">In WPF and XAML 2006, element references are addressed by the framework-level feature of <xref:System.Windows.Data.Binding.ElementName%2A> binding.</span></span> <span data-ttu-id="cb8a5-113">Para la mayoría de las aplicaciones de WPF y escenarios, <xref:System.Windows.Data.Binding.ElementName%2A> todavía debe usarse un enlace.</span><span class="sxs-lookup"><span data-stu-id="cb8a5-113">For most WPF applications and scenarios, <xref:System.Windows.Data.Binding.ElementName%2A> binding should still be used.</span></span> <span data-ttu-id="cb8a5-114">Las excepciones a esta orientación general podrían incluir los casos donde hay contexto de datos o a otras consideraciones de ámbito que no permitan realizar enlace de datos y no tiene ninguna implicación compilación de marcado.</span><span class="sxs-lookup"><span data-stu-id="cb8a5-114">Exceptions to this general guidance might include cases where there are data context or other scoping considerations that make data binding impractical and where markup compilation is not involved.</span></span>  
  
 <span data-ttu-id="cb8a5-115">`x:Reference` es una construcción que se define en XAML 2009.</span><span class="sxs-lookup"><span data-stu-id="cb8a5-115">`x:Reference` is a construct defined in XAML 2009.</span></span> <span data-ttu-id="cb8a5-116">En WPF, puede usar características de XAML 2009 pero solo para XAML que esté compilado por marcado para WPF.</span><span class="sxs-lookup"><span data-stu-id="cb8a5-116">In WPF, you can use XAML 2009 features, but only for XAML that is not WPF markup-compiled.</span></span> <span data-ttu-id="cb8a5-117">El XAML compilado por marcado para WPF y el formulario BAML de XAML no admiten de momento palabras clave ni características del lenguaje XAML 2009.</span><span class="sxs-lookup"><span data-stu-id="cb8a5-117">Markup-compiled XAML and the BAML form of XAML do not currently support the XAML 2009 language keywords and features.</span></span>
