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
ms.openlocfilehash: 2fc74990b15caaa9b58e6eea5b0212ea22505674
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "81433053"
---
# <a name="xamlname-grammar"></a><span data-ttu-id="45c90-102">Gramática de XamlName</span><span class="sxs-lookup"><span data-stu-id="45c90-102">XamlName Grammar</span></span>

<span data-ttu-id="45c90-103">XamlName Grammar es una gramática específica que se define en la especificación de lenguaje XAML [MS-XAML], que se reproduce aquí para mayor comodidad.</span><span class="sxs-lookup"><span data-stu-id="45c90-103">XamlName Grammar is a specific grammar that is defined in the XAML language specification [MS-XAML], which is reproduced here for convenience.</span></span>

## <a name="from-the-xaml-specification"></a><span data-ttu-id="45c90-104">De la especificación XAML</span><span class="sxs-lookup"><span data-stu-id="45c90-104">From the XAML Specification</span></span>

<span data-ttu-id="45c90-105">La especificación [MS-XAML] define la gramática XamlName para identificar el conjunto de identificadores simbólicos legales utilizados para tipos y propiedades.</span><span class="sxs-lookup"><span data-stu-id="45c90-105">The [MS-XAML] specification defines the grammar XamlName to identify the set of legal symbolic identifiers used for types and properties.</span></span>

<span data-ttu-id="45c90-106">Los valores de cadena que son de tipo XamlName deben ajustarse a la gramática siguiente:</span><span class="sxs-lookup"><span data-stu-id="45c90-106">String values that are of type XamlName must conform to the following grammar:</span></span>

```xaml
XamlName ::= NameStartChar ( NameChar )*
NameStartChar ::= LetterCharacter | '_'
NameChar ::= NameStartChar | DecimalDigit | CombiningCharacter
LetterCharacter ::= UnicodeLu | UnicodeLl | UnicodeLo | UnicodeLt | UnicodeNl
DecimalDigit ::= UnicodeNd
CombiningCharacter ::= UnicodeMn | UnicodeMc
```

<span data-ttu-id="45c90-107">Que supone los siguientes valores de categoría general tal como se definen en la base de datos de caracteres Unicode</span><span class="sxs-lookup"><span data-stu-id="45c90-107">Which assumes the following general category values as defined in the Unicode Character Database</span></span>

| <span data-ttu-id="45c90-108">Categoría Unicode</span><span class="sxs-lookup"><span data-stu-id="45c90-108">Unicode category</span></span>   | <span data-ttu-id="45c90-109">Descripción</span><span class="sxs-lookup"><span data-stu-id="45c90-109">Description</span></span>                   |
|--------------------|-------------------------------|
| <span data-ttu-id="45c90-110">Lu</span><span class="sxs-lookup"><span data-stu-id="45c90-110">Lu</span></span>                 | <span data-ttu-id="45c90-111">Letra, mayúscula</span><span class="sxs-lookup"><span data-stu-id="45c90-111">Letter, Uppercase</span></span>             |
| <span data-ttu-id="45c90-112">Ll</span><span class="sxs-lookup"><span data-stu-id="45c90-112">Ll</span></span>                 | <span data-ttu-id="45c90-113">Letra, minúscula</span><span class="sxs-lookup"><span data-stu-id="45c90-113">Letter, Lowercase</span></span>             |
| <span data-ttu-id="45c90-114">Lt</span><span class="sxs-lookup"><span data-stu-id="45c90-114">Lt</span></span>                 | <span data-ttu-id="45c90-115">Letra, inicial en mayúscula</span><span class="sxs-lookup"><span data-stu-id="45c90-115">Letter, Titlecase</span></span>             |
| <span data-ttu-id="45c90-116">Lm</span><span class="sxs-lookup"><span data-stu-id="45c90-116">Lm</span></span>                 | <span data-ttu-id="45c90-117">Letra, modificador</span><span class="sxs-lookup"><span data-stu-id="45c90-117">Letter, Modifier</span></span>              |
| <span data-ttu-id="45c90-118">Lo</span><span class="sxs-lookup"><span data-stu-id="45c90-118">Lo</span></span>                 | <span data-ttu-id="45c90-119">Letra, otra</span><span class="sxs-lookup"><span data-stu-id="45c90-119">Letter, Other</span></span>                 |
| <span data-ttu-id="45c90-120">Mn</span><span class="sxs-lookup"><span data-stu-id="45c90-120">Mn</span></span>                 | <span data-ttu-id="45c90-121">Mark, sin espaciado</span><span class="sxs-lookup"><span data-stu-id="45c90-121">Mark, Non-Spacing</span></span>             |
| <span data-ttu-id="45c90-122">Mc</span><span class="sxs-lookup"><span data-stu-id="45c90-122">Mc</span></span>                 | <span data-ttu-id="45c90-123">Marca, con espacios y combinación</span><span class="sxs-lookup"><span data-stu-id="45c90-123">Mark, Spacing Combining</span></span>       |
| <span data-ttu-id="45c90-124">Nd</span><span class="sxs-lookup"><span data-stu-id="45c90-124">Nd</span></span>                 | <span data-ttu-id="45c90-125">Número, Decimal</span><span class="sxs-lookup"><span data-stu-id="45c90-125">Number, Decimal</span></span>               |
| <span data-ttu-id="45c90-126">Nl</span><span class="sxs-lookup"><span data-stu-id="45c90-126">Nl</span></span>                 | <span data-ttu-id="45c90-127">Número, letra</span><span class="sxs-lookup"><span data-stu-id="45c90-127">Number, Letter</span></span>                |

<span data-ttu-id="45c90-128">XAML define una segunda gramática, DottedXamlName, que se usa para las referencias calificadas de propiedad y eventos, y también para los miembros adjuntos.</span><span class="sxs-lookup"><span data-stu-id="45c90-128">XAML defines a second grammar, DottedXamlName, that is used for property and event qualified references, and also for attached members.</span></span> <span data-ttu-id="45c90-129">Para obtener más <xref:System.Windows.DependencyProperty> información, vea información [general sobre XAML (WPF).](../fundamentals/xaml.md)</span><span class="sxs-lookup"><span data-stu-id="45c90-129">For more information, see <xref:System.Windows.DependencyProperty> and [XAML Overview (WPF)](../fundamentals/xaml.md).</span></span>

<span data-ttu-id="45c90-130">Los valores de cadena de tipo DottedXamlName deben ajustarse a la gramática siguiente:</span><span class="sxs-lookup"><span data-stu-id="45c90-130">String values that are of type DottedXamlName must conform to the following grammar:</span></span>

```xaml
DottedXamlName ::= XamlName '.' XamlName
```

## <a name="remarks"></a><span data-ttu-id="45c90-131">Observaciones</span><span class="sxs-lookup"><span data-stu-id="45c90-131">Remarks</span></span>

<span data-ttu-id="45c90-132">Para obtener la especificación completa, vea [ \[MS-XAML\]](https://docs.microsoft.com/previous-versions/msp-n-p/ff650760(v=pandp.10)).</span><span class="sxs-lookup"><span data-stu-id="45c90-132">For the complete specification, see [\[MS-XAML\]](https://docs.microsoft.com/previous-versions/msp-n-p/ff650760(v=pandp.10)).</span></span>
