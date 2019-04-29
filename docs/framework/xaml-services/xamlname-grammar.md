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
ms.openlocfilehash: 642ca16142bdfe78a40ddf4e6a3a79ce6a8a4985
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61938754"
---
# <a name="xamlname-grammar"></a>Gramática de XamlName
Gramática de XamlName es una gramática concreta que se define en la especificación del lenguaje XAML [MS-XAML], que se reproduce aquí por comodidad.  
  
## <a name="from-the-xaml-specification"></a>De la especificación de XAML  
 La especificación [MS-XAML] define la gramática de XamlName para identificar el conjunto de identificadores simbólicos válidos utilizados para los tipos y propiedades.  
  
 Valores de cadena que son del tipo que XamlName debe ajustarse a la gramática siguiente:  
  
```  
XamlName ::= NameStartChar ( NameChar )*   
NameStartChar ::= LetterCharacter | '_'   
NameChar ::= NameStartChar | DecimalDigit | CombiningCharacter   
LetterCharacter ::= UnicodeLu | UnicodeLl | UnicodeLo | UnicodeLt | UnicodeNl   
DecimalDigit ::= UnicodeNd   
CombiningCharacter ::= UnicodeMn | UnicodeMc  
```  
  
 Lo que supone los siguientes valores de categoría general tal como se define en la base de datos de caracteres Unicode  
  
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
  
 XAML define una segunda gramática, DottedXamlName, que se usa para la propiedad y las referencias de evento y también para los miembros asociados. Para obtener más información, consulte <xref:System.Windows.DependencyProperty> y [información general sobre XAML (WPF)](../wpf/advanced/xaml-overview-wpf.md).  
  
 Valores de cadena que son del tipo que DottedXamlName debe ajustarse a la gramática siguiente:  
  
```  
DottedXamlName ::= XamlName '.' XamlName  
```  
  
## <a name="remarks"></a>Comentarios  
 Para obtener la especificación completa, consulte [ \[MS-XAML\]](https://go.microsoft.com/fwlink/?LinkId=114525).
