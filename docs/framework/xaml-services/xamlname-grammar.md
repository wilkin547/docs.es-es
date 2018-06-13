---
title: Gramática de XamlName
ms.date: 03/30/2017
helpviewer_keywords:
- DottedXamlName grammar [XAML Services]
- grammar [XAML Services], DottedXamlName
- grammar [XAML Services], XamlName
- names in XAML [XAML Services]
- XamlName grammar [XAML Services]
ms.assetid: 11e4cada-41d2-494d-9531-0d3df4dfcbe3
ms.openlocfilehash: 32fd7b7b952ebbc853e41c0a8276d1ab487e619f
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33561896"
---
# <a name="xamlname-grammar"></a><span data-ttu-id="cd884-102">Gramática de XamlName</span><span class="sxs-lookup"><span data-stu-id="cd884-102">XamlName Grammar</span></span>
<span data-ttu-id="cd884-103">XamlName (gramática) es una gramática concreta que se define en la especificación del lenguaje XAML [MS-XAML], que se reproduce aquí por comodidad.</span><span class="sxs-lookup"><span data-stu-id="cd884-103">XamlName Grammar is a specific grammar that is defined in the XAML language specification [MS-XAML], which is reproduced here for convenience.</span></span>  
  
## <a name="from-the-xaml-specification"></a><span data-ttu-id="cd884-104">De la especificación de XAML</span><span class="sxs-lookup"><span data-stu-id="cd884-104">From the XAML Specification</span></span>  
 <span data-ttu-id="cd884-105">La especificación de [MS-XAML] define la gramática de XamlName para identificar el conjunto de identificadores simbólicos válidos utilizados para los tipos y propiedades.</span><span class="sxs-lookup"><span data-stu-id="cd884-105">The [MS-XAML] specification defines the grammar XamlName to identify the set of legal symbolic identifiers used for types and properties.</span></span>  
  
 <span data-ttu-id="cd884-106">Valores de cadena que son del tipo que XamlName deben respetar la gramática siguiente:</span><span class="sxs-lookup"><span data-stu-id="cd884-106">String values that are of type XamlName must conform to the following grammar:</span></span>  
  
```  
XamlName ::= NameStartChar ( NameChar )*   
NameStartChar ::= LetterCharacter | '_'   
NameChar ::= NameStartChar | DecimalDigit | CombiningCharacter   
LetterCharacter ::= UnicodeLu | UnicodeLl | UnicodeLo | UnicodeLt | UnicodeNl   
DecimalDigit ::= UnicodeNd   
CombiningCharacter ::= UnicodeMn | UnicodeMc  
```  
  
 <span data-ttu-id="cd884-107">Lo que supone los siguientes valores de categoría general como se define en la base de datos de caracteres Unicode</span><span class="sxs-lookup"><span data-stu-id="cd884-107">Which assumes the following general category values as defined in the Unicode Character Database</span></span>  
  
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
  
 <span data-ttu-id="cd884-108">XAML define una segunda gramática, DottedXamlName, que se utiliza para la propiedad y el evento referencias parciales y también para los miembros asociados.</span><span class="sxs-lookup"><span data-stu-id="cd884-108">XAML defines a second grammar, DottedXamlName, that is used for property and event qualified references, and also for attached members.</span></span> <span data-ttu-id="cd884-109">Para obtener más información, consulte <xref:System.Windows.DependencyProperty> y [información general sobre XAML (WPF)](../../../docs/framework/wpf/advanced/xaml-overview-wpf.md).</span><span class="sxs-lookup"><span data-stu-id="cd884-109">For more information, see <xref:System.Windows.DependencyProperty> and [XAML Overview (WPF)](../../../docs/framework/wpf/advanced/xaml-overview-wpf.md).</span></span>  
  
 <span data-ttu-id="cd884-110">Valores de cadena que son del tipo que DottedXamlName debe ajustarse a la gramática siguiente:</span><span class="sxs-lookup"><span data-stu-id="cd884-110">String values that are of type DottedXamlName must conform to the following grammar:</span></span>  
  
```  
DottedXamlName ::= XamlName '.' XamlName  
```  
  
## <a name="remarks"></a><span data-ttu-id="cd884-111">Comentarios</span><span class="sxs-lookup"><span data-stu-id="cd884-111">Remarks</span></span>  
 <span data-ttu-id="cd884-112">Para obtener la especificación completa, vea [ \[MS-XAML\]](http://go.microsoft.com/fwlink/?LinkId=114525).</span><span class="sxs-lookup"><span data-stu-id="cd884-112">For the complete specification, see [\[MS-XAML\]](http://go.microsoft.com/fwlink/?LinkId=114525).</span></span>
