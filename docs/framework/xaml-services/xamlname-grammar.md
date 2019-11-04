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
 
 XAML define una segunda gramática, DottedXamlName, que se usa para las referencias calificadas de propiedades y eventos, y también para los miembros adjuntos. Para obtener más información, vea [información general sobre <xref:System.Windows.DependencyProperty> y XAML (WPF)](../../desktop-wpf/fundamentals/xaml.md).  
  
 Los valores de cadena que son de tipo DottedXamlName deben ajustarse a la gramática siguiente:  
  
```xaml  
DottedXamlName ::= XamlName '.' XamlName  
```  
  
## <a name="remarks"></a>Comentarios  
 Para obtener la especificación completa, vea [\[MS-XAML\]](https://go.microsoft.com/fwlink/?LinkId=114525).
