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
# <a name="xreference-markup-extension"></a>x:Reference (extensión de marcado)
Hace referencia a una instancia que se declara en otra parte en el marcado XAML. La referencia se refiere a un elemento `x:Name`.  
  
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
|`instancexName`|El `x:Name` valor (o valor de la <xref:System.Windows.Markup.RuntimeNamePropertyAttribute>-identifica la propiedad) de la instancia que se hace referencia.|  
  
## <a name="remarks"></a>Comentarios  
 `x:Reference`proporciona compatibilidad con el nivel de lenguaje XAML para un concepto de referencia de elemento en caso contrario, se ha implementado en marcos concretos, como WPF.  
  
## <a name="xreference-and-wpf"></a>x: Reference y WPF  
 En WPF y XAML 2006, se tratan las referencias a elementos por la característica de nivel de marco de <xref:System.Windows.Data.Binding.ElementName%2A> enlace. Para la mayoría de las aplicaciones WPF y escenarios, <xref:System.Windows.Data.Binding.ElementName%2A> todavía debe usarse un enlace. Las excepciones a esta orientación general podrían incluir los casos donde hay contexto de datos u otras consideraciones de ámbito que no permitan realizar el enlace de datos y cuando no se trate de compilación de marcado.  
  
 `x:Reference`es una construcción que se define en XAML 2009. En WPF, puede usar características de XAML 2009 pero solo para XAML que esté compilado por marcado para WPF. El XAML compilado por marcado para WPF y el formulario BAML de XAML no admiten de momento palabras clave ni características del lenguaje XAML 2009.
