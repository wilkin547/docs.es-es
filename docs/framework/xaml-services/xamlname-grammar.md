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
# <a name="xamlname-grammar"></a>Gramática de XamlName
XamlName (gramática) es una gramática concreta que se define en la especificación del lenguaje XAML [MS-XAML], que se reproduce aquí por comodidad.  
  
## <a name="from-the-xaml-specification"></a>De la especificación de XAML  
 La especificación de [MS-XAML] define la gramática de XamlName para identificar el conjunto de identificadores simbólicos válidos utilizados para los tipos y propiedades.  
  
 Valores de cadena que son del tipo que XamlName deben respetar la gramática siguiente:  
  
```  
XamlName ::= NameStartChar ( NameChar )*   
NameStartChar ::= LetterCharacter | '_'   
NameChar ::= NameStartChar | DecimalDigit | CombiningCharacter   
LetterCharacter ::= UnicodeLu | UnicodeLl | UnicodeLo | UnicodeLt | UnicodeNl   
DecimalDigit ::= UnicodeNd   
CombiningCharacter ::= UnicodeMn | UnicodeMc  
```  
  
 Lo que supone los siguientes valores de categoría general como se define en la base de datos de caracteres Unicode  
  
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
  
 XAML define una segunda gramática, DottedXamlName, que se utiliza para la propiedad y el evento referencias parciales y también para los miembros asociados. Para obtener más información, consulte <xref:System.Windows.DependencyProperty> y [información general sobre XAML (WPF)](../../../docs/framework/wpf/advanced/xaml-overview-wpf.md).  
  
 Valores de cadena que son del tipo que DottedXamlName debe ajustarse a la gramática siguiente:  
  
```  
DottedXamlName ::= XamlName '.' XamlName  
```  
  
## <a name="remarks"></a>Comentarios  
 Para obtener la especificación completa, vea [ \[MS-XAML\]](http://go.microsoft.com/fwlink/?LinkId=114525).
