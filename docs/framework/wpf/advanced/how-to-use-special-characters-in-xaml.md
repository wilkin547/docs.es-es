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
ms.openlocfilehash: 27f2b18593d075b54eb8c3351bbb84415700cfd4
ms.sourcegitcommit: 2e95559d957a1a942e490c5fd916df04b39d73a9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/16/2019
ms.locfileid: "72395804"
---
# <a name="how-to-use-special-characters-in-xaml"></a>Cómo: Usar caracteres especiales en XAML
Los archivos de marcado creados en [!INCLUDE[TLA#tla_visualstu](../../../../includes/tlasharptla-visualstu-md.md)] se guardan automáticamente en el formato de archivo UTF-8 de Unicode, lo que significa que la mayoría de los caracteres especiales, como las marcas de acento, se codifican correctamente. Sin embargo, hay un conjunto de caracteres especiales usados que se controlan de forma diferente. Estos caracteres especiales siguen el estándar [!INCLUDE[TLA#tla_w3c](../../../../includes/tlasharptla-w3c-md.md)] [!INCLUDE[TL A#tla_xml](../../../../includes/tlasharptla-xml-md.md)] para la codificación.  
  
 En la tabla siguiente se muestra la sintaxis para codificar este conjunto de caracteres especiales:  
  
|Carácter|Sintaxis|Descripción|  
|---------------|------------|-----------------|  
|<|`&lt;`|Símbolo Menor que.|  
|>|`&gt;`|Símbolo Mayor que.|  
|&|`&amp;`|Símbolo Y comercial.|  
|"|`&quot;`|Símbolo Comilla doble.|  
  
> [!NOTE]
> Si crea un archivo de marcado mediante un editor de texto, como el Bloc de notas de Windows, debe guardar el archivo en el formato de archivo UTF-8 de Unicode para conservar los caracteres especiales codificados.  
  
 En el ejemplo siguiente, se muestra cómo usar caracteres especiales en texto cuando se crea la marcación.  
  
## <a name="example"></a>Ejemplo  
 [!code-xaml[SpecialCharsSnippets#SpecialCharsSnippet1](~/samples/snippets/csharp/VS_Snippets_Wpf/SpecialCharsSnippets/CS/Window1.xaml#specialcharssnippet1)]
