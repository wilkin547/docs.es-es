---
title: Filtrar Usar caracteres especiales en XAML
ms.date: 03/30/2017
helpviewer_keywords:
- Unicode UTF-8 file format
- UTF-8 file format
- characters [WPF], special
- typography [WPF], special characters
- special characters [WPF]
ms.assetid: a57776d1-f353-4794-afa0-bfa3c712ed1c
ms.openlocfilehash: 18934e06f45ca4b88f48bce8a310a07b460a5f53
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/05/2019
ms.locfileid: "57377968"
---
# <a name="how-to-use-special-characters-in-xaml"></a>Filtrar Usar caracteres especiales en XAML
Archivos de marcado que se crean en [!INCLUDE[TLA#tla_visualstu](../../../../includes/tlasharptla-visualstu-md.md)] se guardan automáticamente en el [!INCLUDE[TLA#tla_unicode](../../../../includes/tlasharptla-unicode-md.md)] formato de archivo UTF-8, lo que significa que la mayoría de caracteres especiales, como tildes, se codifican correctamente. Sin embargo, hay un conjunto de caracteres especiales usados que se controlan de forma diferente. Estos caracteres especiales siguen el [!INCLUDE[TLA#tla_w3c](../../../../includes/tlasharptla-w3c-md.md)] [!INCLUDE[TL A#tla_xml](../../../../includes/tlasharptla-xml-md.md)] estándar para la codificación.  
  
 En la tabla siguiente se muestra la sintaxis para codificar este conjunto de caracteres especiales:  
  
|Carácter|Sintaxis|Descripción|  
|---------------|------------|-----------------|  
|<|`&lt;`|Símbolo Menor que.|  
|>|`&gt;`|Símbolo Mayor que.|  
|&|`&amp;`|Símbolo Y comercial.|  
|"|`&quot;`|Símbolo Comilla doble.|  
  
> [!NOTE]
>  Si crea un archivo de marcado con un texto editor, como [!INCLUDE[TLA#tla_mswin](../../../../includes/tlasharptla-mswin-md.md)] el Bloc de notas, debe guardar el archivo en el [!INCLUDE[TLA#tla_unicode](../../../../includes/tlasharptla-unicode-md.md)] formato de archivo UTF-8 para conservar cualquier carácter especial codificado.  
  
 En el ejemplo siguiente, se muestra cómo usar caracteres especiales en texto cuando se crea la marcación.  
  
## <a name="example"></a>Ejemplo  
 [!code-xaml[SpecialCharsSnippets#SpecialCharsSnippet1](~/samples/snippets/csharp/VS_Snippets_Wpf/SpecialCharsSnippets/CS/Window1.xaml#specialcharssnippet1)]
