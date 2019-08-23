---
title: Procedimiento Usar caracteres especiales en XAML
ms.date: 03/30/2017
helpviewer_keywords:
- Unicode UTF-8 file format
- UTF-8 file format
- characters [WPF], special
- typography [WPF], special characters
- special characters [WPF]
ms.assetid: a57776d1-f353-4794-afa0-bfa3c712ed1c
ms.openlocfilehash: 61ee38319b2f0aa46690fb063f6ffe6612f993ad
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "69918441"
---
# <a name="how-to-use-special-characters-in-xaml"></a>Procedimiento Usar caracteres especiales en XAML
Los archivos de marcado que se [!INCLUDE[TLA#tla_visualstu](../../../../includes/tlasharptla-visualstu-md.md)] crean en se guardan [!INCLUDE[TLA#tla_unicode](../../../../includes/tlasharptla-unicode-md.md)] automáticamente en el formato de archivo UTF-8, lo que significa que la mayoría de los caracteres especiales, como las marcas de acento, se codifican correctamente. Sin embargo, hay un conjunto de caracteres especiales usados que se controlan de forma diferente. Estos caracteres especiales siguen el [!INCLUDE[TLA#tla_w3c](../../../../includes/tlasharptla-w3c-md.md)] [!INCLUDE[TL A#tla_xml](../../../../includes/tlasharptla-xml-md.md)] estándar de codificación.  
  
 En la tabla siguiente se muestra la sintaxis para codificar este conjunto de caracteres especiales:  
  
|Carácter|Sintaxis|DESCRIPCIÓN|  
|---------------|------------|-----------------|  
|<|`&lt;`|Símbolo Menor que.|  
|>|`&gt;`|Símbolo Mayor que.|  
|&|`&amp;`|Símbolo Y comercial.|  
|"|`&quot;`|Símbolo Comilla doble.|  
  
> [!NOTE]
> Si crea un archivo de marcado mediante un editor de texto, como el Bloc de notas de Windows, debe guardar el [!INCLUDE[TLA#tla_unicode](../../../../includes/tlasharptla-unicode-md.md)] archivo en el formato de archivo UTF-8 para conservar los caracteres especiales codificados.  
  
 En el ejemplo siguiente, se muestra cómo usar caracteres especiales en texto cuando se crea la marcación.  
  
## <a name="example"></a>Ejemplo  
 [!code-xaml[SpecialCharsSnippets#SpecialCharsSnippet1](~/samples/snippets/csharp/VS_Snippets_Wpf/SpecialCharsSnippets/CS/Window1.xaml#specialcharssnippet1)]
