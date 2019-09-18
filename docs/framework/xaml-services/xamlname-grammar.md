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
ms.openlocfilehash: 837a18ca18d0c634dfa5cc133aa013919cfb9d96
ms.sourcegitcommit: 289e06e904b72f34ac717dbcc5074239b977e707
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/17/2019
ms.locfileid: "71053899"
---
# <a name="xamlname-grammar"></a><span data-ttu-id="e0264-102">Gramática de XamlName</span><span class="sxs-lookup"><span data-stu-id="e0264-102">XamlName Grammar</span></span>
<span data-ttu-id="e0264-103">La gramática de XamlName es una gramática específica que se define en la especificación del lenguaje XAML [MS-XAML], que se reproduce aquí por comodidad.</span><span class="sxs-lookup"><span data-stu-id="e0264-103">XamlName Grammar is a specific grammar that is defined in the XAML language specification [MS-XAML], which is reproduced here for convenience.</span></span>  
  
## <a name="from-the-xaml-specification"></a><span data-ttu-id="e0264-104">De la especificación XAML</span><span class="sxs-lookup"><span data-stu-id="e0264-104">From the XAML Specification</span></span>  
 <span data-ttu-id="e0264-105">La especificación [MS-XAML] define la gramática de XamlName para identificar el conjunto de identificadores simbólicos válidos que se usan para los tipos y las propiedades.</span><span class="sxs-lookup"><span data-stu-id="e0264-105">The [MS-XAML] specification defines the grammar XamlName to identify the set of legal symbolic identifiers used for types and properties.</span></span>  
  
 <span data-ttu-id="e0264-106">Los valores de cadena que son del tipo XamlName deben ajustarse a la gramática siguiente:</span><span class="sxs-lookup"><span data-stu-id="e0264-106">String values that are of type XamlName must conform to the following grammar:</span></span>  
  
```xaml  
XamlName ::= NameStartChar ( NameChar )*   
NameStartChar ::= LetterCharacter | '_'   
NameChar ::= NameStartChar | DecimalDigit | CombiningCharacter   
LetterCharacter ::= UnicodeLu | UnicodeLl | UnicodeLo | UnicodeLt | UnicodeNl   
DecimalDigit ::= UnicodeNd   
CombiningCharacter ::= UnicodeMn | UnicodeMc  
```  
  
 <span data-ttu-id="e0264-107">Que presupone los siguientes valores de categoría generales según se define en la base de datos de caracteres Unicode</span><span class="sxs-lookup"><span data-stu-id="e0264-107">Which assumes the following general category values as defined in the Unicode Character Database</span></span>  

| <span data-ttu-id="e0264-108">Categoría Unicode</span><span class="sxs-lookup"><span data-stu-id="e0264-108">Unicode category</span></span>   | <span data-ttu-id="e0264-109">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="e0264-109">Description</span></span>                   |
|--------------------|-------------------------------|
| <span data-ttu-id="e0264-110">Lu</span><span class="sxs-lookup"><span data-stu-id="e0264-110">Lu</span></span>                 | <span data-ttu-id="e0264-111">Letra, mayúscula</span><span class="sxs-lookup"><span data-stu-id="e0264-111">Letter, Uppercase</span></span>             |
| <span data-ttu-id="e0264-112">Ll</span><span class="sxs-lookup"><span data-stu-id="e0264-112">Ll</span></span>                 | <span data-ttu-id="e0264-113">Letra, minúscula</span><span class="sxs-lookup"><span data-stu-id="e0264-113">Letter, Lowercase</span></span>             |
| <span data-ttu-id="e0264-114">Lt</span><span class="sxs-lookup"><span data-stu-id="e0264-114">Lt</span></span>                 | <span data-ttu-id="e0264-115">Letra, inicial en mayúscula</span><span class="sxs-lookup"><span data-stu-id="e0264-115">Letter, Titlecase</span></span>             |
| <span data-ttu-id="e0264-116">Lm</span><span class="sxs-lookup"><span data-stu-id="e0264-116">Lm</span></span>                 | <span data-ttu-id="e0264-117">Letra, modificador</span><span class="sxs-lookup"><span data-stu-id="e0264-117">Letter, Modifier</span></span>              |
| <span data-ttu-id="e0264-118">Lo</span><span class="sxs-lookup"><span data-stu-id="e0264-118">Lo</span></span>                 | <span data-ttu-id="e0264-119">Letra, otra</span><span class="sxs-lookup"><span data-stu-id="e0264-119">Letter, Other</span></span>                 |
| <span data-ttu-id="e0264-120">Mn</span><span class="sxs-lookup"><span data-stu-id="e0264-120">Mn</span></span>                 | <span data-ttu-id="e0264-121">Marca, sin espaciado</span><span class="sxs-lookup"><span data-stu-id="e0264-121">Mark, Non-Spacing</span></span>             |
| <span data-ttu-id="e0264-122">Mc</span><span class="sxs-lookup"><span data-stu-id="e0264-122">Mc</span></span>                 | <span data-ttu-id="e0264-123">Marca, con espacios y combinación</span><span class="sxs-lookup"><span data-stu-id="e0264-123">Mark, Spacing Combining</span></span>       |
| <span data-ttu-id="e0264-124">Nd</span><span class="sxs-lookup"><span data-stu-id="e0264-124">Nd</span></span>                 | <span data-ttu-id="e0264-125">Número, decimal</span><span class="sxs-lookup"><span data-stu-id="e0264-125">Number, Decimal</span></span>               |
| <span data-ttu-id="e0264-126">Nl</span><span class="sxs-lookup"><span data-stu-id="e0264-126">Nl</span></span>                 | <span data-ttu-id="e0264-127">Número, letra</span><span class="sxs-lookup"><span data-stu-id="e0264-127">Number, Letter</span></span>                |
 
 <span data-ttu-id="e0264-128">XAML define una segunda gramática, DottedXamlName, que se usa para las referencias calificadas de propiedades y eventos, y también para los miembros adjuntos.</span><span class="sxs-lookup"><span data-stu-id="e0264-128">XAML defines a second grammar, DottedXamlName, that is used for property and event qualified references, and also for attached members.</span></span> <span data-ttu-id="e0264-129">Para obtener más información, <xref:System.Windows.DependencyProperty> vea e [información general sobre XAML (WPF)](../wpf/advanced/xaml-overview-wpf.md).</span><span class="sxs-lookup"><span data-stu-id="e0264-129">For more information, see <xref:System.Windows.DependencyProperty> and [XAML Overview (WPF)](../wpf/advanced/xaml-overview-wpf.md).</span></span>  
  
 <span data-ttu-id="e0264-130">Los valores de cadena que son de tipo DottedXamlName deben ajustarse a la gramática siguiente:</span><span class="sxs-lookup"><span data-stu-id="e0264-130">String values that are of type DottedXamlName must conform to the following grammar:</span></span>  
  
```xaml  
DottedXamlName ::= XamlName '.' XamlName  
```  
  
## <a name="remarks"></a><span data-ttu-id="e0264-131">Comentarios</span><span class="sxs-lookup"><span data-stu-id="e0264-131">Remarks</span></span>  
 <span data-ttu-id="e0264-132">Para obtener la especificación completa, consulte [ \[MS-\]XAML](https://go.microsoft.com/fwlink/?LinkId=114525).</span><span class="sxs-lookup"><span data-stu-id="e0264-132">For the complete specification, see [\[MS-XAML\]](https://go.microsoft.com/fwlink/?LinkId=114525).</span></span>
