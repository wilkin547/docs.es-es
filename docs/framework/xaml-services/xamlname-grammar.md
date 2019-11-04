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
ms.openlocfilehash: a39d25f03583ab9020878b7a659bc99489231ff9
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/03/2019
ms.locfileid: "73458886"
---
# <a name="xamlname-grammar"></a><span data-ttu-id="9dfc1-102">Gramática de XamlName</span><span class="sxs-lookup"><span data-stu-id="9dfc1-102">XamlName Grammar</span></span>
<span data-ttu-id="9dfc1-103">La gramática de XamlName es una gramática específica que se define en la especificación del lenguaje XAML [MS-XAML], que se reproduce aquí por comodidad.</span><span class="sxs-lookup"><span data-stu-id="9dfc1-103">XamlName Grammar is a specific grammar that is defined in the XAML language specification [MS-XAML], which is reproduced here for convenience.</span></span>  
  
## <a name="from-the-xaml-specification"></a><span data-ttu-id="9dfc1-104">De la especificación XAML</span><span class="sxs-lookup"><span data-stu-id="9dfc1-104">From the XAML Specification</span></span>  
 <span data-ttu-id="9dfc1-105">La especificación [MS-XAML] define la gramática de XamlName para identificar el conjunto de identificadores simbólicos válidos que se usan para los tipos y las propiedades.</span><span class="sxs-lookup"><span data-stu-id="9dfc1-105">The [MS-XAML] specification defines the grammar XamlName to identify the set of legal symbolic identifiers used for types and properties.</span></span>  
  
 <span data-ttu-id="9dfc1-106">Los valores de cadena que son del tipo XamlName deben ajustarse a la gramática siguiente:</span><span class="sxs-lookup"><span data-stu-id="9dfc1-106">String values that are of type XamlName must conform to the following grammar:</span></span>  
  
```xaml  
XamlName ::= NameStartChar ( NameChar )*   
NameStartChar ::= LetterCharacter | '_'   
NameChar ::= NameStartChar | DecimalDigit | CombiningCharacter   
LetterCharacter ::= UnicodeLu | UnicodeLl | UnicodeLo | UnicodeLt | UnicodeNl   
DecimalDigit ::= UnicodeNd   
CombiningCharacter ::= UnicodeMn | UnicodeMc  
```  
  
 <span data-ttu-id="9dfc1-107">Que presupone los siguientes valores de categoría generales según se define en la base de datos de caracteres Unicode</span><span class="sxs-lookup"><span data-stu-id="9dfc1-107">Which assumes the following general category values as defined in the Unicode Character Database</span></span>  

