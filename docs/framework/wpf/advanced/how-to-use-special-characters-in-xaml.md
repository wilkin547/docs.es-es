---
title: "C&#243;mo: Usar caracteres especiales en XAML | Microsoft Docs"
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
  - "caracteres, especiales"
  - "caracteres especiales"
  - "tipografía, caracteres especiales"
  - "Unicode UTF-8 (formato de archivo)"
  - "UTF-8 (formato de archivo)"
ms.assetid: a57776d1-f353-4794-afa0-bfa3c712ed1c
caps.latest.revision: 7
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 3
---
# C&#243;mo: Usar caracteres especiales en XAML
Los archivos de marcado que se crean en [!INCLUDE[TLA#tla_visualstu](../../../../includes/tlasharptla-visualstu-md.md)] se guardan automáticamente en el formato de archivo [!INCLUDE[TLA#tla_unicode](../../../../includes/tlasharptla-unicode-md.md)] UTF\-8, lo que significa que la mayoría de los caracteres especiales, como las tildes, se codifican correctamente.  Sin embargo, existe un conjunto de caracteres especiales utilizados con frecuencia que se administran de manera diferente.  Estos caracteres especiales siguen la norma de codificación [!INCLUDE[TLA#tla_w3c](../../../../includes/tlasharptla-w3c-md.md)] de [!INCLUDE[TLA#tla_xml](../../../../includes/tlasharptla-xml-md.md)].  
  
 En la tabla siguiente se muestra la sintaxis para codificar este conjunto de caracteres especiales:  
  
|Carácter|Sintaxis|Descripción|  
|--------------|--------------|-----------------|  
|\<|`<`|Símbolo de menor que.|  
|\>|`>`|Símbolo de mayor que.|  
|&|`&`|Símbolo de Y comercial.|  
|"|`"`|Símbolo de comillas dobles.|  
  
> [!NOTE]
>  Si crea un archivo de marcado mediante un editor de texto, como el Bloc de notas de [!INCLUDE[TLA#tla_mswin](../../../../includes/tlasharptla-mswin-md.md)], debe guardar el archivo en el formato de archivo [!INCLUDE[TLA#tla_unicode](../../../../includes/tlasharptla-unicode-md.md)] UTF\-8 para conservar los caracteres especiales codificados.  
  
 En el ejemplo siguiente se muestra cómo se pueden utilizar los caracteres especiales en el texto al crear el marcado.  
  
## Ejemplo  
 [!code-xml[SpecialCharsSnippets#SpecialCharsSnippet1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/SpecialCharsSnippets/CS/Window1.xaml#specialcharssnippet1)]