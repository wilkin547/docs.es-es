---
title: "Gram&#225;tica de XamlName | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-wpf"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "DottedXamlName (gramática) [servicios XAML]"
  - "gramática [XAML Services], DottedXamlName"
  - "gramática [XAML Services], XamlName"
  - "nombres en XAML [servicios XAML]"
  - "XamlName (gramática) [servicios XAML]"
ms.assetid: 11e4cada-41d2-494d-9531-0d3df4dfcbe3
caps.latest.revision: 13
author: "wadepickett"
ms.author: "wpickett"
manager: "wpickett"
caps.handback.revision: 13
---
# Gram&#225;tica de XamlName
Gramática de XamlName es una gramática concreta definida en la especificación de lenguaje XAML \[MS\-XAML\], que se reproduce aquí por comodidad.  
  
## De la especificación XAML  
 La especificación \[MS\-XAML\] define la gramática de XamlName para identificar el conjunto de identificadores simbólicos válidos utilizados para los tipos y las propiedades.  
  
 Los valores de cadena que son del tipo XamlName deben respetar la gramática siguiente:  
  
```  
XamlName ::= NameStartChar ( NameChar )*   
NameStartChar ::= LetterCharacter | '_'   
NameChar ::= NameStartChar | DecimalDigit | CombiningCharacter   
LetterCharacter ::= UnicodeLu | UnicodeLl | UnicodeLo | UnicodeLt | UnicodeNl   
DecimalDigit ::= UnicodeNd   
CombiningCharacter ::= UnicodeMn | UnicodeMc  
  
```  
  
 Que supone los valores de categoría generales siguientes, tal y como estén definidos en la base de datos de caracteres Unicode  
  
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
  
 XAML define una segunda gramática, DottedXamlName, que se utiliza para las referencias completas a propiedades y eventos, así como para los miembros asociados.  Para obtener más información, vea <xref:System.Windows.DependencyProperty> y [Información general sobre XAML \(WPF\)](../../../ocs/framework/wpf/advanced/xaml-overview-wpf.md).  
  
 Los valores de cadena que son del tipo DottedXamlName deben respetar la gramática siguiente:  
  
```  
DottedXamlName ::= XamlName '.' XamlName  
```  
  
## Comentarios  
 Para obtener la especificación completa, vea [\[MS\-XAML\]](http://go.microsoft.com/fwlink/?LinkId=114525).