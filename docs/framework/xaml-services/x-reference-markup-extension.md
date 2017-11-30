---
title: "x:Reference (extensión de marcado)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- x:Reference markup extension [XAML Services]
- XAML [XAML Services], x:Reference Markup Extension
- Reference markup extension [XAML Services]
ms.assetid: 2982e68b-d26b-4aa3-826a-34c57a9c5199
caps.latest.revision: "8"
author: wadepickett
ms.author: wpickett
manager: wpickett
ms.openlocfilehash: 06e59e7686004f8fd44473bd9572ed07a0118d1f
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="xreference-markup-extension"></a><span data-ttu-id="15394-102">x:Reference (extensión de marcado)</span><span class="sxs-lookup"><span data-stu-id="15394-102">x:Reference Markup Extension</span></span>
<span data-ttu-id="15394-103">Hace referencia a una instancia que se declara en otra parte en el marcado XAML.</span><span class="sxs-lookup"><span data-stu-id="15394-103">References an instance that is declared elsewhere in XAML markup.</span></span> <span data-ttu-id="15394-104">La referencia se refiere a un elemento `x:Name`.</span><span class="sxs-lookup"><span data-stu-id="15394-104">The reference refers to an element's `x:Name`.</span></span>  
  
## <a name="xaml-attribute-usage"></a><span data-ttu-id="15394-105">Uso de atributos XAML</span><span class="sxs-lookup"><span data-stu-id="15394-105">XAML Attribute Usage</span></span>  
  
```xaml  
<object property="{x:Reference instancexName}" .../>  
```  
  
## <a name="xaml-object-element-usage"></a><span data-ttu-id="15394-106">Uso de elementos de objeto XAML</span><span class="sxs-lookup"><span data-stu-id="15394-106">XAML Object Element Usage</span></span>  
  
```xaml  
<object>  
  <object.property>  
    <x:Reference Name="instancexName"/>  
  </object.property>  
</object>  
```  
  
## <a name="xaml-values"></a><span data-ttu-id="15394-107">Valores XAML</span><span class="sxs-lookup"><span data-stu-id="15394-107">XAML Values</span></span>  
  
|||  
|-|-|  
|`instancexName`|<span data-ttu-id="15394-108">El `x:Name` valor (o valor de la <xref:System.Windows.Markup.RuntimeNamePropertyAttribute>-identifica la propiedad) de la instancia que se hace referencia.</span><span class="sxs-lookup"><span data-stu-id="15394-108">The `x:Name` value (or value of the <xref:System.Windows.Markup.RuntimeNamePropertyAttribute>-identified property) of the referenced instance.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="15394-109">Comentarios</span><span class="sxs-lookup"><span data-stu-id="15394-109">Remarks</span></span>  
 <span data-ttu-id="15394-110">`x:Reference`proporciona compatibilidad con el nivel de lenguaje XAML para un concepto de referencia de elemento en caso contrario, se ha implementado en marcos concretos, como WPF.</span><span class="sxs-lookup"><span data-stu-id="15394-110">`x:Reference` provides XAML language-level support for an element reference concept that was otherwise implemented in specific frameworks such as WPF.</span></span>  
  
## <a name="xreference-and-wpf"></a><span data-ttu-id="15394-111">x: Reference y WPF</span><span class="sxs-lookup"><span data-stu-id="15394-111">x:Reference and WPF</span></span>  
 <span data-ttu-id="15394-112">En WPF y XAML 2006, se tratan las referencias a elementos por la característica de nivel de marco de <xref:System.Windows.Data.Binding.ElementName%2A> enlace.</span><span class="sxs-lookup"><span data-stu-id="15394-112">In WPF and XAML 2006, element references are addressed by the framework-level feature of <xref:System.Windows.Data.Binding.ElementName%2A> binding.</span></span> <span data-ttu-id="15394-113">Para la mayoría de las aplicaciones WPF y escenarios, <xref:System.Windows.Data.Binding.ElementName%2A> todavía debe usarse un enlace.</span><span class="sxs-lookup"><span data-stu-id="15394-113">For most WPF applications and scenarios, <xref:System.Windows.Data.Binding.ElementName%2A> binding should still be used.</span></span> <span data-ttu-id="15394-114">Las excepciones a esta orientación general podrían incluir los casos donde hay contexto de datos u otras consideraciones de ámbito que no permitan realizar el enlace de datos y cuando no se trate de compilación de marcado.</span><span class="sxs-lookup"><span data-stu-id="15394-114">Exceptions to this general guidance might include cases where there are data context or other scoping considerations that make data binding impractical and where markup compilation is not involved.</span></span>  
  
 <span data-ttu-id="15394-115">`x:Reference`es una construcción que se define en XAML 2009.</span><span class="sxs-lookup"><span data-stu-id="15394-115">`x:Reference` is a construct defined in XAML 2009.</span></span> <span data-ttu-id="15394-116">En WPF, puede usar características de XAML 2009 pero solo para XAML que esté compilado por marcado para WPF.</span><span class="sxs-lookup"><span data-stu-id="15394-116">In WPF, you can use XAML 2009 features, but only for XAML that is not WPF markup-compiled.</span></span> <span data-ttu-id="15394-117">El XAML compilado por marcado para WPF y el formulario BAML de XAML no admiten de momento palabras clave ni características del lenguaje XAML 2009.</span><span class="sxs-lookup"><span data-stu-id="15394-117">Markup-compiled XAML and the BAML form of XAML do not currently support the XAML 2009 language keywords and features.</span></span>
