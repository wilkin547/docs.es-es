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
# <a name="xamlname-grammar"></a>Gramática de XamlName

XamlName Grammar es una gramática específica que se define en la especificación de lenguaje XAML [MS-XAML], que se reproduce aquí para mayor comodidad.

## <a name="from-the-xaml-specification"></a>De la especificación XAML

La especificación [MS-XAML] define la gramática XamlName para identificar el conjunto de identificadores simbólicos legales utilizados para tipos y propiedades.

Los valores de cadena que son de tipo XamlName deben ajustarse a la gramática siguiente:

```xaml
XamlName ::= NameStartChar ( NameChar )*
NameStartChar ::= LetterCharacter | '_'
NameChar ::= NameStartChar | DecimalDigit | CombiningCharacter
LetterCharacter ::= UnicodeLu | UnicodeLl | UnicodeLo | UnicodeLt | UnicodeNl
DecimalDigit ::= UnicodeNd
CombiningCharacter ::= UnicodeMn | UnicodeMc
```

Que supone los siguientes valores de categoría general tal como se definen en la base de datos de caracteres Unicode

| Categoría Unicode   | Descripción                   |
|--------------------|-------------------------------|
| Lu                 | Letra, mayúscula             |
| Ll                 | Letra, minúscula             |
| Lt                 | Letra, inicial en mayúscula             |
| Lm                 | Letra, modificador              |
| Lo                 | Letra, otra                 |
| Mn                 | Mark, sin espaciado             |
| Mc                 | Marca, con espacios y combinación       |
| Nd                 | Número, Decimal               |
| Nl                 | Número, letra                |

XAML define una segunda gramática, DottedXamlName, que se usa para las referencias calificadas de propiedad y eventos, y también para los miembros adjuntos. Para obtener más <xref:System.Windows.DependencyProperty> información, vea información [general sobre XAML (WPF).](../fundamentals/xaml.md)

Los valores de cadena de tipo DottedXamlName deben ajustarse a la gramática siguiente:

```xaml
DottedXamlName ::= XamlName '.' XamlName
```

## <a name="remarks"></a>Observaciones

Para obtener la especificación completa, vea [ \[MS-XAML\]](https://docs.microsoft.com/previous-versions/msp-n-p/ff650760(v=pandp.10)).