| <span data-ttu-id="9dfc1-108">Categoría Unicode</span><span class="sxs-lookup"><span data-stu-id="9dfc1-108">Unicode category</span></span>   | <span data-ttu-id="9dfc1-109">Descripción</span><span class="sxs-lookup"><span data-stu-id="9dfc1-109">Description</span></span>                   |
|--------------------|-------------------------------|
| <span data-ttu-id="9dfc1-110">Lu</span><span class="sxs-lookup"><span data-stu-id="9dfc1-110">Lu</span></span>                 | <span data-ttu-id="9dfc1-111">Letra, mayúscula</span><span class="sxs-lookup"><span data-stu-id="9dfc1-111">Letter, Uppercase</span></span>             |
| <span data-ttu-id="9dfc1-112">Ll</span><span class="sxs-lookup"><span data-stu-id="9dfc1-112">Ll</span></span>                 | <span data-ttu-id="9dfc1-113">Letra, minúscula</span><span class="sxs-lookup"><span data-stu-id="9dfc1-113">Letter, Lowercase</span></span>             |
| <span data-ttu-id="9dfc1-114">Lt</span><span class="sxs-lookup"><span data-stu-id="9dfc1-114">Lt</span></span>                 | <span data-ttu-id="9dfc1-115">Letra, inicial en mayúscula</span><span class="sxs-lookup"><span data-stu-id="9dfc1-115">Letter, Titlecase</span></span>             |
| <span data-ttu-id="9dfc1-116">Lm</span><span class="sxs-lookup"><span data-stu-id="9dfc1-116">Lm</span></span>                 | <span data-ttu-id="9dfc1-117">Letra, modificador</span><span class="sxs-lookup"><span data-stu-id="9dfc1-117">Letter, Modifier</span></span>              |
| <span data-ttu-id="9dfc1-118">Lo</span><span class="sxs-lookup"><span data-stu-id="9dfc1-118">Lo</span></span>                 | <span data-ttu-id="9dfc1-119">Letra, otra</span><span class="sxs-lookup"><span data-stu-id="9dfc1-119">Letter, Other</span></span>                 |
| <span data-ttu-id="9dfc1-120">Mn</span><span class="sxs-lookup"><span data-stu-id="9dfc1-120">Mn</span></span>                 | <span data-ttu-id="9dfc1-121">Marca, sin espaciado</span><span class="sxs-lookup"><span data-stu-id="9dfc1-121">Mark, Non-Spacing</span></span>             |
| <span data-ttu-id="9dfc1-122">Mc</span><span class="sxs-lookup"><span data-stu-id="9dfc1-122">Mc</span></span>                 | <span data-ttu-id="9dfc1-123">Marca, con espacios y combinación</span><span class="sxs-lookup"><span data-stu-id="9dfc1-123">Mark, Spacing Combining</span></span>       |
| <span data-ttu-id="9dfc1-124">Nd</span><span class="sxs-lookup"><span data-stu-id="9dfc1-124">Nd</span></span>                 | <span data-ttu-id="9dfc1-125">Número, decimal</span><span class="sxs-lookup"><span data-stu-id="9dfc1-125">Number, Decimal</span></span>               |
| <span data-ttu-id="9dfc1-126">Nl</span><span class="sxs-lookup"><span data-stu-id="9dfc1-126">Nl</span></span>                 | <span data-ttu-id="9dfc1-127">Número, letra</span><span class="sxs-lookup"><span data-stu-id="9dfc1-127">Number, Letter</span></span>                |
 
 <span data-ttu-id="9dfc1-128">XAML define una segunda gramática, DottedXamlName, que se usa para las referencias calificadas de propiedades y eventos, y también para los miembros adjuntos.</span><span class="sxs-lookup"><span data-stu-id="9dfc1-128">XAML defines a second grammar, DottedXamlName, that is used for property and event qualified references, and also for attached members.</span></span> <span data-ttu-id="9dfc1-129">Para obtener más información, vea [información general sobre <xref:System.Windows.DependencyProperty> y XAML (WPF)](../../desktop-wpf/fundamentals/xaml.md).</span><span class="sxs-lookup"><span data-stu-id="9dfc1-129">For more information, see <xref:System.Windows.DependencyProperty> and [XAML Overview (WPF)](../../desktop-wpf/fundamentals/xaml.md).</span></span>  
  
 <span data-ttu-id="9dfc1-130">Los valores de cadena que son de tipo DottedXamlName deben ajustarse a la gramática siguiente:</span><span class="sxs-lookup"><span data-stu-id="9dfc1-130">String values that are of type DottedXamlName must conform to the following grammar:</span></span>  
  
```xaml  
DottedXamlName ::= XamlName '.' XamlName  
```  
  
## <a name="remarks"></a><span data-ttu-id="9dfc1-131">Comentarios</span><span class="sxs-lookup"><span data-stu-id="9dfc1-131">Remarks</span></span>  
 <span data-ttu-id="9dfc1-132">Para obtener la especificación completa, vea [\[MS-XAML\]](https://go.microsoft.com/fwlink/?LinkId=114525).</span><span class="sxs-lookup"><span data-stu-id="9dfc1-132">For the complete specification, see [\[MS-XAML\]](https://go.microsoft.com/fwlink/?LinkId=114525).</span></span>
