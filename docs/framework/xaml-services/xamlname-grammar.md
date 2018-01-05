---
title: "Gramática de XamlName"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- DottedXamlName grammar [XAML Services]
- grammar [XAML Services], DottedXamlName
- grammar [XAML Services], XamlName
- names in XAML [XAML Services]
- XamlName grammar [XAML Services]
ms.assetid: 11e4cada-41d2-494d-9531-0d3df4dfcbe3
caps.latest.revision: "13"
author: wadepickett
ms.author: wpickett
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 47a2d72ea9558003412cc3773e26fb5be751fa19
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="xamlname-grammar"></a><span data-ttu-id="96ba4-102">Gramática de XamlName</span><span class="sxs-lookup"><span data-stu-id="96ba4-102">XamlName Grammar</span></span>
<span data-ttu-id="96ba4-103">XamlName (gramática) es una gramática concreta que se define en la especificación del lenguaje XAML [MS-XAML], que se reproduce aquí por comodidad.</span><span class="sxs-lookup"><span data-stu-id="96ba4-103">XamlName Grammar is a specific grammar that is defined in the XAML language specification [MS-XAML], which is reproduced here for convenience.</span></span>  
  
## <a name="from-the-xaml-specification"></a><span data-ttu-id="96ba4-104">De la especificación de XAML</span><span class="sxs-lookup"><span data-stu-id="96ba4-104">From the XAML Specification</span></span>  
 <span data-ttu-id="96ba4-105">La especificación de [MS-XAML] define la gramática de XamlName para identificar el conjunto de identificadores simbólicos válidos utilizados para los tipos y propiedades.</span><span class="sxs-lookup"><span data-stu-id="96ba4-105">The [MS-XAML] specification defines the grammar XamlName to identify the set of legal symbolic identifiers used for types and properties.</span></span>  
  
 <span data-ttu-id="96ba4-106">Valores de cadena que son del tipo que XamlName deben respetar la gramática siguiente:</span><span class="sxs-lookup"><span data-stu-id="96ba4-106">String values that are of type XamlName must conform to the following grammar:</span></span>  
  
```  
XamlName ::= NameStartChar ( NameChar )*   
NameStartChar ::= LetterCharacter | '_'   
NameChar ::= NameStartChar | DecimalDigit | CombiningCharacter   
LetterCharacter ::= UnicodeLu | UnicodeLl | UnicodeLo | UnicodeLt | UnicodeNl   
DecimalDigit ::= UnicodeNd   
CombiningCharacter ::= UnicodeMn | UnicodeMc  
```  
  
 <span data-ttu-id="96ba4-107">Lo que supone los siguientes valores de categoría general como se define en la base de datos de caracteres Unicode</span><span class="sxs-lookup"><span data-stu-id="96ba4-107">Which assumes the following general category values as defined in the Unicode Character Database</span></span>  
  
```  
Lu  
Letter, Uppercase  
Ll  
Letter, Lowercase  
Lt  
Letter, Titlecase  
Lm  
Letter, Modifier  
Lo  
Letter, Other  
Mn  
Mark, Non-Spacing  
Mc  
Mark, Spacing Combining  
Nd  
Number, Decimal  
Nl  
Number, Letter  
```  
  
 <span data-ttu-id="96ba4-108">XAML define una segunda gramática, DottedXamlName, que se utiliza para la propiedad y el evento referencias parciales y también para los miembros asociados.</span><span class="sxs-lookup"><span data-stu-id="96ba4-108">XAML defines a second grammar, DottedXamlName, that is used for property and event qualified references, and also for attached members.</span></span> <span data-ttu-id="96ba4-109">Para obtener más información, consulte <xref:System.Windows.DependencyProperty> y [información general sobre XAML (WPF)](../../../docs/framework/wpf/advanced/xaml-overview-wpf.md).</span><span class="sxs-lookup"><span data-stu-id="96ba4-109">For more information, see <xref:System.Windows.DependencyProperty> and [XAML Overview (WPF)](../../../docs/framework/wpf/advanced/xaml-overview-wpf.md).</span></span>  
  
 <span data-ttu-id="96ba4-110">Valores de cadena que son del tipo que DottedXamlName debe ajustarse a la gramática siguiente:</span><span class="sxs-lookup"><span data-stu-id="96ba4-110">String values that are of type DottedXamlName must conform to the following grammar:</span></span>  
  
```  
DottedXamlName ::= XamlName '.' XamlName  
```  
  
## <a name="remarks"></a><span data-ttu-id="96ba4-111">Comentarios</span><span class="sxs-lookup"><span data-stu-id="96ba4-111">Remarks</span></span>  
 <span data-ttu-id="96ba4-112">Para obtener la especificación completa, vea [ \[MS-XAML\]](http://go.microsoft.com/fwlink/?LinkId=114525).</span><span class="sxs-lookup"><span data-stu-id="96ba4-112">For the complete specification, see [\[MS-XAML\]](http://go.microsoft.com/fwlink/?LinkId=114525).</span></span>
