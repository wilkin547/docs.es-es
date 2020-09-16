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
ms.openlocfilehash: ceb027938b6d4313babbe02949e0b6dd5ee85589
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/15/2020
ms.locfileid: "90556699"
---
# <a name="xamlname-grammar"></a>Gramática de XamlName

La gramática de XamlName es una gramática específica que se define en la especificación del lenguaje XAML [MS-XAML], que se reproduce aquí por comodidad.

## <a name="from-the-xaml-specification"></a>De la especificación XAML

La especificación [MS-XAML] define la gramática de XamlName para identificar el conjunto de identificadores simbólicos válidos que se usan para los tipos y las propiedades.

Los valores de cadena que son del tipo XamlName deben ajustarse a la gramática siguiente:

```xaml
XamlName ::= NameStartChar ( NameChar )*
NameStartChar ::= LetterCharacter | '_'
NameChar ::= NameStartChar | DecimalDigit | CombiningCharacter
LetterCharacter ::= UnicodeLu | UnicodeLl | UnicodeLo | UnicodeLt | UnicodeNl
DecimalDigit ::= UnicodeNd
CombiningCharacter ::= UnicodeMn | UnicodeMc
```

Que presupone los siguientes valores de categoría generales según se define en la base de datos de caracteres Unicode

| Categoría Unicode   | Descripción                   |
|--------------------|-------------------------------|
| Lu                 | Letra, mayúscula             |
| Ll                 | Letra, minúscula             |
| Lt                 | Letra, inicial en mayúscula             |
| Lm                 | Letra, modificador              |
| Lo                 | Letra, otra                 |
| Mn                 | Marca, sin espaciado             |
| Mc                 | Marca, con espacios y combinación       |
| Nd                 | Número, decimal               |
| Nl                 | Número, letra                |

XAML define una segunda gramática, DottedXamlName, que se usa para las referencias calificadas de propiedades y eventos, y también para los miembros adjuntos. Para obtener más información, vea <xref:System.Windows.DependencyProperty> e [información general sobre XAML (WPF)](../fundamentals/xaml.md).

Los valores de cadena que son de tipo DottedXamlName deben ajustarse a la gramática siguiente:

```xaml
DottedXamlName ::= XamlName '.' XamlName
```

## <a name="remarks"></a>Comentarios

Para obtener la especificación completa, consulte [ \[ MS- \] XAML](/previous-versions/msp-n-p/ff650760(v=pandp.10)).
