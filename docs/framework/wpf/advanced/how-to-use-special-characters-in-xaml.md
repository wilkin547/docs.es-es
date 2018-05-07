---
title: 'Cómo: Usar caracteres especiales en XAML'
ms.date: 03/30/2017
helpviewer_keywords:
- Unicode UTF-8 file format
- UTF-8 file format
- characters [WPF], special
- typography [WPF], special characters
- special characters [WPF]
ms.assetid: a57776d1-f353-4794-afa0-bfa3c712ed1c
ms.openlocfilehash: d60f9e94fd93c95e573bb52847c717821abdd9a0
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-use-special-characters-in-xaml"></a>Cómo: Usar caracteres especiales en XAML
Archivos de marcado que se crean en [!INCLUDE[TLA#tla_visualstu](../../../../includes/tlasharptla-visualstu-md.md)] se guardan automáticamente en el [!INCLUDE[TLA#tla_unicode](../../../../includes/tlasharptla-unicode-md.md)] formato de archivo UTF-8, lo que significa que la mayoría de caracteres especiales, como signos de acentuación se codifican correctamente. Sin embargo, hay un conjunto de caracteres especiales usados que se controlan de forma diferente. Estos caracteres especiales siguen la [!INCLUDE[TLA#tla_w3c](../../../../includes/tlasharptla-w3c-md.md)] [!INCLUDE[TLA#tla_xml](../../../../includes/tlasharptla-xml-md.md)] estándar para la codificación.  
  
 En la tabla siguiente se muestra la sintaxis para codificar este conjunto de caracteres especiales:  
  
|Carácter|Sintaxis|Descripción|  
|---------------|------------|-----------------|  
|<|`<`|Símbolo Menor que.|  
|>|`>`|Símbolo Mayor que.|  
|&|`&`|Símbolo Y comercial.|  
|"|`"`|Símbolo Comilla doble.|  
  
> [!NOTE]
>  Si crea un archivo de marcado mediante un texto de editor, como [!INCLUDE[TLA#tla_mswin](../../../../includes/tlasharptla-mswin-md.md)] el Bloc de notas, debe guardar el archivo en el [!INCLUDE[TLA#tla_unicode](../../../../includes/tlasharptla-unicode-md.md)] formato de archivo UTF-8 con el fin de conservar cualquier codifica caracteres especiales.  
  
 En el ejemplo siguiente, se muestra cómo usar caracteres especiales en texto cuando se crea la marcación.  
  
## <a name="example"></a>Ejemplo  
 [!code-xaml[SpecialCharsSnippets#SpecialCharsSnippet1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/SpecialCharsSnippets/CS/Window1.xaml#specialcharssnippet1)]
